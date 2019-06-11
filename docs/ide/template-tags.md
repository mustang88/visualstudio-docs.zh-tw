---
title: 在專案範本上新增或編輯標籤
ms.date: 04/30/2019
author: minsa110
ms.author: somin
manager: jillfra
ms.topic: reference
helpviewer_keywords:
- item templates, updating
- Visual Studio templates, updating
- project templates, updating
- updating templates [Visual Studio]
- template tagging, updating
- template tags, updating
ms.openlocfilehash: 4a5113fa7f420d58892e2737ec9196422486490e
ms.sourcegitcommit: cd21b38eefdea2cdefb53e68e7a30b868e78dd6b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/22/2019
ms.locfileid: "66038624"
---
# <a name="add-tags-to-project-templates"></a>將標籤新增到專案範本

從 [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/) 16.1 版 Preview 2 開始，您可以將語言、平台和專案類型標籤新增到您的專案範本。 在 [新增專案] 對話方塊中，標籤會用於兩個位置：

- 標籤會出現在範本描述下面

   ![[新增專案] 對話方塊中包含標籤的專案範本](media/npd-item-with-template-tags.png)

- 標籤可讓使用者搜尋和篩選範本

   ![[新增專案] 對話方塊中的搜尋和篩選](media/npd-search-and-filter.png)

若要新增標籤，請使用 Visual Studio 內建的範本標籤來更新 *.vstemplate* XML 檔案，或是建立自訂範本標籤。 範本標籤只會出現在 Visual Studio 2019 的 [新增專案] 對話方塊中。 它們不會影響先前版本 Visual Studio 中的範本呈現。

## <a name="add-or-edit-tags"></a>新增或編輯標籤

在下列情況下，您可能會想要在專案範本的 *.vstemplate* XML 中新增或編輯標籤：

* 使用 [匯出範本精靈] 來[建立新專案範本](/visualstudio/ide/how-to-create-project-templates)

* [更新現有的專案範本](/visualstudio/ide/how-to-update-existing-templates)

* [建立新的 VSIX 專案範本](/visualstudio/extensibility/getting-started-with-the-vsix-project-template)

## <a name="syntax"></a>語法

```xml
<LanguageTag> Language Name </LanguageTag>
<PlatformTag> Platform Name </PlatformTag>
<ProjectTypeTag> Project Type </ProjectTypeTag>
```

## <a name="attributes"></a>屬性

下列屬性為選擇性，且適合用於進階使用者案例。

|屬性|說明|
|---------------|-----------------|
|`Package`|指定 Visual Studio 套件識別碼的 GUID。|
|`ID`|指定 Visual Studio 資源識別碼。|

語法：

```xml
<LanguageTag Package="{PackageID}" ID="ResourceID" />
<PlatformTag Package="{PackageID}" ID="ResourceID" />
<ProjectTypeTag Package="{PackageID}" ID="ResourceID" />
```

## <a name="elements"></a>項目

### <a name="child-elements"></a>子元素

無。

### <a name="parent-elements"></a>父元素

|元素|說明|
|-------------|-----------------|
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|(必要) 將範本分類，並定義該範本在 [新增專案] 或 [加入新項目] 對話方塊中顯示的方式。|

## <a name="text-value"></a>文字值

除非使用 `Package` 和 `ID` 屬性，否則需要文字值。

文字能提供範本的名稱。

## <a name="built-in-tags"></a>內建標籤

Visual Studio 提供內建標籤的清單；新增那些標籤時，該標籤將會轉譯當地語系化的資源。 下列是內建標籤的清單和其對應值 (以括號括住)。

| 語言 | Platform | 專案類型 |
| -- | -- | -- |
| C++ (`cpp`) | Android (`android`) | 雲端 (`cloud`) |
| C# (`csharp`) | Azure (`azure`) | 主控台 (`console`) |
| F# (`fsharp`) | iOS (`ios`) | 桌面 (`desktop`) |
| Java (`java`) | Linux (`linux`) | 擴充 (`extension`) |
| JavaScript (`javascript`) | macOS (`macos`) | 遊戲 (`games`) |
| Python (`python`) | tvOS (`tvos`) | IoT (`iot`) |
| 查詢語言 (`querylanguage`) | Windows (`windows`) | 程式庫 (`library`) |
| TypeScript (`typescript`) | Xbox (`xbox`) | Machine Learning (`machinelearning`) |
| Visual Basic (`visualbasic`) | | 行動 (`mobile`) |
| | | Office (`office`) |
| | | 其他 (`other`) |
| | | 服務 (`service`) |
| | | 測試 (`test`) |
| | | UWP (`uwp`) |
| | | Web (`web`) |

## <a name="example"></a>範例

下列範例顯示適用於 Visual C# 應用程式之專案範本的中繼資料。

```xml
<VSTemplate Type="Project" Version="3.0.0"
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">
    <TemplateData>
        <Name>My template</Name>
        <Description>A basic template</Description>
        <Icon>TemplateIcon.ico</Icon>
        <ProjectType>CSharp</ProjectType>
        <LanguageTag>C#</LanguageTag>
        <PlatformTag>windows</PlatformTag>
        <PlatformTag>linux</PlatformTag>
        <PlatformTag>My Platform</PlatformTag>
        <ProjectTypeTag>console</ProjectTypeTag>
        <ProjectTypeTag>desktop</ProjectTypeTag>
    </TemplateData>
    <TemplateContent>
        <Project File="MyTemplate.csproj">
            <ProjectItem>Form1.cs<ProjectItem>
            <ProjectItem>Form1.Designer.cs</ProjectItem>
            <ProjectItem>Program.cs</ProjectItem>
            <ProjectItem>Properties\AssemblyInfo.cs</ProjectItem>
            <ProjectItem>Properties\Resources.resx</ProjectItem>
            <ProjectItem>Properties\Resources.Designer.cs</ProjectItem>
            <ProjectItem>Properties\Settings.settings</ProjectItem>
            <ProjectItem>Properties\Settings.Designer.cs</ProjectItem>
        </Project>
    </TemplateContent>
</VSTemplate>
```

## <a name="see-also"></a>另請參閱

- [Visual Studio 範本結構描述參考](/visualstudio/extensibility/visual-studio-template-schema-reference)
- [建立專案和項目範本](/visualstudio/ide/creating-project-and-item-templates)
- [自訂專案與項目範本](/visualstudio/ide/customizing-project-and-item-templates)
- [開始使用 VSIX 專案範本](/visualstudio/extensibility/getting-started-with-the-vsix-project-template)