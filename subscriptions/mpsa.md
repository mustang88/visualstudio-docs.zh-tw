---
title: MPSA 中的 Visual Studio 訂閱 |Microsoft Docs
author: evanwindom
ms.author: v-evwin
manager: cabuschl
ms.assetid: b331c837-3524-42b7-820e-b4fdd5e12793
ms.date: 09/03/2020
ms.topic: conceptual
description: '瞭解如何在 Microsoft 產品和服務合約中管理 Visual Studio 訂用帳戶 (MPSA) '
ms.openlocfilehash: 388c847ce19ca7136efb7757fbc87bffdc35a673
ms.sourcegitcommit: f1d47655974a2f08e69704a9a0c46cb007e51589
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/28/2020
ms.locfileid: "92903794"
---
# <a name="visual-studio-subscriptions-in-a-microsoft-products-and-services-agreement-mpsa"></a>Microsoft 產品和服務合約 (MPSA) 中的 Visual Studio 訂閱
如果您已透過 MPSA 方案購買 Visual Studio 訂閱，您必須注意幾件事，才能成為 Visual Studio 訂用帳戶管理員，並將訂用帳戶指派給您的使用者。 如果您已將設定為系統管理員，您可以直接前往 Visual Studio 訂用帳戶 [管理入口網站](https://manage.visualstudio.com/)。

MPSA 客戶管理在入口網站中透過 MPSA 購買的資產（稱為「 [商務中心](https://businessaccount.microsoft.com/Customer)」），其支援的功能與大量授權服務中心 (VLSC) 。 這些包括查看您的授權摘要、訂單、下載、金鑰、使用者等等。不過，MPSA 中的 Visual Studio 訂用帳戶與雲端服務的運作方式很類似。 「商務中心」同樣使用「工作帳戶」來登入，而不是使用 Microsoft 帳戶 (MSA)。 如果組織使用 Office 365 或 Azure Active Directory 之類的雲端服務，而且您的電子郵件已是這兩項服務中任何一項的成員，則此電子郵件已經是「工作帳戶」。 這將可讓您使用現有密碼向「商務中心」註冊。 如果組織未使用雲端服務，而且您的電子郵件也不是「工作帳戶」，您可以使用它向「商務中心」註冊。

此外，Visual Studio 訂用帳戶 [管理入口網站](https://manage.visualstudio.com/) 可讓您在成為 Visual Studio 訂用帳戶系統管理員時，指派訂用帳戶。在 MPSA 中，您必須將 Visual Studio 訂用帳戶布建到其個別的入口網站，也就是 Visual Studio 訂閱的管理入口網站。 若要這樣做，您必須將「購買帳戶」與租用戶 (亦即 contoso.onmicrosoft.com) 建立關聯。

請注意，有兩種類型的租使用者管理的租使用者和不受管理的租使用者。 受管理的租使用者是指已由組織內的系統管理員管理的租使用者。

未受管理的租使用者是沒有任何系統管理員指派的租使用者，不適用於 Office 365 等線上服務。 使用非工作帳戶的電子郵件向「商務中心」註冊時，也會建立未受管理的租使用者。 如果系統要求您在註冊至「商務中心」時建立密碼，這表示您的電子郵件不是工作帳戶，而是建立未受管理的租使用者。

以下是在完成租使用者關聯之前，成為 Visual Studio 訂閱管理員的幾個需求/步驟。

## <a name="pre-tenant-association-managed-tenant"></a>建立租用戶關聯之前 (受控租用戶)
- 您必須是「商務中心」的已註冊使用者。
- 您必須是所屬租用戶的「使用者管理員」(至少需具備此角色) 或「全域管理員」。 (這適用於公司已經使用「雲端服務」的情況)。 這兩個角色都必須是 Visual Studio 訂用帳戶管理員。
- 您必須是所屬租用戶中的「全域管理員」，才能將「購買帳戶」與租用戶建立關聯。
- 您必須是「商務中心」中的「帳戶管理員」(Account Admin) 或「帳戶管理員」(Account Manager)。
- [Azure](https://portal.azure.com/) 中您個人設定檔 (和任何其他使用者) 內的 [國家或地區] 欄位必須依據您的地區適當地填入資訊 (亦即 US、CA 等)。 

> [!NOTE]
> 任何您想要讓 Visual Studio 訂用帳戶管理員的使用者都不需要是 Business Center 中的使用者，因為他們只需要符合準則2和5。

在您符合上述準則之後，即可依照下面的步驟繼續將「購買帳戶」與租用戶建立關聯。
1. 登入[商務中心](https://businessaccount.microsoft.com/Customer)。
2. 按一下 [帳戶]  索引標籤，然後選擇 [建立網域關聯]  。
3. 選取您的 [購買帳戶]  (如果您有多個)。
4. 選取您的 **租用戶** (亦即 contoso.onmicrosoft.com)。
5. 按一下 [建立網域關聯]  。

在關聯時，所有符合準則的使用者通常會在幾分鐘內布建為 Visual Studio 訂閱管理員。 不過，有時可能會花費長達 24 小時的時間。 您的租用戶佈建完成之後，您將能夠存取「Visual Studio 訂閱系統管理入口網站」。 如果這花費的時間超過24小時，請使用下列步驟來 MPSA 支援人員：
1. 連接到 <https://www.microsoft.com/licensing/mpsa/default>
2. 按一下頁面頂端的 [ **更多** ] 功能表。 
3. 選擇 **支援**
4. 選擇 **授權支援**
5. 選取最符合您需求的支援選項。 

> [!NOTE]
> 如果在建立關聯之後，有符合步驟 2 和 5 的新使用者，您必須連絡 MPSA 支援服務。 MPSA 支援人員會提供提供新 Visual Studio 訂閱系統管理員的協助。

## <a name="tenant-association-unmanaged"></a>建立租用戶關聯 (非受控)
如果您已如上面所述，使用非「工作帳戶」(未在 Azure Active Directory “Azure AD” 中註冊) 的電子郵件向「商務中心」進行註冊，租用戶關聯將會有些微不同。 您將需要執行所謂的「網域接管」程序。 在此程式期間，您將會讓自己成為全域管理員，這會將您的租使用者從取消管理變更為受控。

如需此程序的更詳細說明，您可以使用[快速入門指南](https://www.microsoft.com/Licensing/existing-customer/business-center-training-and-resources.aspx)。 請下載名為《設定及使用您的線上服務》  的指南，此指南將會引導您逐步完成網域接管程序。 完成此程序之後，您的「購買帳戶」就也會與您的租用戶建立關聯。

> [!NOTE]
> 完成網域接管程序之後，您必須遵守＜建立租用戶關聯之前 (受控租用戶)＞一節中五個步驟的準則。 符合準則之後，您只需要聯繫 MPSA 支援人員，就能布建額外的 Visual Studio 訂用帳戶管理員。

## <a name="see-also"></a>請參閱
- [Visual Studio 檔](/visualstudio/)
- [Azure DevOps 檔](/azure/devops/)
- [Azure 檔](/azure/)
- [Microsoft 365 檔](/microsoft-365/)

## <a name="next-steps"></a>下一步
深入瞭解如何管理 Visual Studio 的訂閱。
- [指派個別訂用帳戶](assign-license.md)
- [指派多個訂用帳戶](assign-license-bulk.md)
- [編輯訂用帳戶](edit-license.md)
- [刪除訂用帳戶](delete-license.md)
- [判斷最大使用量](maximum-usage.md)