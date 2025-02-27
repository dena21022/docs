---
title: Device statuses
excerpt: Determine the status and connectivity of a device
---

# Device statuses

Device statuses are displayed on the Devices page and the Device Summary page. An overview of the device statuses of a fleet is shown on the Fleets page. Each device can have one of the following statuses:

<img src="/img/common/main_dashboard/application_device_status.png" alt="Application device status" width="40%" >

| Status                     | Description                                                                                                                                                     |
|----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Online**                 | The device is online and is communicating with the cloud within the correct interval. In this state, the device is connected to the VPN and has had recent API communications. |
| **Online (VPN&#160;Only)**<sup>1</sup>      | The device is online, is connected to the VPN, but has **no recent API communications**.                                                       |
| **Online (Heartbeat&#160;Only)**<sup>2</sup>| The device is online, has recent API communications, but is **not connected to the VPN**.                                                      |
| **Offline**                | The device is offline.                                                                                                                                          |
| **Configuring**            | The device is applying OS configuration.                                                                                                                        |
| **Updating**               | The device is updating to a new release.                                                                                                            |
| **Post Provisioning**      | The device has been [provisioned][device-provisioning] but has not yet come online.                                                                             |
| **Inactive**               | The device has been [deactivated][deactivated] or has been [preregistered][preregistered] but has not yet connected to the {{ $names.cloud.lower }} API.        |
| **Frozen**                 | The device has been frozen because it's outside the organization's allowance, or is in a paid [fleet type][fleet type] on a free tier organization. |

## Device Connectivty states

![Device connectivity indicators](/img/common/main_dashboard/device_status.png)

A device's status may include indicators of partial connectivity issues on the device, such as a firewall blocking VPN traffic or a device's inability to communicate with the {{ $names.cloud.lower }} API. These indicators are as follows:
 
<sup>1</sup> `Online (VPN Only)` indicates that the device is unable to communicate with the {{ $names.cloud.lower }} API. 

<sup>2</sup> `Online (Heartbeat Only)` indicates that device is unable to connect to the {{ $names.cloud.lower }} VPN (e.g. a firewall is blocking VPN traffic), and won't be able to provide remote SSH connections.

__Note:__ If the device is powered off or loses all network connectivity, it will remain in the `Online (Heartbeat Only)` state until the last target state fetch exceeds the device [API polling interval][poll-interval].

## Debugging Device Status

If you find your device to be displaying a status which is unclear even with the above notes, visit the [device status][debugging-masterclass#device-status] section in the[device debugging masterclass][debugging-masterclass] for more information.

[deactivated]: /learn/manage/billing/#inactive-devices
[poll-interval]: /learn/manage/configuration/#variable-list
[device-provisioning]: /learn/welcome/primer/#device-provisioning
[preregistered]: /learn/more/masterclasses/advanced-cli/#52-preregistering-a-device
[fleet type]: /learn/manage/fleet-types
[debugging-masterclass]:/learn/more/masterclasses/device-debugging
[debugging-masterclass#device-status]:/learn/more/masterclasses/device-debugging#12-Device-connectivity-status
