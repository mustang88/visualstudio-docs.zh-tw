---
title: 條件式編譯已關閉 |Microsoft Docs
ms.date: 01/18/2017
ms.prod: visual-studio-windows
ms.technology: vs-javascript
ms.topic: error-reference
f1_keywords:
- VS.WebClient.Help.SCRIPT1030
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 59a030b0-a6c6-47f2-b90e-c0ed204d5116
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 91e32971013d2dfcf0ee2dc901d84681522c7e89
ms.sourcegitcommit: e38419bb842d587fd9e37c24b6cf3fc5c2e74817
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/09/2020
ms.locfileid: "91861660"
---
# <a name="conditional-compilation-is-turned-off"></a>條件式編譯已經關閉
您嘗試使用條件式編譯變數，而不需要先開啟的條件式編譯。 開啟條件式編譯會告知 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 編譯器將以 @ 開頭的識別碼作為條件式編譯變數來解讀。 若要這樣做，請使用語句來開始您的條件式程式碼：  
  
```js
/*@cc_on @*/  
```  
  
### <a name="to-correct-this-error"></a>更正這個錯誤  
  
- 將下列語句新增至您的條件式程式碼開頭：  
  
    ```JavaScript  
    /*@cc_on @*/  
    ```  
  
## <a name="see-also"></a>請參閱  
 [條件式編譯](/previous-versions/windows/internet-explorer/ie-developer/scripting-articles/121hztk3(v=vs.84))   
 [條件式編譯變數](/previous-versions/windows/internet-explorer/ie-developer/scripting-articles/s59bkzce(v=vs.84))   
 [@cc_on 聲明](https://developer.mozilla.org/docs/Archive/Web/JavaScript/Microsoft_Extensions/at-cc-on)   
 [@if 聲明](https://developer.mozilla.org/docs/Archive/Web/JavaScript/Microsoft_Extensions/at-if)   
 [@set 聲明](https://developer.mozilla.org/docs/Archive/Web/JavaScript/Microsoft_Extensions/at-set)