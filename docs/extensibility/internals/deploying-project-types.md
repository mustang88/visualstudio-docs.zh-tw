---
title: 部署專案類型 |Microsoft Docs
description: 瞭解如何使用新的專案類型匯總工具部署 managed 程式碼專案類型，以及在 Visual Studio SDK 中重新發佈 Windows Installer 套件。
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- projects [Visual Studio SDK], managed-code
- projects [Visual Studio SDK], aggregator
ms.assetid: 7f132f67-8589-464c-90dc-0d57ae02aa8f
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: b1b015f29b6521482013a77bbcf7c44d8a79afa6
ms.sourcegitcommit: 9ce13a961719afbb389fa033fbb1a93bea814aae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/30/2020
ms.locfileid: "96329870"
---
# <a name="deploy-project-types"></a>部署專案類型
[!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] 會安裝新的專案類型匯總工具 (*ProjectAggregator2.dll*) 以及用於轉 *散發 (ProjectAggregator2.msi) 的* Windows Installer 套件。 您必須針對 managed 程式碼專案類型使用新的匯總工具。 ProjectAggregator2 可解決專案匯總工具中 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 的限制，使 managed 程式碼專案類型無法正常運作。 下列步驟說明如何將 VSPackage 變更為使用新的匯總工具。

1. 從您的方案中移除 NativeHierarchyWrapper 專案。

2. 從您的安裝程式中移除任何 NativeHierarchyWrapper 的二進位檔。

3. 將 *ProjectAggregator2.msi* 新增至您的安裝程式。
