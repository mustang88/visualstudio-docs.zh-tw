---
title: IDebugObject2：： IsEncOutdated |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugObject2::IsEncOutdated
helpviewer_keywords:
- IDebugObject2::IsEncOutdated method
ms.assetid: d3a8c02d-895b-478c-9957-d663130f308e
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: a90ff97b87ec2abaab87dfece5b2a2ac1cabb28c
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/02/2020
ms.locfileid: "80726097"
---
# <a name="idebugobject2isencoutdated"></a>IDebugObject2::IsEncOutdated
這個方法會判斷這個物件或父容器的 [編輯後繼續] 狀態是否已過期。 自訂表格達式評估工具不會執行這個方法，且一律會傳回 `E_NOTIMPL` 。

## <a name="syntax"></a>語法

```cpp
HRESULT IsEncOutdated(
   BOOL* pfEncOutdated
);
```

```csharp
int IsEncOutdated(
   out int pfEncOutdated
);
```

## <a name="parameters"></a>參數
`pfEncOutdated`\
擴展非零 (`TRUE`) 如果 [編輯後繼續] 狀態為 [已過期]，則零 (`FALSE`) （如果沒有的話）。

## <a name="return-value"></a>傳回值
 如果成功，則傳回， `S_OK` 否則傳回錯誤碼。

> [!NOTE]
> 自訂表格達式評估工具應該一律傳回 `E_NOTIMPL` 。

## <a name="see-also"></a>另請參閱
- [IDebugObject2](../../../extensibility/debugger/reference/idebugobject2.md)
