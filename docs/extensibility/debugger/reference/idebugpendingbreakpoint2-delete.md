---
title: IDebugPendingBreakpoint2：:D elete |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugPendingBreakpoint2::Delete
helpviewer_keywords:
- IDebugPendingBreakpoint2::Delete method
- Delete method
ms.assetid: 4cb5ed81-6f0c-41ce-a770-5adb6b4bf5d9
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: fd6e2d61eb7a7ce927a966281bba2f0cbf470dc6
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/02/2020
ms.locfileid: "80725911"
---
# <a name="idebugpendingbreakpoint2delete"></a>IDebugPendingBreakpoint2::Delete
刪除這個暫止中斷點及其系結的所有中斷點。

## <a name="syntax"></a>語法

```cpp
HRESULT Delete(
    void
);
```

```csharp
int Delete();
```

## <a name="return-value"></a>傳回值
如果成功，則傳回， `S_OK` 否則傳回錯誤碼。 `E_BP_DELETED`如果中斷點已刪除，則會傳回。

## <a name="example"></a>範例
下列範例示範如何針對實 IDebugPendingBreakpoint2 介面的簡單物件，執行這個方法 `CPendingBreakpoint` 。 [IDebugPendingBreakpoint2](../../../extensibility/debugger/reference/idebugpendingbreakpoint2.md)

```cpp
HRESULT CPendingBreakpoint::Delete(void)
{
    HRESULT hr;

    // Verify that the pending breakpoint has not been deleted. If deleted,
    // then return hr = E_BP_DELETED.
    if (m_state.state != PBPS_DELETED)
    {
        // If the pending breakpoint has bound and has an associated bound
        // breakpoint, delete and release the bound breakpoint and set the
        // pointer to NULL.
        if (m_pBoundBP)
        {
            m_pBoundBP->Delete();
            m_pBoundBP->Release();
            m_pBoundBP = NULL;
        }
        // If the pending breakpoint did not bind and has an associated
        // error breakpoint, release the error breakpoint and set the
        // pointer to NULL.
        if (m_pErrorBP)
        {
            m_pErrorBP->Release();
            m_pErrorBP = NULL;
        }

        // Set the PENDING_BP_STATE in the PENDING_BP_STATE_INFO structure
        // to deleted.
        m_state.state = PBPS_DELETED;
    }
    else
    {
        hr = E_BP_DELETED;
    }

    return hr;
}
```

## <a name="see-also"></a>另請參閱
- [IDebugPendingBreakpoint2](../../../extensibility/debugger/reference/idebugpendingbreakpoint2.md)
