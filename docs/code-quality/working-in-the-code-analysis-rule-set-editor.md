---
title: 使用程式碼分析規則集編輯器
ms.date: 04/04/2018
description: 瞭解如何在 Visual Studio 中編輯和查看規則集。 瞭解如何設定規則嚴重性、在自訂集中指定規則，以及調整規則集方格中的資料。
ms.custom: SEO-VS-2020
ms.topic: conceptual
f1_keywords:
- vs.codeanalysis.ruleseteditor
ms.assetid: 370c97bf-bb29-4b2f-b9ae-ba125bce7b2d
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4d2703972658aace438ab235d469eed3e0644c06
ms.sourcegitcommit: ed26b6e313b766c4d92764c303954e2385c6693e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/10/2020
ms.locfileid: "94436819"
---
# <a name="use-the-code-analysis-rule-set-editor"></a>使用程式碼分析規則集編輯器

程式碼分析規則集編輯器可讓您指定包含在自訂規則集中的規則，並設定規則違規的嚴重性。

下表顯示嚴重性選項：

|Action (嚴重性) |說明|
|-|-|
|警告|在 [ **錯誤清單** ] 和 [組建階段] 中產生警告。|
|錯誤|在 **錯誤清單** 中以及在組建階段產生錯誤。|
|Info|產生 **錯誤清單** 中的訊息。|
|Hidden|使用者看不到違規。 不過，IDE 會收到違規的通知。|
|無|規則會被隱藏。 行為與規則已從規則集中移除的行為相同。|

編輯器會在樹狀結構中顯示規則，此樹狀結構會依據您指定的規則集欄位將規則分組。 若要從規則集新增或移除規則，請執行下列一或多個步驟：

- 選取或清除 [群組] 節點的核取方塊，以新增或移除群組中的所有規則。 當您選取群組時，所有規則都會設定為 **警告** 動作。

   > [!TIP]
   > 您可以在 [ **群組依據** ] 下拉式清單中變更規則的分組方式。

- 按一下群組的 [ **動作** ] 欄位，指定要套用至群組中所有規則的動作。

- 選取或清除個別規則的核取方塊。 當您選取規則的核取方塊時，規則會設定為 **警告** 動作。

## <a name="toolbar"></a>工具列

您可以使用規則集編輯器的工具列來分組、篩選和搜尋出現在 [規則集] 方格中的資料。

下表說明 [規則集編輯器] 工具列上的控制項。

|Toolbar 控制項|說明|
|---------------------|-----------------|
|**全部展開**|顯示所有群組中的規則。|
|**全部摺疊**|隱藏所有群組中的規則。|
|**分組依據**|指定分組規則所依據的欄位。 按一下 **\<None>** 以顯示沒有群組的規則。|
|**資料行選項**|指定要顯示的規則欄位。|
|**隱藏不適用於目前解決方案的規則**|顯示或隱藏與方案不同的目標型別規則。|
|**顯示可能產生程式碼分析錯誤的規則**|顯示或隱藏指派給錯誤動作的規則。|
|**顯示可以產生程式碼分析警告的規則**|顯示或隱藏指派給警告動作的規則。|
|**顯示未啟用的規則**|顯示或隱藏指派 [無] 動作的規則。|
|**新增或移除子規則集**|新增或移除所選規則集中的規則。|
|**搜尋規則**|搜尋您所指定之字串的所有域值。|

## <a name="rule-set-fields"></a>規則集欄位

[規則集] 欄位會顯示規則集的相關資訊，而且可以用來排序和分組規則清單。 若要顯示或隱藏欄位，請選取 [規則集編輯器] 工具列上的 [ **資料行選項** ]，然後選取或清除要顯示或隱藏之欄位的核取方塊。

下表描述規則集的欄位：

|欄位|描述|
|-----------|-----------------|
|**識別碼**|規則的識別項。|
|**類別**|除了規則集中的成員資格之外，程式碼分析規則也會依類別目錄分組。 如需詳細資訊，請參閱程式 [代碼分析警告](/dotnet/fundamentals/code-analysis/quality-rules/index)。|
|**名稱**|規則的標題。|
|**Namespace**|規則的命名空間。|
|**目標類型**|指出規則適用于原生、managed 或資料庫程式碼。|
|**動作**|在程式碼分析執行中違反規則時所採取的動作。 您可以編輯 [ **動作** ] 欄位。|
|**來源規則集**|包含規則的規則集。|

## <a name="sort-and-filter-rule-sets"></a>排序和篩選規則集

從規則集方格的資料行標頭，您可以依據欄位的值來排序和篩選規則。

- 若要排序規則集清單，請選取您要排序之欄位的資料行標題。 如果群組規則集，每個群組都會個別排序。

- 若要依欄位值篩選規則集，請選取您要篩選之欄位的資料行標頭上的 [篩選] 按鈕。 選取您要顯示之值的核取方塊，並清除您要隱藏之值的核取方塊。

## <a name="see-also"></a>請參閱

- [建立自訂規則集](../code-quality/how-to-create-a-custom-rule-set.md)
