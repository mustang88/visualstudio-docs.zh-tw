---
title: IDebugProperty3：:D estroyObjectID |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProperty3::DestroyObjectID
helpviewer_keywords:
- IDebugProperty3::DestroyObjectID
ms.assetid: bd08f356-cc67-4717-98c9-c3d00cad2040
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: f465bc06712c5032c6e90288ebd02406de4f2330
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/02/2020
ms.locfileid: "80721189"
---
# <a name="idebugproperty3destroyobjectid"></a>IDebugProperty3::DestroyObjectID
終結與這個屬性相關聯的唯一識別碼，表示呼叫端不再在意從所有其他屬性唯一識別此屬性。

## <a name="syntax"></a>語法

```cpp
HRESULT DestroyObjectID(
   void
);
```

```csharp
int DestroyObjectID();
```

## <a name="return-value"></a>傳回值
 如果成功，則傳回， `S_OK` 否則傳回錯誤碼。

## <a name="remarks"></a>備註
 如果 debug engine 不需要支援屬性 (的唯一識別碼，因為它已經在) 內部追蹤它們，所以它可以直接 `E_NOTIMPL` 針對此方法傳回。

 當呼叫端想要確保在所有其他屬性中唯一識別這個屬性時，會使用 [CreateObjectID](../../../extensibility/debugger/reference/idebugproperty3-createobjectid.md) 方法的呼叫來建立唯一識別碼。

## <a name="see-also"></a>另請參閱
- [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md)
- [CreateObjectID](../../../extensibility/debugger/reference/idebugproperty3-createobjectid.md)
