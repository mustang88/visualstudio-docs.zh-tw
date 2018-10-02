---
title: 如何： 偵錯自我裝載的 WCF 服務 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- debugging, WCF
- WCF, self-hosted service
- WCF, debugging
ms.assetid: 288922be-ba3f-411e-af50-bba39c9529cc
caps.latest.revision: 28
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b1e87af205a88e84942eb4958876c2030a175065
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/22/2018
ms.locfileid: "47500095"
---
# <a name="how-to-debug-a-self-hosted-wcf-service"></a>如何：偵錯自我裝載的 WCF 服務
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主題的最新的版本可從[如何： 偵錯自我裝載 WCF 服務](https://docs.microsoft.com/visualstudio/debugger/how-to-debug-a-self-hosted-wcf-service)。  
  
A*自我裝載的服務*是 iis 中，WCF 服務主機，不會執行的 WCF 服務或[!INCLUDE[vstecasp](../includes/vstecasp-md.md)]程式開發伺服器。 若要偵錯自我裝載的 WCF 的最簡單方式是設定[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]以啟動用戶端和伺服器，當您選擇**啟動偵錯**上**偵錯**功能表。  
  
 如果內部或無法啟動，請在這種方式，例如 NT 服務的程序，將自我裝載 WCF 服務，您無法使用這個方法。 相反地，您可以執行下列其中一項：  
  
-   手動將偵錯工具附加至裝載處理序中。 如需詳細資訊，請參閱 <<c0> [ 附加至執行的處理序](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)。  
  
     — 或 —  
  
-   開始偵錯用戶端，並接著逐步執行服務的呼叫。 這需要您啟用的 app.config 檔案中的偵錯。 如需詳細資訊， [WCF 偵錯的限制](../debugger/limitations-on-wcf-debugging.md)。  
  
### <a name="to-start-both-client-and-host-from-visual-studio"></a>若要從 Visual Studio 啟動用戶端和主機  
  
1.  建立[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]包含用戶端和伺服器專案的方案。  
  
2.  將方案設定為啟動用戶端和伺服器處理序，當您選擇**開始**上**偵錯**功能表。  
  
    1.  在 [**方案總管] 中**，以滑鼠右鍵按一下方案名稱。  
  
    2.  按一下 **設定啟始專案**。  
  
    3.  在 **解決方案\<名稱 > 屬性**對話方塊中，選取**多個啟始專案**。  
  
    4.  在 **多個啟始專案**方格中的，對應至伺服器專案中之線條上按一下**動作**，然後選擇 **啟動**。  
  
    5.  在一行中，對應至用戶端專案，按一下**動作**，然後選擇**開始**。  
  
    6.  按一下 [確定 **Deploying Office Solutions**]。  
  
## <a name="see-also"></a>另請參閱  
 [偵錯 WCF 服務](../debugger/debugging-wcf-services.md)   
 [WCF 偵錯的限制](../debugger/limitations-on-wcf-debugging.md)   
 [如何：逐步執行 WCF 服務](../debugger/how-to-step-into-wcf-services.md)


