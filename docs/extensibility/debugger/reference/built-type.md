---
title: BUILT_TYPE |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- BUILT_TYPE
helpviewer_keywords:
- BUILT_TYPE structure
ms.assetid: cc02c32c-0f65-4210-ad25-a9b1899066e8
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 885f17b0841a39672c87be5bc7c947b2e0d9c7e0
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/02/2020
ms.locfileid: "80737692"
---
# <a name="built_type"></a>BUILT_TYPE
此結構會指定取自中繼資料之欄位類型的相關資訊。

## <a name="syntax"></a>語法

```cpp
typedef struct _tagTYPE_BUILT {
    ULONG32      ulAppDomainID;
    GUID         guidModule;
    IDebugField* pUnderlyingField;
} BUILT_TYPE;
```

```csharp
public struct BUILT_TYPE {
    public uint        ulAppDomainID;
    public Guid        guidModule;
    public IDebugField pUnderlyingField;
};
```

## <a name="members"></a>成員
`ulAppDomainID`\
符號的來源應用程式識別碼。 這是用來唯一識別應用程式的實例。

`guidModule`\
包含此欄位之模組的 GUID。

`pUnderlyingField`\
[IDebugField](../../../extensibility/debugger/reference/idebugfield.md)物件，識別與這個內建欄位相關聯的基礎欄位。

## <a name="remarks"></a>備註
當結構的[TYPE_INFO](../../../extensibility/debugger/reference/type-info.md) `dwKind` 欄位 `TYPE_INFO` 設定為 `TYPE_KIND_BUILT` ([dwTYPE_KIND](../../../extensibility/debugger/reference/dwtype-kind.md)列舉) 中的值時，這個結構會顯示為 TYPE_INFO 結構中聯集的一部分。

## <a name="requirements"></a>需求
標頭： sh. h

命名空間： VisualStudio

元件： Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>另請參閱
- [Structures and Unions](../../../extensibility/debugger/reference/structures-and-unions.md)
- [TYPE_INFO](../../../extensibility/debugger/reference/type-info.md)
- [dwTYPE_KIND](../../../extensibility/debugger/reference/dwtype-kind.md)
- [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)
