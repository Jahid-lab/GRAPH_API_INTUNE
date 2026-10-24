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



# GROUPING-INTUNE

A PowerShell script for bulk-adding devices to Microsoft Entra ID groups using Microsoft Graph PowerShell, supporting Intune device management workflows.

## Features

- Install the required Microsoft Graph PowerShell modules.
- Authenticate to Microsoft Graph using device code sign-in.
- Read device names from a `.txt` file.
- Find matching device objects in Microsoft Entra ID.
- Add devices to a specified group.
- Report successful additions, missing devices and failures.

## Requirements

- PowerShell
- Microsoft Graph PowerShell SDK
- Appropriate Microsoft Graph permissions
- An existing Microsoft Entra ID group
- A `.txt` file containing one device name per line

## Configuration

Update these variables in the script:

- `$groupName` — the target group name.
- `$deviceListPath` — the full path to the text file containing device names.

Example device list:

```text
DEVICE001
DEVICE002
DEVICE003
```

## Usage

1. Open PowerShell.
2. Run the script using an account with the required permissions.
3. Authenticate using the device code sign-in prompt.
4. Set the target group and device list path.
5. Review the results and summary for successful additions and failures.

## Microsoft Graph Permissions

The script requests the following delegated permissions:

- `GroupMember.ReadWrite.All`
- `Device.Read.All`

The signed-in account must have sufficient permissions to modify the target group's membership.

## Disclaimer

This script modifies Microsoft Entra ID group membership, which can affect Intune application deployments, configuration policies and other group-based assignments. Test with a small device list before running it at scale.
