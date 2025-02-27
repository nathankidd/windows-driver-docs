---
title: OID_GEN_RCV_NO_BUFFER
description: As a query, the OID_GEN_RCV_NO_BUFFER OID specifies the number of frames that the NIC cannot receive due to lack of NIC receive buffer space.
ms.date: 08/08/2017
keywords: 
 -OID_GEN_RCV_NO_BUFFER Network Drivers Starting with Windows Vista
---

# OID\_GEN\_RCV\_NO\_BUFFER


As a query, the OID\_GEN\_RCV\_NO\_BUFFER OID specifies the number of frames that the NIC cannot receive due to lack of NIC receive buffer space. Some NICs do not provide the exact number of missed frames; they provide only the number of times at least one frame is missed.

**Version Information**

<a href="" id="windows-vista-and-later-versions-of-windows"></a>Windows Vista and later versions of Windows  
Obsolete.

<a href="" id="ndis-6-0-and-later-drivers"></a>NDIS 6.0 and later drivers  
Not requested. Use [OID\_GEN\_STATISTICS](oid-gen-statistics.md) instead.

<a href="" id="ndis-5-1-drivers"></a>NDIS 5.1 drivers  
Mandatory.

<a href="" id="windows-xp"></a>Windows XP  
Supported.

<a href="" id="ndis-5-1-drivers"></a>NDIS 5.1 drivers  
Mandatory.

## Remarks

For general information about statistics OIDs, see [General Statistics](./ndis-general-statistics-oids.md).

## Requirements

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Header</p></td>
<td>Ntddndis.h (include Ndis.h)</td>
</tr>
</tbody>
</table>

## See also


[OID\_GEN\_STATISTICS](oid-gen-statistics.md)

 

