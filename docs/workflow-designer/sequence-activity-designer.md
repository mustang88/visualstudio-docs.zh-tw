---
title: 工作流程設計工具順序活動設計工具
description: 瞭解順序活動如何包含依序執行之子活動的已排序集合。
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- System.Activities.Statements.Sequence.UI
ms.assetid: 51c8d3cb-4d43-458f-9631-b63755f9ac94
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b9e7e6e9114405bc1575e0256dd63211a4fb6d08
ms.sourcegitcommit: ed26b6e313b766c4d92764c303954e2385c6693e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/10/2020
ms.locfileid: "94433969"
---
# <a name="sequence-activity-designer"></a>Sequence 活動設計工具

<xref:System.Activities.Statements.Sequence> 活動會包含子活動的已排序集合，而該集合會依序執行。

另一種依序執行一組活動的方式，則是使用 <xref:System.Activities.Statements.Flowchart> 活動。 當您有想要 diagrammatically 模型的簡單分支或迴圈程式流程時，請考慮使用 [流程圖](../workflow-designer/flowchart-activity-designer.md) 。

## <a name="using-the-sequence-activity-designer"></a>使用 Sequence 活動設計工具

若要加入 <xref:System.Activities.Statements.Sequence> 活動，請從 [工具箱] 將 [ **Sequence** ] 活動設計 **工具** 拖曳至 [工作流程設計工具介面。 若要將子活動新增至此 <xref:System.Activities.Statements.Sequence> 活動，請從 [ **工具箱** ] 拖曳一些其他活動，然後將它放在方塊中的三角形旁邊，並將提示文字顯示為 [在此放置活動]。

### <a name="sequence-activity-properties-in-the-workflow-designer"></a>工作流程設計工具中的 Sequence 活動屬性

下表顯示 <xref:System.Activities.Statements.Sequence> 屬性，並且描述屬性在設計工具中的使用方式。 這些屬性可以在屬性方格中或在設計工具介面上編輯。

|屬性名稱|必要|使用量|
|-|--------------|-|
|<xref:System.Activities.Activity.DisplayName%2A>|否|指定 <xref:System.Activities.Statements.Sequence> 活動設計工具在標頭中的易記名稱。 預設值為 Sequence。 此值可在屬性方格中編輯，或是直接在活動設計工具的標頭上編輯。<br /><br /> 雖然 <xref:System.Activities.Activity.DisplayName%2A> 並非絕對必要，但建議您盡量使用。|

## <a name="see-also"></a>請參閱

- [流程圖](../workflow-designer/flowchart-activity-designer.md)
- [控制流程](../workflow-designer/control-flow-activity-designers.md)