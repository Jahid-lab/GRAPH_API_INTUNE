# GRPAH_API_INTUNE

# TOOLKIT-EUC

A menu-driven PowerShell toolkit for EUC (End User Computing) and Endpoint Engineering tasks using Microsoft Graph API.

TOOLKIT-EUC simplifies common Microsoft Intune and Microsoft Entra ID reporting and troubleshooting tasks, providing a central place to search application assignments, check installation status, look up Autopilot devices, compare device group memberships and review device inventory.

## Features

| Option | Feature | Description |
|---|---|---|
| 1 | Search Applications and Assignments | Search apps by name and view platform, version where available, assignment intent, included/excluded groups and assignment filters. |
| 2 | Find Apps Assigned to a Group | Identify applications assigned to a specific group. |
| 3 | Check Application Installation Status | Retrieve app installation status and identify devices reporting an installed application. |
| 4 | Autopilot Device Lookup | Look up Windows Autopilot device information. |
| 5 | Compare Device Group Memberships | Review device group memberships to assist with troubleshooting. |
| 6 | View Device Inventory | Retrieve and filter managed device inventory, including Windows 11 workstations matching the `UELIMD-*` naming convention. |

## Requirements

- PowerShell
- Microsoft Graph PowerShell SDK
- An account with the required Microsoft Graph permissions
- Appropriate access to Microsoft Intune and Microsoft Entra ID

## Microsoft Graph Permissions

The toolkit uses the following delegated Microsoft Graph scopes:

- `DeviceManagementManagedDevices.Read.All`
- `DeviceManagementApps.Read.All`
- `DeviceManagementConfiguration.Read.All`
- `DeviceManagementServiceConfig.Read.All`
- `Group.Read.All`
- `Device.Read.All`

Access depends on the signed-in account's permissions and the relevant Microsoft Graph API endpoint.

## Getting Started

1. Clone or download this repository.
2. Install the Microsoft Graph PowerShell SDK if required.
3. Open PowerShell.
4. Connect to Microsoft Graph using the permissions required by the script.
5. Run the toolkit script and select an option from the interactive menu.

## Exporting Results

Where supported, results can be exported to CSV.

Exports are saved to:

`Documents\EUC-Exports`

The toolkit uses timestamped filenames to help distinguish between reports.

## Security

- Review the script before running it in a production environment.
- Use least-privilege access and grant only the required permissions.
- Never commit credentials, access tokens, tenant secrets or sensitive device exports to the repository.
- Verify Graph API calls and permissions before use.

## Disclaimer

TOOLKIT-EUC is an administrative toolkit intended to support EUC and Endpoint Engineering reporting and troubleshooting. Results depend on the Microsoft Graph API, available device and application properties, account permissions and tenant configuration.
