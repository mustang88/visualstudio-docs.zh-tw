---
title: IDebugProcessSecurity：： GetUserName |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugProcessSecurity::GetUserName
ms.assetid: c73c60ac-da6e-45ae-8f04-95353a24ca3e
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: ef00a0b7489c3e5cb709520546f3d3f26c8a4eba
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/02/2020
ms.locfileid: "80723253"
---
# <a name="idebugprocesssecuritygetusername"></a>IDebugProcessSecurity::GetUserName
從埠供應商取得使用者名稱。

## <a name="syntax"></a>語法

```cpp
HRESULT GetUserName(
    BSTR *pbstrUserName
);
```

```csharp
int GetUserName (
    string pbstrUserName
);
```

## <a name="parameters"></a>參數
`pbstrUserName`\
擴展包含使用者名稱的字串。

## <a name="return-value"></a>傳回值
 如果方法成功，它會傳回 `S_OK`。 否則會傳回錯誤碼。

## <a name="remarks"></a>備註
 `GetUserName`傳回 [**附加至進程**] 對話方塊的 [**使用者名稱**] 欄中所顯示的使用者名稱。 若要查看 [**附加至進程**] 對話方塊，請在整合式開發環境 (IDE) 中，按一下 [**工具**] 功能表上的 [**附加至進程**] [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] 。

## <a name="see-also"></a>另請參閱
- [IDebugProcessSecurity](../../../extensibility/debugger/reference/idebugprocesssecurity.md)
