---
UID: NF:ntifs.CcRemapBcb
title: CcRemapBcb function (ntifs.h)
description: The CcRemapBcb routine maps a buffer control block (BCB) an additional time to preserve it through several calls that perform additional maps and unpins.
old-location: ifsk\ccremapbcb.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["CcRemapBcb function"]
ms.keywords: CcRemapBcb, CcRemapBcb routine [Installable File System Drivers], ccref_64bd8036-ecdd-48bd-8894-fea7f28cc3be.xml, ifsk.ccremapbcb, ntifs/CcRemapBcb
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available on Microsoft Windows 2000 and later.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - CcRemapBcb
 - ntifs/CcRemapBcb
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - CcRemapBcb
---

# CcRemapBcb function


## -description

The <b>CcRemapBcb</b> routine maps a buffer control block (BCB) an additional time to preserve it through several calls that perform additional maps and unpins.

## -parameters

### -param Bcb [in]


Pointer to the BCB to be remapped.

## -returns

<b>CcRemapBcb</b> returns a pointer to the remapped BCB with a read-only indicator.

## -remarks

Like <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccmapdata">CcMapData</a>, <b>CcRemapBcb</b> maps data in a cached file for read access. Note that after <b>CcRemapBcb</b> is called, the data is mapped; but it is not pinned. This distinction is important. Data that is mapped but not pinned cannot safely be modified. To pin the data, use <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccpinmappeddata">CcPinMappedData</a>, <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccpinread">CcPinRead</a>, or <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccpreparepinwrite">CcPreparePinWrite</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccmapdata">CcMapData</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccpinmappeddata">CcPinMappedData</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccpinread">CcPinRead</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccpreparepinwrite">CcPreparePinWrite</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccunpindata">CcUnpinData</a>
