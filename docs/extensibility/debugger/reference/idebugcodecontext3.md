---
title: IDebugCodeCoNtext3 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugCodeContext3 interface
ms.assetid: 524eb882-0ad5-4bfb-95eb-eb3abb3d0237
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: e3f81168d9af7fbbb93b5c59f3ab19a17107b56b
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/02/2020
ms.locfileid: "80734183"
---
# <a name="idebugcodecontext3"></a>IDebugCodeContext3
擴充 [IDebugCodeCoNtext2](../../../extensibility/debugger/reference/idebugcodecontext2.md) 介面，以啟用模組和進程介面的抓取。

## <a name="syntax"></a>語法

```
IDebugCodeContext3 : IDebugCodeContext2
```

## <a name="notes-for-implementers"></a>實施者的注意事項
 由 debug 引擎所執行，並由 [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] debug 封裝使用。

## <a name="methods"></a>方法
 除了介面上的方法 `IDebugCodeContext2` ，這個介面也會執行下列方法：

|方法|描述|
|------------|-----------------|
|[GetModule](../../../extensibility/debugger/reference/idebugcodecontext3-getmodule.md)|抓取 debug 模組的介面參考。|
|[GetProcess](../../../extensibility/debugger/reference/idebugcodecontext3-getprocess.md)|抓取對 debug 進程介面的參考。|

## <a name="remarks"></a>備註
 這是選擇性的介面，通常不需要執行。

## <a name="requirements"></a>需求
 標頭： Msdbg。h

 命名空間： VisualStudio

 元件： Microsoft.VisualStudio.Debugger.Interop.dll
