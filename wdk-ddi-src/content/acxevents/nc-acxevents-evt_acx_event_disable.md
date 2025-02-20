---
UID: NC:acxevents.EVT_ACX_EVENT_DISABLE
tech.root: audio
title: EVT_ACX_EVENT_DISABLE
ms.date: 06/22/2022
targetos: Windows
description: The EVT_ACX_EVENT_DISABLE callback is used by the driver to disable the ACXEVENT source.
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxevents.h
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
 - acxevents.h
api_name:
 - EVT_ACX_EVENT_DISABLE
f1_keywords:
 - EVT_ACX_EVENT_DISABLE
 - acxevents/EVT_ACX_EVENT_DISABLE
dev_langs:
 - c++
---

## -description

The **EVT_ACX_EVENT_DISABLE** callback is used by the driver to disable the ACXEVENT source.

## -parameters

### -param Event

The ACXEVENT object (described in [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects)).

## -remarks

### Example

This sample shows the use of the EVT_ACX_EVENT_DISABLE callback.

```cpp
    //
    // Add enable/disable callbacks for this element.
    //
    ACX_EVENT_CALLBACKS_INIT(&eventCallbacks);
    eventCallbacks.EvtAcxEventEnable = &TestElement::EvtEventEnableCallback; 
    eventCallbacks.EvtAcxEventDisable = &TestElement::EvtEventDisableCallback;

    ACX_EVENT_CONFIG_INIT(&eventCfg);

NTSTATUS
TestElement::EvtEventDisableCallback(
    _In_ ACXEVENT Event
    )
{
    TEST_EVENT_CONTEXT * eventCtx;
    TestElement * This;
    
    PAGED_CODE();

    eventCtx = GetTestEventContext(Event);
    ASSERT(eventCtx != NULL);
    ASSERT(eventCtx->TestElement != NULL);

    This = eventCtx->TestElement;

    // Add code to disable event source.    

    return STATUS_SUCCESS;
}
```

## -see-also

- [acxevents.h header](index.md)

