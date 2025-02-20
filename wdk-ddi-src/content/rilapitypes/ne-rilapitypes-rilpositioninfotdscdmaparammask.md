---
UID: NE:rilapitypes.RILPOSITIONINFOTDSCDMAPARAMMASK
title: RILPOSITIONINFOTDSCDMAPARAMMASK (rilapitypes.h)
description: "Microsoft reserves the RILPOSITIONINFOTDSCDMAPARAMMASK enumeration for internal use only. Don't use this enumeration in your code."
old-location: netvista\rilpositioninfotdscdmaparammask_2.htm
tech.root: netvista
ms.date: 02/26/2018
keywords: ["RILPOSITIONINFOTDSCDMAPARAMMASK enumeration"]
ms.keywords: RILPOSITIONINFOTDSCDMAPARAMMASK, RILPOSITIONINFOTDSCDMAPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_POSITION_TDSCDMA_ALL, RIL_PARAM_POSITION_TDSCDMA_CELLID, RIL_PARAM_POSITION_TDSCDMA_CELLPARAM, RIL_PARAM_POSITION_TDSCDMA_LAC, RIL_PARAM_POSITION_TDSCDMA_MNC, RIL_PARAM_POSITION_TDSCDMA_PATHLOSS, RIL_PARAM_POSITION_TDSCDMA_RSCP, RIL_PARAM_POSITION_TDSCDMA_TA, RIL_PARAM_POSITION_TDSCDMA_UARFCN, netvista.rilpositioninfotdscdmaparammask_2, rilapitypes/RILPOSITIONINFOTDSCDMAPARAMMASK, rilapitypes/RIL_PARAM_POSITION_TDSCDMA_ALL, rilapitypes/RIL_PARAM_POSITION_TDSCDMA_CELLID, rilapitypes/RIL_PARAM_POSITION_TDSCDMA_CELLPARAM, rilapitypes/RIL_PARAM_POSITION_TDSCDMA_LAC, rilapitypes/RIL_PARAM_POSITION_TDSCDMA_MNC, rilapitypes/RIL_PARAM_POSITION_TDSCDMA_PATHLOSS, rilapitypes/RIL_PARAM_POSITION_TDSCDMA_RSCP, rilapitypes/RIL_PARAM_POSITION_TDSCDMA_TA, rilapitypes/RIL_PARAM_POSITION_TDSCDMA_UARFCN
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
targetos: Windows
req.typenames: RILPOSITIONINFOTDSCDMAPARAMMASK
req.product: Windows 10 or later.
f1_keywords:
 - RILPOSITIONINFOTDSCDMAPARAMMASK
 - rilapitypes/RILPOSITIONINFOTDSCDMAPARAMMASK
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - rilapitypes.h
api_name:
 - RILPOSITIONINFOTDSCDMAPARAMMASK
---

# RILPOSITIONINFOTDSCDMAPARAMMASK enumeration (rilapitypes.h)


## -description

This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## -enum-fields

### -field RIL_PARAM_POSITION_TDSCDMA_MCC

### -field RIL_PARAM_POSITION_TDSCDMA_MNC

### -field RIL_PARAM_POSITION_TDSCDMA_LAC

### -field RIL_PARAM_POSITION_TDSCDMA_CELLID

### -field RIL_PARAM_POSITION_TDSCDMA_UARFCN

### -field RIL_PARAM_POSITION_TDSCDMA_CELLPARAM

### -field RIL_PARAM_POSITION_TDSCDMA_TA

### -field RIL_PARAM_POSITION_TDSCDMA_RSCP

### -field RIL_PARAM_POSITION_TDSCDMA_PATHLOSS

### -field RIL_PARAM_POSITION_TDSCDMA_ALL

## -syntax

```cpp
typedef enum _RILPOSITIONINFOTDSCDMAPARAMMASK {
  RIL_PARAM_POSITION_TDSCDMA_MNC,
  RIL_PARAM_POSITION_TDSCDMA_LAC,
  RIL_PARAM_POSITION_TDSCDMA_CELLID,
  RIL_PARAM_POSITION_TDSCDMA_UARFCN,
  RIL_PARAM_POSITION_TDSCDMA_CELLPARAM,
  RIL_PARAM_POSITION_TDSCDMA_TA,
  RIL_PARAM_POSITION_TDSCDMA_RSCP,
  RIL_PARAM_POSITION_TDSCDMA_PATHLOSS,
  RIL_PARAM_POSITION_TDSCDMA_ALL
} RILPOSITIONINFOTDSCDMAPARAMMASK;
```

