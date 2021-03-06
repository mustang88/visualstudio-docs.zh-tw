---
title: 使用文字範本中的逸出序列
description: '瞭解如何使用文字模板中的 escape 序列來產生文字模板標記，以及僅在 c # 程式碼中將控制字元和引號換用。'
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- text templates, escape sequences
author: JoshuaPartlow
ms.author: joshuapa
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8b007a9b5ccf41a27cda7d9833064eb60394c4dc
ms.sourcegitcommit: 4d394866b7817689411afee98e85da1653ec42f2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/12/2020
ms.locfileid: "97361322"
---
# <a name="use-escape-sequences-in-text-templates"></a>在文字模板中使用 escape 序列

您可以在文字模板中使用 escape 序列來產生文字模板標記，並在 c # 程式碼中 (只) 來將控制字元和引號換用。

若要將標準程式碼區塊的開啟和關閉標記列印到輸出檔，請將標記如下：

```
\<# ... \#>
```

您可以使用其他文字模板指示詞和程式碼區塊標記來進行相同的動作。

如果文字區塊包含用來將文字模板標記換用的字串，則您可以使用下列 escape 順序：

- 如果文字樣板標記前面加上偶數的 escape (\\) 個字元，範本剖析器將會包含一半的 escape 字元，並將序列包含為文字模板標記。 例如，如果文字模板中有四個 escape 字元，則產生的檔案中將會有兩個 " \\ " 字元。

- 如果文字樣板標記前面加上奇數數目的 escape (\\) 個字元，則範本剖析器將會包含一半的 " \\ " 字元加上標記本身 (\<# or #>) 。 標記不會被視為文字模板標記。

- 如果 escape (\\) 字元會出現在其他任何順序中，而 (不是以 c # 中的任何順序（僅限 c #）進行) ，則會直接輸出該字元。

## <a name="see-also"></a>請參閱

- [如何：使用逸出序列從範本產生範本](../modeling/how-to-generate-templates-from-templates-by-using-escape-sequences.md)
