---
title: IDiaEnumTables::Skip | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumTables::Skip method
ms.assetid: 5c9db956-0654-4f1a-8775-530aa980d8ec
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 27daf70a3cc5f155bfbe6b2678cce42b50801153
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/02/2020
ms.locfileid: "85467460"
---
# <a name="idiaenumtablesskip"></a>IDiaEnumTables::Skip
略過列舉序列中指定數目的資料表。

## <a name="syntax"></a>語法

```C++
HRESULT Skip ( 
   ULONG celt
);
```

#### <a name="parameters"></a>參數
 `celt`

在列舉順序中要跳過的資料表數目。

## <a name="return-value"></a>傳回值
 如果成功， `S_OK` 則傳回; 否則， `S_FALSE` 如果沒有其他要略過的資料表，則會傳回。

## <a name="see-also"></a>另請參閱
- [IDiaEnumTables](../../debugger/debug-interface-access/idiaenumtables.md)