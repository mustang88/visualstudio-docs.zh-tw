---
title: 停止在 Visual Basic 中的陳述式 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
- VB
helpviewer_keywords:
- End statements
- breakpoints, Stop statements
- debugging managed code, Stop statements vs breakpoints
- Stop statements, about Stop statements
- debugging [Visual Basic], Stop statements vs. breakpoints
ms.assetid: 4ad3fe5c-3dfb-4913-b2eb-a0b635751c18
caps.latest.revision: 16
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0fcb4e3018dad53ef869748a4394363dba78f71c
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/22/2018
ms.locfileid: "47484976"
---
# <a name="stop-statements-in-visual-basic"></a>Visual Basic 中的 Stop 陳述式
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主題的最新的版本可從[停止在 Visual Basic 中的陳述式](https://docs.microsoft.com/visualstudio/debugger/stop-statements-in-visual-basic)。  
  
Visual Basic 的 Stop 陳述式提供了設定中斷點的程式設計替代方式。 當偵錯工具碰到 Stop 陳述式時，它會中斷程式的執行 (進入中斷模式)。 C# 程式設計人員使用 System.Diagnostics.Debugger.Break 的呼叫，可以達到相同的效果。  
  
 您可編輯原始程式碼來設定或移除 Stop 陳述式。 您無法像處理中斷點一樣，使用偵錯工具的命令來設定或清除 Stop 陳述式。  
  
 不同於 End 陳述式，Stop 陳述式並不會重設變數，或帶您返回設計模式。 您可選擇 [偵錯] 功能表內的 [繼續] 來繼續執行應用程式。  
  
 當您在偵錯工具外執行 Visual Basic 應用程式時，如果啟用 Just-in-Time 偵錯，Stop 陳述式將啟動偵錯工具。 如果並未啟用 Just-in-Time 偵錯，Stop 陳述式的行為就好像 End 陳述式一樣，將會終止執行。 不會發生 QueryUnload 或 Unload 事件，因此您必須從 Visual Basic 應用程式的發行版本 (Release Version) 中移除所有的 Stop 陳述式。 如需詳細資訊，請參閱 < [Just-In-Time 偵錯](../debugger/just-in-time-debugging-in-visual-studio.md)。  
  
 若要省略移除 Stop 陳述式的需要，您可使用條件式編譯：  
  
```  
#If DEBUG Then  
   Stop  
#Else  
   ' Don't stop  
#End If  
```  
  
 另一個替代方式為使用 Assert 陳述式，而非 Stop 陳述式。 Debug.Assert 陳述式只會在指定的條件不符合時才中斷執行，並在您建置發行版本時自動移除。 如需詳細資訊，請參閱 < [Managed 程式碼中的判斷提示](../debugger/assertions-in-managed-code.md)。 如果您希望 Assert 陳述式一直都中斷偵錯版本的執行，就可加入下列程式碼：  
  
```  
Debug.Assert(false)  
```  
  
 另一個替代方式為使用 Debug.Fail 方法：  
  
```  
Debug.Fail("a clever output string goes here")  
```  
  
## <a name="see-also"></a>另請參閱  
 [偵錯工具安全性](../debugger/debugger-security.md)   
 [C#、F# 和 Visual Basic 專案類型](../debugger/debugging-preparation-csharp-f-hash-and-visual-basic-project-types.md)   
 [偵錯 Managed 程式碼](../debugger/debugging-managed-code.md)


