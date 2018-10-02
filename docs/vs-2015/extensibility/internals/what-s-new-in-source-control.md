---
title: 什麼&#39;原始檔控制的新功能 |Microsoft Docs
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
- what's new [Visual Studio SDK], source control
- source control [Visual Studio SDK], what's new
ms.assetid: bcf85418-18fb-4824-9dae-d14bf3d56a77
caps.latest.revision: 28
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f098c9f46d649a8b93c29eff57c5606438d3e399
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/22/2018
ms.locfileid: "47491357"
---
# <a name="what39s-new-in-source-control"></a>什麼&#39;原始檔控制的新功能
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主題的最新的版本可從[功能&#39;新原始檔控制中的 s](https://docs.microsoft.com/visualstudio/extensibility/internals/what-s-new-in-source-control)。  
  
在 [!INCLUDE[vsipsdk](../../includes/vsipsdk-md.md)]您可以藉由實作原始檔控制 VSPackage 提供深入的整合式原始檔控制解決方案。 本節說明的原始檔控制 Vspackage 功能，並提供實作步驟的概觀。  
  
## <a name="the-source-control-vspackage"></a>原始檔控制 VSPackage  
 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] 支援兩種類型的原始檔控制解決方案。 在所有版本的[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]，您仍然可以整合原始檔控制外掛程式 API 為基礎外掛程式。 您也可以建立可提供深層整合原始檔控制 VSPackage[!INCLUDE[vsipsdk](../../includes/vsipsdk-md.md)]適用於原始檔控制解決方案需要高層級的複雜度與自我管理的路徑。  
  
 VSPackage 可以將幾乎任何一種功能[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]。 原始檔控制 VSPackage 提供的完整原始檔控制功能[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]，從 UI 呈現給使用者，以原始檔控制系統的後端通訊。  
  
 實作原始檔控制 VSPackage，需要 「 全部或全無 」 的策略。 原始檔控制 VSPackage 的建立者必須投入大量心力來實作許多原始檔控制的介面和新的 UI 項目 （對話方塊、 功能表和工具列） 以涵蓋整個原始檔控制功能，以及介面成功整合所需的任何套件[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]。  
  
 下列步驟提供所需實作原始檔控制套件的一般概觀。 如需詳細資訊，請參閱 <<c0> [ 建立原始檔控制 VSPackage](../../extensibility/internals/creating-a-source-control-vspackage.md)。  
  
1.  建立提供私用的原始檔控制服務的 VSPackage。  
  
2.  在原始檔控制相關服務，會提供實作介面[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)](例如<xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2>而<xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProvider>介面)。  
  
3.  註冊您的原始檔控制 VSPackage。  
  
4.  實作所有的原始檔控制 UI，包括功能表項目、 對話方塊、 工具列和快顯功能表。  
  
5.  所有的原始檔控制相關事件會傳遞至原始檔控制 VSackage 中，當它為作用中且必須由您的 VSPackage。  
  
6.  原始檔控制 VSPackage 必須接聽事件，例如實作<xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3>介面及追蹤專案文件 (TPD) 事件 (由實作<xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2>介面)，並採取必要動作。  
  
## <a name="see-also"></a>另請參閱  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProvider>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2>   
 [概觀](../../extensibility/internals/source-control-integration-overview.md)   
 [建立原始檔控制 VSPackage](../../extensibility/internals/creating-a-source-control-vspackage.md)
