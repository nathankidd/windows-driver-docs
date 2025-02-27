---
title: DEVPKEY_Device_ContainerId
description: DEVPKEY_Device_ContainerId
keywords: ["DEVPKEY_Device_ContainerId Device and Driver Installation"]
topic_type:
- apiref
api_name:
- DEVPKEY_Device_ContainerId
api_location:
- Devpkey.h
api_type:
- HeaderDef
ms.date: 10/17/2018
---

# DEVPKEY_Device_ContainerId


The DEVPKEY_Device_ContainerId device property is used by the Plug and Play (PnP) manager to group one or more device nodes (*devnodes*) into a *device container* that represents an instance of a physical device.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr>
<th>Attribute</th>
<th>Value</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>Property key</strong></p></td>
<td align="left"><p>DEVPKEY_Device_ContainerId</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>Property-data-type identifier</strong></p></td>
<td align="left"><a href="devprop-type-guid.md" data-raw-source="[&lt;strong&gt;DEVPROP_TYPE_GUID&lt;/strong&gt;](devprop-type-guid.md)"><strong>DEVPROP_TYPE_GUID</strong></a></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Property access</strong></p></td>
<td align="left"><p>Read-only access by installation applications and installers</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>Localized?</strong></p></td>
<td align="left"><p>No</p></td>
</tr>
</tbody>
</table>

 

## Remarks

Starting with Windows 7, the PnP manager uses the device container and its identifier (*ContainerID*) to group one or more *devnodes* that originated from and belong to each instance of a particular physical device. The ContainerID for a device instance is referenced through the DEVPKEY_Device_ContainerId device property.

When you group all the devnodes that originated from an instance of a single device into containers, you accomplish the following results:

-   The operating system can determine how functionality is related among *devnodes* that originate from a physical device.

-   The user or applications are presented with a device-centric view of devices instead of the traditional function-centric view.

The DEVPKEY_Device_ContainerId can be used to determine the device container grouping of *devnodes* in a system. For a given devnode, you can determine all the devnodes that belong to the same container by completing the following steps:

-   Call [**SetupDiGetDeviceProperty**](/windows/win32/api/setupapi/nf-setupapi-setupdigetdevicepropertyw) to query DEVPKEY_Device_ContainerId for the given devnode. Windows returns the ContainerID *GUID* value for the device container to which that devnode belongs.

-   Enumerate all devnodes on the computer and query each devnode for its DEVPKEY_Device_ContainerId. Each ContainerId value that matches the ContainerId value of the original devnode is part of same container.

**Note**  All *devnodes* that belong to a container on a given bus type must share the same ContainerID value.

 

For more information about ContainerIDs, see [Container IDs](./container-ids.md).

## Requirements

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p>Version</p></td>
<td align="left"><p>Available in Windows 7 and later versions of Windows.</p></td>
</tr>
<tr class="even">
<td align="left"><p>Header</p></td>
<td align="left">Devpkey.h (include Devpkey.h)</td>
</tr>
</tbody>
</table>

## See also


[Container IDs](./container-ids.md)

[**SetupDiGetDeviceProperty**](/windows/win32/api/setupapi/nf-setupapi-setupdigetdevicepropertyw)

