---
UID: NC:d3dkmddi.DXGKDDI_VIDPNTARGETMODESET_ADDMODE
title: DXGKDDI_VIDPNTARGETMODESET_ADDMODE (d3dkmddi.h)
description: The pfnAddMode function adds a VidPN target mode to a specified VidPN target mode set object.
old-location: display\dxgk_vidpntargetmodeset_interface_pfnaddmode.htm
ms.date: 05/10/2018
keywords: ["DXGKDDI_VIDPNTARGETMODESET_ADDMODE callback function"]
ms.keywords: DXGKDDI_VIDPNTARGETMODESET_ADDMODE, DXGKDDI_VIDPNTARGETMODESET_ADDMODE callback, VidPnFunctions_96cfc36e-77db-49c8-b19c-e56624e72fb4.xml, d3dkmddi/dxgk_vidpntargetmodeset_interface_pfnAddMode, display.dxgk_vidpntargetmodeset_interface_pfnaddmode, dxgk_vidpntargetmodeset_interface_pfnAddMode, dxgk_vidpntargetmodeset_interface_pfnAddMode callback function [Display Devices]
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - DXGKDDI_VIDPNTARGETMODESET_ADDMODE
 - d3dkmddi/DXGKDDI_VIDPNTARGETMODESET_ADDMODE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DXGKDDI_VIDPNTARGETMODESET_ADDMODE
product:
 - Windows
---

# DXGKDDI_VIDPNTARGETMODESET_ADDMODE callback function


## -description

The <b>pfnAddMode</b> function adds a VidPN target mode to a specified VidPN target mode set object.

## -parameters

### -param hVidPnTargetModeSet [in]

A handle to a VidPN target mode set object. The display miniport driver previously obtained this handle by calling the <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpn_acquiretargetmodeset">pfnAcquireTargetModeSet</a> function of the <a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_vidpn_interface">DXGK_VIDPN_INTERFACE</a> interface.

### -param pVidPnTargetModeInfo [in]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_target_mode">D3DKMDT_VIDPN_TARGET_MODE</a> structure that describes the target mode. The display miniport driver previously obtained this structure by calling <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpntargetmodeset_createnewmodeinfo">pfnCreateNewModeInfo</a>.

## -returns

The <b>pfnAddMode</b> function returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The function succeeded.|
|STATUS_GRAPHICS_INVALID_VIDPN_TARGETMODESET|The handle supplied in hVidPnTargetModeSet was invalid.|

## -remarks

To add a mode to a target mode set, the display miniport driver performs the following steps.

<ol>
<li>
Call <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpntargetmodeset_createnewmodeinfo">pfnCreateNewModeInfo</a> to obtain a pointer to a <a href="/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_target_mode">D3DKMDT_VIDPN_TARGET_MODE</a> structure. The <b>pnfCreateNewModeInfo</b> function allocates the structure and fills in the <b>Id</b> member with a newly generated target mode identifier.

</li>
<li>
The <b>Info</b> member of the D3DKMDT_VIDPN_TARGET_MODE structure is a <a href="/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_video_signal_info">D3DKMDT_VIDEO_SIGNAL_MODE</a> structure. Populate that structure with information about the mode.

</li>
<li>
Call <b>pfnAddMode</b> to add the mode to a target mode set.

</li>
</ol>
The VidPN manager allocates a D3DKMDT_VIDPN_TARGET_MODE structure when you call <b>pfnCreateNewModeInfo</b>. If you add the mode described by that structure to a target mode set, you do not need to explicitly release the structure; <b>pfnAddMode</b> releases it.

If you obtain a D3DKMDT_VIDPN_TARGET_MODE structure by calling <b>pfnCreateNewModeInfo</b> and then decide not to add that mode to a target mode set, you must explicity release the structure by calling <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpntargetmodeset_releasemodeinfo">pfnReleaseModeInfo</a>.

The D3DKMDT_HVIDPNTARGETMODESET data type is defined in <i>D3dkmdt.h</i>.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_vidpn_target_mode">D3DKMDT_VIDPN_TARGET_MODE</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpntargetmodeset_createnewmodeinfo">pfnCreateNewModeInfo</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpntargetmodeset_releasemodeinfo">pfnReleaseModeInfo</a>

