---
title: IEnumDebugPortSuppliers2：： Reset |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumDebugPortSuppliers2::Next
helpviewer_keywords:
- IEnumDebugPortSuppliers2::Next
ms.assetid: f69cbacf-da9d-4b22-b8a2-abd9b8c131f2
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: d7d5a376a8478fc2254e354085a4b25349317f84
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/02/2020
ms.locfileid: "80715968"
---
# <a name="ienumdebugportsuppliers2reset"></a>IEnumDebugPortSuppliers2::Reset
將列舉重設為第一個元素。

## <a name="syntax"></a>語法

```cpp
HRESULT Reset(
   void
);
```

```csharp
int Reset();
```

## <a name="return-value"></a>傳回值
 如果成功，則傳回， `S_OK` 否則傳回錯誤碼。

## <a name="remarks"></a>備註
 呼叫這個方法之後，下一次呼叫 [next](../../../extensibility/debugger/reference/ienumdebugportsuppliers2-next.md) 方法會傳回列舉的第一個元素。

## <a name="see-also"></a>另請參閱
- [IEnumDebugPortSuppliers2](../../../extensibility/debugger/reference/ienumdebugportsuppliers2.md)
