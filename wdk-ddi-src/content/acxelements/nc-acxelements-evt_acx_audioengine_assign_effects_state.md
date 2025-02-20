---
UID: NC:acxelements.EVT_ACX_AUDIOENGINE_ASSIGN_EFFECTS_STATE
tech.root: audio 
title: EVT_ACX_AUDIOENGINE_ASSIGN_EFFECTS_STATE
ms.date: 04/29/2022
targetos: Windows
description: The EVT_ACX_AUDIOENGINE_ASSIGN_EFFECTS_STATE callback function is implemented by the driver and is called when the global effects state is set for an audio engine node. 
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxelements.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - acxelements.h
api_name:
 - EVT_ACX_AUDIOENGINE_ASSIGN_EFFECTS_STATE
f1_keywords:
 - EVT_ACX_AUDIOENGINE_ASSIGN_EFFECTS_STATE
 - acxelements/EVT_ACX_AUDIOENGINE_ASSIGN_EFFECTS_STATE
dev_langs:
 - c++
---

## -description

The **EVT_ACX_AUDIOENGINE_ASSIGN_EFFECTS_STATE** callback function is implemented by the driver and is called when the global effects state is set for an audio engine node. The global effects state can be set to TRUE or FALSE, where TRUE indicates that global effect processing in the audio engine node is enabled and FALSE indicates that global effect processing in the audio engine node is disabled. 

## -parameters

### -param AudioEngine

An ACXAUDIOENGINE object that is used in a render circuit to represent a DSP. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param State

The State value is of type ULONG but gets converted to type BOOLEAN in the callback to indicate whether global effect processing in the audio engine node is enabled. A value of TRUE indicates that processing is enabled. FALSE indicates that it is disabled.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

Example usage is shown below.

```cpp
typedef struct _DSP_ENGINE_CONTEXT
{
    ACXDATAFORMAT MixFormat;
    BOOLEAN GFxEnabled;
} DSP_ENGINE_CONTEXT, *PDSP_ENGINE_CONTEXT;

WDF_DECLARE_CONTEXT_TYPE_WITH_NAME(DSP_ENGINE_CONTEXT, GetDspEngineContext)

EVT_ACX_AUDIOENGINE_ASSIGN_EFFECTS_STATE        DspR_EvtAcxAudioEngineAssignEffectsState;

NTSTATUS
DspR_EvtAcxAudioEngineAssignEffectsState(
    ACXAUDIOENGINE  AudioEngine,
    ULONG           State
)
{
    PAGED_CODE();
    
    PDSP_ENGINE_CONTEXT   pAudioEngineCtx;
    pAudioEngineCtx = GetDspEngineContext(AudioEngine);

    pAudioEngineCtx->GFxEnabled = (BOOLEAN)State;

    return STATUS_SUCCESS;
}
```
## -see-also

- [acxelements.h header](index.md)

