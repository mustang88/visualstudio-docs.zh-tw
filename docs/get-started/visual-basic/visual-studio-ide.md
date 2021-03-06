---
title: Visual Basic 開發人員概觀
description: 瞭解如何使用 Visual Studio 來編輯、偵測和建立程式碼，然後將應用程式發佈為 Visual Basic 開發人員。
ms.date: 11/15/2018
ms.technology: vs-ide-general
ms.custom:
- get-started
- SEO-VS-2020
ms.topic: conceptual
author: TerryGLee
ms.author: tglee
manager: jillfra
dev_langs:
- VB
ms.workload:
- dotnet
ms.openlocfilehash: 990bff2832f290987ed29fd48b69f4d7a1a05bba
ms.sourcegitcommit: b1b747063ce0bba63ad2558fa521b823f952ab51
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2020
ms.locfileid: "96189884"
---
# <a name="welcome-to-the-visual-studio-ide--visual-basic"></a>歡迎使用 Visual Studio IDE | Visual Basic

Visual Studio「整合式開發環境」是一個有創意的啟動控制板，可供您編輯、偵錯及建置程式碼，然後發佈應用程式。 整合式開發環境 (IDE) 是功能豐富的程式，可用於軟體開發的許多方面。 除了大部分 IDE 提供的標準編輯器和偵錯工具之外，Visual Studio 還有編譯器、程式碼完成工具、圖形設計工具和更多功能，讓軟體開發程序變得更為容易。

::: moniker range="vs-2017"

![Visual Studio IDE](../media/visual-studio-ide.png)

::: moniker-end

::: moniker range=">=vs-2019"

[![Visual Studio 2019 IDE](media/vs-2019/ide-overview.png)](media/vs-2019/ide-overview.png#lightbox)

::: moniker-end

此圖顯示 Visual Studio，其中包含一個開啟的專案，以及您想要使用的數個重要工具視窗：

- 「方案總管」(右上) 可讓您檢視、巡覽及管理您的程式碼檔案。 **方案總管** 可以將檔案分組到 [方案和專案](tutorial-projects-solutions.md)中，以協助組織程式碼。

- 「編輯器視窗」(中間) 會顯示檔案內容，您大部分的時間可能都是花在這裡。 您在這裡編輯程式碼或設計使用者介面，例如有按鈕和文字方塊的視窗。

- [輸出視窗](../../ide/reference/output-window.md) (中下) 是 Visual Studio 傳送通知的位置，例如偵錯和錯誤訊息、編譯器警告、發佈狀態訊息等。 每個訊息來源都有自己的索引標籤。

- [Team Explorer](/azure/devops/user-guide/work-team-explorer?view=vsts&preserve-view=true) (右下) 可讓您追蹤工作項目，並使用版本控制技術 (例如 [Git](https://git-scm.com/) 和 [Team Foundation 版本控制 (TFVC)](/azure/devops/repos/tfvc/overview?view=vsts&preserve-view=true)) 與其他人共用程式碼。

## <a name="editions"></a>版本

Visual Studio 適用於 Windows 和 Mac。 [Visual Studio for Mac](/visualstudio/mac/) 有許多與 Visual Studio 2017 相同的功能，並已針對開發跨平台和行動應用程式最佳化。 本文著重於 Windows 版的 Visual Studio 2017。

有三種 Visual Studio 2017 的版本：Community、Professional 及 Enterprise。 若要了解每個版本支援哪些功能，請參閱[比較 Visual Studio 2017 IDE](https://visualstudio.microsoft.com/vs/compare/)。

## <a name="popular-productivity-features"></a>熱門的生產力功能

Visual Studio 的某些熱門功能可在您開發軟體時協助您提高生產力，這些功能包括：

- 波浪線和[快速動作](../../ide/quick-actions.md)

   波浪線是波浪底線，可在您鍵入程式碼時，針對錯誤或潛在問題提出警示。 這些視覺提示可讓您立即修正問題，不必等到建置期間或執行程式時發現錯誤。 如果您將滑鼠停留在波浪線，您會看到有關此錯誤的其他資訊。 左邊界也可能會出現燈泡與修正錯誤的動作，稱為「快速動作」。

   ::: moniker range="vs-2017"

   ![Visual Studio 的波浪線](media/squiggles-error.png)

   ::: moniker-end

   ::: moniker range=">=vs-2019"

   ![Visual Studio 的波浪線](media/vs-2019/squiggles-error.png)

   ::: moniker-end

- [重構](../../ide/refactoring-in-visual-studio.md)

   重構作業包括：智慧型重新命名變數、擷取一或多行程式碼放入新方法、變更方法參數順序及更多。

   ::: moniker range="vs-2017"

   ![Visual Studio 中的重構功能表](media/refactoring-menu.png)

   ::: moniker-end

   ::: moniker range=">=vs-2019"

   ![Visual Studio 中的重構功能表](media/vs-2019/refactorings-menu.png)

   ::: moniker-end

- [智慧](../../ide/using-intellisense.md)

   IntelliSense 為一組功能的字詞，會直接在編輯器中顯示有關您程式碼的資訊，而在某些情況下會為您撰寫一些程式碼。 就像內嵌在編輯器中的基本文件，讓您不必在其他位置查閱類型資訊。 IntelliSense 功能會因語言而異。 如需詳細資訊，請參閱 [c # intellisense](../../ide/visual-csharp-intellisense.md)、 [Visual C++ IntelliSense](../../ide/visual-cpp-intellisense.md)、 [JavaScript intellisense](../../ide/javascript-intellisense.md)和 [Visual Basic intellisense](../../ide/visual-basic-specific-intellisense.md)。 下圖顯示 IntelliSense 如何顯示類型的成員清單：

   ::: moniker range="vs-2017"

   ![Visual Studio 成員清單](media/intellisense-list-members.png)

   ::: moniker-end

   ::: moniker range=">=vs-2019"

   ![Visual Studio 成員清單](media/vs-2019/intellisense-list-members.png)

   ::: moniker-end

- 搜尋方塊

   Visual Studio 使用這麼多的功能表、選項和屬性，有時似乎讓人有壓迫感。 搜尋方塊是一個可讓您在 Visual Studio 中快速找到所需項目的絕佳方式。 當您開始鍵入要尋找的項目名稱時，Visual Studio 會列出結果，將您引導至您確實想要去的地方。 如果您需要在 Visual Studio 中新增功能，例如新增對其他程式設計語言的支援，搜尋方塊提供的結果可開啟 Visual Studio 安裝程式，安裝工作負載或個別元件。

   > [!TIP]
   > 按 **Ctrl** + **Q** 作為搜尋方塊的快捷方式。

   ::: moniker range="vs-2017"

   ![Visual Studio 2017 中的 [快速啟動] 搜尋方塊](../media/quick-launch-nuget.png)

   如需詳細資訊，請參閱[快速啟動](../../ide/reference/quick-launch-environment-options-dialog-box.md)。

   ::: moniker-end

   ::: moniker range=">=vs-2019"

   ![Visual Studio 2019 中的搜尋方塊](media/vs-2019/quick-launch.png)

   ::: moniker-end

- [Live Share](/visualstudio/liveshare/)

   即時與其他人共同編輯和偵錯，而無論您的應用程式類型或程式設計語言為何。 您可以立即且安全地共用專案，然後視需要偵錯工作階段、終端機執行個體、localhost Web 應用程式、語音通話等。

- [呼叫階層](../../ide/reference/call-hierarchy.md)

   [呼叫階層] 視窗會顯示呼叫所選方法的方法。 當您考慮要變更或移除方法，或嘗試追蹤 Bug 時，這會是有用的資訊。

   ::: moniker range="vs-2017"

   ![Visual Studio 中的 [呼叫階層] 視窗](media/call-hierarchy.png)

   ::: moniker-end

   ::: moniker range=">=vs-2019"

   ![Visual Studio 中的 [呼叫階層] 視窗](media/vs-2019/call-hierarchy.png)

   ::: moniker-end

- [CodeLens](../../ide/find-code-changes-and-other-history-with-codelens.md)

   CodeLens 可協助您尋找程式碼的參考、程式碼的變更、已連結的 Bug、工作項目、程式碼檢閱和單元測試，全都不用離開編輯器。

   ::: moniker range="vs-2017"

   ![Visual Studio 中的 CodeLens](media/codelens.png)

   ::: moniker-end

   ::: moniker range=">=vs-2019"

   ![Visual Studio 中的 CodeLens](media/vs-2019/codelens.png)

   ::: moniker-end

- [移至定義](../../ide/go-to-and-peek-definition.md)

   [移至定義] 功能就可以直接帶您進入定義函式或類型的位置。

   ::: moniker range="vs-2017"

   ![Visual Studio 2017 中的 [移至定義]](media/go-to-definition-menu.png)

   ::: moniker-end

   ::: moniker range=">=vs-2019"

   ![Visual Studio 2019 中的 [移至定義]](media/vs-2019/go-to-definition-menu.png)

   ::: moniker-end

- [查看定義](../../ide/how-to-view-and-edit-code-by-using-peek-definition-alt-plus-f12.md)

   [查看定義] 視窗會顯示方法或類型的定義，不必實際開啟個別的檔案。

   ::: moniker range="vs-2017"

   ![Visual Studio 中的 [查看定義]](media/peek-definition.png)

   ::: moniker-end

   ::: moniker range=">=vs-2019"

   ![Visual Studio 中的 [查看定義]](media/vs-2019/peek-definition.png)

   ::: moniker-end

## <a name="install-the-visual-studio-ide"></a>安裝 Visual Studio IDE

在本節中，您將建立一個簡單的專案，以試用一些您可透過 Visual Studio 執行的動作。 您將變更色彩佈景主題、使用 [IntelliSense](../../ide/using-intellisense.md) 作為編碼協助工具，以及在程式執行期間偵錯應用程式來查看變數值。

::: moniker range="vs-2017"

若要開始使用，請 [下載 Visual Studio](https://visualstudio.microsoft.com/vs/older-downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=vs+2017+download) ，並將它安裝在您的系統上。 模組安裝程式可讓您選擇並安裝「工作負載」，這些通常是您慣用的程式設計語言或平台所需的幾組功能。 若要遵循 [建立程式](#create-a-program)的步驟，請務必在安裝期間選取 **.NET Core 跨平台開發** 工作負載。

::: moniker-end

::: moniker range=">=vs-2019"

若要開始使用，請 [下載 Visual Studio](https://visualstudio.microsoft.com/downloads) ，並將它安裝在您的系統上。 模組安裝程式可讓您選擇並安裝「工作負載」，這些通常是您慣用的程式設計語言或平台所需的幾組功能。 若要遵循 [建立程式](#create-a-program)的步驟，請務必在安裝期間選取 **.NET Core 跨平台開發** 工作負載。

::: moniker-end

![Visual Studio 安裝程式中的 .NET Core 跨平台開發工作負載](../media/dotnet-core-cross-platform-workload.png)

當您第一次開啟 Visual Studio 時，可以選擇性地使用您的 Microsoft 帳戶或是公司或學校帳戶來[登入](../../ide/signing-in-to-visual-studio.md)。

## <a name="customize-visual-studio"></a>自訂 Visual Studio

您可以個人化 Visual Studio 使用者介面，包括變更預設的色彩佈景主題。

### <a name="change-the-color-theme"></a>變更色彩佈景主題

若要變更為 [深色] 佈景主題：

::: moniker range="vs-2017"

1. 開啟 Visual Studio。

::: moniker-end

::: moniker range=">=vs-2019"

1. 開啟 Visual Studio。 在 [開始] 視窗中，選擇 [不使用程式碼繼續]。

   ![Visual Studio 2019 中的 [開始] 視窗](media/vs-2019/continue-without-code.png)

   IDE 隨即開啟。

::: moniker-end

2. 在功能表列上，選擇 [**工具**  >  **選項**] 以開啟 [**選項**] 對話方塊。

3. 在 [**環境**  >  **一般** 選項] 頁面上，將 **色彩主題** 選取範圍變更為 [**深色**]，然後選擇 **[確定]**。

   ![在 Visual Studio 中將色彩佈景主題變更為深色](media/change-color-theme.png)

   整個 IDE 的色彩佈景主題會變更為 [深色]。

   ::: moniker range="vs-2017"

   ![深色佈景主題的 Visual Studio](../../ide/media/quickstart-personalize-dark-theme.png)

   ::: moniker-end

   ::: moniker range=">=vs-2019"

   ![深色佈景主題的 Visual Studio](media/vs-2019/dark-theme.png)

   ::: moniker-end

### <a name="select-environment-settings"></a>選取環境設定

接下來，我們將設定 Visual Studio 來使用為 Visual Basic 開發人員量身打造的環境設定。

1. 在功能表列上，選擇 [**工具** 匯  >  **入和匯出設定**]。

2. 在 [匯入和匯出設定精靈] 中，選取第一頁上的 [重設所有設定]，然後選擇 [下一步]。

3. 在 [儲存目前設定] 頁面上，選取一個選項來指出是否要儲存目前的設定，然後選擇 [下一步]。 (如果您尚未自訂任何設定，請選取 [否，直接重設設定並覆寫目前的設定])。

4. 在 [選擇預設的設定集合] 頁面上，選擇 [Visual Basic]，然後選擇 [完成]。

5. 在 [重設完成] 頁面上，選擇 [關閉]。

若要了解您可以個人化 IDE 的其他方式，請參閱[個人化 Visual Studio](../../ide/personalizing-the-visual-studio-ide.md)。

## <a name="create-a-program"></a>建立程式

讓我們來深入探討並建立一個簡單的程式。

::: moniker range="vs-2017"

1. 在 Visual Studio 功能表列上，選擇 [檔案]**[新增專案]** > 。

   ![功能表列上的 [檔案] > [新增專案]](media/file-new-project-menu.png)

   [ **新增專案** ] 對話方塊會顯示數個專案 *範本*。 範本包含指定專案類型所需的基本檔案和設定。

1. 選擇 [Visual Basic] 下的 [.NET Core] 類別，然後選擇 [主控台應用程式 (.NET Core)] 範本。 在 [名稱] 文字方塊中，鍵入 **HelloWorld**，然後選取 [確定] 按鈕。

   ![.NET Core 應用程式範本](media/overview-npd.png)

   > [!NOTE]
   > 如果您未看到 [.NET Core] 類別，則需要安裝 [.NET Core 跨平台開發] 工作負載。 若要安裝，請選擇 [新增專案] 對話方塊左下角的 [開啟 Visual Studio 安裝程式] 連結。 在 Visual Studio 安裝程式開啟後，向下捲動並選取 [.NET Core 跨平台開發] 工作負載，然後選取 [修改]。

   Visual Studio 會建立專案。 其為簡單的 "Hello World" 應用程式，會呼叫 <xref:System.Console.WriteLine?displayProperty=nameWithType> 方法來顯示常值字串 "Hello World!" 在主控台 (程式輸出) 視窗中。

   您應該會立即看到類似下列的畫面：

   ![Visual Studio IDE](media/overview-ide-console-app.png)

   應用程式的 Visual Basic 程式碼會顯示在編輯器視窗中，占據大部分的空間。 請注意，系統會將文字自動標示色彩，以表示不同部分的程式碼，例如關鍵字和類型。 此外，程式碼中的垂直小虛線會指出那些大括號彼此成對，而行號則可協助您稍後找出程式碼。 您可以選擇帶方框的小負號來摺疊或展開程式碼區塊。 此程式碼大綱功能可讓您隱藏您不需要的程式碼，有助於讓畫面變得較為簡潔。 專案檔會列在右邊稱作 [方案總管] 的視窗中。

   ![具有紅色方塊的 Visual Studio IDE](media/overview-ide-console-app-red-boxes.png)

   還有其他可用的功能表和工具視窗，但讓我們目前先繼續進行操作。

1. 現在，啟動應用程式。 您可以藉由從功能表列上的 [偵錯] 功能表選擇 [啟動但不偵錯]，來執行此動作。 您也可以按下 **Ctrl** + **F5**。

   ![[偵錯] > [啟動但不偵錯] 功能表](../media/overview-start-without-debugging.png)

   Visual Studio 會建立應用程式，而主控台視窗隨即開啟，並顯示訊息 **Hello World！**。 您現在已有一個執行中的應用程式！

   ![主控台視窗](../media/overview-console-window.png)

1. 若要關閉主控台視窗，請在鍵盤上按下任意鍵。

1. 讓我們將一些其他程式碼新增至應用程式。 在 `Console.WriteLine("Hello World!")` 行前新增下列 Visual Basic 程式碼：

   ```vb
   Console.WriteLine("What is your name?")
   Dim name = Console.ReadLine()
   ```

   此程式碼會在主控台視窗中顯示 **What is your name?**，然後等待使用者輸入某些文字並按下 **Enter** 鍵。

1. 將 `Console.WriteLine("Hello World!")` 行變更為下列程式碼：

   ```vb
   Console.WriteLine("Hello " + name + "!")
   ```

1. 按下 **Ctrl** F5 再次執行應用程式 + ****。

   Visual Studio 會重建應用程式，然後主控台視窗會開啟並提示您輸入您的名稱。

1. 請在主控台視窗中輸入您的名稱，並按下 **ENTER**。

   ![主控台視窗輸入](../media/overview-console-input.png)

1. 按任意鍵以關閉主控台視窗並停止執行程式。

::: moniker-end

::: moniker range=">=vs-2019"

1. 在 Visual Studio 功能表列上，選擇 [檔案]**[新增專案]** > 。

   ![功能表列上的 [檔案] > [新增專案]](media/vs-2019/file-new-project.png)

   [建立新專案] 視窗隨即開啟，並顯示數個專案「範本」。 範本包含指定專案類型所需的基本檔案和設定。

1. 若要尋找所需的範本，在搜尋方塊中鍵入或輸入 **.net core 主控台**。 系統即會根據您所輸入的關鍵字自動篩選可用的範本清單。 您可以從 [語言] 下拉式清單中選擇 [Visual Basic]，進一步篩選範本結果。

1. 選取 [主控台應用程式 (.NET Core)] 範本，然後選擇 [下一步]。

   ![在 Visual Studio 中建立新專案](media/vs-2019/create-new-project.png)

1. 在 [設定新專案] 視窗中，於 [專案名稱] 方塊中輸入 **HelloWorld**、選擇性地變更專案檔的目錄位置，然後選擇 [建立]。

   ![在 Visual Studio 中設定新專案](media/vs-2019/configure-new-project.png)

   Visual Studio 會建立專案。 其為簡單的 "Hello World" 應用程式，會呼叫 <xref:System.Console.WriteLine?displayProperty=nameWithType> 方法來顯示常值字串 "Hello World!" 在主控台 (程式輸出) 視窗中。

   您應該會立即看到類似下列的畫面：

   ![Visual Studio IDE](media/overview-ide-console-app.png)

   應用程式的 Visual Basic 程式碼會顯示在編輯器視窗中，占據大部分的空間。 請注意，系統會將文字自動標示色彩，以表示不同部分的程式碼，例如關鍵字和類型。 此外，程式碼中的垂直小虛線會指出那些大括號彼此成對，而行號則可協助您稍後找出程式碼。 您可以選擇帶方框的小負號來摺疊或展開程式碼區塊。 此程式碼大綱功能可讓您隱藏您不需要的程式碼，有助於讓畫面變得較為簡潔。 專案檔會列在右邊稱作 [方案總管] 的視窗中。

   ![具有紅色方塊的 Visual Studio IDE](media/overview-ide-console-app-red-boxes.png)

   還有其他可用的功能表和工具視窗，但讓我們目前先繼續進行操作。

1. 現在，啟動應用程式。 您可以藉由從功能表列上的 [偵錯] 功能表選擇 [啟動但不偵錯]，來執行此動作。 您也可以按下 **Ctrl** + **F5**。

   ![[偵錯] > [啟動但不偵錯] 功能表](media/vs-2019/start-without-debugging.png)

   Visual Studio 會建立應用程式，而主控台視窗隨即開啟，並顯示訊息 **Hello World！**。 您現在已有一個執行中的應用程式！

   ![顯示 Hello World 訊息之主控台視窗的螢幕擷取畫面。](../media/vs-2019/overview-console-window.png)

1. 若要關閉主控台視窗，請在鍵盤上按下任意鍵。

1. 讓我們將一些其他程式碼新增至應用程式。 在 `Console.WriteLine("Hello World!")` 行前新增下列 Visual Basic 程式碼：

   ```vb
   Console.WriteLine("What is your name?")
   Dim name = Console.ReadLine()
   ```

   此程式碼會在主控台視窗中顯示 **What is your name?**，然後等待使用者輸入某些文字並按下 **Enter** 鍵。

1. 將 `Console.WriteLine("Hello World!")` 行變更為下列程式碼：

   ```vb
   Console.WriteLine("Hello " + name + "!")
   ```

1. 按下 **Ctrl** F5 再次執行應用程式 + ****。

   Visual Studio 會重建應用程式，然後主控台視窗會開啟並提示您輸入您的名稱。

1. 請在主控台視窗中輸入您的名稱，並按下 **ENTER**。

   ![主控台視窗的螢幕擷取畫面，其中顯示您的名稱問題和應用程式的回應。](../media/vs-2019/overview-console-input.png)

1. 按任意鍵以關閉主控台視窗並停止執行程式。

::: moniker-end

## <a name="use-refactoring-and-intellisense"></a>使用重構和 IntelliSense

讓我們看看[重構](../../ide/refactoring-in-visual-studio.md)和 [IntelliSense](../../ide/using-intellisense.md) 這兩種方式如何協助您更有效率地撰寫程式碼。

首先，請重新命名 `name` 變數：

1. 按兩下 `name` 變數來選取它。

2. 鍵入變數的新名稱 **username**。

   請注意，變數周圍會出現一個灰色方塊，而邊界會出現一個燈泡。

3. 選取燈泡圖示以顯示可用的[快速動作](../../ide/quick-actions.md)。 選取 [將 'name' 重新命名為 'username']。

   ![重新命名 Visual Studio 中的動作](media/rename-quick-action.png)

   此變數會在專案中重新命名，在我們的案例中只有兩個位置。

4. 現在，讓我們看看 IntelliSense。 在 `Console.WriteLine("Hello " + username + "!")` 行下面，輸入下列程式碼片段：

    ```vb
   Dim now = Date.
   ```

   一個方塊會顯示 <xref:System.DateTime> 類別的成員。 此外，目前選取成員的描述會顯示在另一個方塊中。

   ![Visual Studio 中的 IntelliSense 清單成員](media/intellisense-list-members.png)

5. 按兩下名為 **Now** 的成員 (類別的屬性) 或使用上下方向鍵選取它並按下 **Tab** 來選取此成員。

6. 在下方輸入或貼上下列程式碼：

   ```vb
   Dim dayOfYear = now.DayOfYear
   Console.Write("Day of year: ")
   Console.WriteLine(dayOfYear)
   ```

   > [!TIP]
   > <xref:System.Console.Write%2A?displayProperty=nameWithType> 與 <xref:System.Console.WriteLine%2A?displayProperty=nameWithType> 稍有不同，它不會在列印之後新增行結束字元。 這表示傳送至輸出的下一段文字會列印在同一行。 您可以將滑鼠移至程式碼中每個方法上方來查看其描述。

7. 接下來，我們將再使用一次重構，讓程式碼更精簡。 按一下 `Dim now = Date.Now` 行中的變數 `now`。

   請注意，該行的邊界會出現一個小螺絲起子圖示。

8. 按一下螺絲起子圖示，以查看 Visual Studio 所提供的建議。 在此案例中，它會顯示[內嵌暫存變數](../../ide/reference/inline-temporary-variable.md)重構以移除程式碼，而不會變更程式碼的整體行為：

   ![Visual Studio 中的內嵌暫存變數重構](media/inline-temporary-variable-refactoring.png)

9. 按一下 [內嵌暫存變數] 以重構程式碼。

::: moniker range="vs-2017"

10. 按下 **Ctrl** + **F5** 再次執行程式。 輸出看起來會像這樣：

    ![含有程式輸出的主控台視窗](../media/overview-console-final.png)

::: moniker-end

::: moniker range=">=vs-2019"

10. 按下 **Ctrl** + **F5** 再次執行程式。 輸出看起來會像這樣：

    ![含有程式輸出的主控台視窗](../media/vs-2019/overview-console-final.png)

::: moniker-end

## <a name="debug-code"></a>偵錯程式碼

當您撰寫程式碼時，必須執行並測試它，以找出 Bug。 Visual Studio 偵錯系統可讓您以一次一個陳述式的方式逐步偵錯程式碼，並一邊檢查變數。 您可以設定「中斷點」，其會停止執行特定行的程式碼。 您可以觀察變數值如何隨著程式碼執行而變更，以及更多。

讓我們來設定中斷點，以查看程式「進行」期間的 `username` 變數值。

1. 尋找程式碼行 `Console.WriteLine("Hello " + username + "!")`。 若要設定這行程式碼的中斷點，讓程式在這行暫停執行，請按一下編輯器的左邊界。 您也可以按一下該行程式碼的任何位置，然後按下 **F9** 鍵。

   左邊界會出現一個紅色圓圈，並以紅色醒目顯示程式碼。

   ![Visual Studio 中程式碼行的中斷點](media/breakpoint.png)

1. 選取 [ **Debug**  >  **開始調試** 程式] 或按下 **F5** 來開始進行偵錯工具。

1. 在主控台視窗出現並要求您的名稱時，鍵入名稱並按 **Enter** 鍵。

   焦點會返回 Visual Studio 程式碼編輯器，並以黃色醒目提示具有中斷點的程式碼。 這表示程式要執行的下一行程式碼。

1. 將滑鼠移至 `username` 變數上方以查看其值。 或者，您可以在 `username` 上按一下滑鼠右鍵，然後選取 [新增監看式] 將變數新增至 [監看式] 視窗，您也可以在此查看其值。

   ![Visual Studio 偵錯期間的變數值](media/debugging-variable-value.png)

1. 若要讓程式執行到完成，請再按一次 **F5** 鍵。

如需有關 Visual Studio 中之 偵錯的更多詳細資料，請參閱[偵錯工具功能導覽](../../debugger/debugger-feature-tour.md)。

## <a name="next-steps"></a>後續步驟

遵循以下其中一篇簡介文章，進一步探索 Visual Studio：

> [!div class="nextstepaction"]
> [了解如何使用程式碼編輯器](tutorial-editor.md)

> [!div class="nextstepaction"]
> [了解專案與解決方案](tutorial-projects-solutions.md)

## <a name="see-also"></a>另請參閱

- 探索[更多 Visual Studio 功能](../../ide/advanced-feature-overview.md)
- 瀏覽 [visualstudio.microsoft.com](https://visualstudio.microsoft.com/vs/)
- 閱讀 [Visual Studio 部落格](https://devblogs.microsoft.com/visualstudio/)
