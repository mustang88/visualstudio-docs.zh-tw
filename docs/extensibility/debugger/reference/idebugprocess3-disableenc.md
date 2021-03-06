---
title: IDebugProcess3：:D isableENC |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProcess3::DisableENC
helpviewer_keywords:
- IDebugProcess3::DisableENC
ms.assetid: cffdbdac-4d76-4aeb-aa55-5d0410db99f1
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 5b39bb448501bacd5ab458b7e61bb1a5044bc8a3
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/02/2020
ms.locfileid: "80723728"
---
# <a name="idebugprocess3disableenc"></a>IDebugProcess3::DisableENC
這個方法會明確停用此進程的 [編輯後繼續] (以及它包含) 的所有程式。 自訂埠供應商應該一律傳回 `E_NOTIMPL` 。

## <a name="syntax"></a>語法

```cpp
HRESULT DisableENC(
   EncUnavailableReason reason
);
```

```csharp
   EncUnavailableReason reason
);
```

## <a name="parameters"></a>參數
`reason`\
在來自 [EncUnavailableReason](../../../extensibility/debugger/reference/encunavailablereason.md) 列舉的值。

## <a name="return-value"></a>傳回值
 如果成功，則傳回， `S_OK` 否則傳回錯誤碼。

> [!NOTE]
> 自訂埠供應商應該一律傳回 `E_NOTIMPL` 。

## <a name="remarks"></a>備註
 一旦停用某個進程的 [編輯後繼續]，就只能藉由重新開機處理常式來重新啟用。

## <a name="see-also"></a>另請參閱
- [IDebugProcess3](../../../extensibility/debugger/reference/idebugprocess3.md)
- [EncUnavailableReason](../../../extensibility/debugger/reference/encunavailablereason.md)
