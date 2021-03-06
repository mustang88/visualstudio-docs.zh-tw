---
title: require-azureartifactscredentialprovider
description: devinit 工具需要-azureartifactscredentialprovider。
ms.date: 11/20/2020
ms.topic: reference
author: andysterland
ms.author: andster
manager: jillfra
ms.workload:
- multiple
monikerRange: '>= vs-2019'
ms.prod: visual-studio-windows
ms.technology: devinit
ms.openlocfilehash: ad39bc070841dae5202abca8ca4624927a100f23
ms.sourcegitcommit: 02f14db142dce68d084dcb0a19ca41a16f5bccff
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/23/2020
ms.locfileid: "95440385"
---
# <a name="require-azureartifactscredentialprovider"></a>require-azureartifactscredentialprovider

此 `require-azureartifactscredentialprovider` 工具會安裝 Azure Artifacts 認證提供者。 Azure Artifacts 認證提供者會自動取得將 NuGet 套件還原為 .NET 開發工作流程一部分所需的認證。 如需 Azure Artifacts 認證提供者的詳細資訊，請參閱 [這裡](https://github.com/microsoft/artifacts-credprovider/blob/master/README.md)。

## <a name="usage"></a>使用方式

如果 `input` 和 `additionalOptions` 屬性都省略或空白，則工具將會遵循以下詳述的 [預設](#default-behavior) 行為。

| 名稱                                             | 類型   | 必要 | 值                                                                                |
|--------------------------------------------------|--------|----------|--------------------------------------------------------------------------------------|
| **評論**                                     | 字串 | No       | 選擇性批註屬性。 未使用。                                                |
| [**輸入**](#input)                              | 字串 | No       | 未使用。 如需詳細資料，請參閱下列 [輸入](#input) 。 |
| [**additionalOptions**](#additional-options)     | 字串 | No       | 請參閱下方的 [其他選項](#additional-options) 以取得詳細資料。                     |

### <a name="input"></a>輸入

未使用。 如果有提及，會忽略任何輸入。

### <a name="additional-options"></a>其他選項

其他選項會依原樣傳遞至認證提供者命令。

### <a name="default-behavior"></a>預設行為

工具的預設行為 `require-azureartifactscredentialprovider` 是安裝最新版本的 Azure Artifacts 認證提供者。

## <a name="example-usage"></a>使用方式範例
以下是如何使用執行的範例 `require-azureartifactscredentialprovider` `.devinit.json` 。

#### <a name="devinitjson-that-will-install-azure-artifacts-credential-provider"></a>.devinit.js將會安裝 Azure Artifacts 認證提供者：
```json
{
    "$schema": "https://json.schemastore.org/devinit.schema-3.0",
    "run": [
        {
            "tool": "require-azureartifactscredentialprovider",
        }
    ]
}
```
