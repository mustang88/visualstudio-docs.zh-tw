---
title: '從 FxCop 遷移至來源分析 ( .NET 分析器) '
ms.custom: SEO-VS-2020
description: 瞭解如何首次分析程式碼，或如何從二進位分析 (FxCop) 遷移至使用來源分析 ( .NET 分析器) 來分析 managed 程式碼的新方法。
ms.date: 03/06/2020
ms.topic: conceptual
f1_keywords:
- vs.projectpropertypages.codeanalysis
helpviewer_keywords:
- FxCop, migration
- legacy analysis, migration
- source code analysis, migration
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 84acec58ed78884f0b037950fa25ce40f6adcbfc
ms.sourcegitcommit: 967c2f8c1b3f805cf42c0246389517689d971b53
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/25/2020
ms.locfileid: "96112210"
---
# <a name="migrate-from-legacy-analysis-fxcop-to-source-analysis-net-analyzers"></a>從舊版分析 (FxCop) 遷移至來源分析 ( .NET 分析器) 

.NET Compiler Platform ( "Roslyn" 的來源分析 ) 分析器會取代 managed 程式碼的 [舊版分析](../code-quality/code-analysis-for-managed-code-overview.md) 。 針對較新的專案範本（例如 .NET Core 和 .NET Standard 專案），無法使用舊版分析。

已針對 .NET 分析器（一組 Roslyn 程式碼分析器）重寫了許多舊版分析 (FxCop) 規則。 Roslyn 分析器會在編譯器執行期間執行以程式碼為基礎的分析。 分析器結果會與編譯器結果一併回報。

如需舊版分析和來源分析之間差異的詳細資訊，請參閱下列各項：

- [原始碼分析與舊版分析](../code-quality/net-analyzers-faq.md#whats-the-difference-between-legacy-fxcop-and-net-analyzers)

- [.NET 分析器的常見問題](../code-quality/net-analyzers-faq.md)

## <a name="migration"></a>遷移

若要遷移至來源分析，請 [啟用或安裝 .net 分析器](install-net-analyzers.md)。 如同舊版分析規則違規，原始程式碼分析違規會出現在 Visual Studio 的 [錯誤清單] 視窗中。 此外，來來源程式代碼分析違規也會在程式碼編輯器中顯示為有問題的程式碼下的 *波浪線* 。 波形曲線色彩取決於規則的[嚴重性設定](../code-quality/use-roslyn-analyzers.md#configure-severity-levels)。 若要查看已移植至新 .NET 分析器之規則的狀態，請參閱 [移植和 unported 規則](../code-quality/fxcop-rule-port-status.md)。

> [!NOTE]
> 在 Visual Studio 2019 16.8 和 .NET 5.0 之前，這些分析器會以 `Microsoft.CodeAnalysis.FxCopAnalyzers` [NuGet 套件](https://www.nuget.org/packages/Microsoft.CodeAnalysis.FxCopAnalyzers)的形式傳送。 從 Visual Studio 2019 16.8 和 .NET 5.0 開始，這些分析器會 [隨附于 .NET SDK](/dotnet/fundamentals/code-analysis/overview)。 它們也可以作為 `Microsoft.CodeAnalysis.NetAnalyzers` [NuGet 套件](https://www.nuget.org/packages/Microsoft.CodeAnalysis.NetAnalyzers)。 如需詳細資訊，請參閱 [從 FxCop 分析器遷移至 .net 分析器](migrate-from-fxcop-analyzers-to-net-analyzers.md)。

## <a name="configuration"></a>設定

若要深入瞭解如何設定 .NET 分析器：

- 若要設定 .NET 分析器，請參閱 [設定 .net 分析器](/dotnet/fundamentals/code-analysis/code-quality-rule-options)。

- 若要瞭解如何使用預先定義的規則搭配 EditorConfig 或規則集檔案來設定分析器，請參閱 [啟用規則的類別](/dotnet/fundamentals/code-analysis/code-quality-rule-options)。

## <a name="see-also"></a>另請參閱

- [從 FxCop 分析器遷移至 .NET 分析器](migrate-from-fxcop-analyzers-to-net-analyzers.md)
