---
title: IDiaSegment::get_write | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaSegment::get_write method
ms.assetid: 5fcda988-6be1-4b2f-8660-b59aa78fc35d
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 498a72888ff59d09abf4f8d4dd830db25678761c
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/02/2020
ms.locfileid: "85465934"
---
# <a name="idiasegmentget_write"></a>IDiaSegment::get_write
抓取旗標，這個旗標會指出區段是否可以修改。

## <a name="syntax"></a>語法

```C++
HRESULT get_write ( 
   BOOL* pRetVal
);
```

#### <a name="parameters"></a>參數
 `pRetVal`

擴展 `TRUE` 如果可以寫入區段，則傳回，否則傳回 `FALSE` 。

## <a name="return-value"></a>傳回值
 如果成功，則傳回 `S_OK`。 `S_FALSE`如果不支援這個屬性，則傳回。 否則會傳回錯誤碼。

## <a name="see-also"></a>另請參閱
- [IDiaSegment](../../debugger/debug-interface-access/idiasegment.md)