---
title: IDebugClassField：： EnumNestedEnums |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugClassField::EnumNestedEnums
helpviewer_keywords:
- IDebugClassField::EnumNestedEnums method
ms.assetid: 90fd0cef-9145-4de6-91d4-6c881df39d6e
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 38ee3ccd1ffd3130bc918da18c631cf08683f064
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/02/2020
ms.locfileid: "80734403"
---
# <a name="idebugclassfieldenumnestedenums"></a>IDebugClassField::EnumNestedEnums
建立此類別之嵌套列舉值的枚舉器。

## <a name="syntax"></a>語法

```cpp
HRESULT EnumNestedEnums(
    IEnumDebugFields** ppEnum
);
```

```csharp
int EnumNestedEnums(
    out IEnumDebugFields ppEnum
);
```

## <a name="parameters"></a>參數
`ppEnum`\
擴展傳回代表嵌套列舉清單的 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) 物件。 如果沒有任何嵌套列舉，則會傳回 null 值。

## <a name="return-value"></a>傳回值
如果成功，會傳回 S_OK，或如果沒有任何嵌套列舉值，則傳回 S_FALSE。 否則會傳回錯誤碼。

## <a name="remarks"></a>備註
列舉的每個元素都是描述嵌套列舉的 [IDebugEnumField](../../../extensibility/debugger/reference/idebugenumfield.md) 物件。

在類別內宣告的列舉會被視為嵌套列舉。 例如，假設：

```
class RootClass {
    enum NestedEnum { EnumValue = 0 }
};
```

`EnumNestedEnums`方法會傳回[IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)物件，其中包含代表列舉的一個[IDebugEnumField](../../../extensibility/debugger/reference/idebugenumfield.md)物件 `NestedEnum` 。

## <a name="see-also"></a>另請參閱
- [IDebugClassField](../../../extensibility/debugger/reference/idebugclassfield.md)
- [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)
- [IDebugEnumField](../../../extensibility/debugger/reference/idebugenumfield.md)
