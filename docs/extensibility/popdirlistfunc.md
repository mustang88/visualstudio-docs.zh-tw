---
title: POPDIRLISTFUNC |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- POPLISTFUNC
helpviewer_keywords:
- POPDIRLISTFUNC callback function
ms.assetid: 0ee90fd2-5467-4154-ab4c-7eb02ac3a14c
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 52a0c16af0e142bda8527c5244a22e0830ced9e0
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/02/2020
ms.locfileid: "80702072"
---
# <a name="popdirlistfunc"></a>POPDIRLISTFUNC
這是提供給 [SccPopulateDirList](../extensibility/sccpopulatedirlist-function.md) 函式的回呼函式，可更新目錄的集合，並 (選擇性地) 檔案名，以找出原始檔控制下的檔案名稱。

 只有在提供給函式的 `POPDIRLISTFUNC` 清單中， (在原始檔控制下的函式) ，才應該呼叫回呼 `SccPopulateDirList` 。

## <a name="signature"></a>簽章

```cpp
typedef BOOL (*POPDIRLISTFUNC)(
   LPVOID pvCallerData,
   BOOL bFolder,
   LPCSTR lpDirectoryOrFileName
);
```

## <a name="parameters"></a>參數
 pvCallerData

在提供給 [SccPopulateDirList](../extensibility/sccpopulatedirlist-function.md)的使用者值。

 bFolder

[in] `TRUE` 如果中的名稱是目錄，則為， `lpDirectoryOrFileName` 否則名稱為檔案名。

 lpDirectoryOrFileName

在在原始程式碼控制之下的目錄或檔案名的完整本機路徑。

## <a name="return-value"></a>傳回值
 IDE 會傳回適當的錯誤碼：

|值|描述|
|-----------|-----------------|
|SCC_OK|繼續處理。|
|SCC_I_OPERATIONCANCELED|停止處理。|
|SCC_E_xxx|任何適當的原始檔控制錯誤都應該停止處理。|

## <a name="remarks"></a>備註
 如果函式的 `fOptions` 參數 `SccPopulateDirList` 包含旗標 `SCC_PDL_INCLUDEFILES` ，則清單中可能會包含檔案名和目錄名稱。

## <a name="see-also"></a>另請參閱
- [IDE 所執行的回呼函數](../extensibility/callback-functions-implemented-by-the-ide.md)
- [SccPopulateDirList](../extensibility/sccpopulatedirlist-function.md)
- [錯誤碼](../extensibility/error-codes.md)
