---
title: DEVPKEY_Device_NoConnectSound
description: DEVPKEY_Device_NoConnectSound
keywords: ["DEVPKEY_Device_NoConnectSound Device and Driver Installation"]
topic_type:
- apiref
api_name:
- DEVPKEY_Device_NoConnectSound
api_location:
- Devpkey.h
api_type:
- HeaderDef
ms.date: 10/17/2018
---

# DEVPKEY_Device_NoConnectSound


The DEVPKEY_Device_NoConnectSound device property represents a Boolean value that indicates whether to suppress the sound that the Microsoft Windows operating system plays to indicate that a removable device arrived or was removed.

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
<td align="left"><p>DEVPKEY_Device_NoConnectSound</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>Property-data-type identifier</strong></p></td>
<td align="left"><p><a href="devprop-type-boolean.md" data-raw-source="[&lt;strong&gt;DEVPROP_TYPE_BOOLEAN&lt;/strong&gt;](devprop-type-boolean.md)"><strong>DEVPROP_TYPE_BOOLEAN</strong></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Property access</strong></p></td>
<td align="left"><p>Read and write access by installation applications and installers</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>Localized?</strong></p></td>
<td align="left"><p>No</p></td>
</tr>
</tbody>
</table>

 

## Remarks

The value of DEVPKEY_Device_NoConnectSound is set to DEVPROP_TRUE to suppress playing sound. Otherwise, the value of the property is set to DEVPROP_FALSE.

The DEVPKEY_Device_NoConnectSound property is typically set by an [**INF AddProperty directive**](./inf-addproperty-directive.md) in the INF file for a device.

You can call [**SetupDiGetDeviceProperty**](/windows/win32/api/setupapi/nf-setupapi-setupdigetdevicepropertyw) or [**SetupDiSetDeviceProperty**](/windows/win32/api/setupapi/nf-setupapi-setupdisetdevicepropertyw) to retrieve or set the value of DEVPKEY_Device_NoConnectSound.

Windows Server 2003, Windows XP, and Windows 2000 do not support this property.

## Requirements

**Version**: Windows Vista and later versions of Windows
**Header**: Devpkey.h (include Devpkey.h)


## See also


[**INF AddProperty Directive**](./inf-addproperty-directive.md)

[**SetupDiGetDeviceProperty**](/windows/win32/api/setupapi/nf-setupapi-setupdigetdevicepropertyw)

 

