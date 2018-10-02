---
title: 模組檢視 - 爭用資料 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Modules view
ms.assetid: 1a9aa122-2d8f-4a09-b503-92975aa6b648
caps.latest.revision: 17
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ccd57d1bbc81c44ce1b6130613e9752f2fc55b35
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/22/2018
ms.locfileid: "47485370"
---
# <a name="modules-view---contention-data"></a>模組檢視 - 爭用資料
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主題的最新的版本可從[模組檢視-爭用資料](https://docs.microsoft.com/visualstudio/profiling/modules-view-contention-data)。  
  
爭用資料的 [模組檢視] 會顯示根據分析資料中取樣的模組所分組的效能資料。 每個模組都是階層式樹狀結構的根。 爭用事件發生所在模組的函式會列在模組節點之下。  
  
 如果函式在發生爭用事件時正在執行其專屬程式碼，(即函式在呼叫堆疊最上方)，則執行中原始程式行和指令位址會列在函式節點之下。 因為資料是在執行程式行或指令時，針對原始程式行或指令指標來收集資料，所以程式行資料和指令資料的內含值和專屬值一律相同。  
  
 下表描述爭用資料之 [模組檢視] 中資料行的值。  
  
|資料行|描述|  
|------------|-----------------|  
|**專有封鎖時間**|-   針對函式，即為此函式已遭封鎖而無法執行函式主體中程式碼的時間。 不包括由該函式所呼叫函式的封鎖時間。<br />-   針對模組，即為模組中函式的專有封鎖時間總和。<br />-   針對程式行或指令，即為封鎖執行此程式行或指令的時間。|  
|**專有封鎖時間 %**|-   針對函式或模組，即為在分析回合的所有封鎖時間中，屬於此函式或模組的專有封鎖時間百分比。<br />-   針對程式行或指令，即為分析回合中封鎖執行此程式行或指令之所有封鎖時間的百分比。|  
|**專有爭用**|-   針對函式，即為此函式已遭封鎖而無法執行函式主體中程式碼的次數。 不包含由該函式所呼叫函式中的爭用。<br />-   針對模組，即為模組中函式專有爭用的總和。<br />-   針對程式行或指令，即為封鎖執行此程式行或指令的次數。|  
|**專有爭用 %**|-   針對函式或模組，即為在分析回合的所有爭用中，屬於此函式或模組的專有爭用百分比。<br />-   針對程式行或指令，即為在分析回合的所有爭用中，屬於封鎖執行此程式行或指令的爭用百分比。|  
|**內含封鎖時間**|-   針對函式，即為此函式或此函式所呼叫函式已遭封鎖而無法執行的時間。<br />-   針對模組，即為此模組中至少有一個函式在堆疊上的封鎖時間總和。<br />-   針對程式行或指令，即為封鎖執行此程式行或指令的時間。|  
|**內含封鎖時間 %**|-   針對函式或模組，即為在分析回合的所有封鎖時間中，屬於此函式或模組的內含封鎖時間百分比。<br />-   針對程式行或指令，即為分析回合中執行此程式行或指令之所有封鎖時間的百分比。|  
|**內含爭用**|-   針對函式，即為此函式或此函式所呼叫函式已遭封鎖而無法執行的次數。<br />-   針對模組，即為此模組中至少有一個函式在堆疊上的爭用數目。<br />-   針對程式行或指令，即為封鎖執行此程式行或指令的次數。|  
|**內含爭用 %**|-   針對函式或模組，即為在分析回合的所有爭用中，屬於此函式或模組的內含爭用百分比。<br />-   針對程式行或指令，即為分析回合中執行此程式行或指令之所有封鎖時間的百分比。|  
|**函式行號**|原始程式檔中這個函式的開頭行號。|  
|**模組名稱**|包含該函式、程式行或指令指標的模組名稱。|  
|**模組路徑**|包含該模組、函式、程式行或指令指標的模組路徑。|  
|**名稱**|模組或函式的名稱。|  
|**處理序 ID**|分析執行的處理序 ID (PID)。|  
|**處理序名稱**|處理序的名稱。|  
|**原始程式檔**|含有這個函式定義的原始程式檔。|  
  
## <a name="see-also"></a>另請參閱  
 [如何：自訂報表檢視資料行](../profiling/how-to-customize-report-view-columns.md)   
 [模組檢視](../profiling/modules-view.md)   
 [模組檢視 - 檢測](../profiling/modules-view-dotnet-memory-instrumentation-data.md)   
 [模組檢視 - 取樣](../profiling/modules-view-dotnet-memory-sampling-data.md)   
 [模組檢視](../profiling/modules-view-instrumentation-data.md)   
 [模組檢視](../profiling/modules-view-sampling-data.md)


