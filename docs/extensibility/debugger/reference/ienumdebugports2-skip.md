---
title: IEnumDebugPorts2：： Skip |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEnumDebugPorts2::Skip
helpviewer_keywords:
- IEnumDebugPorts2::Skip
ms.assetid: a837383f-7b39-4e06-b336-f1715b073dbe
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: c57eaa465a29cf505d62c720b1fe7f6aca8bda5e
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/02/2020
ms.locfileid: "80716155"
---
# <a name="ienumdebugports2skip"></a>IEnumDebugPorts2::Skip
略過指定的元素數目。

## <a name="syntax"></a>語法

```cpp
HRESULT Skip(
   ULONG celt
);
```

```csharp
int Skip(
   uint celt
);
```

## <a name="parameters"></a>參數
`celt`\
在要略過的元素數目。

## <a name="return-value"></a>傳回值
 如果成功，則傳回 `S_OK`。 `S_FALSE`如果 `celt` 大於剩餘元素的數目，則傳回，否則傳回錯誤碼。

## <a name="remarks"></a>備註
 如果 `celt` 指定的值大於剩餘的元素數目，則列舉會設定為 end，並 `S_FALSE` 傳回。

## <a name="see-also"></a>另請參閱
- [IEnumDebugPorts2](../../../extensibility/debugger/reference/ienumdebugports2.md)
