---
title: 設定瀑布圖 | Microsoft IntelliTest 開發人員測試工具
description: 瞭解設定瀑布圖，此設定會在元件、裝置和流覽層級組織設定。
ms.custom: SEO-VS-2020
ms.date: 05/02/2017
ms.topic: conceptual
helpviewer_keywords:
- IntelliTest, Settings waterfall
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
author: mikejo5000
ms.openlocfilehash: bdb053218b65924abfa64053a8a3c7e9e0543d49
ms.sourcegitcommit: 9ce13a961719afbb389fa033fbb1a93bea814aae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/30/2020
ms.locfileid: "96329506"
---
# <a name="settings-waterfall"></a>設定瀑布圖

設定瀑布圖的概念，表示使用者可以在 **組件**、**裝置** 和 **探索** 層級指定設定：

* 組件 - [PexAssemblySettings](attribute-glossary.md#pexassemblysettings)
* 裝置 - [PexClass](attribute-glossary.md#pexclass)
* 探索 - [PexExplorationAttributeBase](attribute-glossary.md#pexexplorationattributebase)

在 **組件** 層級指定的設定會影響該組件下的所有裝置和探索。 在 **裝置** 層級指定的設定會影響該裝置下的所有探索。 子設定優先&mdash;如果 **組件** 和 **裝置** 層級都定義了設定，則會使用 **裝置** 的設定。

請注意，某些設定專屬於 **組件** 層級或 **裝置** 層級。

**範例**

```csharp
using Microsoft.Pex.Framework;

[assembly: PexAssemblySettings(MaxBranches = 1000)] // we override the default value of maxbranches

namespace MyTests
{
    [PexClass(MaxBranches = 500)] // we override the 1000 value and set maxbranches to 500
    public partial class MyTests
    {
        [PexMethod(MaxBranches = 100)] // we override again, maxbranches = 100
        public void MyTest(...) { ... }
    }
}
```

## <a name="got-feedback"></a>有人給您意見嗎？

在[開發人員社群](https://developercommunity.visualstudio.com/content/idea/post.html?space=8)上張貼您的意見與功能建議。
