---
title: GetScheduledTasksForDebugger 方法 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- GetScheduledTasksForDebugger method, TaskScheduler class [.NET Framework debug engines]
ms.assetid: 7c9b4cde-6e4a-4cef-929f-7d02b1da5762
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: fca6c8e92cd0b4755bd79b8e142a7e1d283f868d
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/02/2020
ms.locfileid: "80738658"
---
# <a name="getscheduledtasksfordebugger-method"></a>GetScheduledTasksForDebugger 方法
捕獲所有排程工作的陣列。

 **命名空間：** <xref:System.Threading.Tasks?displayProperty=fullName>

 **元件：** *mscorlib.dll*) 中的 mscorlib (

 因為您無法從 .NET Framework 存取此內部成員，所以會在) 的通用中繼語言中提供下列語法 (。

## <a name="syntax"></a>語法

```csharp
.method assembly hidebysig instance class System.Threading.Tasks.Task[] GetScheduledTasksForDebugger() cil managed
```

## <a name="return-value"></a>傳回值
 所有排程工作的陣列。 每項工作正在執行或已完成執行。

## <a name="remarks"></a>備註
 這個方法不是安全線程，因此您不應該與的其他實例同時使用它 <xref:System.Threading.Tasks.TaskScheduler> 。 只有當偵錯工具暫停所有其他執行緒時，才從偵錯工具呼叫這個方法。

## <a name="see-also"></a>另請參閱
- [TaskScheduler 類別](../../extensibility/debugger/taskscheduler-class-internal-members.md)
