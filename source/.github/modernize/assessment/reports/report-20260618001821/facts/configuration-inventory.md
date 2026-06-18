# Configuration & Externalized Settings Inventory

SocialGoal uses a small set of mostly file-based configuration sources centered on `Web.config`, plus code-based startup wiring in the MVC application. There are no environment-specific configuration files, remote config stores, or managed secret providers in the repository.

## Configuration Sources

| Source | Type | Path/Location | Notes |
|---|---|---|---|
| Web.config | ASP.NET runtime config | `source/SocialGoal/Web.config` | Primary source for connection strings, app settings, forms auth, ELMAH, mail, and EF provider settings |
| App.config | Library runtime config | `source/SocialGoal.Data/App.config` | Declares EF provider section for the data project |
| App.config | Test runtime config | `source/SocialGoal.Tests/App.config` | Declares EF provider and MVC binding redirect for tests |
| Bootstrapper.cs | Code-based startup config | `source/SocialGoal/App_Start/Bootstrapper.cs` | Registers Autofac dependencies and initializes AutoMapper |
| Startup.Auth.cs | Code-based auth config | `source/SocialGoal/App_Start/Startup.Auth.cs` | Enables OWIN cookie auth and Google login |
| Global.asax.cs | Application startup | `source/SocialGoal/Global.asax.cs` | Sets EF database initializer and starts MVC infrastructure |
| packages.config files | Build-time dependency config | `source/*/packages.config` | Package inventory for web and test projects |

## Build Profiles

| Profile | Activation | Purpose | Key Dependencies/Plugins |
|---|---|---|---|
| Debug | Default local build in project files | Enables symbols, no optimization, `DEBUG;TRACE` constants | Standard MSBuild CSharp targets |
| Release | Manual selection in project files | Optimized output with `TRACE` constant | Standard MSBuild CSharp targets |

## Runtime Profiles

| Profile | Activation Method | Config Files | Key Overrides |
|---|---|---|---|
| Default | ASP.NET application startup | `Web.config` | Uses local SQL Server connection, forms auth, ELMAH, and MvcMailer base URL |
| Data library runtime | Loaded by consuming application | `SocialGoal.Data/App.config` | EF provider registration only |
| Test runtime | Loaded by test runner | `SocialGoal.Tests/App.config` | EF provider plus MVC binding redirect |

## Properties Inventory

### SocialGoal.Web

| Property Key | Default | Profiles | Source |
|---|---|---|---|
| `SocialGoalEntities` | `Data Source=.\;Initial Catalog=SocialGoal;Integrated Security=True` | Default | `Web.config` connection string |
| `webpages:Version` | `3.0.0.0` | Default | `Web.config` appSettings |
| `webpages:Enabled` | `false` | Default | `Web.config` appSettings |
| `ClientValidationEnabled` | `true` | Default | `Web.config` appSettings |
| `UnobtrusiveJavaScriptEnabled` | `true` | Default | `Web.config` appSettings |
| `elmah.mvc.disableHandler` | `false` | Default | `Web.config` appSettings |
| `elmah.mvc.disableHandleErrorFilter` | `false` | Default | `Web.config` appSettings |
| `elmah.mvc.requiresAuthentication` | `false` | Default | `Web.config` appSettings |
| `elmah.mvc.allowedRoles` | `*` | Default | `Web.config` appSettings |
| `elmah.mvc.allowedUsers` | `*` | Default | `Web.config` appSettings |
| `elmah.mvc.route` | `elmah` | Default | `Web.config` appSettings |
| `MvcMailer.BaseURL` | empty string | Default | `Web.config` appSettings |
| `forms.loginUrl` | `~/Account/Login` | Default | `Web.config` system.web |
| `forms.timeout` | `1` | Default | `Web.config` system.web |
| `forms.slidingExpiration` | `true` | Default | `Web.config` system.web |

### SocialGoal.Data and SocialGoal.Tests

| Property Key | Default | Profiles | Source |
|---|---|---|---|
| `entityFramework.defaultConnectionFactory` | `SqlConnectionFactory` | Shared library and test runtime | `App.config` files |
| `entityFramework.provider:System.Data.SqlClient` | EF SQL Server provider | Shared library and test runtime | `App.config` files |
| `System.Web.Mvc bindingRedirect` | `5.0.0.0` | Test runtime | `SocialGoal.Tests/App.config` |

## Startup Parameters & Resource Requirements

| Service | JVM/Runtime Options | Memory | Instance Count |
|---|---|---|---|
| SocialGoal.Web | None declared in repository | Not specified | Not specified |
| SocialGoal.Data | None declared in repository | Not specified | In-process with web app |
| SocialGoal.Tests | None declared in repository | Not specified | Test-runner controlled |

## Startup Dependency Chain

1. `Global.asax.cs` starts the MVC application and sets `GoalsSampleData` as the Entity Framework database initializer.
2. `RouteConfig`, `FilterConfig`, and `BundleConfig` are registered during `Application_Start`.
3. `Bootstrapper.Run()` configures Autofac registrations and AutoMapper profiles before request handling begins.
4. `Startup.Auth.ConfigureAuth()` wires OWIN cookie authentication and optional Google login.
5. The application depends on the SQL Server database being reachable when repositories first resolve `SocialGoalEntities`.

## Secrets & Sensitive Configuration

| Secret Reference | Type | Storage (masked) |
|---|---|---|
| `SocialGoalEntities` connection string | Database connection | Uses integrated security; no password committed |
| SMTP credentials example | Email credentials | Commented sample values in `Web.config`, effectively `[MASKED]` |
| External login client identifiers | OAuth credentials | Placeholder comments only; no committed values |
| Security tokens persisted in database | Application secret material | Stored in database tables, not externalized in config |

### Secrets Provisioning Workflow

The repository does not use an external secret manager. The current workflow is manual: the web application reads its database connection from `Web.config`, optional SMTP credentials can be inserted into the commented mail settings block, and OAuth provider secrets would need to be added directly in startup configuration before deployment. Because no Key Vault, Vault, or environment-variable based secret injection is configured, secret provisioning appears to rely on host-level configuration and careful file management outside source control.

## Feature Flags

| Flag Name | Default | Controlled By |
|---|---|---|
| None detected | Not applicable | No feature flag framework or conditional configuration pattern found |

## Framework & Runtime Versions

| Component | Version | Source |
|---|---:|---|
| .NET Framework target | 4.5 | `*.csproj`, `Web.config` |
| MSBuild ToolsVersion | 12.0 | project files |
| ASP.NET MVC | 5.0.0 | `packages.config` |
| ASP.NET Identity Core and EF | 1.0.0 | `packages.config` |
| Microsoft.Owin | 2.0.0 | `packages.config` |
| Entity Framework | 6.0.2-beta1 | web `packages.config` |
| Autofac | 3.1.5 | `packages.config` |
| AutoMapper | 3.1.1-ci1000 | `packages.config` |
| ELMAH MVC | 2.1.1 | `packages.config` |
| MvcMailer | 4.5 | `packages.config` |
| jQuery | 1.10.2 | `packages.config` |
| Bootstrap | 3.0.0 | `packages.config` |
