---
title: IDebugExpressionEvaluator：： GetMethodLocationProperty |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugExpressionEvaluator::GetMethodLocationProperty
helpviewer_keywords:
- IDebugExpressionEvaluator::GetMethodLocationProperty method
ms.assetid: 52c42a2e-f144-476b-8bef-442464c8fe8e
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: a6ba87d6c1a1f7370ce5e209440589f362b87035
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/02/2020
ms.locfileid: "80729515"
---
# <a name="idebugexpressionevaluatorgetmethodlocationproperty"></a>IDebugExpressionEvaluator::GetMethodLocationProperty
這個方法會將方法位置和位移轉換成記憶體位址。

## <a name="syntax"></a>語法

```cpp
HRESULT GetMethodLocationProperty( 
   LPCOLESTR             upstrFullyQualifiedMethodPlusOffset,
   IDebugSymbolProvider* pSymbolProvider,
   IDebugAddress*        pAddress,
   IDebugBinder*         pBinder,
   IDebugProperty2**     ppProperty
);
```

```csharp
int GetMethodLocationProperty(
   string               upstrFullyQualifiedMethodPlusOffset,
   IDebugSymbolProvider pSymbolProvider,
   IDebugAddress        pAddress,
   IDebugBinder         pBinder,
   out IDebugProperty2  ppProperty
);
```

## <a name="parameters"></a>參數
`upstrFullyQualifiedMethodPlusOffset`\
在方法位置和位移，以字串表示。

`pSymbolProvider`\
在表示為 [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md) 物件的符號提供者。

`pAddress`\
在方法內的位址，以 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) 物件表示。

`pBinder`\
在以 [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md) 物件表示的系結器。

`ppProperty`\
擴展傳回代表記憶體位址的 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) 介面。

## <a name="return-value"></a>傳回值
 如果成功，則傳回， `S_OK` 否則傳回錯誤碼。

## <a name="remarks"></a>備註
 例如，傳回的位址可以用來設定中斷點。

 儘管有名稱 `upstrFullyQualifiedMethodPlusOffset` ，此參數也可以傳遞至部分限定的方法名稱。 在這種情況下，選取的方法是包含的方法 `pAddress` 。 此參數的解讀方式是由運算式評估工具和它所支援的語言來執行。

## <a name="see-also"></a>另請參閱
- [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md)
- [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md)
- [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)
- [IDebugExpressionEvaluator](../../../extensibility/debugger/reference/idebugexpressionevaluator.md)
