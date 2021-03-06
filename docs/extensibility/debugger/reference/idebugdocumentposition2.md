---
title: IDebugDocumentPosition2 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugDocumentPosition2
helpviewer_keywords:
- IDebugDocumentPosition2 interface
ms.assetid: 0e838ced-12bb-4efc-b811-2b7c034b77b0
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 63742f220d5a776fca180a3f9f7fe9c15e04c66a
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/02/2020
ms.locfileid: "80731645"
---
# <a name="idebugdocumentposition2"></a>IDebugDocumentPosition2
此介面代表原始程式檔中的抽象位置。

## <a name="syntax"></a>語法

```
IDebugDocumentPosition2 : IUnknown
```

## <a name="notes-for-implementers"></a>實施者的注意事項
 Visual Studio 通常會執行這個介面。 如果它必須提供自己的原始程式碼 (（如同 DE [IDebugDocument2](../../../extensibility/debugger/reference/idebugdocument2.md) 介面) 時），則 debug ENGINE (DE) 也會執行這個介面。

## <a name="notes-for-callers"></a>呼叫者注意事項
 這個介面會傳入做為 [EnumCodeCoNtexts](../../../extensibility/debugger/reference/idebugprogram2-enumcodecontexts.md)的引數。 它也會當做[BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md)聯集的一部分來提供， (明確地說，它是[BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md)結構的一部分[BP_LOCATION_CODE_FILE_LINE](../../../extensibility/debugger/reference/bp-location-code-file-line.md)) 結構，可用於建立暫止中斷點。

## <a name="methods-in-vtable-order"></a>依照 Vtable 順序的方法
 下表顯示的方法 `IDebugDocumentPosition2` 。

|方法|描述|
|------------|-----------------|
|[GetFileName](../../../extensibility/debugger/reference/idebugdocumentposition2-getfilename.md)|取得包含此檔位置之原始程式檔的檔案名。|
|[GetDocument](../../../extensibility/debugger/reference/idebugdocumentposition2-getdocument.md)|取得包含的檔。|
|[IsPositionInDocument](../../../extensibility/debugger/reference/idebugdocumentposition2-ispositionindocument.md)|判斷此位置是否包含在指定的檔中。|
|[GetRange](../../../extensibility/debugger/reference/idebugdocumentposition2-getrange.md)|取得此檔位置的範圍。|

## <a name="requirements"></a>需求
 標頭： msdbg。h

 命名空間： VisualStudio

 元件： Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>另請參閱
- [EnumCodeContexts](../../../extensibility/debugger/reference/idebugprogram2-enumcodecontexts.md)
- [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)
- [BP_LOCATION_CODE_FILE_LINE](../../../extensibility/debugger/reference/bp-location-code-file-line.md)
