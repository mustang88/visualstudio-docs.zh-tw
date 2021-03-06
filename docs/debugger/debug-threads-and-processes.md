---
title: 偵測執行緒和進程的工具 |Microsoft Docs
ms.date: 04/21/2018
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- multiprocess debugging
- threading [Visual Studio], debugging
- processes, debugging
- debugging threads
- debugging [Visual Studio], threads
ms.assetid: 9f0c8505-b6b2-452b-adfd-076db14d8115
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: dcdaf083462b75485449cae05894681e2bb5c900
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/02/2020
ms.locfileid: "72738385"
---
# <a name="tools-to-debug-threads-and-processes-in-visual-studio"></a>在 Visual Studio 中偵測執行緒和進程的工具
「執行緒」** 和「處理序」** 在電腦科學中是相關的概念。 兩者都代表必須以特定順序執行的指令序列。 但是，不同執行緒或處理序中的指令能夠平行執行。

 處理序存在於作業系統中，並對應至所謂的程式或應用程式。 從另一方面來說，執行緒存在於處理序中。 基於這個原因，執行緒有時候會稱為「輕量處理序」**。 每個處理序是由一或多個執行緒組成。

 具有多個處理序能夠讓電腦同時執行一項以上的工作。 具有多個執行緒能夠讓處理序分割工作以平行方式執行。 使用多個處理器的電腦能夠在不同的處理器上執行處理序或執行緒。 如此可達到真正的平行處理。

 但是並非都能達到完美的平行處理境界。 執行緒有時候必須進行同步處理。 一個執行緒可能需要等候其他執行緒的結果，或是一個執行緒可能需要其他執行緒正在使用之資源的獨佔存取權。 同步處理是多執行緒應用程式中發生錯誤的常見原因。 有時候執行緒會演變成一直在等候永遠無法使用的資源。 這會導致所謂的「死結」** 情況。

 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 偵錯工具提供強大而容易使用的工具以便偵錯執行緒和處理序。

## <a name="tools-and-features"></a>工具與功能
您需要使用的工具取決於 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 您嘗試要進行的程式碼類型：

- 針對進程，主要工具是 [ **附加至進程** ] 對話方塊、[ **進程** ] 視窗和 [ **偵錯工具位置** ] 工具列。

- 針對執行緒，用於偵測執行緒的主要工具是 [ **執行緒** ] 視窗、來源視窗中的執行緒標記、[ **平行堆疊** ] 視窗、[ **平行監看** 式] 視窗和 [ **偵錯工具位置** ] 工具列。

- 針對 <xref:System.Threading.Tasks.Task> 在工作平行程式庫中使用[ (TPL) ](/dotnet/standard/parallel-programming/task-parallel-library-tpl)的程式碼，[並行執行階段](/cpp/parallel/concrt/concurrency-runtime/) (機器碼) 中，調試多執行緒應用程式的主要工具是 [**平行堆疊**] 視窗、[**平行監看**式**Tasks** ] 視窗和 [ **Tasks**工作] 視窗 ([工作] 視窗也支援 JavaScript 承諾物件) 。

- 若要在 GPU 上進行執行緒的偵錯工具，主要工具是 [ **GPU 執行緒** ] 視窗。

  下表顯示在這些位置中可用的資訊與能夠執行的動作：

|使用者介面|可用的資訊|能夠執行的動作|
|--------------------|---------------------------|-----------------------------|
|[附加至處理序]**** 對話方塊|能夠附加至的可用處理序：<br /><br /> -   處理序名稱 (.exe)<br />-   處理序識別碼<br />-   功能表列標題<br />-   類型 (受控 v4.0；受控 v2.0、v1.1、v1.0；x86；x64；IA64)<br />-   使用者名稱 (帳戶名稱)<br />-   工作階段編號|選取要附加至的處理序<br /><br /> 選取遠端電腦<br /><br /> 變更連接至遠端電腦的傳輸類型|
|[處理序]**** 視窗|附加之處理序：<br /><br /> -   處理序名稱<br />-   處理序識別碼<br />-   處理序 .exe 的路徑<br />-   功能表列標題<br />-   狀態 (中斷。 執行)<br />-   偵錯 (原生、受控等。)<br />-   傳輸類型 (預設、未經驗證的機器碼)<br />-   傳輸限定詞 (遠端電腦)|工具：<br /><br /> -   附加<br />-   中斷連結<br />-   終止<br /><br /> 捷徑功能表：<br /><br /> -   附加<br />-   中斷連結<br />-   當偵錯停止時中斷連結<br />-   終止|
|**執行緒** 視窗|目前處理序中的執行緒：<br /><br /> -   執行緒識別碼<br />-   受控識別碼<br />-   分類 (主執行緒、介面執行緒、遠端程序呼叫處理常式或背景工作執行緒)<br />-   執行緒名稱<br />-   建立執行緒的位置<br />-   優先權<br />-   親和性遮罩<br />-   暫停計數<br />-   處理序名稱<br />-   旗標指標<br />-   暫停指標|工具：<br /><br /> -   搜尋<br />-   搜尋呼叫堆疊<br />-   將 Just My Code 加上旗標<br />-   將自訂模組選取範圍加上旗標<br />-   分組依據<br />-   資料行<br />-   展開/摺疊呼叫堆疊<br />-   展開/摺疊群組<br />-   凍結/解除凍結執行緒<br /><br /> 捷徑功能表：<br /><br /> -   在原始程式碼中顯示執行緒<br />-   切換至執行緒<br />-   將執行中的執行緒凍結<br />-   將執行緒解除凍結<br />-   爲執行緒加上旗標以利進一步研究<br />-   取消執行緒的旗標<br />-   重新命名執行緒<br />-   顯示和隱藏執行緒<br /><br /> 其他動作：<br /><br /> -   在 DataTip 中檢視執行緒的呼叫堆疊|
|來源視窗|左側巡覽邊上的執行緒指示器能指出是單一或多個執行緒 (預設為關閉，可使用 [執行緒]**** 視窗中的捷徑功能表開啟)|捷徑功能表：<br /><br /> -   切換至執行緒<br />-   爲執行緒加上旗標以利進一步研究<br />-   取消執行緒的旗標|
|[偵錯位置]**** 工具列|-   目前的處理序<br />-   暫停應用程式<br />-   繼續執行應用程式<br />-   暫停並關閉應用程式<br />-   目前的執行緒<br />-   切換目前執行緒的旗標狀態<br />-   僅顯示有旗標的執行緒<br />-   僅顯示目前處理序<br />-   目前的堆疊框架|-   切換至另一個處理序<br />-   暫停、繼續或關閉應用程式<br />-   切換至目前處理序中的另一個執行緒<br />-   切換至目前執行緒中的另一個堆疊框架<br />-   將目前執行緒加上旗標或取消旗標<br />-   僅顯示有旗標的執行緒<br />-   僅顯示目前處理序|
|[平行堆疊]**** 視窗|-   一個視窗中多個執行緒的呼叫堆疊。<br />-   每個執行緒的作用中堆疊框架。<br />-   任何方法的呼叫端和被呼叫端。|-   篩選掉指定的執行緒<br />-切換至工作視圖<br />-   將執行緒加上旗標或取消旗標<br />-   縮放|
|[平行監看式]**** 視窗|-   旗標資料行，您可以在該資料行中標示想要特別注意的執行緒。<br />-   框架資料行，其中的箭號表示所選的框架。<br />-   可以顯示電腦、處理序、磚、工作和執行緒的可設定資料行。|-   將執行緒加上旗標或取消旗標<br />-   僅顯示已加上旗標的執行緒<br />-   切換框架<br />-   排序資料行<br />-   群組執行緒<br />-   將執行緒凍結或解除凍結<br />-   匯出 [平行監看式] 視窗中的資料|
|**Tasks**工作視窗|-   檢閱 <xref:System.Threading.Tasks.Task> 物件的相關資訊，包括工作識別碼、工作狀態 (已排程、執行中、等待中、死結)，以及指派給工作的執行緒。<br />-   呼叫堆疊中的目前位置。<br />-   在建立時傳遞至工作的委派|-   切換至目前工作<br />-   將工作加上旗標或取消旗標<br />-   將工作凍結或解除凍結|
|**GPU 執行緒** 視窗|-   旗標資料行，您可以在該資料行中標示想要特別注意的執行緒。<br />-目前的執行緒資料行，其中黃色箭號表示目前的執行緒。<br />-   [執行緒計數]**** 資料行，可顯示同一位置的執行緒數目。<br />-   [行]**** 資料行，可顯示每個執行緒群組所在的程式碼行。<br />-   [位址]**** 資料行，可顯示每個執行緒群組所在的指令位址。<br />-   [位置]**** 資料行，是位址在程式碼中的位置。<br />-   [狀態]**** 資料行，可顯示執行緒為使用中或已封鎖。<br />-   [磚]**** 資料行，可顯示資料列中執行緒的磚索引。|-變更為不同的執行緒<br />-   顯示特定磚和執行緒<br />-   顯示或隱藏資料行<br />-   依資料行排序<br />-   群組執行緒<br />-   將執行緒凍結或解除凍結<br />-   將執行緒加上旗標或取消旗標<br />-   僅顯示已加上旗標的執行緒|

## <a name="see-also"></a>另請參閱

- [附加到正在執行的處理序](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)
- [偵錯多執行緒應用程式](../debugger/debug-multithreaded-applications-in-visual-studio.md)
- [偵錯 GPU 程式碼](../debugger/debugging-gpu-code.md)