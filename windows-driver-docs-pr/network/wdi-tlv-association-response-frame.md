---
title: WDI_TLV_ASSOCIATION_RESPONSE_FRAME
description: WDI_TLV_ASSOCIATION_RESPONSE_FRAME is a TLV that contains the received association response.
ms.date: 07/18/2017
keywords:
 - WDI_TLV_ASSOCIATION_RESPONSE_FRAME Network Drivers Starting with Windows Vista
---

# WDI\_TLV\_ASSOCIATION\_RESPONSE\_FRAME

[!INCLUDE [WDI topic note](../includes/wdi-version-warning.md)]


WDI\_TLV\_ASSOCIATION\_RESPONSE\_FRAME is a TLV that contains the received association response.

## TLV Type


0x2F

## Length


The size (in bytes) of the array of UINT8 elements. The array must contain 1 or more elements.

## Values


| Type      | Description                                                                                                              |
|-----------|--------------------------------------------------------------------------------------------------------------------------|
| UINT8\[\] | An array of UINT8 elements that contains the received association response. This does not include the 802.11 MAC header. |

 

## Requirements

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Minimum supported client</p></td>
<td><p>Windows 10</p></td>
</tr>
<tr class="even">
<td><p>Minimum supported server</p></td>
<td><p>Windows Server 2016</p></td>
</tr>
<tr class="odd">
<td><p>Header</p></td>
<td>Wditypes.hpp</td>
</tr>
</tbody>
</table>

 

 




