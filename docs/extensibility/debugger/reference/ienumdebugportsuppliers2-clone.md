---
title: IEnumDebugPortSuppliers2：： Clone |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumDebugPortSuppliers2::Clone
helpviewer_keywords:
- IEnumDebugPortSuppliers2::Clone
ms.assetid: 98b9914d-4f32-44da-b422-68830bce44b4
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: bc6dc6c055f9821c9c7f02312762d3dd0a44bc58
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/02/2020
ms.locfileid: "80716091"
---
# <a name="ienumdebugportsuppliers2clone"></a>IEnumDebugPortSuppliers2::Clone
傳回目前列舉的複本作為個別的物件。

## <a name="syntax"></a>語法

```cpp
HRESULT Clone(
   IEnumDebugPortSuppliers2** ppEnum
);
```

```csharp
int Clone(
   out IEnumDebugPortSuppliers2 ppEnum
);
```

## <a name="parameters"></a>參數
`ppEnum`\
擴展傳回這個列舉的複本作為個別的物件。

## <a name="return-value"></a>傳回值
 如果成功，則傳回， `S_OK` 否則傳回錯誤碼。

## <a name="remarks"></a>備註
 列舉的複本在呼叫這個方法時，的狀態與原始的相同。 不過，複本和原始的狀態是分開的，而且可以個別變更。

## <a name="see-also"></a>另請參閱
- [IEnumDebugPortSuppliers2](../../../extensibility/debugger/reference/ienumdebugportsuppliers2.md)
