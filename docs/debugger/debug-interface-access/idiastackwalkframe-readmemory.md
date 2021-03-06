---
title: IDiaStackWalkFrame：： readMemory |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalkFrame::readMemory method
ms.assetid: 7ab0b525-a5a7-4692-acad-e8c00fa9ab9a
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f682f3fe0e300f84dc28b959497138a5019f954b
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/02/2020
ms.locfileid: "85464825"
---
# <a name="idiastackwalkframereadmemory"></a>IDiaStackWalkFrame::readMemory
從映射讀取記憶體。

## <a name="syntax"></a>語法

```C++
HRESULT readMemory ( 
   MemoryTypeEnum type,
   ULONGLONG va,
   DWORD     cbData,
   DWORD*    pcbData,
   BYTE      data[]
);
```

#### <a name="parameters"></a>參數
 `type`

在其中一個 [MemoryTypeEnum 列舉](../../debugger/debug-interface-access/memorytypeenum.md) 列舉值，這個值會指定要存取的記憶體種類。

 `va`

在映射中要開始讀取的虛擬位址位置。

 `cbData`

在資料緩衝區的大小（以位元組為單位）。

 `pcbData`

擴展傳回傳回的位元組數目。 如果 `data` 為 `NULL` ，則 `pcbData` 包含可用的資料位元組總數。

 `data`

擴展要以指定位置中的資料填入的緩衝區。

## <a name="return-value"></a>傳回值
 如果成功，則傳回， `S_OK` 否則傳回錯誤碼。

## <a name="see-also"></a>另請參閱
- [IDiaStackWalkFrame](../../debugger/debug-interface-access/idiastackwalkframe.md)