# Configuration & Externalized Settings Inventory

This inventory captures configuration files and runtime settings used by the SocialGoal solution, including web configuration, package/build settings, and environment-specific transforms.

## Configuration Sources

| Source | Type | Path/Location | Notes |
|---|---|---|---|
| `Web.config` | Primary runtime config | `source/SocialGoal/Web.config` | Connection string, auth mode, app settings, EF provider, ELMAH config |
| `Web.Debug.config` | Environment transform | `source/SocialGoal/Web.Debug.config` | Debug-specific XML transform template |
| `Web.Release.config` | Environment transform | `source/SocialGoal/Web.Release.config` | Removes debug compilation attribute in release |
| `App.config` | Library runtime config | `source/SocialGoal.Data/App.config` | EF provider registration for data project |
| `App.config` | Test runtime config | `source/SocialGoal.Tests/App.config` | EF provider + MVC binding redirect for tests |
| `packages.config` files | Dependency config | `source/*/packages.config` | Package versions per project (no central package management) |
| `*.csproj` / `SocialGoal.sln` | Build configuration | `source/*.csproj`, `source/SocialGoal.sln` | Target framework and debug/release outputs |

## Build Profiles

| Profile | Activation | Purpose | Key Dependencies/Plugins |
|---|---|---|---|
| Debug | Build configuration (`/p:Configuration=Debug`) | Development build with symbols and no optimization | `DefineConstants=DEBUG;TRACE` |
| Release | Build configuration (`/p:Configuration=Release`) | Optimized production build artifacts | `Optimize=true`, `DefineConstants=TRACE` |
| Web Release Transform | Publish/build transform | Removes `debug` compilation attribute from web config | `Web.Release.config` transform |

## Runtime Profiles

| Profile | Activation Method | Config Files | Key Overrides |
|---|---|---|---|
| Default runtime | IIS/IIS Express app start | `Web.config` | Forms auth login path, SQL connection string, appSettings flags |
| Debug web runtime | Debug deployment transform | `Web.Debug.config` + `Web.config` | Placeholder transform structure; no concrete override entries |
| Release web runtime | Release deployment transform | `Web.Release.config` + `Web.config` | Removes `system.web/compilation@debug` attribute |

## Properties Inventory

### SocialGoal.Web

| Property Key | Default | Profiles | Source |
|---|---|---|---|
| `SocialGoalEntities` | `Data Source=.\;Initial Catalog=SocialGoal;Integrated Security=True` | Default | `Web.config` connectionStrings |
| `webpages:Version` | `3.0.0.0` | Default | `Web.config` appSettings |
| `ClientValidationEnabled` | `true` | Default | `Web.config` appSettings |
| `UnobtrusiveJavaScriptEnabled` | `true` | Default | `Web.config` appSettings |
| `elmah.mvc.route` | `elmah` | Default | `Web.config` appSettings |
| `MvcMailer.BaseURL` | empty | Default | `Web.config` appSettings |
| `forms loginUrl` | `~/Account/Login` | Default | `Web.config` system.web/authentication |
| `forms timeout` | `1` | Default | `Web.config` system.web/authentication |

### SocialGoal.Data / Tests

| Property Key | Default | Profiles | Source |
|---|---|---|---|
| `entityFramework.defaultConnectionFactory` | `SqlConnectionFactory` | Default | `SocialGoal.Data/App.config`, `SocialGoal.Tests/App.config` |
| `entityFramework.provider[System.Data.SqlClient]` | EF SQL provider type | Default | `SocialGoal.Data/App.config`, `SocialGoal.Tests/App.config` |

## Startup Parameters & Resource Requirements

| Service | JVM/Runtime Options | Memory | Instance Count |
|---|---|---|---|
| SocialGoal.Web (ASP.NET MVC) | No explicit startup CLI/system property settings in repo | Not specified in repo | Not specified |
| SocialGoal.Tests | Standard test host runtime | Not specified in repo | On-demand per test run |
| Class library projects | Loaded by host process | N/A | N/A |

## Startup Dependency Chain

1. `SocialGoal.Web` starts in IIS and loads `Web.config` settings.
2. `Application_Start` initializes sample data initializer (`GoalsSampleData`) and MVC pipeline registrations.
3. `Bootstrapper.Run()` builds Autofac container and registers repositories/services/auth abstractions.
4. OWIN startup config (`Startup.Configuration`) wires cookie/external authentication middleware before handling authenticated requests.
5. Data access becomes available once `SocialGoalEntities` can connect through `SocialGoalEntities` connection string.

## Secrets & Sensitive Configuration

| Secret Reference | Type | Storage (masked) |
|---|---|---|
| `SocialGoalEntities` connection details | Database connection | `Web.config` (integrated security, no password present) |
| Optional SMTP credentials | Email secret placeholder | `Web.config` comments (`[MASKED]/not configured`) |
| External auth provider secrets | OAuth client secret placeholders | `Startup.Auth.cs` commented placeholders (`[MASKED]/not configured`) |

### Secrets Provisioning Workflow

The repository mostly uses local/static configuration files. Database access currently relies on integrated Windows authentication in the connection string, so no explicit password secret flow is defined in code. Optional SMTP and OAuth credentials are represented as commented placeholders, implying manual out-of-band provisioning at deployment time rather than an integrated key vault or secret manager pipeline.

## Feature Flags

| Flag Name | Default | Controlled By |
|---|---|---|
| `webpages:Enabled` | `false` | `Web.config` appSettings |
| `ClientValidationEnabled` | `true` | `Web.config` appSettings |
| `UnobtrusiveJavaScriptEnabled` | `true` | `Web.config` appSettings |
| `elmah.mvc.disableHandler` | `false` | `Web.config` appSettings |

## Framework & Runtime Versions

| Component | Version | Source |
|---|---|---|
| .NET Framework target | v4.5 | `*.csproj` (`TargetFrameworkVersion`) |
| ASP.NET MVC | 5.0.0 | `SocialGoal/packages.config` |
| ASP.NET Identity | 1.0.0 | `SocialGoal/packages.config`, `SocialGoal.Service.csproj` refs |
| OWIN packages | 2.0.0 | `SocialGoal/packages.config` |
| Entity Framework | 6.0.x | `packages.config` + `SocialGoal.Data.csproj` |
| Autofac | 3.1.5 | `SocialGoal/packages.config` |
| AutoMapper | 3.1.1 | `SocialGoal/packages.config` |
| NUnit (tests) | 2.6.3 | `SocialGoal.Tests/packages.config` |
