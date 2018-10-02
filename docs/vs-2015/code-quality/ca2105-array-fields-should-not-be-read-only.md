---
title: CA2105： 陣列欄位應該不唯讀 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- CA2105
- ArrayFieldsShouldNotBeReadOnly
helpviewer_keywords:
- ArrayFieldsShouldNotBeReadOnly
- CA2105
ms.assetid: 0bdc3421-3ceb-4182-b30c-a992fbfcc35d
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 88e7c9413ce8d1cb31e9abd7c9e1d32ef11612ca
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/24/2018
ms.locfileid: "47588316"
---
# <a name="ca2105-array-fields-should-not-be-read-only"></a>CA2105：陣列欄位不應為唯讀
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主題的最新的版本可從[CA2105： 陣列欄位不應該為唯讀](https://docs.microsoft.com/visualstudio/code-quality/ca2105-array-fields-should-not-be-read-only)。

|||
|-|-|
|TypeName|ArrayFieldsShouldNotBeReadOnly|
|CheckId|CA2105|
|分類|Microsoft.Security|
|中斷變更|中斷|

## <a name="cause"></a>原因
 公用或受保護的欄位來保存陣列被宣告為唯讀。

## <a name="rule-description"></a>規則描述
 當您套用`readonly`(`ReadOnly`在[!INCLUDE[vbprvb](../includes/vbprvb-md.md)]) 修飾詞，以包含陣列之欄位的欄位不能變更為指向不同的陣列。 但是，儲存在唯讀欄位的陣列元素則可以變更。 做出決策，或執行作業的可公開存取的唯讀陣列項目為基礎的程式碼可能會包含可利用來攻擊的安全性弱點。

 請注意，有一個公用的欄位也違反設計規則[CA1051： 不要宣告可見的執行個體欄位](../code-quality/ca1051-do-not-declare-visible-instance-fields.md)。

## <a name="how-to-fix-violations"></a>如何修正違規
 若要修正此規則所識別的安全性弱點，請勿依賴可公開存取的唯讀陣列的內容。 強烈建議使用下列程序的其中一個：

-   無法變更的強類型集合取代陣列。 如需詳細資訊，請參閱<xref:System.Collections.ReadOnlyCollectionBase?displayProperty=fullName>。

-   公用欄位取代為傳回的私用陣列複製品的方法。 因為您的程式碼不需要複製，不是可能如果修改的項目。

 如果您選擇第二種方法，並不會取代欄位與屬性;負面傳回陣列的屬性會影響效能。 如需詳細資訊，請參閱 < [CA1819： 屬性不應該傳回陣列](../code-quality/ca1819-properties-should-not-return-arrays.md)。

## <a name="when-to-suppress-warnings"></a>隱藏警告的時機
 此規則的警告排除極為不妥。 幾乎在所有情況中，就會都發生唯讀欄位的內容中都很重要。 如果這是您的案例的情況，移除`readonly`修飾詞，而不是排除該訊息。

## <a name="example"></a>範例
 此範例示範違反此規則的危險性。 第一個部分示範的範例程式庫，都有類型， `MyClassWithReadOnlyArrayField`，其中包含兩個欄位 (`grades`和`privateGrades`)，並不安全。 欄位`grades`是公用的且因此容易遭受任何呼叫端。 欄位`privateGrades`是私用，但會仍可能受到攻擊，因為它會傳回到呼叫端所`GetPrivateGrades`方法。 `securePrivateGrades`欄位會以安全的方式在`GetSecurePrivateGrades`方法。 它宣告為 private 遵循良好的設計做法。 第二個部分顯示中所儲存的值變更的程式碼`grades`和`privateGrades`成員。

 範例類別程式庫會出現在下列範例。

 [!code-csharp[FxCop.Security.ArrayFieldsNotReadOnly#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Security.ArrayFieldsNotReadOnly/cs/FxCop.Security.ArrayFieldsNotReadOnly.cs#1)]

## <a name="example"></a>範例
 下列程式碼會使用範例類別程式庫，來說明唯讀陣列安全性問題。

 [!code-csharp[FxCop.Security.TestArrayFieldsRead#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Security.TestArrayFieldsRead/cs/FxCop.Security.TestArrayFieldsRead.cs#1)]

 此範例的輸出是：

 **之前竄改： 成績:-90，90，90 的私用成績:-90，90，90 保護等級，90，90，90**
**之後遭到竄改： 成績： 90、 555，90 的私用成績： 90、 555，90 保護等級，90，90，90**
## <a name="see-also"></a>另請參閱
 <xref:System.Array?displayProperty=fullName> <xref:System.Collections.ReadOnlyCollectionBase?displayProperty=fullName>


