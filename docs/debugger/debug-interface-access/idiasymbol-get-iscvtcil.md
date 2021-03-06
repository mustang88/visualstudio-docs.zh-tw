---
title: IDiaSymbol::get_isCVTCIL | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_isCVTCIL method
ms.assetid: 711b81fd-9549-44dc-9761-5eb862ed64c0
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 068720e4b35ca52e07351aeb6f74d7594fe69d1e
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/02/2020
ms.locfileid: "85463432"
---
# <a name="idiasymbolget_iscvtcil"></a>IDiaSymbol::get_isCVTCIL
抓取旗標，指出模組是否已從通用中繼語言 (CIL) 模組轉換成原生模組。

## <a name="syntax"></a>語法

```C++
HRESULT get_isCVTCIL(
   BOOL *pFlag
);
```

#### <a name="parameters"></a>參數
 `pFlag`

擴展 `TRUE` 如果模組已從 CIL 轉換成機器碼，則傳回，否則傳回 `FALSE` 。

## <a name="return-value"></a>傳回值
 如果成功，則傳回， `S_OK` 否則傳回 `S_FALSE` 錯誤碼。

> [!NOTE]
> 的傳回值 `S_FALSE` 表示該符號無法使用該屬性。

## <a name="remarks"></a>備註
 您可以從符號類型取得這個屬性 `SymTagCompilandDetails` (請參閱 [CompilandDetails](../../debugger/debug-interface-access/compilanddetails.md)。

## <a name="requirements"></a>需求

|需求|描述|
|-----------------|-----------------|
|標頭：|dia2。h|
|版本：|DIA SDK v8.0|

## <a name="see-also"></a>另請參閱
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
- [CompilandDetails](../../debugger/debug-interface-access/compilanddetails.md)