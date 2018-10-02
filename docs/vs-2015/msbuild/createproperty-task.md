---
title: CreateProperty 工作 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#CreateProperty
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- CreateProperty task [MSBuild]
- MSBuild, CreateProperty task
ms.assetid: fbc31a88-62d4-43d2-b739-68ef3fac38f5
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 961f034f2bb508175d258259097f3be25e2a0b11
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/22/2018
ms.locfileid: "47498621"
---
# <a name="createproperty-task"></a>CreateProperty 工作
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主題的最新的版本可從[CreateProperty 工作](https://docs.microsoft.com/visualstudio/msbuild/createproperty-task)。  
  
  
將傳入的值填入屬性中。 這允許將值從某個屬性或字串複製至另一個屬性或字串。  
  
## <a name="attributes"></a>屬性  
 下表說明 `CreateProperty` 工作的參數。  
  
|參數|描述|  
|---------------|-----------------|  
|`Value`|選擇性的 `String` 輸出參數。<br /><br /> 指定要複製至新屬性的值。|  
|`ValueSetByTask`|選擇性的 `String` 輸出參數。<br /><br /> 包含與 `Value` 參數相同的值。 因輸出具有最新資訊而略過封入目標時，只有在您想要避免具有 [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] 所設定的輸出屬性時，才使用此參數。|  
  
## <a name="remarks"></a>備註  
 除了上述所列的參數，此項工作還會繼承 <xref:Microsoft.Build.Tasks.TaskExtension> 類別中的參數，而該類別本身又繼承 <xref:Microsoft.Build.Utilities.Task> 類別。 如需這些其他參數的清單及其說明，請參閱 [TaskExtension Base Class](../msbuild/taskextension-base-class.md)。  
  
## <a name="example"></a>範例  
 下列範例使用 `CreateProperty` 工作，以使用 `SourceFilename` 和 `SourceFileExtension` 屬性值組合建立 `NewFile` 屬性。  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <PropertyGroup>  
        <SourceFilename>Module1</SourceFilename>  
        <SourceFileExtension>vb</SourceFileExtension>  
    </PropertyGroup>  
  
    <Target Name="CreateProperties">  
  
        <CreateProperty  
            Value="$(SourceFilename).$(SourceFileExtension)">  
            <Output  
                TaskParameter="Value"  
                PropertyName="NewFile" />  
        </CreateProperty>  
  
    </Target>  
  
</Project>  
```  
  
 執行專案之後，`NewFile` 屬性的值是 `Module1.vb`。  
  
## <a name="see-also"></a>另請參閱  
 [工作參考](../msbuild/msbuild-task-reference.md)   
 [工作](../msbuild/msbuild-tasks.md)


