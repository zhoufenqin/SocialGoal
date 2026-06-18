# SocialGoal.Core

## Summary

| Metric | Value |
|--------|-------|
| Total Issues | 30 |
| Mandatory Blockers | 11 |
| Potential Issues | 11 |

## Component Information

| Property | Value |
|----------|-------|
| Language | C# |
| Frameworks | .NETFramework,Version=v4.5 |
| Build tools | MSBuild |

## Cloud Readiness Issues

| Issue Name | Criticality | Story Points | Occurrences |
|------------|-------------|--------------|-------------|
| Windows authentication detected | Mandatory | 3 | [1](#Windows_authentication_detected) |
| Old .NET Framework dependency detected | Potential | 3 | [7](#Old_NET_Framework_dependency_detected) |
| Hardcoded URLs detected | Potential | 1 | [5](#Hardcoded_URLs_detected) |
| Local or network IO operations detected | Potential | 3 | [2](#Local_or_network_IO_operations_detected) |
| SMTP connections detected | Potential | 3 | [1](#SMTP_connections_detected) |
| SQL database connection detected | Potential | 3 | [1](#SQL_database_connection_detected) |
| Access to external resources via HTTP is detected | Potential | 3 | [1](#Access_to_external_resources_via_HTTP_is_detected) |
| Hardcoded sensitive data detected | Optional | 3 | [30](#Hardcoded_sensitive_data_detected) |
| MachineKey dependency is detected | Optional | 3 | [3](#MachineKey_dependency_is_detected) |
| Connection strings without configuration builders detected | Optional | 3 | [2](#Connection_strings_without_configuration_builders_detected) |
| Static content detected | Optional | 3 | [1](#Static_content_detected) |
| System.Data.SqlClient dependency detected | Optional | 3 | [1](#System_Data_SqlClient_dependency_detected) |
| Synchronous API usage detected | Optional | 1 | [1](#Synchronous_API_usage_detected) |

### Issue Details

<details id="Windows_authentication_detected">
<summary><b>Windows authentication detected</b> — affected files</summary>

- `SocialGoal\Web.config`

</details>

<details id="Old_NET_Framework_dependency_detected">
<summary><b>Old .NET Framework dependency detected</b> — affected files</summary>

- `SocialGoal.Core\SocialGoal.Core.csproj`
- `SocialGoal.Data\SocialGoal.Data.csproj`
- `SocialGoal.Model\SocialGoal.Model.csproj`
- `SocialGoal.Service\SocialGoal.Service.csproj`
- `SocialGoal.Tests\SocialGoal.Tests.csproj`
- `SocialGoal.Web.Core\SocialGoal.Web.Core.csproj`
- `SocialGoal\SocialGoal.Web.csproj`

</details>

<details id="Hardcoded_URLs_detected">
<summary><b>Hardcoded URLs detected</b> — affected files</summary>

- `SocialGoal.Tests\Controllers\AccountControllerTest.cs (line 685)`
- `SocialGoal.Tests\Controllers\AccountControllerTest.cs (line 740)`
- `SocialGoal.Tests\Controllers\AccountControllerTest.cs (line 782)`
- `SocialGoal.Tests\Controllers\EmailRequestControllerTest.cs (line 150)`
- `SocialGoal.Tests\Controllers\EmailRequestControllerTest.cs (line 237)`

</details>

<details id="Local_or_network_IO_operations_detected">
<summary><b>Local or network IO operations detected</b> — affected files</summary>

- `SocialGoal\Controllers\AccountController.cs (line 427)`
- `SocialGoal\Controllers\AccountController.cs (line 429)`

</details>

<details id="SMTP_connections_detected">
<summary><b>SMTP connections detected</b> — affected files</summary>

- `SocialGoal.Tests\Controllers\GoalControllerTest.cs (line 1157)`

</details>

<details id="SQL_database_connection_detected">
<summary><b>SQL database connection detected</b> — affected files</summary>

- `SocialGoal\Web.config`

</details>

<details id="Access_to_external_resources_via_HTTP_is_detected">
<summary><b>Access to external resources via HTTP is detected</b> — affected files</summary>

- `SocialGoal\Controllers\AccountController.cs (line 455)`

</details>

<details id="Hardcoded_sensitive_data_detected">
<summary><b>Hardcoded sensitive data detected</b> — affected files</summary>

- `SocialGoal\Web.config`
- `SocialGoal\Controllers\AccountController.cs (line 203)`
- `SocialGoal\Controllers\AccountController.cs (line 81)`
- `SocialGoal\Controllers\AccountController.cs (line 166)`
- `SocialGoal\Controllers\AccountController.cs (line 167)`
- `SocialGoal\Mailers\UserMailer.cs (line 48)`
- `SocialGoal\Mailers\UserMailer.cs (line 45)`
- `SocialGoal\Models\AccountViewModels.cs (line 25)`
- `SocialGoal\Models\AccountViewModels.cs (line 58)`
- `SocialGoal\Models\AccountViewModels.cs (line 15)`
- `SocialGoal\Models\AccountViewModels.cs (line 21)`
- `SocialGoal\Models\AccountViewModels.cs (line 26)`
- `SocialGoal\Models\AccountViewModels.cs (line 38)`
- `SocialGoal\Models\AccountViewModels.cs (line 54)`
- `SocialGoal\Models\AccountViewModels.cs (line 59)`
- `SocialGoal\Models\AccountViewModels.cs (line 26)`
- `SocialGoal\Models\AccountViewModels.cs (line 59)`
- `SocialGoal\Properties\Resources.Designer.cs (line 76)`
- `SocialGoal\Properties\Resources.Designer.cs (line 166)`
- `SocialGoal\Properties\Resources.Designer.cs (line 220)`
- `SocialGoal\ViewModels\ChangePasswordFormModel.cs (line 23)`
- `SocialGoal\ViewModels\ChangePasswordFormModel.cs (line 13)`
- `SocialGoal\ViewModels\ChangePasswordFormModel.cs (line 19)`
- `SocialGoal\ViewModels\ChangePasswordFormModel.cs (line 24)`
- `SocialGoal\ViewModels\ChangePasswordFormModel.cs (line 24)`
- `SocialGoal\ViewModels\UserFormModel.cs (line 39)`
- `SocialGoal\ViewModels\UserFormModel.cs (line 40)`
- `SocialGoal\ViewModels\UserFormModel.cs (line 35)`
- `SocialGoal\ViewModels\UserFormModel.cs (line 40)`
- `SocialGoal\ViewModels\UserFormModel.cs (line 56)`

</details>

<details id="MachineKey_dependency_is_detected">
<summary><b>MachineKey dependency is detected</b> — affected files</summary>

- `SocialGoal.Web.Core\Authentication\DefaultFormsAuthentication.cs (line 40)`
- `SocialGoal.Web.Core\Authentication\DefaultFormsAuthentication.cs (line 22)`
- `SocialGoal.Web.Core\Authentication\DefaultFormsAuthentication.cs (line 27)`

</details>

<details id="Connection_strings_without_configuration_builders_detected">
<summary><b>Connection strings without configuration builders detected</b> — affected files</summary>

- `SocialGoal\Web.config`
- `SocialGoal\Web.config`

</details>

<details id="Static_content_detected">
<summary><b>Static content detected</b> — affected files</summary>

- `SocialGoal\SocialGoal.Web.csproj`

</details>

<details id="System_Data_SqlClient_dependency_detected">
<summary><b>System.Data.SqlClient dependency detected</b> — affected files</summary>

- `SocialGoal\Web.config`

</details>

<details id="Synchronous_API_usage_detected">
<summary><b>Synchronous API usage detected</b> — affected files</summary>

- `SocialGoal\Controllers\AccountController.cs (line 464)`

</details>

## DotNET Upgrade Issues [View Details](scenarios/dotnet-version-upgrade/assessment.md)

| Issue Category | Criticality | Story Points | Occurrences |
|----------------|-------------|--------------|-------------|
| Binary incompatible for selected .NET version | Mandatory | 1 | [371](#Binary_incompatible_for_selected_NET_version) |
| NuGet package is incompatible | Mandatory | 1 | [33](#NuGet_package_is_incompatible) |
| System.Web.Optimization bundling and minification is not supported in .NET Core and should be replaced with actual html tags pointing to content files | Mandatory | 1 | [8](#System_Web_Optimization_bundling_and_minification_is_not_supported_in_NET_Core_and_should_be_replaced_with_actual_html_tags_pointing_to_content_files) |
| Project file needs to be converted to SDK-style | Mandatory | 1 | [7](#Project_file_needs_to_be_converted_to_SDK-style) |
| Project's target framework(s) needs to be changed | Mandatory | 1 | [7](#Project_s_target_framework_s_needs_to_be_changed) |
| NuGet package functionality is included with framework reference | Mandatory | 1 | [4](#NuGet_package_functionality_is_included_with_framework_reference) |
| Routes registration via RouteCollection is not supported in .NET Core and needs to be converted to the route mappings on the application object | Mandatory | 1 | [2](#Routes_registration_via_RouteCollection_is_not_supported_in_NET_Core_and_needs_to_be_converted_to_the_route_mappings_on_the_application_object) |
| Convert application initialization code from Global.asax.cs to .NET Core and clean up Global.asax.cs | Mandatory | 1 | [1](#Convert_application_initialization_code_from_Global_asax_cs_to_NET_Core_and_clean_up_Global_asax_cs) |
| ASP.NET Framework (System.Web) | Mandatory | 4 | 0 |
| GDI+ / System.Drawing | Mandatory | 1 | 0 |
| Source incompatible for selected .NET version | Potential | 1 | [268](#Source_incompatible_for_selected_NET_version) |
| AutoGenerateBindingRedirects not set and no manual redirects | Potential | 1 | [5](#AutoGenerateBindingRedirects_not_set_and_no_manual_redirects) |
| NuGet package upgrade is recommended | Potential | 1 | [5](#NuGet_package_upgrade_is_recommended) |
| Behavioral change in selected .NET version | Potential | 1 | [3](#Behavioral_change_in_selected_NET_version) |
| Library-hosted entry point missing GenerateBindingRedirectsOutputType | Potential | 1 | [1](#Library-hosted_entry_point_missing_GenerateBindingRedirectsOutputType) |
| NuGet package is deprecated | Optional | 1 | [14](#NuGet_package_is_deprecated) |
| NuGet package contains security vulnerability | Optional | 1 | [8](#NuGet_package_contains_security_vulnerability) |

### Issue Details

<details id="Binary_incompatible_for_selected_NET_version">
<summary><b>Binary incompatible for selected .NET version</b> — affected files</summary>

- `SocialGoal.Tests\Controllers\NotificationControllerTest.cs (line 302, col 12)`
- `SocialGoal.Tests\Controllers\NotificationControllerTest.cs (line 300, col 12)`
- `SocialGoal.Tests\Controllers\NotificationControllerTest.cs (line 270, col 12)`
- `SocialGoal.Tests\Controllers\NotificationControllerTest.cs (line 216, col 12)`
- `SocialGoal.Tests\Controllers\NotificationControllerTest.cs (line 214, col 12)`
- `SocialGoal.Tests\Controllers\NotificationControllerTest.cs (line 182, col 12)`
- `SocialGoal.Tests\Controllers\NotificationControllerTest.cs (line 129, col 12)`
- `SocialGoal.Tests\Controllers\NotificationControllerTest.cs (line 127, col 12)`
- `SocialGoal.Tests\Controllers\NotificationControllerTest.cs (line 97, col 12)`
- `SocialGoal.Tests\Controllers\GroupControllerTest.cs (line 2025, col 12)`
- `SocialGoal.Tests\Controllers\GroupControllerTest.cs (line 2023, col 12)`
- `SocialGoal.Tests\Controllers\GroupControllerTest.cs (line 1996, col 12)`
- `SocialGoal.Tests\Controllers\GroupControllerTest.cs (line 1928, col 12)`
- `SocialGoal.Tests\Controllers\GroupControllerTest.cs (line 1926, col 12)`
- `SocialGoal.Tests\Controllers\GroupControllerTest.cs (line 1898, col 12)`
- `SocialGoal.Tests\Controllers\GroupControllerTest.cs (line 1762, col 12)`
- `SocialGoal.Tests\Controllers\GroupControllerTest.cs (line 1760, col 12)`
- `SocialGoal.Tests\Controllers\GroupControllerTest.cs (line 1727, col 12)`
- `SocialGoal.Tests\Controllers\GroupControllerTest.cs (line 1704, col 12)`
- `SocialGoal.Tests\Controllers\GroupControllerTest.cs (line 1702, col 12)`
- `SocialGoal.Tests\Controllers\GroupControllerTest.cs (line 1669, col 12)`
- `SocialGoal.Tests\Controllers\GroupControllerTest.cs (line 1594, col 12)`
- `SocialGoal.Tests\Controllers\GroupControllerTest.cs (line 1592, col 12)`
- `SocialGoal.Tests\Controllers\GroupControllerTest.cs (line 1569, col 12)`
- `SocialGoal.Tests\Controllers\GroupControllerTest.cs (line 1497, col 12)`
- `SocialGoal.Tests\Controllers\GroupControllerTest.cs (line 1495, col 12)`
- `SocialGoal.Tests\Controllers\GroupControllerTest.cs (line 1466, col 12)`
- `SocialGoal.Tests\Controllers\GroupControllerTest.cs (line 1370, col 12)`
- `SocialGoal.Tests\Controllers\GroupControllerTest.cs (line 1368, col 12)`
- `SocialGoal.Tests\Controllers\GroupControllerTest.cs (line 1340, col 12)`
- `SocialGoal.Tests\Controllers\GroupControllerTest.cs (line 1271, col 12)`
- `SocialGoal.Tests\Controllers\GroupControllerTest.cs (line 1269, col 12)`
- `SocialGoal.Tests\Controllers\GroupControllerTest.cs (line 1241, col 12)`
- `SocialGoal.Tests\Controllers\GroupControllerTest.cs (line 779, col 12)`
- `SocialGoal.Tests\Controllers\GroupControllerTest.cs (line 777, col 12)`
- `SocialGoal.Tests\Controllers\GroupControllerTest.cs (line 752, col 12)`
- `SocialGoal.Tests\Controllers\GroupControllerTest.cs (line 682, col 12)`
- `SocialGoal.Tests\Controllers\GroupControllerTest.cs (line 681, col 12)`
- `SocialGoal.Tests\Controllers\GroupControllerTest.cs (line 650, col 12)`
- `SocialGoal.Tests\Controllers\GroupControllerTest.cs (line 579, col 12)`
- `SocialGoal.Tests\Controllers\GroupControllerTest.cs (line 578, col 12)`
- `SocialGoal.Tests\Controllers\GroupControllerTest.cs (line 559, col 12)`
- `SocialGoal.Tests\Controllers\GroupControllerTest.cs (line 481, col 12)`
- `SocialGoal.Tests\Controllers\GroupControllerTest.cs (line 480, col 12)`
- `SocialGoal.Tests\Controllers\GroupControllerTest.cs (line 458, col 12)`
- `SocialGoal.Tests\Controllers\GroupControllerTest.cs (line 422, col 12)`
- `SocialGoal.Tests\Controllers\GroupControllerTest.cs (line 420, col 12)`
- `SocialGoal.Tests\Controllers\GroupControllerTest.cs (line 390, col 12)`
- `SocialGoal.Tests\Controllers\GroupControllerTest.cs (line 347, col 12)`
- `SocialGoal.Tests\Controllers\GroupControllerTest.cs (line 345, col 12)`
- `SocialGoal.Tests\Controllers\GroupControllerTest.cs (line 315, col 12)`
- `SocialGoal.Tests\Controllers\GroupControllerTest.cs (line 190, col 12)`
- `SocialGoal.Tests\Controllers\GroupControllerTest.cs (line 188, col 12)`
- `SocialGoal.Tests\Controllers\GroupControllerTest.cs (line 158, col 12)`
- `SocialGoal.Tests\Controllers\GoalControllerTest.cs (line 1293, col 12)`
- `SocialGoal.Tests\Controllers\GoalControllerTest.cs (line 1291, col 12)`
- `SocialGoal.Tests\Controllers\GoalControllerTest.cs (line 1262, col 12)`
- `SocialGoal.Tests\Controllers\GoalControllerTest.cs (line 1142, col 12)`
- `SocialGoal.Tests\Controllers\GoalControllerTest.cs (line 1140, col 12)`
- `SocialGoal.Tests\Controllers\GoalControllerTest.cs (line 1112, col 12)`
- `SocialGoal.Tests\Controllers\GoalControllerTest.cs (line 1072, col 12)`
- `SocialGoal.Tests\Controllers\GoalControllerTest.cs (line 1070, col 12)`
- `SocialGoal.Tests\Controllers\GoalControllerTest.cs (line 1040, col 12)`
- `SocialGoal.Tests\Controllers\GoalControllerTest.cs (line 1007, col 12)`
- `SocialGoal.Tests\Controllers\GoalControllerTest.cs (line 1005, col 12)`
- `SocialGoal.Tests\Controllers\GoalControllerTest.cs (line 976, col 12)`
- `SocialGoal.Tests\Controllers\GoalControllerTest.cs (line 929, col 12)`
- `SocialGoal.Tests\Controllers\GoalControllerTest.cs (line 927, col 12)`
- `SocialGoal.Tests\Controllers\GoalControllerTest.cs (line 897, col 12)`
- `SocialGoal.Tests\Controllers\GoalControllerTest.cs (line 834, col 12)`
- `SocialGoal.Tests\Controllers\GoalControllerTest.cs (line 832, col 12)`
- `SocialGoal.Tests\Controllers\GoalControllerTest.cs (line 803, col 12)`
- `SocialGoal.Tests\Controllers\GoalControllerTest.cs (line 736, col 12)`
- `SocialGoal.Tests\Controllers\GoalControllerTest.cs (line 734, col 12)`
- `SocialGoal.Tests\Controllers\GoalControllerTest.cs (line 705, col 12)`
- `SocialGoal.Tests\Controllers\GoalControllerTest.cs (line 635, col 12)`
- `SocialGoal.Tests\Controllers\GoalControllerTest.cs (line 633, col 12)`
- `SocialGoal.Tests\Controllers\GoalControllerTest.cs (line 604, col 12)`
- `SocialGoal.Tests\Controllers\GoalControllerTest.cs (line 579, col 12)`
- `SocialGoal.Tests\Controllers\GoalControllerTest.cs (line 577, col 12)`
- `SocialGoal.Tests\Controllers\GoalControllerTest.cs (line 547, col 12)`
- `SocialGoal.Tests\Controllers\GoalControllerTest.cs (line 513, col 12)`
- `SocialGoal.Tests\Controllers\GoalControllerTest.cs (line 511, col 12)`
- `SocialGoal.Tests\Controllers\GoalControllerTest.cs (line 482, col 12)`
- `SocialGoal.Tests\Controllers\GoalControllerTest.cs (line 253, col 12)`
- `SocialGoal.Tests\Controllers\GoalControllerTest.cs (line 251, col 12)`
- `SocialGoal.Tests\Controllers\GoalControllerTest.cs (line 230, col 12)`
- `SocialGoal.Tests\Controllers\GoalControllerTest.cs (line 186, col 12)`
- `SocialGoal.Tests\Controllers\GoalControllerTest.cs (line 184, col 12)`
- `SocialGoal.Tests\Controllers\GoalControllerTest.cs (line 158, col 12)`
- `SocialGoal.Tests\Controllers\EmailRequestControllerTest.cs (line 242, col 12)`
- `SocialGoal.Tests\Controllers\EmailRequestControllerTest.cs (line 240, col 12)`
- `SocialGoal.Tests\Controllers\EmailRequestControllerTest.cs (line 239, col 12)`
- `SocialGoal.Tests\Controllers\EmailRequestControllerTest.cs (line 237, col 12)`
- `SocialGoal.Tests\Controllers\EmailRequestControllerTest.cs (line 233, col 12)`
- `SocialGoal.Tests\Controllers\EmailRequestControllerTest.cs (line 231, col 12)`
- `SocialGoal.Tests\Controllers\EmailRequestControllerTest.cs (line 203, col 12)`
- `SocialGoal.Tests\Controllers\EmailRequestControllerTest.cs (line 155, col 12)`
- `SocialGoal.Tests\Controllers\EmailRequestControllerTest.cs (line 153, col 12)`
- `SocialGoal.Tests\Controllers\EmailRequestControllerTest.cs (line 152, col 12)`
- `SocialGoal.Tests\Controllers\EmailRequestControllerTest.cs (line 150, col 12)`
- `SocialGoal.Tests\Controllers\EmailRequestControllerTest.cs (line 146, col 12)`
- `SocialGoal.Tests\Controllers\EmailRequestControllerTest.cs (line 144, col 12)`
- `SocialGoal.Tests\Controllers\EmailRequestControllerTest.cs (line 116, col 12)`
- `SocialGoal.Tests\Controllers\AccountControllerTest.cs (line 787, col 12)`
- `SocialGoal.Tests\Controllers\AccountControllerTest.cs (line 785, col 12)`
- `SocialGoal.Tests\Controllers\AccountControllerTest.cs (line 784, col 12)`
- `SocialGoal.Tests\Controllers\AccountControllerTest.cs (line 782, col 12)`
- `SocialGoal.Tests\Controllers\AccountControllerTest.cs (line 744, col 12)`
- `SocialGoal.Tests\Controllers\AccountControllerTest.cs (line 743, col 12)`
- `SocialGoal.Tests\Controllers\AccountControllerTest.cs (line 742, col 12)`
- `SocialGoal.Tests\Controllers\AccountControllerTest.cs (line 740, col 12)`
- `SocialGoal.Tests\Controllers\AccountControllerTest.cs (line 690, col 12)`
- `SocialGoal.Tests\Controllers\AccountControllerTest.cs (line 688, col 12)`
- `SocialGoal.Tests\Controllers\AccountControllerTest.cs (line 687, col 12)`
- `SocialGoal.Tests\Controllers\AccountControllerTest.cs (line 685, col 12)`
- `SocialGoal.Tests\Controllers\AccountControllerTest.cs (line 636, col 12)`
- `SocialGoal.Tests\Controllers\AccountControllerTest.cs (line 634, col 12)`
- `SocialGoal.Tests\Controllers\AccountControllerTest.cs (line 606, col 12)`
- `SocialGoal.Tests\Controllers\AccountControllerTest.cs (line 570, col 12)`
- `SocialGoal.Tests\Controllers\AccountControllerTest.cs (line 568, col 12)`
- `SocialGoal.Tests\Controllers\AccountControllerTest.cs (line 539, col 12)`
- `SocialGoal.Tests\Controllers\AccountControllerTest.cs (line 509, col 12)`
- `SocialGoal.Tests\Controllers\AccountControllerTest.cs (line 507, col 12)`
- `SocialGoal.Tests\Controllers\AccountControllerTest.cs (line 478, col 12)`
- `SocialGoal.Tests\Controllers\AccountControllerTest.cs (line 424, col 12)`
- `SocialGoal.Tests\Controllers\AccountControllerTest.cs (line 422, col 12)`
- `SocialGoal.Tests\Controllers\AccountControllerTest.cs (line 394, col 12)`
- `SocialGoal.Tests\Controllers\AccountControllerTest.cs (line 343, col 12)`
- `SocialGoal.Tests\Controllers\AccountControllerTest.cs (line 342, col 12)`
- `SocialGoal.Tests\Controllers\AccountControllerTest.cs (line 324, col 12)`
- `SocialGoal.Tests\Controllers\AccountControllerTest.cs (line 291, col 12)`
- `SocialGoal.Tests\Controllers\AccountControllerTest.cs (line 290, col 12)`
- `SocialGoal.Tests\Controllers\AccountControllerTest.cs (line 272, col 12)`
- `SocialGoal.Tests\Controllers\AccountControllerTest.cs (line 223, col 12)`
- `SocialGoal.Tests\Controllers\AccountControllerTest.cs (line 222, col 12)`
- `SocialGoal.Tests\Controllers\AccountControllerTest.cs (line 203, col 12)`
- `SocialGoal.Tests\Controllers\AccountControllerTest.cs (line 161, col 12)`
- `SocialGoal.Tests\Controllers\AccountControllerTest.cs (line 160, col 12)`
- `SocialGoal.Tests\Controllers\AccountControllerTest.cs (line 142, col 12)`
- `SocialGoal.Web.Core\Models\SocialGoalUser.cs (line 31, col 8)`
- `SocialGoal.Web.Core\Models\SocialGoalUser.cs (line 32, col 52)`
- `SocialGoal.Web.Core\Models\SocialGoalUser.cs (line 32, col 19)`
- `SocialGoal.Web.Core\Authentication\IFormsAuthentication.cs (line 11, col 8)`
- `SocialGoal.Web.Core\Authentication\IFormsAuthentication.cs (line 10, col 8)`
- `SocialGoal.Web.Core\Authentication\IFormsAuthentication.cs (line 9, col 8)`
- `SocialGoal.Web.Core\Authentication\DefaultFormsAuthentication.cs (line 38, col 8)`
- `SocialGoal.Web.Core\Authentication\DefaultFormsAuthentication.cs (line 40, col 12)`
- `SocialGoal.Web.Core\Authentication\DefaultFormsAuthentication.cs (line 25, col 8)`
- `SocialGoal.Web.Core\Authentication\DefaultFormsAuthentication.cs (line 28, col 12)`
- `SocialGoal.Web.Core\Authentication\DefaultFormsAuthentication.cs (line 27, col 12)`
- `SocialGoal.Web.Core\Authentication\DefaultFormsAuthentication.cs (line 20, col 8)`
- `SocialGoal.Web.Core\Authentication\DefaultFormsAuthentication.cs (line 23, col 12)`
- `SocialGoal.Web.Core\Authentication\DefaultFormsAuthentication.cs (line 22, col 12)`
- `SocialGoal.Web.Core\Authentication\DefaultFormsAuthentication.cs (line 17, col 12)`
- `SocialGoal.Web.Core\Authentication\DefaultFormsAuthentication.cs (line 12, col 12)`
- `SocialGoal\Global.asax.cs (line 18, col 12)`
- `SocialGoal\App_Start\RouteConfig.cs (line 11, col 8)`

</details>

<details id="NuGet_package_is_incompatible">
<summary><b>NuGet package is incompatible</b> — affected files</summary>

- `SocialGoal.Data\SocialGoal.Data.csproj`
- `SocialGoal.Service\SocialGoal.Service.csproj`
- `SocialGoal.Tests\SocialGoal.Tests.csproj`
- `SocialGoal.Web.Core\SocialGoal.Web.Core.csproj`
- `SocialGoal\SocialGoal.Web.csproj`

</details>

<details id="System_Web_Optimization_bundling_and_minification_is_not_supported_in_NET_Core_and_should_be_replaced_with_actual_html_tags_pointing_to_content_files">
<summary><b>System.Web.Optimization bundling and minification is not supported in .NET Core and should be replaced with actual html tags pointing to content files</b> — affected files</summary>

- `SocialGoal\Views\Account\ExternalLoginConfirmation.cshtml`
- `SocialGoal\Views\Account\Login.cshtml`
- `SocialGoal\Views\Account\Manage.cshtml`
- `SocialGoal\Views\Account\Register.cshtml`
- `SocialGoal\Views\Shared\_GoalLayout.cshtml`
- `SocialGoal\Views\Shared\_HomeLayout.cshtml`
- `SocialGoal\Views\Shared\_Layout.cshtml`
- `SocialGoal\Views\Shared\_PageLayout.cshtml`

</details>

<details id="Project_file_needs_to_be_converted_to_SDK-style">
<summary><b>Project file needs to be converted to SDK-style</b> — affected files</summary>

- `SocialGoal.Core\SocialGoal.Core.csproj`
- `SocialGoal.Data\SocialGoal.Data.csproj`
- `SocialGoal.Model\SocialGoal.Model.csproj`
- `SocialGoal.Service\SocialGoal.Service.csproj`
- `SocialGoal.Tests\SocialGoal.Tests.csproj`
- `SocialGoal.Web.Core\SocialGoal.Web.Core.csproj`
- `SocialGoal\SocialGoal.Web.csproj`

</details>

<details id="Project_s_target_framework_s_needs_to_be_changed">
<summary><b>Project's target framework(s) needs to be changed</b> — affected files</summary>

- `SocialGoal.Core\SocialGoal.Core.csproj`
- `SocialGoal.Data\SocialGoal.Data.csproj`
- `SocialGoal.Model\SocialGoal.Model.csproj`
- `SocialGoal.Service\SocialGoal.Service.csproj`
- `SocialGoal.Tests\SocialGoal.Tests.csproj`
- `SocialGoal.Web.Core\SocialGoal.Web.Core.csproj`
- `SocialGoal\SocialGoal.Web.csproj`

</details>

<details id="NuGet_package_functionality_is_included_with_framework_reference">
<summary><b>NuGet package functionality is included with framework reference</b> — affected files</summary>

- `SocialGoal\SocialGoal.Web.csproj`

</details>

<details id="Routes_registration_via_RouteCollection_is_not_supported_in_NET_Core_and_needs_to_be_converted_to_the_route_mappings_on_the_application_object">
<summary><b>Routes registration via RouteCollection is not supported in .NET Core and needs to be converted to the route mappings on the application object</b> — affected files</summary>

- `SocialGoal\Global.asax.cs`
- `SocialGoal\App_Start\RouteConfig.cs`

</details>

<details id="Convert_application_initialization_code_from_Global_asax_cs_to_NET_Core_and_clean_up_Global_asax_cs">
<summary><b>Convert application initialization code from Global.asax.cs to .NET Core and clean up Global.asax.cs</b> — affected files</summary>

- `SocialGoal\Global.asax.cs`

</details>

<details id="Source_incompatible_for_selected_NET_version">
<summary><b>Source incompatible for selected .NET version</b> — affected files</summary>

- `SocialGoal.Model\Models\ProfilePic.cs (line 6, col 50)`
- `SocialGoal.Model\Models\ProfilePic.cs (line 6, col 45)`
- `SocialGoal.Model\Models\ProfilePic.cs (line 6, col 8)`
- `SocialGoal.Tests\Controllers\NotificationControllerTest.cs (line 302, col 12)`
- `SocialGoal.Tests\Controllers\NotificationControllerTest.cs (line 292, col 12)`
- `SocialGoal.Tests\Controllers\NotificationControllerTest.cs (line 216, col 12)`
- `SocialGoal.Tests\Controllers\NotificationControllerTest.cs (line 206, col 12)`
- `SocialGoal.Tests\Controllers\NotificationControllerTest.cs (line 129, col 12)`
- `SocialGoal.Tests\Controllers\NotificationControllerTest.cs (line 119, col 12)`
- `SocialGoal.Tests\Controllers\GroupControllerTest.cs (line 2025, col 12)`
- `SocialGoal.Tests\Controllers\GroupControllerTest.cs (line 2018, col 12)`
- `SocialGoal.Tests\Controllers\GroupControllerTest.cs (line 1928, col 12)`
- `SocialGoal.Tests\Controllers\GroupControllerTest.cs (line 1918, col 12)`
- `SocialGoal.Tests\Controllers\GroupControllerTest.cs (line 1762, col 12)`
- `SocialGoal.Tests\Controllers\GroupControllerTest.cs (line 1752, col 12)`
- `SocialGoal.Tests\Controllers\GroupControllerTest.cs (line 1704, col 12)`
- `SocialGoal.Tests\Controllers\GroupControllerTest.cs (line 1694, col 12)`
- `SocialGoal.Tests\Controllers\GroupControllerTest.cs (line 1594, col 12)`
- `SocialGoal.Tests\Controllers\GroupControllerTest.cs (line 1587, col 12)`
- `SocialGoal.Tests\Controllers\GroupControllerTest.cs (line 1497, col 12)`
- `SocialGoal.Tests\Controllers\GroupControllerTest.cs (line 1487, col 12)`
- `SocialGoal.Tests\Controllers\GroupControllerTest.cs (line 1370, col 12)`
- `SocialGoal.Tests\Controllers\GroupControllerTest.cs (line 1360, col 12)`
- `SocialGoal.Tests\Controllers\GroupControllerTest.cs (line 1271, col 12)`
- `SocialGoal.Tests\Controllers\GroupControllerTest.cs (line 1261, col 12)`
- `SocialGoal.Tests\Controllers\GroupControllerTest.cs (line 779, col 12)`
- `SocialGoal.Tests\Controllers\GroupControllerTest.cs (line 769, col 12)`
- `SocialGoal.Tests\Controllers\GroupControllerTest.cs (line 682, col 12)`
- `SocialGoal.Tests\Controllers\GroupControllerTest.cs (line 678, col 12)`
- `SocialGoal.Tests\Controllers\GroupControllerTest.cs (line 579, col 12)`
- `SocialGoal.Tests\Controllers\GroupControllerTest.cs (line 575, col 12)`
- `SocialGoal.Tests\Controllers\GroupControllerTest.cs (line 481, col 12)`
- `SocialGoal.Tests\Controllers\GroupControllerTest.cs (line 477, col 12)`
- `SocialGoal.Tests\Controllers\GroupControllerTest.cs (line 422, col 12)`
- `SocialGoal.Tests\Controllers\GroupControllerTest.cs (line 412, col 12)`
- `SocialGoal.Tests\Controllers\GroupControllerTest.cs (line 347, col 12)`
- `SocialGoal.Tests\Controllers\GroupControllerTest.cs (line 337, col 12)`
- `SocialGoal.Tests\Controllers\GroupControllerTest.cs (line 190, col 12)`
- `SocialGoal.Tests\Controllers\GroupControllerTest.cs (line 180, col 12)`
- `SocialGoal.Tests\Controllers\GoalControllerTest.cs (line 1293, col 12)`
- `SocialGoal.Tests\Controllers\GoalControllerTest.cs (line 1283, col 12)`
- `SocialGoal.Tests\Controllers\GoalControllerTest.cs (line 1142, col 12)`
- `SocialGoal.Tests\Controllers\GoalControllerTest.cs (line 1132, col 12)`
- `SocialGoal.Tests\Controllers\GoalControllerTest.cs (line 1072, col 12)`
- `SocialGoal.Tests\Controllers\GoalControllerTest.cs (line 1062, col 12)`
- `SocialGoal.Tests\Controllers\GoalControllerTest.cs (line 1007, col 12)`
- `SocialGoal.Tests\Controllers\GoalControllerTest.cs (line 997, col 12)`
- `SocialGoal.Tests\Controllers\GoalControllerTest.cs (line 929, col 12)`
- `SocialGoal.Tests\Controllers\GoalControllerTest.cs (line 919, col 12)`
- `SocialGoal.Tests\Controllers\GoalControllerTest.cs (line 834, col 12)`
- `SocialGoal.Tests\Controllers\GoalControllerTest.cs (line 824, col 12)`
- `SocialGoal.Tests\Controllers\GoalControllerTest.cs (line 736, col 12)`
- `SocialGoal.Tests\Controllers\GoalControllerTest.cs (line 726, col 12)`
- `SocialGoal.Tests\Controllers\GoalControllerTest.cs (line 635, col 12)`
- `SocialGoal.Tests\Controllers\GoalControllerTest.cs (line 625, col 12)`
- `SocialGoal.Tests\Controllers\GoalControllerTest.cs (line 579, col 12)`
- `SocialGoal.Tests\Controllers\GoalControllerTest.cs (line 569, col 12)`
- `SocialGoal.Tests\Controllers\GoalControllerTest.cs (line 513, col 12)`
- `SocialGoal.Tests\Controllers\GoalControllerTest.cs (line 503, col 12)`
- `SocialGoal.Tests\Controllers\GoalControllerTest.cs (line 253, col 12)`
- `SocialGoal.Tests\Controllers\GoalControllerTest.cs (line 248, col 12)`
- `SocialGoal.Tests\Controllers\GoalControllerTest.cs (line 186, col 12)`
- `SocialGoal.Tests\Controllers\GoalControllerTest.cs (line 176, col 12)`
- `SocialGoal.Tests\Controllers\EmailRequestControllerTest.cs (line 258, col 12)`
- `SocialGoal.Tests\Controllers\EmailRequestControllerTest.cs (line 251, col 12)`
- `SocialGoal.Tests\Controllers\EmailRequestControllerTest.cs (line 242, col 12)`
- `SocialGoal.Tests\Controllers\EmailRequestControllerTest.cs (line 240, col 12)`
- `SocialGoal.Tests\Controllers\EmailRequestControllerTest.cs (line 239, col 12)`
- `SocialGoal.Tests\Controllers\EmailRequestControllerTest.cs (line 237, col 12)`
- `SocialGoal.Tests\Controllers\EmailRequestControllerTest.cs (line 233, col 12)`
- `SocialGoal.Tests\Controllers\EmailRequestControllerTest.cs (line 223, col 12)`
- `SocialGoal.Tests\Controllers\EmailRequestControllerTest.cs (line 171, col 12)`
- `SocialGoal.Tests\Controllers\EmailRequestControllerTest.cs (line 164, col 12)`
- `SocialGoal.Tests\Controllers\EmailRequestControllerTest.cs (line 155, col 12)`
- `SocialGoal.Tests\Controllers\EmailRequestControllerTest.cs (line 153, col 12)`
- `SocialGoal.Tests\Controllers\EmailRequestControllerTest.cs (line 152, col 12)`
- `SocialGoal.Tests\Controllers\EmailRequestControllerTest.cs (line 150, col 12)`
- `SocialGoal.Tests\Controllers\EmailRequestControllerTest.cs (line 146, col 12)`
- `SocialGoal.Tests\Controllers\EmailRequestControllerTest.cs (line 136, col 12)`
- `SocialGoal.Tests\Controllers\AccountControllerTest.cs (line 801, col 12)`
- `SocialGoal.Tests\Controllers\AccountControllerTest.cs (line 795, col 12)`
- `SocialGoal.Tests\Controllers\AccountControllerTest.cs (line 787, col 12)`
- `SocialGoal.Tests\Controllers\AccountControllerTest.cs (line 785, col 12)`
- `SocialGoal.Tests\Controllers\AccountControllerTest.cs (line 784, col 12)`
- `SocialGoal.Tests\Controllers\AccountControllerTest.cs (line 782, col 12)`
- `SocialGoal.Tests\Controllers\AccountControllerTest.cs (line 758, col 12)`
- `SocialGoal.Tests\Controllers\AccountControllerTest.cs (line 752, col 12)`
- `SocialGoal.Tests\Controllers\AccountControllerTest.cs (line 744, col 12)`
- `SocialGoal.Tests\Controllers\AccountControllerTest.cs (line 743, col 12)`
- `SocialGoal.Tests\Controllers\AccountControllerTest.cs (line 742, col 12)`
- `SocialGoal.Tests\Controllers\AccountControllerTest.cs (line 740, col 12)`
- `SocialGoal.Tests\Controllers\AccountControllerTest.cs (line 706, col 12)`
- `SocialGoal.Tests\Controllers\AccountControllerTest.cs (line 699, col 12)`
- `SocialGoal.Tests\Controllers\AccountControllerTest.cs (line 690, col 12)`
- `SocialGoal.Tests\Controllers\AccountControllerTest.cs (line 688, col 12)`
- `SocialGoal.Tests\Controllers\AccountControllerTest.cs (line 687, col 12)`
- `SocialGoal.Tests\Controllers\AccountControllerTest.cs (line 685, col 12)`
- `SocialGoal.Tests\Controllers\AccountControllerTest.cs (line 636, col 12)`
- `SocialGoal.Tests\Controllers\AccountControllerTest.cs (line 626, col 12)`
- `SocialGoal.Tests\Controllers\AccountControllerTest.cs (line 570, col 12)`
- `SocialGoal.Tests\Controllers\AccountControllerTest.cs (line 560, col 12)`
- `SocialGoal.Tests\Controllers\AccountControllerTest.cs (line 509, col 12)`
- `SocialGoal.Tests\Controllers\AccountControllerTest.cs (line 499, col 12)`
- `SocialGoal.Tests\Controllers\AccountControllerTest.cs (line 424, col 12)`
- `SocialGoal.Tests\Controllers\AccountControllerTest.cs (line 414, col 12)`
- `SocialGoal.Tests\Controllers\AccountControllerTest.cs (line 343, col 12)`
- `SocialGoal.Tests\Controllers\AccountControllerTest.cs (line 339, col 12)`
- `SocialGoal.Tests\Controllers\AccountControllerTest.cs (line 291, col 12)`
- `SocialGoal.Tests\Controllers\AccountControllerTest.cs (line 287, col 12)`
- `SocialGoal.Tests\Controllers\AccountControllerTest.cs (line 223, col 12)`
- `SocialGoal.Tests\Controllers\AccountControllerTest.cs (line 219, col 12)`
- `SocialGoal.Tests\Controllers\AccountControllerTest.cs (line 161, col 12)`
- `SocialGoal.Tests\Controllers\AccountControllerTest.cs (line 157, col 12)`
- `SocialGoal.Web.Core\Authentication\IFormsAuthentication.cs (line 10, col 8)`
- `SocialGoal.Web.Core\Authentication\IFormsAuthentication.cs (line 9, col 8)`
- `SocialGoal.Web.Core\Authentication\DefaultFormsAuthentication.cs (line 25, col 8)`
- `SocialGoal.Web.Core\Authentication\DefaultFormsAuthentication.cs (line 28, col 12)`
- `SocialGoal.Web.Core\Authentication\DefaultFormsAuthentication.cs (line 20, col 8)`
- `SocialGoal.Web.Core\Authentication\DefaultFormsAuthentication.cs (line 23, col 12)`
- `SocialGoal.Web.Core\ActionFilters\CompressResponseAttribute.cs (line 32, col 20)`
- `SocialGoal.Web.Core\ActionFilters\CompressResponseAttribute.cs (line 31, col 20)`
- `SocialGoal.Web.Core\ActionFilters\CompressResponseAttribute.cs (line 27, col 20)`
- `SocialGoal.Web.Core\ActionFilters\CompressResponseAttribute.cs (line 26, col 20)`
- `SocialGoal.Web.Core\ActionFilters\CompressResponseAttribute.cs (line 16, col 12)`
- `SocialGoal\ViewModels\UploadImageViewModel.cs (line 13, col 46)`
- `SocialGoal\ViewModels\UploadImageViewModel.cs (line 13, col 41)`
- `SocialGoal\ViewModels\UploadImageViewModel.cs (line 12, col 8)`
- `SocialGoal\Helpers\SocialGoalSessionFacade.cs (line 32, col 12)`
- `SocialGoal\Helpers\SocialGoalSessionFacade.cs (line 27, col 12)`
- `SocialGoal\Helpers\SocialGoalSessionFacade.cs (line 21, col 16)`
- `SocialGoal\Helpers\SocialGoalSessionFacade.cs (line 16, col 16)`
- `SocialGoal\Controllers\AccountController.cs (line 496, col 8)`
- `SocialGoal\Controllers\AccountController.cs (line 504, col 16)`
- `SocialGoal\Controllers\AccountController.cs (line 503, col 16)`
- `SocialGoal\Controllers\AccountController.cs (line 502, col 16)`
- `SocialGoal\Controllers\AccountController.cs (line 500, col 12)`
- `SocialGoal\Controllers\AccountController.cs (line 498, col 12)`
- `SocialGoal\Controllers\AccountController.cs (line 445, col 8)`
- `SocialGoal\Controllers\AccountController.cs (line 469, col 16)`
- `SocialGoal\Controllers\AccountController.cs (line 455, col 16)`
- `SocialGoal\Controllers\AccountController.cs (line 425, col 20)`
- `SocialGoal\Controllers\AccountController.cs (line 419, col 20)`
- `SocialGoal\Controllers\AccountController.cs (line 413, col 20)`
- `SocialGoal\Controllers\AccountController.cs (line 412, col 20)`
- `SocialGoal\Controllers\AccountController.cs (line 409, col 21)`
- `SocialGoal\Controllers\AccountController.cs (line 407, col 20)`
- `SocialGoal\Global.asax.cs (line 11, col 45)`

</details>

<details id="AutoGenerateBindingRedirects_not_set_and_no_manual_redirects">
<summary><b>AutoGenerateBindingRedirects not set and no manual redirects</b> — affected files</summary>

- `SocialGoal.Core\SocialGoal.Core.csproj`
- `SocialGoal.Data\SocialGoal.Data.csproj`
- `SocialGoal.Model\SocialGoal.Model.csproj`
- `SocialGoal.Service\SocialGoal.Service.csproj`
- `SocialGoal.Web.Core\SocialGoal.Web.Core.csproj`

</details>

<details id="NuGet_package_upgrade_is_recommended">
<summary><b>NuGet package upgrade is recommended</b> — affected files</summary>

- `SocialGoal.Data\SocialGoal.Data.csproj`
- `SocialGoal.Tests\SocialGoal.Tests.csproj`
- `SocialGoal\SocialGoal.Web.csproj`

</details>

<details id="Behavioral_change_in_selected_NET_version">
<summary><b>Behavioral change in selected .NET version</b> — affected files</summary>

- `SocialGoal.Web.Core\Models\UserInfo.cs (line 27, col 12)`
- `SocialGoal.Web.Core\Models\UserInfo.cs (line 17, col 12)`
- `SocialGoal\Controllers\AccountController.cs (line 450, col 12)`

</details>

<details id="Library-hosted_entry_point_missing_GenerateBindingRedirectsOutputType">
<summary><b>Library-hosted entry point missing GenerateBindingRedirectsOutputType</b> — affected files</summary>

- `SocialGoal.Tests\SocialGoal.Tests.csproj`

</details>

<details id="NuGet_package_is_deprecated">
<summary><b>NuGet package is deprecated</b> — affected files</summary>

- `SocialGoal.Data\SocialGoal.Data.csproj`
- `SocialGoal.Tests\SocialGoal.Tests.csproj`
- `SocialGoal\SocialGoal.Web.csproj`

</details>

<details id="NuGet_package_contains_security_vulnerability">
<summary><b>NuGet package contains security vulnerability</b> — affected files</summary>

- `SocialGoal.Tests\SocialGoal.Tests.csproj`
- `SocialGoal\SocialGoal.Web.csproj`

</details>

---

## Codebase Insights

> **Note:** These documents are generated by AI and may contain inaccuracies or incomplete information. Please review carefully.

1. **[Architecture Diagram](facts/architecture-diagram.md)** — Understand the big picture: system layers and component relationships
2. **[Dependency Map](facts/dependency-map.md)** — Know what the project depends on and where the risks are
3. **[API & Service Contracts](facts/api-service-contracts.md)** — See how services communicate and what contracts they expose
4. **[Data Architecture](facts/data-architecture.md)** — Explore data models, storage, and data flow patterns
5. **[Configuration Inventory](facts/configuration-inventory.md)** — Review how the application is configured across environments
6. **[Business Workflows](facts/business-workflows.md)** — Trace end-to-end business processes and domain logic

[Share feedback](https://aka.ms/ghcp-appmod/feedback)
