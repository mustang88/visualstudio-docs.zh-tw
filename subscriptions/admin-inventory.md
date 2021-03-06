---
title: Visual Studio 訂用帳戶中的生產前清查 |Visual Studio Marketplace
author: evanwindom
ms.author: v-evwin
manager: cabuschl
ms.assetid: 7d74e113-8fb2-490e-8502-48cce7b1327a
ms.date: 10/22/2020
ms.topic: conceptual
description: 瞭解管理員負責執行生產前清查的責任
ms.openlocfilehash: b464a7d9cfa8c802cd2367c5c7d0e76141583f3a
ms.sourcegitcommit: bf5e2bba5acdcf05869b861211f8bb755081e5ce
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/23/2020
ms.locfileid: "92467423"
---
# <a name="inventory-of-pre-production-environment"></a>清查生產前環境
Visual Studio 訂用帳戶透過計算使用者　(而不是裝置) 來簡化資產管理。

Visual Studio 系統管理員必須將 Visual Studio 訂閱指派給 **特定的命名個人**。 **不允許**像是 Dev1、Dev2 或使用小組名稱 (例如 "FeatureTeam") 的命名慣例。

以下是用來簡化生產前環境清查作業的一些方法：
- 檢閱您的使用者指派。 Microsoft 提供一個稱為 [Visual Studio 系統管理入口網站](https://manage.visualstudio.com/)的網站，協助您追蹤 Visual Studio 訂用帳戶指派。
- 使用內部部署或雲端式 Active Directory 來列出使用者。 如果您使用 Active Directory 來管理使用者存取權，則可以透過其目錄的成員資格來識別開發及測試使用者。
- 使用自動化工具來清查系統。 您可能也需要使用軟體清查工具來協助管理軟體資產，以及區分生產前環境與生產環境。 使用 Microsoft System Center 的許多客戶都會建立命名慣例，以協助將清查程序的這個部分自動化。
- 取得手動重新調解的協助。 登錄您的員工，協助協調開發和測試使用者與開發和測試環境。

## <a name="resources"></a>資源
- [Visual Studio 授權技術白皮書](https://visualstudio.microsoft.com/wp-content/uploads/2019/06/Visual-Studio-Licensing-Whitepaper-May-2019.pdf)
- [Visual Studio 管理與訂閱支援](https://visualstudio.microsoft.com/support/support-overview-vs)
- [大量授權條款](https://www.microsoft.com/licensing/product-licensing/products.aspx)

## <a name="see-also"></a>另請參閱
- [Visual Studio 檔](/visualstudio/)
- [Azure DevOps 檔](/azure/devops/)
- [Azure 檔](/azure/)
- [Microsoft 365 檔](/microsoft-365/)

## <a name="next-steps"></a>後續步驟
深入瞭解系統管理員的責任：
- [系統管理員責任](admin-responsibilities.md)
- [管理大型小組及外部承攬人](manage-teams.md)
- [追蹤使用者指派及處理訂單](assignments-orders.md)
- 使用[使用量上限](maximum-usage.md)來追蹤購買承諾用量