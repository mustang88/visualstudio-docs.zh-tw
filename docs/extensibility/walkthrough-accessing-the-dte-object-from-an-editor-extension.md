---
title: 從編輯器延伸模組存取 DTE 物件
ms.date: 04/24/2019
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], new - getting the DTE object
ms.assetid: c1f40bab-c6ec-45b0-8333-ea5ceb02a39d
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: e37bdb21b7c8132f0dfb166d19e03d36e838245d
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/02/2020
ms.locfileid: "80697655"
---
# <a name="walkthrough-access-the-dte-object-from-an-editor-extension"></a>逐步解說：從編輯器延伸模組存取 DTE 物件

在 Vspackage 中，您可以 <xref:Microsoft.VisualStudio.Shell.Package.GetService%2A> 使用 dte 物件的型別來呼叫方法，以取得 dte 物件。 在 Managed Extensibility Framework (MEF) 擴充功能的情況下，您可以匯入， <xref:Microsoft.VisualStudio.Shell.SVsServiceProvider> 然後 <xref:Microsoft.VisualStudio.Shell.ServiceProvider.GetService%2A> 使用的類型來呼叫方法 <xref:EnvDTE.DTE> 。

## <a name="prerequisites"></a>先決條件

若要依照本逐步解說執行作業，您必須安裝 Visual Studio SDK。 如需詳細資訊，請參閱 [VISUAL STUDIO SDK](../extensibility/visual-studio-sdk.md)。

## <a name="get-the-dte-object"></a>取得 DTE 物件

1. 建立 c # VSIX 專案，並將它命名為 **DTETest**。 加入 **編輯器分類** 專案範本，並將它命名為 **DTETest**。

   如需詳細資訊，請參閱 [使用編輯器專案範本建立延伸](../extensibility/creating-an-extension-with-an-editor-item-template.md)。

::: moniker range=">=vs-2019"

2. 將下列元件參考新增至專案：

    - VisualStudio 架構
    - VisualStudio，不變的10。0

3. 在 *DTETestProvider.cs* 檔案中，新增下列指示詞 `using` ：

    ```csharp
    using EnvDTE;
    using Microsoft.VisualStudio.Shell;
    ```

4. 在 `DTETestProvider` 類別中，匯入 <xref:Microsoft.VisualStudio.Shell.SVsServiceProvider> 。

    ```csharp
    [Import]
    internal SVsServiceProvider ServiceProvider = null;
    ```

5. 在 `GetClassifier()` 方法中，于語句之前加入下列程式碼 `return` ：

    ```csharp
   ThreadHelper.ThrowIfNotOnUIThread();
   DTE dte = (DTE)ServiceProvider.GetService(typeof(DTE));
   ```

::: moniker-end

::: moniker range="vs-2017"

2. 將下列元件參考新增至專案：

   - EnvDTE
   - VisualStudio 架構

3. 在 *DTETestProvider.cs* 檔案中，新增下列指示詞 `using` ：

    ```csharp
    using EnvDTE;
    using Microsoft.VisualStudio.Shell;
    ```

4. 在 `DTETestProvider` 類別中，匯入 <xref:Microsoft.VisualStudio.Shell.SVsServiceProvider> 。

    ```csharp
    [Import]
    internal SVsServiceProvider ServiceProvider = null;
    ```

5. 在 `GetClassifier()` 方法中，于語句之前加入下列程式碼 `return` ：

    ```csharp
   DTE dte = (DTE)ServiceProvider.GetService(typeof(DTE));
   ```

::: moniker-end

## <a name="see-also"></a>另請參閱

- [語言服務及編輯器擴充點](../extensibility/language-service-and-editor-extension-points.md)
- [使用 DTE 啟動 Visual Studio](launch-visual-studio-dte.md)
