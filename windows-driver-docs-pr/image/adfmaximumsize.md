---
title: ADFMaximumSize element
description: The required ADFMaximumSize element specifies the largest size document that an end user can scan on the front or back side of the automatic document feeder (ADF).
keywords: ["ADFMaximumSize element Imaging Devices"]
topic_type:
- apiref
api_name:
- wscn ADFMaximumSize
api_type:
- Schema
ms.date: 11/28/2017
---

# ADFMaximumSize element


The required **ADFMaximumSize** element specifies the largest size document that an end user can scan on the front or back side of the automatic document feeder (ADF).

## Usage

```xml
<wscn:ADFMaximumSize>
  child elements
</wscn:ADFMaximumSize>
```

## Attributes

There are no attributes.

## Child elements


<table>
<colgroup>
<col width="100%" />
</colgroup>
<thead>
<tr class="header">
<th>Element</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="height.md" data-raw-source="[&lt;strong&gt;Height&lt;/strong&gt;](height.md)"><strong>Height</strong></a></p></td>
</tr>
<tr class="even">
<td><p><a href="width.md" data-raw-source="[&lt;strong&gt;Width&lt;/strong&gt;](width.md)"><strong>Width</strong></a></p></td>
</tr>
</tbody>
</table>

## Parent elements


<table>
<colgroup>
<col width="100%" />
</colgroup>
<thead>
<tr class="header">
<th>Element</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="adfback.md" data-raw-source="[&lt;strong&gt;ADFBack&lt;/strong&gt;](adfback.md)"><strong>ADFBack</strong></a></p></td>
</tr>
<tr class="even">
<td><p><a href="adffront.md" data-raw-source="[&lt;strong&gt;ADFFront&lt;/strong&gt;](adffront.md)"><strong>ADFFront</strong></a></p></td>
</tr>
</tbody>
</table>

## Remarks

The [**Width**](width.md) child element specifies the maximum size of media that the ADF supports in the fast scan direction. The [**Height**](height.md) child element specifies the maximum size of media that the ADF supports in the slow scan direction.

If the parent element of the **ADFMaximumSize** element is [**ADFFront**](adffront.md), the specified maximum size applies to the front side of the ADF; otherwise, the parent element is [**ADFBack**](adfback.md) and the maximum size applies to the back side of the ADF.

All media dimensions are measured in one-thousandths (1/1000) of an inch. The possible values for both **Width** and **Height** range from 1 through 2147483648.

## See also


[**ADFBack**](adfback.md)

[**ADFFront**](adffront.md)

[**Height**](height.md)

[**Width**](width.md)

 

 






