---
title: 哪裡可以查看 Win32 錯誤碼？ | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vc.errors
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- error codes, Win32
- Win32, error codes
ms.assetid: 8fb4ff42-b8eb-4152-b49e-b802d194b05e
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a8e3dda1b728cd631efe8a84913af3d5c475138d
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/02/2020
ms.locfileid: "72728039"
---
# <a name="where-can-i-look-up-win32-error-codes"></a>哪裡可以查看 Win32 錯誤碼？
您的預設系統安裝 INCLUDE 目錄裡的 WINERROR.H 包含 Win32 API 函式的錯誤碼定義。

 您可以在 [監看式]**** 視窗或 [快速監看式]**** 對話方塊中鍵入程式碼來查看錯誤碼。 例如：

`0x80000004,hr`

## <a name="see-also"></a>另請參閱
- [機器碼偵錯 FAQ](../debugger/debugging-native-code-faqs.md)
- [偵錯機器碼](../debugger/debugging-native-code.md)