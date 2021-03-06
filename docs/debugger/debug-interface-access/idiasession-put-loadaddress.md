---
title: IDiaSession::put_loadAddress | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::put_loadAddress method
ms.assetid: b157b245-1ea0-4b80-8962-d8b278dbc742
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 807346ef5a34c0b175257fe2099dc25e8de692f6
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/02/2020
ms.locfileid: "85465381"
---
# <a name="idiasessionput_loadaddress"></a>IDiaSession::put_loadAddress
設定可執行檔的載入位址，這些檔案會對應到此符號存放區中的符號。

## <a name="syntax"></a>語法

```C++
HRESULT put_loadAddress ( 
   ULONGLONG NewVal
);
```

#### <a name="parameters"></a>參數
 `NewVal`

在可執行檔的載入位址。

## <a name="remarks"></a>備註
 符號虛擬位址 (VA) 屬性是使用這個方法的值來計算。 除非將此屬性設定為非零，否則不會計算虛擬位址。

> [!NOTE]
> 如果您需要在符號上使用任何虛擬屬性，則在取得 [IDiaSession](../../debugger/debug-interface-access/idiasession.md) 物件以及開始使用物件之前，您必須呼叫這個方法。

## <a name="see-also"></a>另請參閱
- [IDiaSession](../../debugger/debug-interface-access/idiasession.md)