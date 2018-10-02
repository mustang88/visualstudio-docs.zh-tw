---
title: 文字範本轉換流程 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- text templates, transformation process
ms.assetid: 80b3f0e0-49e7-4865-a1ac-dba068abe96b
caps.latest.revision: 32
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: c7b39517e5e4c88bbefe6bf378e1dffd3c233872
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/22/2018
ms.locfileid: "47497223"
---
# <a name="the-text-template-transformation-process"></a>文字範本轉換流程
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主題的最新的版本可從[文字範本轉換流程](https://docs.microsoft.com/visualstudio/modeling/the-text-template-transformation-process)。  
  
文字範本轉換流程會做為輸入的文字範本檔案，並產生新的文字檔，做為輸出。 例如，您可以使用文字範本產生 Visual Basic 或 C# 程式碼，或您可以產生一份 HTML 報告。  
  
 三個元件參與 「 此程序： 引擎、 主機和指示詞處理器。 此引擎會控制此程序;它與主應用程式和指示詞處理器，以產生輸出檔案互動。 主機提供的環境，例如尋找檔案和組件的任何互動。 指示詞處理器加入功能，例如從 XML 檔案或資料庫讀取資料。  
  
 文字範本轉換流程是在兩個步驟執行。 首先，引擎會建立暫時的類別，也就是產生的轉換類別。 這個類別包含指示詞和控制區塊所產生的程式碼。 在那之後，引擎會編譯，並執行產生的轉換類別來產生輸出檔。  
  
## <a name="components"></a>元件  
  
|元件|描述|可自訂 （是/否）|  
|---------------|-----------------|------------------------------|  
|引擎|引擎元件控制文字範本轉換流程|否。|  
|主機|主機是引擎與使用者環境之間的介面。 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 是一堆文字轉換程序。|可以。 您可以撰寫自訂主機。|  
|指示詞處理器|指示詞處理器會處理文字範本中的指示詞的類別。 您可以使用指示詞提供資料給文字範本中，從輸入來源。|可以。 您可以撰寫自訂指示詞處理器|  
  
## <a name="the-engine"></a>引擎  
 引擎會收到範本做為字串，從主應用程式，用來處理轉換程序中使用的所有檔案。 然後，引擎會要求主應用程式找出任何自訂指示詞處理器和環境的其他方面。 然後，引擎會編譯，並執行產生的轉換類別。 引擎會傳回產生的文字至主機，通常會將文字儲存至檔案。  
  
## <a name="the-host"></a>主應用程式  
 主應用程式會負責任何與轉換處理序，包括下列外部環境相關的項目：  
  
-   尋找文字和二進位檔案要求的引擎或指示詞處理器。 主應用程式可以搜尋目錄和全域組件快取，以找出組件。 主應用程式可以找到自訂指示詞處理器的程式碼引擎。 主機也可以找出並讀取文字檔案然後傳回其內容為字串。  
  
-   提供的標準組件和由引擎用來建立產生的轉換類別的命名空間的清單。  
  
-   提供應用程式定義域時，引擎會編譯並執行產生的轉換類別所使用。 個別應用程式定義域用來保護主應用程式發生錯誤的範本程式碼。  
  
-   寫入產生的輸出檔案。  
  
-   設定產生的輸出檔的預設副檔名。  
  
-   處理文字範本轉換錯誤。 比方說，主應用程式可以在使用者介面中顯示的錯誤，或將它們寫入至檔案。 (在[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]，錯誤會顯示錯誤訊息視窗中。)  
  
-   如果使用者已呼叫指示詞，而不需提供值，請提供必要的參數值。 指示詞處理器可以指定指示詞，並使用參數的名稱，並要求主應用程式提供的預設值，如果有的話。  
  
## <a name="directives-and-directive-processors"></a>指示詞和指示詞處理器  
 指示詞是在文字範本中的命令。 它提供在產生程序的參數。 通常指示詞所定義的來源和類型的模型或其他的輸入和輸出檔案的副檔名。  
  
 指示詞處理器可以處理一或多個指示詞。 當您轉換範本時，您必須已安裝的範本中的指示詞可以處理指示詞處理器。  
  
 指示詞加入程式碼產生的轉換類別中的運作。 建立產生的轉換類別時，您可以呼叫從文字範本，而且引擎處理指示詞的所有呼叫的指示詞。 已成功呼叫指示詞之後，您撰寫文字範本中的程式碼的其餘部分可以依賴指示詞提供的功能。 例如，您可以進行下列呼叫來`import`範本指示詞：  
  
 `<#@ import namespace="System.Text" #>`  
  
 標準的指示詞處理器會將轉換為`using`產生的轉換類別中的陳述式。 然後您可以使用`StringBuilder`類別的未限定為您的範本程式碼其餘部分`System.Text.StringBuilder`。


