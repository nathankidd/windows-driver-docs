---
title: KSPROPERTY_CAMERACONTROL_PAN
description: User-mode clients use the KSPROPERTY_CAMERACONTROL_PAN property to get or set a camera's pan setting. This property is optional.
keywords: ["KSPROPERTY_CAMERACONTROL_PAN Streaming Media Devices"]
topic_type:
- apiref
api_name:
- KSPROPERTY_CAMERACONTROL_PAN
api_location:
- Ksmedia.h
api_type:
- HeaderDef
ms.date: 10/14/2021
---

# KSPROPERTY_CAMERACONTROL_PAN

User-mode clients use the **KSPROPERTY_CAMERACONTROL_PAN** property to get or set a camera's pan setting. This property is optional.

## Usage Summary Table

| Get | Set | Target | Property descriptor type | Property value type |
|--|--|--|--|--|
| Yes | Yes | Filter or node | [**KSPROPERTY_CAMERACONTROL_S**](/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksproperty_cameracontrol_s) or [**KSPROPERTY_CAMERACONTROL_NODE_S**](/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksproperty_cameracontrol_node_s) | LONG |

The property value (operation data) is a LONG that specifies a camera's pan setting. This value is expressed in degrees.

Positive values indicate that the camera is rotated clockwise. Negative values indicate that the camera is rotated counterclockwise, as shown in the following illustration.

![illustration showing camera pan values.](images/cam-pan-1.png)

Every video capture minidriver that supports this property must define a range and default value for this property. The range for the device must be -180 through +180. The default value must be 0.

> [!CAUTION]
> When writing or testing an app, you should be aware that in practice, some drivers define a custom range of pan values and custom step values that might not be based on typical units. Drivers might implement the pan control either physically or digitally.

## Remarks

The **Value** member of the **KSPROPERTY_CAMERACONTROL_S** structure specifies the pan setting.

## Requirements

**Header:** ksmedia.h (include Ksmedia.h)

## See also

[**KSPROPERTY**](ksproperty-structure.md)

[**KSPROPERTY_CAMERACONTROL_S**](/windows-hardware/drivers/ddi/ksmedia/ns-ksmedia-ksproperty_cameracontrol_s)
