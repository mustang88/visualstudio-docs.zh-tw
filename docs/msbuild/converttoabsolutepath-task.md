---
title: ConvertToAbsolutePath 工作 | Microsoft Docs
description: 使用 MSBuild ConvertToAbsolutePath 工作，將相對路徑或參考轉換為絕對路徑。
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#ConvertToAbsolutePath
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- ConvertToAbsolutePath task [MSBuild]
- MSBuild, ConvertToAbsolutePath task
ms.assetid: f1af2cb8-b4ef-4a72-be80-22fa526c4491
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ecf9695b36f341fa350abf53062e70095c03c374
ms.sourcegitcommit: bd9417123c6ef67aa2215307ba5eeec511e43e02
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/28/2020
ms.locfileid: "92796156"
---
# <a name="converttoabsolutepath-task"></a>ConvertToAbsolutePath 工作

將相對路徑或參考轉換為絕對路徑。

## <a name="task-parameters"></a>工作參數

 下表說明 `ConvertToAbsolutePath` 工作的參數。

|參數|描述|
|---------------|-----------------|
|`Paths`|必要的 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 參數。<br /><br /> 要轉換為絕對路徑的相對路徑清單。|
|`AbsolutePaths`|選擇性的 <xref:Microsoft.Build.Framework.ITaskItem>`[]` 輸出參數。<br /><br /> 已傳入項目的絕對路徑清單。|

## <a name="remarks"></a>備註

 除了上述所列的參數，此項工作還會繼承 <xref:Microsoft.Build.Tasks.TaskExtension> 類別中的參數，而該類別本身又繼承 <xref:Microsoft.Build.Utilities.Task> 類別。 如需這些額外參數的清單及其描述，請參閱 [TaskExtension 基類（base class](../msbuild/taskextension-base-class.md)）。

## <a name="see-also"></a>請參閱

- [工作](../msbuild/msbuild-tasks.md)
- [工作參考](../msbuild/msbuild-task-reference.md)
