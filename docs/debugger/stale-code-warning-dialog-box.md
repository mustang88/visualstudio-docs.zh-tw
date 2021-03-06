---
title: 過時程式碼警告對話方塊 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.debug.ENC.stalecode
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- Stale Code Warning dialog box
- code, stale code warning
- warnings, Stale Code Warning dialog box
- Edit and Continue, stale code
ms.assetid: 594b894c-e652-4e13-a980-9909473d5712
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: dba38e5b5d9f7a2be710cad58d6f2297dd03a412
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/02/2020
ms.locfileid: "72729536"
---
# <a name="stale-code-warning-dialog-box"></a>過時程式碼警告對話方塊

當您對 [編輯後繼續]**** 無法立即套用的機器碼進行變更時，這個對話方塊就會出現。 因此，現在目前堆疊框架中的某些機器碼已過期，也就是過時了。 如需詳細資訊，請參閱[編輯後繼續 (C++)](edit-and-continue-visual-cpp.md)。

**不要再顯示此對話方塊**

如果選取這個核取方塊，[編輯後繼續] 以後將直接套用程式碼變更，並且不再請求允許變更。 您可以在 [選項]**** 對話方塊中開啟 [偵錯]**** 資料夾，按一下 [編輯後繼續]**** 頁面，然後選取 [警告出現過時的程式碼]****，即可重新開啟這個警告。

## <a name="see-also"></a>另請參閱

- [ (c + +) 支援的程式碼變更 ](supported-code-changes-cpp.md)
- [選項對話方塊、偵錯、編輯後繼續](edit-and-continue.md)