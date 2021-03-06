---
title: IDiaEnumInjectedSources::Item | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumInjectedSources::Item method
ms.assetid: 14846955-7270-451d-91d2-9cb34bb65187
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 76e89c89bca8b164645c71df6083b230850e61ca
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/02/2020
ms.locfileid: "85468270"
---
# <a name="idiaenuminjectedsourcesitem"></a>IDiaEnumInjectedSources::Item
藉由索引來抓取插入的來源。

## <a name="syntax"></a>語法

```C++
HRESULT Item ( 
   DWORD                index,
   IDiaInjectedSource** injectedSource
);
```

#### <a name="parameters"></a>參數
 索引

在要抓取之 [IDiaInjectedSource](../../debugger/debug-interface-access/idiainjectedsource.md) 物件的索引。 索引是從0到 `count` -1 的範圍，其中 `count` 是 [IDiaEnumInjectedSources：： get_Count](../../debugger/debug-interface-access/idiaenuminjectedsources-get-count.md) 方法所傳回的。

 injectedSource

擴展傳回代表插入來源的 [IDiaInjectedSource](../../debugger/debug-interface-access/idiainjectedsource.md) 物件。

## <a name="return-value"></a>傳回值
 如果成功，則傳回， `S_OK` 否則傳回錯誤碼。

## <a name="see-also"></a>另請參閱
- [IDiaEnumInjectedSources](../../debugger/debug-interface-access/idiaenuminjectedsources.md)
- [IDiaInjectedSource](../../debugger/debug-interface-access/idiainjectedsource.md)