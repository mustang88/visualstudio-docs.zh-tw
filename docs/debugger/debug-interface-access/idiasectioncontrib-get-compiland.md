---
title: IDiaSectionContrib：： get_compiland |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaSectionContrib::get_compiland method
ms.assetid: c0496f6f-f8f2-435f-8674-6c32db6c5934
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d0243b5d083b33c9838edc93e6570a2df606f543
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/02/2020
ms.locfileid: "85466340"
---
# <a name="idiasectioncontribget_compiland"></a>IDiaSectionContrib::get_compiland
抓取參與此區段之編譯單位符號的參考。

## <a name="syntax"></a>語法

```C++
HRESULT get_compiland ( 
   IDiaSymbol** pRetVal
);
```

#### <a name="parameters"></a>參數
 `pRetVal`

擴展傳回 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md) 物件，此物件代表參與此區段的編譯單位。

## <a name="return-value"></a>傳回值
 如果成功，則傳回 `S_OK`。 `S_FALSE`如果不支援這個屬性，則傳回。 否則會傳回錯誤碼。

## <a name="see-also"></a>另請參閱
- [IDiaSectionContrib](../../debugger/debug-interface-access/idiasectioncontrib.md)
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)