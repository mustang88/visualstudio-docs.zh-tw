---
title: TrackedVCToolTask 類別 | Microsoft Docs
description: 瞭解 TrackedVCToolTask 基類新增至繼承自該類別之工作的參數。
ms.custom: SEO-VS-2020
ms.date: 03/10/2019
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
author: ghogen
ms.author: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 01b55e0ad88cb520078479217306bac948e6cd60
ms.sourcegitcommit: 1a36533f385e50c05f661f440380fda6386ed3c1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/30/2020
ms.locfileid: "93046993"
---
# <a name="trackedvctooltask-base-class"></a>TrackedVCToolTask 基底類別

許多工作最終繼承自 <xref:Microsoft.Build.Utilities.Task> 類別和 [ToolTask](/dotnet/api/microsoft.build.utilities.tooltask) 類別。 此類別會將數個參數新增至衍生自 [VCToolTask](../msbuild/vctooltask-base-class.md) 的工作。 本文件會列出這些參數。

## <a name="parameters"></a>參數

下表說明 **TrackedVCToolTask** 基底類別的參數。

|參數|描述|
|---------------|-----------------|
|**DeleteOutputOnExecute**|選擇性的 **bool** 參數。|
|**EnableExecuteTool**|選擇性的 **bool** 參數。|
|**ExcludedInputPaths**|選擇性的 **ITaskItem []** 參數。|
|**MinimalRebuildFromTracking**|選擇性的 **bool** 參數。|
|**PathOverride**|選擇性的 **字串** 參數。|
|**PostBuildTrackingCleanup**|選擇性的 **bool** 參數。|
|**RootSource**|選擇性的 **字串** 參數。|
|**SkippedExecution**|選擇性的 **bool** 輸出參數。|
|**SourcesCompiled**|選擇性的 **ITaskItem[]** 輸出參數。|
|**TLogCommandFile**|選擇性的 **ITaskItem** 參數。|
|**TLogReadFiles**|選擇性的 **ITaskItem []** 參數。|
|**TLogWriteFiles**|選擇性的 **ITaskItem []** 參數。|
|**ToolArchitecture**|選擇性的 **字串** 參數。|
|**TrackCommandLines**|選擇性的 **bool** 參數。|
|**TrackFileAccess**|選擇性的 **bool** 參數。|
|**TrackedInputFilesToIgnore**|選擇性的 **ITaskItem []** 參數。|
|**TrackedOutputFilesToIgnore**|選擇性的 **ITaskItem []** 參數。|
|**TrackerFrameworkPath**|選擇性的 **字串** 參數。|
|**TrackerSdkPath**|選擇性的 **字串** 參數。|

## <a name="see-also"></a>請參閱

[工作參考](../msbuild/msbuild-task-reference.md)<br/>
[工作](../msbuild/msbuild-tasks.md)
