---
title: IDiaPropertyStorage：： ReadMultiple |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaPropertyStorage::ReadMultiple
ms.assetid: 6ccc9397-ce41-4f72-b261-72ac252cd4a5
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8681032840f09bcc4a90df66b3a6f37d664739ab
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/02/2020
ms.locfileid: "85466571"
---
# <a name="idiapropertystoragereadmultiple"></a>IDiaPropertyStorage::ReadMultiple
從目前的屬性集讀取指定的屬性。

## <a name="syntax"></a>語法

```C++
HRESULT ReadMultiple( 
   ULONG          cpspec,
   PROPSPEC const rgpspec,
   PROPVARIANT    rgvar
);
```

#### <a name="parameters"></a>參數
 `cpspec`

在陣列中指定的屬性計數 `rgpspec` 。 如果為零，則方法不會傳回任何屬性，但會傳回 `S_OK` 為成功碼。

 `rgpspec`

在要讀取的屬性陣列。 您可以透過屬性識別碼或選擇性字串名稱來指定屬性。 不需要指定陣列中任何特定順序的屬性。 陣列可包含重複的屬性，因此會在簡單屬性的傳回時產生重複的屬性值。 非簡單的屬性應該會在第二次嘗試開啟存取權時傳回拒絕存取。 陣列可包含屬性識別碼和字串識別碼的混合。 此陣列必須至少有 `cpspec` 屬性值的數目。

 `rgvar`

[in，out] `PROPVARIANT` VisualStudio 命名空間中的結構陣列 () 要填入每個屬性的值。 陣列必須至少有大小的 `cpspec` 元素。 呼叫端不需要初始化陣列中的值。

## <a name="return-value"></a>傳回值
 如果成功，則傳回 `S_OK`。 `S_FALSE`如果找不到一或多個屬性，則傳回。 反之則會傳回錯誤碼。

## <a name="remarks"></a>備註
 如果找不到屬性，則陣列中的對應專案會包含型別為 `rgvar` `VARIANT` 的 `VT_EMPTY` 。

## <a name="see-also"></a>另請參閱
- [IDiaPropertyStorage](../../debugger/debug-interface-access/idiapropertystorage.md)