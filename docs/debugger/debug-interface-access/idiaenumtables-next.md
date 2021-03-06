---
title: IDiaEnumTables::Next | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumTables::Next method
ms.assetid: 8d7bd359-d33e-4317-9674-d89283efd7de
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 9d425e16e18338c0269ccbf88030a47c7b184507
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/02/2020
ms.locfileid: "85467523"
---
# <a name="idiaenumtablesnext"></a>IDiaEnumTables::Next
捕獲列舉序列中指定的資料表數目。

## <a name="syntax"></a>語法

```C++
HRESULT Next ( 
   ULONG       celt,
   IDiaTable** rgelt,
   ULONG*      pceltFetched
);
```

#### <a name="parameters"></a>參數
 `celt`

在要抓取的列舉值中的資料表數目。

 `rgelt`

擴展要填入 [IDiaTable](../../debugger/debug-interface-access/idiatable.md) 物件的陣列，這些物件代表所需的資料表。

 `pceltFetched`

擴展傳回已提取列舉值中的資料表數目。

## <a name="return-value"></a>傳回值
 如果成功，則傳回 `S_OK`。 `S_FALSE`如果沒有其他資料表，則會傳回。 否則會傳回錯誤碼。

## <a name="see-also"></a>另請參閱
- [IDiaEnumTables](../../debugger/debug-interface-access/idiaenumtables.md)
- [IDiaTable](../../debugger/debug-interface-access/idiatable.md)