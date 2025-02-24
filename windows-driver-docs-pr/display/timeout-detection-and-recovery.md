---
title: Timeout detection and recovery (TDR)
description: Describes timeout detection and recovery (TDR) for the Windows Display Driver Model (WDDM)
keywords:
- TDR (timeout detection and recovery) WDK display
- TDR (timeout detection and recovery) WDK graphics
ms.date: 10/06/2020
ms.custom: contperf-fy21q2
---

# Timeout detection and recovery (TDR)

This page describes timeout detection and recovery (TDR) for driver developers. See also [TDR in Windows 8 and later](tdr-changes-in-windows-8.md) for additional implementation details.

## Overview

One of the most common stability problems in graphics occurs when a computer "hangs", or when it appears to be completely "frozen" while, in reality, it is processing an end-user command or operation. The user typically waits a few seconds and then decides to reboot the computer. The frozen appearance of the computer typically occurs because the GPU is busy processing intensive graphical operations, typically during game play, and hence does not update the display screen. TDRs enable the operating system to detect that the UI is not responsive.

The figure below shows the TDR process.

![timeout detection and recovery (tdr) of gpus through wddm.](images/timeoutdetectionrecoverygpusthroughwddm.jpg)

The operating system (OS) attempts to detect situations in which computers appear to be "frozen". The OS then attempts to dynamically recover from the frozen situations so that desktops are responsive again, alleviating the situation where end users needlessly reboot their systems.

If the OS detects that six (6) or more GPU hangs and subsequent recoveries occur within one (1) minute, the OS bug-checks the computer on the next GPU hang.

## Timeout detection in WDDM

The GPU scheduler, which is part of the DirectX graphics kernel subsystem (*Dxgkrnl.sys*), detects that the GPU is taking more than the permitted amount of time to execute a particular task. The GPU scheduler then tries to preempt this particular task. The preempt operation has a "wait" timeout, which is the actual TDR timeout. The default timeout period in Windows Vista and later operating systems is 2 seconds. If the GPU cannot complete or preempt the current task within the TDR timeout period, the OS diagnoses that the GPU is frozen.

To prevent timeout detection from occurring, hardware vendors should ensure that graphics operations (that is, direct memory access (DMA) buffer completion) take no more than 2 seconds in end-user scenarios such as productivity and game play.

## Preparation for recovery

The GPU scheduler calls the display miniport driver's [*DxgkDdiResetFromTimeout*](/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_resetfromtimeout) function to inform the driver that the OS detected a timeout. The driver must then reinitialize itself and reset the GPU. In addition, the driver must stop accessing memory and should not access hardware. The OS and the driver collect hardware and other state information that can be useful for post-recovery diagnosis.

See [TDR in Windows 8 and later](tdr-changes-in-windows-8.md) for additional implementation details.

## Desktop recovery

The OS resets the appropriate state of the graphics stack. The video memory manager, which is also part of *Dxgkrnl.sys*, purges all allocations from video memory. The display miniport driver resets the GPU hardware state. The graphics stack takes the final actions and restores the desktop to the responsive state.

The only visible artifact from the hang detection to the recovery is a screen flicker. This flicker results when the OS resets some portions of the graphics stack, which causes a screen redraw. It is eliminated if the display miniport driver complies with WDDM 1.2 and later (see [Providing seamless state transitions in WDDM 1.2 and later](seamless-state-transitions-in-wddm-1-2-and-later.md)).

When the OS has successfully recovered the desktop, it does the following:

* Displays an informational message to the end user, saying "Display driver stopped responding and has recovered."
* Logs the preceding message in the Event Viewer application and collects diagnosis information in the form of a debug report. If the end user opted in to provide feedback, the OS returns this debug report to Microsoft through the Online Crash Analysis (OCA) mechanism.

Some legacy DirectX applications might just render black at the end of this recovery, which requires the end user to restart these applications. Well-written DirectX 9Ex and DirectX 10 and later applications that handle Device Remove technology continue to work correctly. An application must release and then re-create its Microsoft Direct3D device and all of the device's objects.

## Thread synchronization and TDR

See [Thread synchronization and TDR](thread-synchronization-and-tdr.md) for details.

## Testing and debugging TDR

See [Testing and debugging TDR](tdr-registry-keys.md) for details.
