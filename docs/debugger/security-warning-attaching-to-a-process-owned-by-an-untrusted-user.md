---
title: 安全性警告：附加至未受信任的使用者所擁有的處理序可能會造成危險。 如果下列資訊看起來很可疑，或您不確定，請不要附加至此進程 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.debug.attachsecuritywarning
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: 52246c1e-a371-40a0-b756-a435cc51876f
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 05b78ea0ca06a0ba9670e61cc065cf539ea21ebc
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/02/2020
ms.locfileid: "72729782"
---
# <a name="security-warning-attaching-to-a-process-owned-by-an-untrusted-user-can-be-dangerous-if-the-following-information-looks-suspicious-or-you-are-unsure-do-not-attach-to-this-process"></a>安全性警告：附加至未受信任的使用者所擁有的處理序可能會造成危險。 如果下面的資訊看起來有問題，或者您並不確定，請不要附加至此處理序
當您附加至包含部分受信任程式碼的處理序，或是附加至在附加之前即由未受信任之使用者所擁有的處理序時，這個警告對話方塊就會出現。 包含惡意程式碼的未受信任處理序可能會損害進行偵錯的電腦。 如果您有不信任處理序的理由，則應該按一下 [取消]**** 避免進行偵錯。

 若要在調試合法案例時隱藏此警告，請關閉 Visual Studio，並將此登錄機碼的值設定為1： `HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\<version>\Debugger\DisableAttachSecurityWarning` ，然後重新開機 Visual Studio。 在您完成情節的偵錯之後，將值重設為 0，並重新啟動 Visual Studio。

 「受信任的使用者」包括您自己以及一組標準使用者，這些使用者通常是在已安裝 .NET Framework 的電腦上定義，例如 `aspnet`、`localsystem`、`networkservice` 和 `localservice`。

## <a name="uielement-list"></a>UIElement 清單
 要求進行偵錯工具的元件名稱

 使用者目前的使用者

 附加按下以繼續透過附加來進行偵錯工具

 不要附加 [不要附加至進程]

## <a name="see-also"></a>另請參閱
- [附加到正在執行的處理序](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)
- [偵錯工具安全性](../debugger/debugger-security.md)