---
title: KSEVENT_CROSSBAR_CHANGED
description: The KSEVENT_CROSSBAR_CHANGED event propagates an action, such as a new routing configuration, from the kernel-mode video capture minidriver to DirectShow in user-mode.
keywords: ["KSEVENT_CROSSBAR_CHANGED Streaming Media Devices"]
topic_type:
- apiref
api_name:
- KSEVENT_CROSSBAR_CHANGED
api_type:
- NA
ms.date: 10/11/2021
---

# KSEVENT_CROSSBAR_CHANGED

The **KSEVENT_CROSSBAR_CHANGED** event propagates an action, such as a new routing configuration, from the kernel-mode video capture minidriver to DirectShow in user-mode.

## Usage Summary Table

| Get | Set | Target | Event descriptor type | Event value type    |
|-----|-----|--------|-----------------------|---------------------|
| No  | Yes | Pin    | [**KSE_NODE**](/windows-hardware/drivers/ddi/ks/ns-ks-kse_node)     | [**KSEVENTDATA**](/windows-hardware/drivers/ddi/ks/ns-ks-kseventdata) |

For more information about DirectShow filters and KsProxy see [Kernel Streaming Proxy](/windows-hardware/drivers/ddi/_stream/index).
