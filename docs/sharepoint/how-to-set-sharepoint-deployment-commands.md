---
title: 如何：設定 SharePoint 部署命令 |Microsoft Docs
description: 瞭解如何藉由設定 SharePoint 預先部署和部署後命令來自訂部署流程。
ms.custom: SEO-VS-2020
ms.date: 02/02/2017
ms.topic: how-to
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, deploying
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: fc1da67206e5e5c9fde1b5c595424239d1685ac7
ms.sourcegitcommit: 2244665d5a0e22d12dd976417f2a782e68684705
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/28/2020
ms.locfileid: "96304393"
---
# <a name="how-to-set-sharepoint-deployment-commands"></a>如何：設定 SharePoint 部署命令
  您可以藉由設定部署前和部署後命令來自訂部署流程。 當您從 Visual Studio 中的 SharePoint 方案進行調試時，這些命令會在其他部署動作之前和之後執行。

### <a name="to-add-a-pre-deployment-command"></a>新增預先部署命令

1. 在功能表列上，選擇 [**專案**  >  **\<*ProjectName*> 屬性**]。

2. 選擇 [ **SharePoint** ] 索引標籤。

3. 在 [ **預先部署命令列** ] 文字方塊中，輸入 MS-DOS 或 MSBuild 命令以自訂此步驟。

     例如，若要在部署完成之前列出目錄內容，請輸入 **dir**。

### <a name="to-add-a-post-deployment-command"></a>新增部署後命令

1. 在功能表列上，選擇 [**專案**  >  **\<*ProjectName*> 屬性**]。

2. 選擇 [ **SharePoint** ] 索引標籤。

3. 在 [ **部署後命令列** ] 文字方塊中，輸入 MS-DOS 或 MSBuild 命令以自訂此步驟。

     例如，若要在部署完成後列出目錄內容，請輸入 **dir**。 若要使用 MSBuild 變數從組建目錄複寫元件，請輸入 **copy $ (TargetPath) c:\DeploymentDirectory**。

## <a name="see-also"></a>另請參閱
- [封裝和部署 SharePoint 方案](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)
