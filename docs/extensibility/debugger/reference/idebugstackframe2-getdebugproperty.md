---
title: IDebugStackFrame2：： GetDebugProperty |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugStackFrame2::GetDebugProperty
helpviewer_keywords:
- IDebugStackFrame2::GetDebugProperty
ms.assetid: 02c2fa04-1424-4bca-9936-feaecd2afab6
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: aa98107ada265d232647d27b4050b507d4581df7
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/02/2020
ms.locfileid: "80719791"
---
# <a name="idebugstackframe2getdebugproperty"></a>IDebugStackFrame2::GetDebugProperty
取得堆疊框架屬性的描述。

## <a name="syntax"></a>語法

```cpp
HRESULT GetDebugProperty ( 
   IDebugProperty2** ppDebugProp
);
```

```csharp
int GetDebugProperty ( 
   out IDebugProperty2 ppDebugProp
);
```

## <a name="parameters"></a>參數
`ppDebugProp`\
擴展傳回 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) 物件，這個物件會描述這個堆疊框架的屬性。

## <a name="return-value"></a>傳回值
 如果成功，則傳回， `S_OK` 否則傳回錯誤碼。

## <a name="remarks"></a>備註
 使用適當的篩選準則呼叫 [EnumChildren](../../../extensibility/debugger/reference/idebugproperty2-enumchildren.md) 方法，可以抓取與堆疊框架相關聯的區域變數、方法參數、暫存器和 "this" 指標。

## <a name="see-also"></a>另請參閱
- [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)
- [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)
