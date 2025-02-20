---
UID: NF:ntifs.CcFastCopyRead
title: CcFastCopyRead function (ntifs.h)
description: The CcFastCopyRead routine performs a fast copy read from a cached file to a buffer in memory.
old-location: ifsk\ccfastcopyread.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["CcFastCopyRead function"]
ms.keywords: CcFastCopyRead, CcFastCopyRead routine [Installable File System Drivers], ccref_7198ef60-5199-4597-9809-ddacc59e6223.xml, ifsk.ccfastcopyread, ntifs/CcFastCopyRead
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: 
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
req.irql: < DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - CcFastCopyRead
 - ntifs/CcFastCopyRead
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - CcFastCopyRead
---

# CcFastCopyRead function


## -description

The <b>CcFastCopyRead</b> routine performs a fast copy read from a cached file to a buffer in memory.

## -parameters

### -param FileObject [in]


Pointer to a file object for the cached file from which the data is to be read.

### -param FileOffset [in]


Starting byte offset within the cached file.

### -param Length [in]


Length in bytes of the data to be read.

### -param PageCount [in]


Number of pages spanned by the read.

### -param Buffer [out]


Pointer to a buffer into which the data is to be copied.

### -param IoStatus [out]


Pointer to a structure that receives the final completion status and information about the operation. If not all of the data is copied successfully, <i>IoStatus.Information</i> contains the actual number of bytes that were copied.

## -remarks

<b>CcFastCopyRead</b> is a faster version of <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-cccopyread">CcCopyRead</a>. It differs from <b>CcCopyRead</b> in the following respects:

<ul>
<li>
<i>FileOffset</i> is a ULONG, not a PLARGE_INTEGER.

</li>
<li>
There is no <i>Wait</i> parameter. The caller must be able to enter a wait state until all the data has been copied.

</li>
<li>
<b>CcFastCopyRead</b> does not return a BOOLEAN to indicate whether the read operation was successful.

</li>
</ul>
<i>FileOffset</i> plus <i>Length</i> must be less than or equal to the size of the cached file, or an assertion failure will occur.

If any failure occurs, <b>CcFastCopyRead</b> raises a status exception for that particular failure. For example, if a pool allocation failure occurs, <b>CcFastCopyRead</b> raises a STATUS_INSUFFICIENT_RESOURCES exception; if an I/O error occurs, <b>CcFastCopyRead</b> raises the status exception of the I/O error. Therefore, to gain control if a failure occurs, the driver should wrap the call to <b>CcFastCopyRead</b> in a <b>try-except</b> or <b>try-finally</b> statement.

To cache a file, use <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccinitializecachemap">CcInitializeCacheMap</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-cccopyread">CcCopyRead</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccinitializecachemap">CcInitializeCacheMap</a>



<a href="/previous-versions/ff539191(v=vs.85)">CcReadAhead</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccschedulereadahead">CcScheduleReadAhead</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccsetadditionalcacheattributes">CcSetAdditionalCacheAttributes</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccsetreadaheadgranularity">CcSetReadAheadGranularity</a>
