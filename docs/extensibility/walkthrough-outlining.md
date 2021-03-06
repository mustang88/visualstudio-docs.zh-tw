---
title: 逐步解說：大綱 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: how-to
helpviewer_keywords:
- editors [Visual Studio SDK], new - outlining
ms.assetid: d75a44aa-265a-44d4-9c28-457f59c4ff9f
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- csharp
- vb
ms.openlocfilehash: 6e3e60fe873d7bcb512e56c844e76fcbef037d42
ms.sourcegitcommit: 5caad925ca0b5d136416144a279e984836d8f28c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/07/2020
ms.locfileid: "89508921"
---
# <a name="walkthrough-outlining"></a>逐步解說︰大綱
藉由定義要展開或折迭的文字區欄位型別，來設定以語言為基礎的功能，例如大綱。 您可以在語言服務的內容中定義區域，或定義自己的副檔名和內容類型，並將區域定義套用至現有的內容類型， (例如 "text" ) 。 本逐步解說會示範如何定義和顯示大綱區域。

## <a name="prerequisites"></a>必要條件
 從 Visual Studio 2015 開始，您不會從下載中心安裝 Visual Studio SDK。 它在 Visual Studio 安裝程式中包含為選用功能。 您也可以稍後再安裝 VS SDK。 如需詳細資訊，請參閱 [安裝 VISUAL STUDIO SDK](../extensibility/installing-the-visual-studio-sdk.md)。

## <a name="create-a-managed-extensibility-framework-mef-project"></a>建立 Managed Extensibility Framework (MEF) 專案

### <a name="to-create-a-mef-project"></a>建立 MEF 專案

1. 建立 VSIX 專案。 將方案命名為 `OutlineRegionTest`。

2. 將編輯器分類專案範本加入至專案。 如需詳細資訊，請參閱 [使用編輯器專案範本建立延伸](../extensibility/creating-an-extension-with-an-editor-item-template.md)。

3. 刪除現有類別檔案。

## <a name="implement-an-outlining-tagger"></a>執行大綱標記
 大綱區域會以一種標記 () 標記 <xref:Microsoft.VisualStudio.Text.Tagging.OutliningRegionTag> 。 此標記提供標準大綱行為。 您可以展開或折迭大綱區域。 如果已折迭，則會以加號標示 () 如果已折迭，則會將其標示為 **+**)  (減號 **-** ，如果展開，則會以垂直線劃定展開的區域。

 下列步驟示範如何定義一個標記，以針對以括弧 (**[**，**]**) 分隔的所有區域建立大綱區域。

### <a name="to-implement-an-outlining-tagger"></a>若要執行大綱標記

1. 加入類別檔案，並將它命名為 `OutliningTagger`。

2. 匯入下列命名空間。

     [!code-csharp[VSSDKOutlineRegionTest#1](../extensibility/codesnippet/CSharp/walkthrough-outlining_1.cs)]
     [!code-vb[VSSDKOutlineRegionTest#1](../extensibility/codesnippet/VisualBasic/walkthrough-outlining_1.vb)]

3. 建立名為的類別 `OutliningTagger` ，並讓它執行 <xref:Microsoft.VisualStudio.Text.Tagging.ITagger%601> ：

     [!code-csharp[VSSDKOutlineRegionTest#2](../extensibility/codesnippet/CSharp/walkthrough-outlining_2.cs)]
     [!code-vb[VSSDKOutlineRegionTest#2](../extensibility/codesnippet/VisualBasic/walkthrough-outlining_2.vb)]

4. 新增一些欄位來追蹤文字緩衝區和快照，以及累積應標記為大綱區域的行組。 此程式碼包含區域物件清單 (稍後要定義) 表示大綱區域。

     [!code-csharp[VSSDKOutlineRegionTest#3](../extensibility/codesnippet/CSharp/walkthrough-outlining_3.cs)]
     [!code-vb[VSSDKOutlineRegionTest#3](../extensibility/codesnippet/VisualBasic/walkthrough-outlining_3.vb)]

5. 新增可初始化欄位、剖析緩衝區，並將事件處理常式加入至事件的標記函式 <xref:Microsoft.VisualStudio.Text.ITextBuffer.Changed> 。

     [!code-csharp[VSSDKOutlineRegionTest#4](../extensibility/codesnippet/CSharp/walkthrough-outlining_4.cs)]
     [!code-vb[VSSDKOutlineRegionTest#4](../extensibility/codesnippet/VisualBasic/walkthrough-outlining_4.vb)]

6. 執行可具現 <xref:Microsoft.VisualStudio.Text.Tagging.ITagger%601.GetTags%2A> 化標記範圍的方法。 這個範例假設傳入方法中的範圍 <xref:Microsoft.VisualStudio.Text.NormalizedSpanCollection> 是連續的，但不一定是如此。 這個方法會為每個大綱區域具現化新的標記範圍。

     [!code-csharp[VSSDKOutlineRegionTest#5](../extensibility/codesnippet/CSharp/walkthrough-outlining_5.cs)]
     [!code-vb[VSSDKOutlineRegionTest#5](../extensibility/codesnippet/VisualBasic/walkthrough-outlining_5.vb)]

7. 宣告 `TagsChanged` 事件處理常式。

     [!code-csharp[VSSDKOutlineRegionTest#6](../extensibility/codesnippet/CSharp/walkthrough-outlining_6.cs)]
     [!code-vb[VSSDKOutlineRegionTest#6](../extensibility/codesnippet/VisualBasic/walkthrough-outlining_6.vb)]

8. 加入 `BufferChanged` 事件處理常式，藉 <xref:Microsoft.VisualStudio.Text.ITextBuffer.Changed> 由剖析文字緩衝區來回應事件。

     [!code-csharp[VSSDKOutlineRegionTest#7](../extensibility/codesnippet/CSharp/walkthrough-outlining_7.cs)]
     [!code-vb[VSSDKOutlineRegionTest#7](../extensibility/codesnippet/VisualBasic/walkthrough-outlining_7.vb)]

9. 新增剖析緩衝區的方法。 此處提供的範例僅供說明之用。 它會以同步方式將緩衝區剖析為嵌套大綱區域。

     [!code-csharp[VSSDKOutlineRegionTest#8](../extensibility/codesnippet/CSharp/walkthrough-outlining_8.cs)]
     [!code-vb[VSSDKOutlineRegionTest#8](../extensibility/codesnippet/VisualBasic/walkthrough-outlining_8.vb)]

10. 下列 helper 方法會取得表示大綱層級的整數，因此1是最左邊的大括弧組。

     [!code-csharp[VSSDKOutlineRegionTest#9](../extensibility/codesnippet/CSharp/walkthrough-outlining_9.cs)]
     [!code-vb[VSSDKOutlineRegionTest#9](../extensibility/codesnippet/VisualBasic/walkthrough-outlining_9.vb)]

11. 下列 helper 方法會將本文稍後定義的區域 (轉譯) SnapshotSpan。

     [!code-csharp[VSSDKOutlineRegionTest#10](../extensibility/codesnippet/CSharp/walkthrough-outlining_10.cs)]
     [!code-vb[VSSDKOutlineRegionTest#10](../extensibility/codesnippet/VisualBasic/walkthrough-outlining_10.vb)]

12. 下列程式碼僅供說明之用。 它會定義 PartialRegion 類別，其中包含大綱區域開頭的行號和位移，以及父區域 (（如果有任何) ）的參考。 這段程式碼可讓剖析器設定嵌套大綱區域。 衍生的區域類別包含大綱區域結尾的行號參考。

     [!code-csharp[VSSDKOutlineRegionTest#11](../extensibility/codesnippet/CSharp/walkthrough-outlining_11.cs)]
     [!code-vb[VSSDKOutlineRegionTest#11](../extensibility/codesnippet/VisualBasic/walkthrough-outlining_11.vb)]

## <a name="implement-a-tagger-provider"></a>執行標記提供者
 匯出標記的標記提供者。 標記提供者會 `OutliningTagger` 為 "text" 內容類型的緩衝區建立，否則 `OutliningTagger` 如果緩衝區已經有的話，則會傳回。

### <a name="to-implement-a-tagger-provider"></a>若要執行標記提供者

1. 建立一個名為的類別，該類別會執行 `OutliningTaggerProvider` <xref:Microsoft.VisualStudio.Text.Tagging.ITaggerProvider> ，並將其匯出為 ContentType 和 TagType 屬性。

     [!code-csharp[VSSDKOutlineRegionTest#12](../extensibility/codesnippet/CSharp/walkthrough-outlining_12.cs)]
     [!code-vb[VSSDKOutlineRegionTest#12](../extensibility/codesnippet/VisualBasic/walkthrough-outlining_12.vb)]

2. 藉 <xref:Microsoft.VisualStudio.Text.Tagging.ITaggerProvider.CreateTagger%2A> 由將加入 `OutliningTagger` 至緩衝區的屬性來執行方法。

     [!code-csharp[VSSDKOutlineRegionTest#13](../extensibility/codesnippet/CSharp/walkthrough-outlining_13.cs)]
     [!code-vb[VSSDKOutlineRegionTest#13](../extensibility/codesnippet/VisualBasic/walkthrough-outlining_13.vb)]

## <a name="build-and-test-the-code"></a>建立並測試程式碼
 若要測試此程式碼，請建立 OutlineRegionTest 方案，並在實驗實例中執行它。

### <a name="to-build-and-test-the-outlineregiontest-solution"></a>若要建立及測試 OutlineRegionTest 方案

1. 建置方案。

2. 當您在偵錯工具中執行此專案時，會啟動 Visual Studio 的第二個實例。

3. 建立文字檔 輸入一些文字，其中包含左括弧和右括弧。

    ```
    [
       Hello
    ]
    ```

4. 應該會有包含這兩個括弧的大綱區域。 您應該可以按一下左括弧左邊的減號，以折迭大綱區域。 當區域折迭時，省略號符號 (*...*) 應該會出現在已折迭區域的左邊，而且當您將指標移至省略號上方時，就會出現包含文字暫留 **文字** 的快顯視窗。

## <a name="see-also"></a>另請參閱
- [逐步解說：將內容類型連結至副檔名](../extensibility/walkthrough-linking-a-content-type-to-a-file-name-extension.md)
