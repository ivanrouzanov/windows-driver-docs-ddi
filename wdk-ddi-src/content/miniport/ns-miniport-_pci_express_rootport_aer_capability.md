---
UID: NS:miniport._PCI_EXPRESS_ROOTPORT_AER_CAPABILITY
title: PCI_EXPRESS_ROOTPORT_AER_CAPABILITY (miniport.h)
description: The _PCI_EXPRESS_ROOTPORT_AER_CAPABILITY structure (miniport.h) describes a PCI Express (PCIe) advanced error reporting capability structure.
old-location: pci\pci_express_rootport_aer_capability.htm
tech.root: PCI
ms.date: 01/09/2022
keywords: ["PCI_EXPRESS_ROOTPORT_AER_CAPABILITY structure"]
ms.keywords: "*PPCI_EXPRESS_ROOTPORT_AER_CAPABILITY, PCI.pci_express_rootport_aer_capability, PCI_EXPRESS_ROOTPORT_AER_CAPABILITY, PCI_EXPRESS_ROOTPORT_AER_CAPABILITY structure [Buses], PPCI_EXPRESS_ROOTPORT_AER_CAPABILITY, PPCI_EXPRESS_ROOTPORT_AER_CAPABILITY structure pointer [Buses], _PCI_EXPRESS_ROOTPORT_AER_CAPABILITY, pci_struct_f65551d3-2213-468e-aa94-508b29c11844.xml, wdm/PCI_EXPRESS_ROOTPORT_AER_CAPABILITY, wdm/PPCI_EXPRESS_ROOTPORT_AER_CAPABILITY"
req.header: miniport.h
req.include-header: Ntddk.h, Wdm.h, Miniport.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: Windows Server 2008
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
req.irql: Any level (see Remarks section)
targetos: Windows
req.typenames: PCI_EXPRESS_ROOTPORT_AER_CAPABILITY, *PPCI_EXPRESS_ROOTPORT_AER_CAPABILITY
f1_keywords:
 - _PCI_EXPRESS_ROOTPORT_AER_CAPABILITY
 - miniport/_PCI_EXPRESS_ROOTPORT_AER_CAPABILITY
 - PPCI_EXPRESS_ROOTPORT_AER_CAPABILITY
 - miniport/PPCI_EXPRESS_ROOTPORT_AER_CAPABILITY
 - PCI_EXPRESS_ROOTPORT_AER_CAPABILITY
 - miniport/PCI_EXPRESS_ROOTPORT_AER_CAPABILITY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _PCI_EXPRESS_ROOTPORT_AER_CAPABILITY
 - PPCI_EXPRESS_ROOTPORT_AER_CAPABILITY
 - PCI_EXPRESS_ROOTPORT_AER_CAPABILITY
---

# PCI_EXPRESS_ROOTPORT_AER_CAPABILITY structure (miniport.h)

## -description

The **PCI_EXPRESS_ROOTPORT_AER_CAPABILITY** structure describes a PCI Express (PCIe) advanced error reporting capability structure for a root port or a root complex event collector.

## -struct-fields

### -field Header

A [**PCI_EXPRESS_ENHANCED_CAPABILITY_HEADER**](../wdm/ns-wdm-_pci_express_enhanced_capability_header.md) structure that describes the header for this structure.

### -field UncorrectableErrorStatus

A [**PCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS**](../wdm/ns-wdm-_pci_express_uncorrectable_error_status.md) structure that describes the PCIe uncorrectable error status register of the PCIe AER capability structure.

### -field UncorrectableErrorMask

A [**PCI_EXPRESS_UNCORRECTABLE_ERROR_MASK**](../wdm/ns-wdm-_pci_express_uncorrectable_error_mask.md) structure that describes the PCIe uncorrectable error mask register of the PCIe AER capability structure.

### -field UncorrectableErrorSeverity

A [**PCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY**](../wdm/ns-wdm-_pci_express_uncorrectable_error_severity.md) structure that describes the PCIe uncorrectable error severity register of the PCIe AER capability structure.

### -field CorrectableErrorStatus

A [**PCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS**](../wdm/ns-wdm-_pci_express_uncorrectable_error_status.md) structure that describes the PCIe uncorrectable error status register of the PCIe AER capability structure.

### -field CorrectableErrorMask

A [**PCI_EXPRESS_UNCORRECTABLE_ERROR_MASK**](../wdm/ns-wdm-_pci_express_uncorrectable_error_mask.md) structure that describes the PCIe uncorrectable error mask register of the PCIe AER capability structure.

### -field CapabilitiesAndControl

A [**PCI_EXPRESS_AER_CAPABILITIES**](../wdm/ns-wdm-_pci_express_aer_capabilities.md) structure that describes the PCIe advanced error capabilities and control register of the PCIe AER capability structure.

### -field HeaderLog

An array of four 32-bit values that together contain the header for the transaction layer packet (TLP) that corresponds to a detected error.

> [!NOTE]
>
> Within each 32-bit value in the array, the bytes of the TLP are in big-endian byte order.

### -field RootErrorCommand

A [**PCI_EXPRESS_ROOT_ERROR_COMMAND**](../wdm/ns-wdm-_pci_express_root_error_command.md) structure that describes the PCIe root error command register of the PCIe AER capability structure.

### -field RootErrorStatus

A [**PCI_EXPRESS_ROOT_ERROR_STATUS**](../wdm/ns-wdm-_pci_express_root_error_status.md) structure that describes the PCIe root error status register of the PCIe AER capability structure.

### -field ErrorSourceId

A [**PCI_EXPRESS_ERROR_SOURCE_ID**](../wdm/ns-wdm-_pci_express_error_source_id.md) structure that describes the PCIe error source identification register of the PCIe AER capability structure.

## -remarks

PCIe bridge devices use the [**PCI_EXPRESS_BRIDGE_AER_CAPABILITY**](../wdm/ns-wdm-_pci_express_bridge_aer_capability.md) structure instead of the PCI_EXPRESS_ROOTPORT_AER_CAPABILITY structure to describe the PCIe advanced error reporting capability structure.

All other PCIe devices and ports that are not root ports or root complex event collectors use the [**PCI_EXPRESS_AER_CAPABILITY**](../wdm/ns-wdm-_pci_express_aer_capability.md) structure instead of the PCI_EXPRESS_ROOTPORT_AER_CAPABILITY structure to describe the PCIe advanced error reporting capability structure.

For additional information about the PCIe advanced error reporting capability structure, see the [PCI Express Specification](https://pcisig.com/specifications/pciexpress).

## -see-also

[**PCI_EXPRESS_CORRECTABLE_ERROR_STATUS**](../wdm/ns-wdm-_pci_express_correctable_error_status.md)

[**PCI_EXPRESS_UNCORRECTABLE_ERROR_SEVERITY**](../wdm/ns-wdm-_pci_express_uncorrectable_error_severity.md)

[**PCI_EXPRESS_ROOT_ERROR_STATUS**](../wdm/ns-wdm-_pci_express_root_error_status.md)

[**PCI_EXPRESS_UNCORRECTABLE_ERROR_MASK**](../wdm/ns-wdm-_pci_express_uncorrectable_error_mask.md)

[**PCI_EXPRESS_ROOT_ERROR_COMMAND**](../wdm/ns-wdm-_pci_express_root_error_command.md)

[**PCI_EXPRESS_AER_CAPABILITY**](../wdm/ns-wdm-_pci_express_aer_capability.md)

[**PCI_EXPRESS_AER_CAPABILITIES**](../wdm/ns-wdm-_pci_express_aer_capabilities.md)

[**PCI_EXPRESS_ENHANCED_CAPABILITY_HEADER**](../wdm/ns-wdm-_pci_express_enhanced_capability_header.md)

[**PCI_EXPRESS_BRIDGE_AER_CAPABILITY**](../wdm/ns-wdm-_pci_express_bridge_aer_capability.md)

[**PCI_EXPRESS_UNCORRECTABLE_ERROR_STATUS**](../wdm/ns-wdm-_pci_express_uncorrectable_error_status.md)

[**PCI_EXPRESS_ERROR_SOURCE_ID**](../wdm/ns-wdm-_pci_express_error_source_id.md)

[**PCI_EXPRESS_CORRECTABLE_ERROR_MASK**](../wdm/ns-wdm-_pci_express_correctable_error_mask.md)
