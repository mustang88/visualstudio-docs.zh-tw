---
title: 在檔案中尋找和取代
description: 瞭解 [檔案中取代] 功能，以及它如何讓您針對字串或運算式搜尋指定檔案集的程式碼，以及變更部分或所有找到的相符專案。
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.findreplace.replaceinfiles
- vs.replaceinfiles
helpviewer_keywords:
- text searches, replacing text
- find and replace
- replace in files
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 0c3499c1b2073d0263231eb1f60129b2cd3548fa
ms.sourcegitcommit: df6ba39a62eae387e29f89388be9e3ee5ceff69c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/02/2020
ms.locfileid: "96480027"
---
# <a name="replace-in-files"></a>檔案中取代

[檔案中取代] 可讓您在一組指定檔案中搜尋程式碼的字串或運算式，並變更部分或所有找到的相符項目。 找到的相符專案與所採取的動作會列在 [**結果選項**] 中所選取的 [**尋找結果**] 視窗中。

> [!NOTE]
> 您所看到的對話方塊和功能表命令可能會與 [說明] 中描述的不同 **，視您使用的設定** 或版本而定。 若要變更您的設定 (例如變更為 [一般] 或 [Visual C++] 設定)，請選擇 [工具] > [匯入和匯出設定]，然後選擇 [重設所有設定]。

您可以使用下列方法之一，在 [檔案中尋找] 視窗中顯示 [檔案中取代]。

## <a name="to-display-replace-in-files"></a>若要顯示檔案中取代

1. 在 [編輯] 功能表上，展開 [尋找和取代]。

2. 選擇 [檔案中取代]。

   — 或者—

   如果 [尋找和取代] 視窗已開啟，請選擇工具列中的 [檔案中取代]。

## <a name="find-what"></a>尋找目標

若要搜尋新的文字字串或運算式，請在方塊中指定。 若要搜尋您最近搜尋過的 20 個字串之一，請開啟下拉式清單，然後選擇字串。 如果您想要在搜尋字串中使用一或多個規則運算式，請選擇相鄰的 [運算式產生器] 按鈕。 如需詳細資訊，請參閱[在 Visual Studio 中使用規則運算式](../ide/using-regular-expressions-in-visual-studio.md)。

> [!NOTE]
> 只有在選取 [尋找選項] 下方的 [使用規則運算式] 時，才會啟用 [運算式產生器] 按鈕。

## <a name="replace-with"></a>取代為

若要將 [尋找目標] 方塊中的字串執行個體取代為其他字串，請在 [取代為] 方塊中輸入取代字串。 若要刪除 [尋找目標] 方塊中的字串執行個體，請將此欄位保留空白。 開啟清單即可顯示您最近搜尋的 20 筆字串。 如果您想要在取代字串中使用一或多個規則運算式，請選擇相鄰的 [運算式產生器] 按鈕。 如需詳細資訊，請參閱[在 Visual Studio 中使用規則運算式](../ide/using-regular-expressions-in-visual-studio.md)。

## <a name="look-in"></a>查詢

您從 [查詢] 下拉式清單中選擇的選項，可決定 [檔案中取代] 僅搜尋目前使用中的檔案，或搜尋儲存在特定資料夾中的所有檔案。 從清單中選取搜尋範圍、輸入資料夾路徑，或按一下 [瀏覽 (...)] 按鈕，顯示 [選擇搜尋資料夾] 對話方塊，然後選擇要搜尋的資料夾集合。 您也可以直接在 [查詢] 方塊中輸入路徑。

> [!NOTE]
> 如果選取 [查詢] 選項時，所搜尋的檔案已從原始程式碼控制簽出，則只會搜尋該檔案的本機電腦下載版本。

## <a name="find-options"></a>尋找選項

您可以展開或折迭 [ **尋找選項** ] 區段。 可選取或清除下列選項：

**大小寫須相符**

選取時，[尋找結果] 視窗僅會顯示內容和大小寫都相符的 [尋找目標] 字串執行個體。 例如，若搜尋 "MyObject" 時選取 [大小寫須相符]，則會傳回 "MyObject"，而不是 "myobject" 或 "MYOBJECT"。

**全字拼寫須相符**

選取時，[尋找結果] 視窗僅會顯示完整字組相符的 [尋找目標] 字串執行個體。 例如，搜尋 "MyObject" 時會傳回 "MyObject"，而不是 "CMyObject" 或 "MyObjectC"。

**使用正則運算式**

如果已選取此核取方塊，您可以在 [尋找目標] 或 [取代為] 文字方塊中，使用特殊標記法來定義文字模式。 如需這些標記法的清單，請參閱[在 Visual Studio 中使用規則運算式](../ide/using-regular-expressions-in-visual-studio.md)。

**尋找下列檔案類型**

這個清單可指定要在 [查詢] 目錄中搜尋的檔案類型。 如果此欄位保持空白，則會搜尋 [查詢] 目錄中的所有檔案。 選取此清單中的任一項目，即可輸入預先設定的搜尋字串，以尋找特定類型的檔案。

## <a name="result-options"></a>結果選項

您可以展開或折迭 [ **結果選項** ] 區段。 可選取或清除下列選項：

**尋找結果 1** 視窗

若選取此選項，目前搜尋的結果將會取代 [尋找結果 1] 視窗的內容。 此視窗會自動開啟，以顯示您的搜尋結果。 若要手動開啟此視窗，請從 [檢視] 功能表中選取 [其他視窗]，並選擇 [尋找結果 1]。

**尋找結果 2** 視窗

若選取此選項，目前搜尋的結果將會取代 [尋找結果 2] 視窗的內容。 此視窗會自動開啟，以顯示您的搜尋結果。 若要手動開啟此視窗，請從 [檢視] 功能表中選取 [其他視窗]，並選擇 [尋找結果 2]。

**僅顯示檔案名稱**

選取此核取方塊時，[尋找結果] 視窗會列出包含搜尋字串之所有檔案的完整名稱和路徑。 不過，這些結果不含字串出現位置的程式碼行。 此核取方塊僅在 [檔案中尋找] 中提供。

**全部取代後保持已修改檔案為開啟狀態**

如果選取，就會將有進行取代作業的所有檔案保持開啟，以便您恢復或儲存變更。 記憶體的容量可能會限制進行取代作業之後，能夠保持開啟的檔案數目。

> [!CAUTION]
> 您僅能針對仍然保持開啟以供編輯的檔案執行 [恢復] 動作。 如果沒有選取此選項，沒有開啟以供編輯的檔案將會保持關閉狀態，且該些檔案就無法使用 [恢復] 選項。

## <a name="see-also"></a>另請參閱

- [尋找和取代文字](../ide/finding-and-replacing-text.md)
- [檔案中尋找](../ide/find-in-files.md)
- [Visual Studio 命令](../ide/reference/visual-studio-commands.md)
