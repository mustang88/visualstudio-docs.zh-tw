---
title: 如何：新增建立者方法 |Microsoft Docs
description: 瞭解如何新增建立者方法，該方法會將新的資料加入至 SharePoint 中的商務資料連線 (BDC) 服務之實體的資料來源。
ms.custom: SEO-VS-2020
ms.date: 02/02/2017
ms.topic: how-to
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- BDC [SharePoint development in Visual Studio], Creator
- BDC [SharePoint development in Visual Studio], adding entity instances
- Business Data Connectivity service [SharePoint development in Visual Studio], adding entities
- Business Data Connectivity service [SharePoint development in Visual Studio], adding entity instances
- BDC [SharePoint development in Visual Studio], adding entities
- Business Data Connectivity service [SharePoint development in Visual Studio], Creator
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 790b4265b232c71ff3e0613cffcb45e710081fa3
ms.sourcegitcommit: 8e9c38da7bcfbe9a461c378083846714933a0e1e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/09/2020
ms.locfileid: "96915449"
---
# <a name="how-to-add-a-creator-method"></a>如何：新增建立者方法
  建立者方法會將新的資料加入至實體的資料來源。 當使用者在以模型為基礎之清單的 **功能區** 上選擇 [**新增專案**] 按鈕時， (BDC) 服務的商務資料連線會呼叫這個方法。 如需詳細資訊，請參閱 [設計商務資料連線模型](../sharepoint/designing-a-business-data-connectivity-model.md)。

### <a name="to-add-a-creator-method"></a>新增建立者方法

1. 在 **BDC 設計** 工具上，選擇實體。

2. 在功能表列上，選擇 [**查看**  >  **其他 Windows**  > **BDC 方法詳細資料**]。

    [ **BDC 方法詳細資料** ] 視窗隨即開啟。 如需該視窗的詳細資訊，請參閱 [BDC 模型設計工具總覽](../sharepoint/bdc-model-design-tools-overview.md)。

3. 在 [ **加入方法** ] 清單中，選擇 [ **建立建立者方法**]。

    Visual Studio 將下列元素加入至模型，而且這些專案會出現在 [ **BDC 方法詳細資料** ] 視窗中。

   - 名為 **Create** 的方法。

   - 方法的輸入參數。

   - 方法的傳回參數。

   - 參數的類型描述元。

   - 方法的方法實例。

     如需詳細資訊，請參閱 [設計商務資料連線模型](../sharepoint/designing-a-business-data-connectivity-model.md)。

4. 在 **方案總管** 中，開啟針對實體所產生之服務程式代碼檔案的快捷方式功能表，然後選擇 [ **View code**]。

    Entity service 程式碼檔案會在程式碼編輯器中開啟。 如需實體服務程式代碼檔案的詳細資訊，請參閱 [建立商務資料連線模型](../sharepoint/creating-a-business-data-connectivity-model.md)。

5. 將程式碼加入至將資料加入至資料來源的建立者方法。 下列範例會在 AdventureWorks 範例資料庫中加入 SQL Server 的連絡人。

   > [!NOTE]
   > 將欄位的值取代為 `ServerName` 您伺服器的名稱。

    [!code-csharp[SP_BDC#4](../sharepoint/codesnippet/CSharp/SP_BDC/bdcmodel1/contactservice.cs#4)]
    [!code-vb[SP_BDC#4](../sharepoint/codesnippet/VisualBasic/sp_bdc/bdcmodel1/contactservice.vb#4)]

## <a name="see-also"></a>另請參閱
- [設計商務資料連線模型](../sharepoint/designing-a-business-data-connectivity-model.md)
- [如何：加入搜尋工具方法](../sharepoint/how-to-add-a-finder-method.md)
- [如何：新增特定搜尋工具方法](../sharepoint/how-to-add-a-specific-finder-method.md)
- [如何：加入刪除者方法](../sharepoint/how-to-add-a-deleter-method.md)
- [如何：加入更新程式方法](../sharepoint/how-to-add-an-updater-method.md)
- [BDC 模型設計工具總覽](../sharepoint/bdc-model-design-tools-overview.md)
- [如何：將參數加入至方法](../sharepoint/how-to-add-a-parameter-to-a-method.md)
- [如何：定義方法實例](../sharepoint/how-to-define-a-method-instance.md)
