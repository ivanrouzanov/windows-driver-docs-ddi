---
UID: NS:rilapitypes.RILPOSITIONINFOLTE
title: RILPOSITIONINFOLTE (rilapitypes.h)
description: "Microsoft reserves the RILPOSITIONINFOLTE structure for internal use only. Don't use this structure in your code."
old-location: netvista\rilpositioninfolte_2.htm
tech.root: netvista
ms.date: 02/26/2018
keywords: ["RILPOSITIONINFOLTE structure"]
ms.keywords: "*LPRILPOSITIONINFOLTE, RILPOSITIONINFOLTE, RILPOSITIONINFOLTE structure [Network Drivers Starting with Windows Vista], netvista.rilpositioninfolte_2, rilapitypes/RILPOSITIONINFOLTE"
req.header: rilapitypes.h
req.include-header: 
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: RILPOSITIONINFOLTE, *LPRILPOSITIONINFOLTE
req.product: Windows 10 or later.
f1_keywords:
 - RILPOSITIONINFOLTE
 - rilapitypes/RILPOSITIONINFOLTE
 - LPRILPOSITIONINFOLTE
 - rilapitypes/LPRILPOSITIONINFOLTE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - rilapitypes.h
api_name:
 - RILPOSITIONINFOLTE
 - LPRILPOSITIONINFOLTE
---

# RILPOSITIONINFOLTE structure (rilapitypes.h)


## -description

This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## -struct-fields

### -field dwParams

### -field dwMobileCountryCode

### -field dwMobileNetworkCode

### -field dwCellID

### -field dwEARFCN

### -field dwPhysCellID

### -field dwTAC

### -field dwRSRP

### -field dwRSRQ

### -field dwTimingAdvance

## -syntax

```cpp
typedef struct _RILPOSITIONINFOLTE {
  DWORD  dwParams;
  DWORD  dwMobileCountryCode;
  DWORD  dwMobileNetworkCode;
  DWORD  dwCellID;
  DWORD  dwEARFCN;
  DWORD  dwPhysCellID;
  DWORD  dwTAC;
  LONG   dwRSRP;
  LONG   dwRSRQ;
  DWORD  dwTimingAdvance;
} RILPOSITIONINFOLTE, RILPOSITIONINFOLTE;
```

