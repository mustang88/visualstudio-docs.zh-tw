---
title: CA1024： 使用屬性適當 |Microsoft Docs
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
- UsePropertiesWhereAppropriate
- CA1024
helpviewer_keywords:
- CA1024
- UsePropertiesWhereAppropriate
ms.assetid: 3a04f765-af7c-4872-87ad-9cc29e8e657f
caps.latest.revision: 23
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 952bb3c63e9d8ce645b9e986f44aaed50cb0afa4
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/24/2018
ms.locfileid: "47588415"
---
# <a name="ca1024-use-properties-where-appropriate"></a>CA1024：建議在適當時使用屬性
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主題的最新的版本可從[CA1024： 在適當時使用屬性](https://docs.microsoft.com/visualstudio/code-quality/ca1024-use-properties-where-appropriate)。

|||
|-|-|
|TypeName|UsePropertiesWhereAppropriate|
|CheckId|CA1024|
|分類|Microsoft.Design|
|中斷變更|中斷|

## <a name="cause"></a>原因
 公用或受保護的方法有名稱開頭為`Get`、 不採用任何參數和傳回值，這個值不是陣列。

## <a name="rule-description"></a>規則描述
 在大部分情況下，屬性代表資料，方法執行動作。 屬性與欄位類似，讓它們可使用的工作變得更容易存取。 方法是成為屬性，若符合下列條件之一，則的良好候選項目：

-   不接受引數，並傳回物件的狀態資訊。

-   接受單一引數來設定物件狀態的某些部分。

 屬性應該如同它們是欄位，如果方法無法處理，它應該不會變更的屬性。 方法是優於在下列情況中的屬性：

-   這個方法會執行耗時的作業。 此方法為感覺比所需的設定或取得欄位的值時間。

-   這個方法會執行轉換。 存取欄位不會傳回轉換的版本，它會將儲存的資料。

-   Get 方法具有可預見的副作用。 擷取欄位的值不會產生任何副作用。

-   執行的順序很重要。 設定欄位的值不需要其他作業一次。

-   連續兩次呼叫方法時，會建立不同的結果。

-   方法是靜態的但是會傳回呼叫者可以變更的物件。 擷取欄位的值不允許呼叫端將變更儲存欄位的資料。

-   方法會傳回陣列。

## <a name="how-to-fix-violations"></a>如何修正違規
 若要修正此規則的違規情形，請將方法變更為屬性。

## <a name="when-to-suppress-warnings"></a>隱藏警告的時機
 如果方法會符合至少其中一個先前所列的準則，則隱藏此規則的警告。

## <a name="controlling-property-expansion-in-the-debugger"></a>控制偵錯工具中的屬性擴充
 程式設計師可讓您避免使用屬性的其中一個原因是因為不想偵錯工具自動展開。 例如，配置大型物件或呼叫 P/Invoke，可能會牽涉到的屬性，但它可能實際上沒有任何可預見的副作用。

 您可以防止偵錯工具自動擴充屬性，藉由套用<xref:System.Diagnostics.DebuggerBrowsableAttribute?displayProperty=fullName>。 下列範例示範套用至執行個體屬性的這個屬性。

```vb
Imports System
Imports System.Diagnostics

Namespace Microsoft.Samples

    Public Class TestClass

        ' [...]

        <DebuggerBrowsable(DebuggerBrowsableState.Never)> _
        Public ReadOnly Property LargeObject() As LargeObject
            Get
                ' Allocate large object
                ' [...]
            End Get
        End Property

    End Class

End Namespace
```

```csharp

      using System;
using System.Diagnostics;

namespace Microsoft.Samples
{
    publicclass TestClass
    {
        // [...]

        [DebuggerBrowsable(DebuggerBrowsableState.Never)]
        public LargeObject LargeObject
        {
            get
            {
                // Allocate large object
                // [...]

        }
    }
}
```

## <a name="example"></a>範例
 下列範例包含數種方法，應該轉換成屬性，以及數個，應該不是因為它們不行為與欄位一樣。

 [!code-csharp[FxCop.Design.MethodsProperties#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.MethodsProperties/cs/FxCop.Design.MethodsProperties.cs#1)]


