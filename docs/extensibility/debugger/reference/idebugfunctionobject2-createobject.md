---
title: IDebugFunctionObject2：： CreateObject |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugFunctionObject2::CreateObject
- CreateObject
ms.assetid: 148de615-941e-4b64-ab11-75b692aae465
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 6de1a30a032919a90fbb3d760837d5eeca00feaf
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/02/2020
ms.locfileid: "80728487"
---
# <a name="idebugfunctionobject2createobject"></a>IDebugFunctionObject2::CreateObject
建立物件，該物件會使用指定的評估旗標設定和超時值的函式。

## <a name="syntax"></a>語法

```cpp
HRESULT CreateObject (
   IDebugFunctionObject* pConstructor,
   DWORD                 dwArgs,
   IDebugObject*         pArgs[],
   DWORD                 dwEvalFlags,
   DWORD                 dwTimeout,
   IDebugObject**        ppObject
);
```

```csharp
int CreateObject (
   IDebugFunctionObject pConstructor,
   uint                 dwArgs,
   IDebugObject[]       pArgs,
   uint                 dwEvalFlags,
   uint                 dwTimeout,
   out IDebugObject**   ppObject
);
```

## <a name="parameters"></a>參數
`pConstructor`\
在 [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md) 物件，表示要建立之物件的函式。

`dwArgs`\
在陣列中的參數數目 `pArg` 。 代表傳遞至函式的參數數目。

`pArgs`\
在 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) 物件的陣列，表示傳遞至該函式的參數。

`dwEvalFlags`\
在 [EVALFLAGS](../../../extensibility/debugger/reference/evalflags.md) 列舉中的旗標組合，指定評估的執行方式。

`dwTimeout`\
在從這個方法傳回之前等候的最長時間（以毫秒為單位）。 使用 **無限** 期等候無限期等候。

`ppObject`\
擴展傳回代表新建立之物件的 **IDebugObject** 。

## <a name="return-value"></a>傳回值
 如果成功，則傳回， `S_OK` 否則傳回錯誤碼。

## <a name="remarks"></a>備註
 呼叫這個方法來建立物件，該物件代表類別的實例，或其他需要函式的複雜型別（也就是參數）。

## <a name="see-also"></a>另請參閱
- [IDebugFunctionObject2](../../../extensibility/debugger/reference/idebugfunctionobject2.md)
