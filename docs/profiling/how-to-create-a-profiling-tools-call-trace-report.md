---
title: 建立分析工具呼叫追蹤報表 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: how-to
helpviewer_keywords:
- performance tools, viewing ETW data
- ETW [Visual Studio ALM], viewing data
ms.assetid: 7640520a-7d3c-456c-b184-872a5d2f82f3
author: mikejo5000
ms.author: mikejo
manager: jillfra
monikerRange: vs-2017
ms.workload:
- multiple
ms.openlocfilehash: 1d7d315d1931dfa64ce0070790c833651fa4fc11
ms.sourcegitcommit: 062615c058d2ff44751e8d0c704ccfa3c5543469
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/22/2020
ms.locfileid: "90851199"
---
# <a name="how-to-create-a-profiling-tools-call-trace-report"></a>如何：建立分析工具呼叫追蹤報表
[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 分析工具的「呼叫追蹤報表」** 會列出您應用程式函式每個進入點和結束點的計時資訊，以及您的函式對其他函式的每次呼叫。 只有使用檢測方法收集分析資料時，呼叫追蹤報表才能用於資料分析。

> [!NOTE]
> 您無法在 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 中顯示呼叫追蹤報表。 您必須使用 **VSPerfReport** 命令列工具來產生 ( 的逗號分隔值。*csv*) 或。*xml* 檔案。 如需此工具的詳細資訊，請參閱 [VSPerfReport](../profiling/vsperfreport.md)。

### <a name="to-create-a-call-trace-report"></a>建立呼叫追蹤報表

1. 開啟 [ **命令提示** 字元] 視窗。

2. 在命令提示字元中，輸入下列命令：

     *ToolsPath* **VSPerfReport** *VSPFile*  **/CallTrace [/Xml]**

    |項目|描述|
    |-|-|
    |*ToolsPath*|分析工具命令列工具的路徑。 如需詳細資訊，請參閱[指定命令列工具的路徑](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md)。|
    |*VSPFile*|分析資料 (。*.vsp* 或。*.vsps*) 檔。 可接受完整和部分路徑。|
    |Xml|產生 XML 格式化報表。|

## <a name="see-also"></a>另請參閱
- [如何：收集 Windows 事件追蹤 (ETW) 資料](../profiling/how-to-collect-event-tracing-for-windows-etw-data.md)
- [程式碼剖析工具 Api](../profiling/profiling-tools-apis.md)
