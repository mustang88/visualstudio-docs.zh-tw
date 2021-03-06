---
title: 專案和方案
description: 本文件概述 Visual Studio for Mac 中的專案和方案。
ms.topic: overview
author: heiligerdankgesang
ms.author: dominicn
ms.date: 11/09/2020
ms.assetid: 8254505D-D96E-48BD-8A5E-CF6A917897EA
ms.openlocfilehash: c52b8513937505b40d17f7cd9fc05d9cf6a47941
ms.sourcegitcommit: 2cf3a03044592367191b836b9d19028768141470
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/11/2020
ms.locfileid: "94493396"
---
# <a name="projects-and-solutions-in-visual-studio-for-mac"></a>Visual Studio for Mac 中的專案和解決方案

本文能提供 Visual Studio for Mac 中「專案」和「方案」的概念概觀。

> [!NOTE] 
> 本主題適用於 Visual Studio for Mac。 針對 Windows 上的 Visual Studio，請參閱 [Visual Studio 中的專案和方案](/visualstudio/ide/solutions-and-projects-in-visual-studio)。

## <a name="projects"></a>專案

當您要在 Visual Studio for Mac 中建立新的應用程式和網站之類的內容時，您會以專案作為開始。 專案會包含編譯可執行檔、程式庫或網站所需的所有檔案 (原始程式碼、影像、資料檔案等等)。

專案是由某個檔案所定義 (例如針對 C# 專案為 `.csproj`)，其包含能定義檔案和資料夾階層的 XML、針對檔案和專案特定設定 (例如建置設定) 的路徑。

當 Visual Studio for Mac 載入專案時，方案視窗會使用專案檔來顯示專案中的檔案和資料夾。 在編譯期間，MSBuild 會從專案檔讀取設定來建立可執行檔。

## <a name="solutions"></a>方案

「方案」是指能將一或多個相關專案分組在一起的容器。 方案是由具有自己獨特格式的文字檔 (副檔名為 `.sln`) 所描述；它通常不適合手動編輯。

## <a name="managing-projects-in-the-solution-window"></a>在方案視窗中管理專案

一旦建立或載入專案之後，您就可以使用 [方案] 視窗來查看和管理專案或方案，以及中包含的檔案。 下圖顯示包含兩個專案之 .NET Core 方案的 [方案] 視窗：

![具有多個專案的範例方案](media/solution-example.png)

您可以按兩下專案或方案名稱，或是以滑鼠右鍵按一下並選擇 [選項]，來管理專案和方案的屬性。

[管理方案和專案屬性](managing-solutions-and-project-properties.md)一文提供這些選項的詳細資訊。

## <a name="see-also"></a>請參閱

- [Visual Studio 中的方案和專案 (Windows)](/visualstudio/ide/solutions-and-projects-in-visual-studio)
