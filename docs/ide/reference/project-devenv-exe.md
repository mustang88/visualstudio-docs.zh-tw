---
title: -Project (devenv.exe)
description: 瞭解如何使用專案 devenv 命令列參數來識別指定之方案設定內的單一專案，以建立、清除、重建或部署專案。
ms.custom: SEO-VS-2020
ms.date: 12/10/2018
ms.topic: reference
helpviewer_keywords:
- /Project Devenv switch
- projects [Visual Studio], rebuilding
- projects [Visual Studio], building
- deployment projects, specifying
- Project Devenv switch (/Project)
- Devenv, /Project switch
- projects [Visual Studio], cleaning
ms.assetid: 8b07859c-3439-436d-9b9a-a8ee744eee30
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 90c1cdf37ddda7209b4f951e42ad07720e5cc40b
ms.sourcegitcommit: 967c2f8c1b3f805cf42c0246389517689d971b53
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/25/2020
ms.locfileid: "96040104"
---
# <a name="project-devenvexe"></a>/Project (devenv.exe)

識別所指定方案組態內要建置、清除、重建或部署的單一專案。

## <a name="syntax"></a>語法

```shell
devenv SolutionName {/Build|/Clean|/Deploy|/Rebuild} [SolnConfigName [/Project ProjName [/ProjectConfig ProjConfigName]] [/Out OutputFilename]]
```

## <a name="arguments"></a>引數

- *SolutionName*

  必要。 方案檔的完整路徑和名稱。

- {`/Build`|`/Clean`|`/Deploy`|`/Rebuild`}

  必要。 [建置](build-devenv-exe.md)、[清除](clean-devenv-exe.md)、[部署](deploy-devenv-exe.md)或[重建](rebuild-devenv-exe.md)專案。

- *SolnConfigName*

  選擇性。 將套用至 *SolutionName* 中所指定方案的方案組態名稱 (例如 `Debug` 或 `Release`)。 如果有多個方案平台可供使用，您也必須指定平台 (例如 `Debug|Win32`)。 如果未指定這個引數或其為空字串 (`""`)，則工具會使用方案的作用中組態。

- `/Project` *專案名稱*

  選擇性。 方案中專案檔的路徑和名稱。 您可以輸入專案的顯示名稱或從 *SolutionName* 資料夾到專案檔的相對路徑。 您也可以輸入專案檔的完整路徑和名稱。

- `/ProjectConfig` *ProjConfigName*

  選擇性。 要套用至所指定 `/Project` 的專案組建組態名稱 (例如 `Debug` 或 `Release`)。 如果有多個方案平台可供使用，您也必須指定平台 (例如 `Debug|Win32`)。

- `/Out`*OutputFilename*

  選擇性。 您要將工具的輸出傳送到其中的檔案名稱。 如果檔案已經存在，工具就會將輸出附加至檔案結尾。

## <a name="remarks"></a>備註

- 必須用於 `devenv` `/Build` 、 `/Clean` 、 `/Rebuild` 或 `/Deploy` 命令的一部分。

- 請以雙引號括住包含空格的字串。

- 組建的摘要資訊 (包括錯誤) 可顯示在 [命令] 視窗中，或使用 `/Out` 參數指定的任何記錄檔中。

## <a name="example"></a>範例

此範例會使用 `MySolution` 內的 `Debug` 專案組建組態來建置專案 `CSharpWinApp`。

```shell
devenv "%USERPROFILE%\source\repos\MySolution\MySolution.sln" /build Debug /project "CSharpWinApp\CSharpWinApp.csproj" /projectconfig Debug
```

## <a name="see-also"></a>另請參閱

- [Devenv 命令列參數](../../ide/reference/devenv-command-line-switches.md)
- [/ProjectConfig ( # A0) ](../../ide/reference/projectconfig-devenv-exe.md)
- [/Build ( # A0) ](../../ide/reference/build-devenv-exe.md)
- [/Clean ( # A0) ](../../ide/reference/clean-devenv-exe.md)
- [/Rebuild ( # A0) ](../../ide/reference/rebuild-devenv-exe.md)
- [/Deploy ( # A0) ](../../ide/reference/deploy-devenv-exe.md)
- [/Out ( # A0) ](../../ide/reference/out-devenv-exe.md)
