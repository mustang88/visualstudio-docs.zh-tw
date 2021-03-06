---
title: '準備進行 c #、F # 和 VB 專案的調試 |Microsoft Docs'
ms.custom: seodec18
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [Visual Basic]
- debug builds, project settings
- Visual C# projects, debugging
- Visual Basic projects, debugging
- debugging [C#]
- debugger, settings by project type
ms.assetid: 7a0535f6-1cd4-4b51-ad34-f4a45b9f1ce3
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 90e108ddd64a9b520c8ae1d0c86e416dea64e5be
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/02/2020
ms.locfileid: "72738123"
---
# <a name="debugging-preparation-c-f-and-visual-basic-project-types"></a>偵錯準備：C#、F# 和 Visual Basic 專案類型
本章節內的主題說明如何偵錯由 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 專案範本所建立的 C#、F# 和 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 專案類型。

 請注意，建立 Dll 做為其輸出的專案類型，因為它們所共用的常見功能而被分組到 [偵錯工具 Dll 專案](../debugger/debugging-dll-projects.md) 中。

## <a name="in-this-section"></a>本節內容
 [建議的屬性設定](../debugger/managed-debugging-recommended-property-settings.md) 本節說明 c #、F # 和 Visual Basic 專案的建議調試相關屬性設定。

 [Windows Forms 應用程式](../debugger/debugging-preparation-windows-forms-applications.md) 描述 Windows 應用程式專案，並提供偵錯工具、變更預設的偵錯工具設定，以及在之外啟動應用程式，以及 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 附加至它的指示。

 [主控台專案](../debugger/debugging-preparation-console-projects.md) 提供偵錯工具 c # 或 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 主控台應用程式的其他考慮。 包括指定命令列引數、從命令提示字元啟動應用程式、寫入至 [輸出] 視窗，和 [主控台] 視窗的疑難排解。

 [Windows 服務](../debugger/debugging-preparation-windows-services.md) 描述 Windows 服務，並提供對 Windows 服務應用程式進行偵錯工具的連結。

## <a name="related-sections"></a>相關章節
 [偵錯工具設定和準備](../debugger/debugger-settings-and-preparation.md) 涵蓋使用偵錯工具來對程式進行程式設計時，必須執行的設定和準備 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 。

 [Managed 程式碼的調試](../debugger/debugging-managed-code.md) 程式涵蓋以 managed 程式碼撰寫之應用程式的常見偵錯工具問題和技術。

## <a name="see-also"></a>另請參閱
- [偵錯工具安全性](../debugger/debugger-security.md)