---
title: 範本原則和 [屬性] 視窗 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Properties window, template policy
ms.assetid: 1d8019d3-5e57-47ba-b358-526b0796a63b
caps.latest.revision: 16
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 9f8b2085818c539fe0e751a63562496363b43555
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/22/2018
ms.locfileid: "47499259"
---
# <a name="template-policy-and-the-properties-window"></a>範本原則和屬性視窗
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主題的最新的版本可從[範本原則和 [屬性] 視窗](https://docs.microsoft.com/visualstudio/extensibility/internals/template-policy-and-the-properties-window)。  
  
當專案包含在 enterprise 範本專案時，該企業樣板專案可以強制執行原則。 原則範本會變成可用來設定屬性的預設值、 隱藏的屬性、 加入屬性等等的條件約束系統。  
  
 使用範本的原則來控制顯示的資訊**屬性** 視窗是不同的實作<xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing>。 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing> 雖然您可以使用範本的原則，限制在方案或專案層級的物件屬性，會處理在元件層級的物件屬性。 亦即  
  
-   實作方法<xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing>來判斷在顯示的內容**屬性**視窗針對特定物件  
  
-   使用方案和專案層級的原則範本，來判斷中顯示的內容**屬性**先前指定的物件 視窗  
  
 使用範本的原則來選擇性地限制在特定的屬性**屬性**中選取視窗的指定類型的專案項目時**方案總管 中**將大有助益的所有成員開發小組使用的專案。 比方說，使用範本的原則，您可以設定所有的連接字串資訊在資料庫中您的開發人員並將連接字串，為唯讀。 如此一來，您可以提供簡單的方式，以確保每位開發人員會使用正確的路徑進行資料存取。  
  
## <a name="see-also"></a>另請參閱  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing>   
 [擴充屬性](../../extensibility/internals/extending-properties.md)
