---
title: IDebugExpression2：： Abort |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugExpression2::Abort
helpviewer_keywords:
- IDebugExpression2::Abort
ms.assetid: 4fcb712e-1bdb-4b75-a440-35cc79ee147e
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 5de2e34a8ae1e038c2109627099dacc5bd03a1ac
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/02/2020
ms.locfileid: "80729769"
---
# <a name="idebugexpression2abort"></a>IDebugExpression2::Abort
這個方法會取消呼叫 [EvaluateAsync](../../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md) 方法所啟動的非同步運算式評估。

## <a name="syntax"></a>語法

```cpp
HRESULT Abort(
   void
);
```

```csharp
int Abort();
```

## <a name="return-value"></a>傳回值
 如果成功，則傳回， `S_OK` 否則傳回錯誤碼。

## <a name="remarks"></a>備註
 取消非同步運算式評估時，請勿將 [IDebugExpressionEvaluationCompleteEvent2](../../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2.md) 事件傳送至傳遞給 [附加](../../../extensibility/debugger/reference/idebugprogram2-attach.md) 或 [附加](../../../extensibility/debugger/reference/idebugengine2-attach.md) 方法的事件回呼。

## <a name="see-also"></a>另請參閱
- [IDebugExpression2](../../../extensibility/debugger/reference/idebugexpression2.md)
- [IDebugExpressionEvaluationCompleteEvent2](../../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2.md)
- [EvaluateAsync](../../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md)
