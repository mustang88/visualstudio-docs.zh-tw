---
title: 預期函數 |Microsoft Docs
ms.date: 01/18/2017
ms.prod: visual-studio-windows
ms.technology: vs-javascript
ms.topic: error-reference
f1_keywords:
- VS.WebClient.Help.SCRIPT5002
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: f62ade94-9f6f-4832-9b9b-49a06a385bbe
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2028d8923c2f81d1d99fec752d7ac0ce2fb32f65
ms.sourcegitcommit: e38419bb842d587fd9e37c24b6cf3fc5c2e74817
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/09/2020
ms.locfileid: "91862172"
---
# <a name="function-expected"></a>必須是函式
您嘗試在不是物件的物件上叫用其中一個函式 **原型** 方法 `Function` ，或您在函式呼叫內容中使用了物件。 例如，下列程式碼會產生這個錯誤，因為 **範例** 不是函數。  
  
```JavaScript  
var example = new Object();  // Create a new object called "example".  
var x = example();           // Try and call example as if it were a function.  
```  
  
### <a name="to-correct-this-error"></a>更正這個錯誤  
  
- 只對物件呼叫函式 **原型** 方法 `Function` 。  
  
- 確定您使用函式呼叫運算子 `()` 只呼叫函式。  
  
## <a name="see-also"></a>請參閱  
 [Function 物件](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Function)   
 [prototype 屬性 (Object)](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object)