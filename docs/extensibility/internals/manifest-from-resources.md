---
title: Manifest from Resources |Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 0234109b-5dcb-4d9d-acb9-a63f8bd5699c
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 6ea5931c77e267bc6065693be1ae144c250ce6df
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/02/2020
ms.locfileid: "85536224"
---
# <a name="manifest-from-resources"></a>來自資源的資訊清單
Manifest from Resources 工具是一種主控台應用程式，它會將影像資源清單 ( .png 或 .xaml 檔案) 並產生 imagemanifest 檔案，以允許這些影像與 Visual Studio 影像服務搭配使用。 此外，此工具可以用來將影像新增至現有的 imagemanifest。 此工具適用于將影像的高 DPI 和主題支援新增至 Visual Studio 延伸模組。 產生的 imagemanifest 檔案應該包含在中，並部署為 Visual Studio 擴充功能的一部分 ( .vsix) 。

## <a name="how-to-use-the-tool"></a>如何使用工具
 **語法**

 ManifestFromResources/resources： \<Dir1> ; \<Img1> /assembly： \<AssemblyName>\<Optional Args>

 **引數**

|**交換器名稱**|**備註**|**必要或選擇性**|
|-|-|-|
|/resources|以分號分隔的影像或目錄清單。 這份清單應該一律包含將在資訊清單中的完整映射清單。 如果只提供部分清單，不包含的專案將會遺失。<br /><br /> 如果指定的資源檔是影像區域，則工具會將它分割成不同的映射，再將每個 subimage 新增至資訊清單。<br /><br /> 如果影像是 .png 檔案，我們建議您將名稱格式化，如此一來，工具才能填入正確的影像屬性： \<Name> ... \<Width> \<Height>Png。|必要|
|/assembly|Managed 元件的名稱 (不包括延伸模組) ，或是裝載資源之原生元件的執行時間路徑， (相對於資訊清單的執行時間位置) 。|必要|
|/manifest|要提供給所產生之 imagemanifest 檔案的名稱。 這也可以包含絕對或相對路徑，以在不同的位置建立檔案。 預設名稱符合元件名稱。<br /><br /> 預設值： \<Current Directory> \\<Assembly \> . imagemanifest|選擇性|
|/guidName|要提供給所產生資訊清單中所有影像之 GUID 符號的名稱。<br /><br /> 預設值： AssetsGuid|選擇性|
|/rootPath|建立受控資源 Uri 之前需要移除的根路徑。  (此旗標可協助您解決工具取得相對 URI 路徑錯誤的情況，導致資源無法載入。 ) <br /><br /> 預設： \<Current Directory>|選擇性|
|/recursive|設定此旗標可告知工具以遞迴方式搜尋/resources 引數中的任何目錄。 省略此旗標將會產生最上層的目錄搜尋。|選擇性|
|/isNative|當元件引數是原生元件的路徑時，請設定這個旗標。 當元件引數是 managed 元件的名稱時，請省略此旗標。  (請參閱附注一節，以取得此旗標的其他相關資訊。 ) |選擇性|
|/newGuids|設定此旗標會告知工具為影像的 GUID 符號建立新的值，而不是從現有的資訊清單合併。|選擇性|
|/newIds|設定此旗標會告知工具為每個影像建立新的識別碼符號值，而不是合併現有資訊清單中的值。|選擇性|
|/noLogo|設定此旗標會停止產品和著作權資訊的列印。|選擇性|
|/?|列印出說明資訊。|選擇性|
|/help|列印出說明資訊。|選用|

 **範例**

- ManifestFromResources/resources： D:\Images/assembly： My. Name/isNative

- ManifestFromResources/resources:D:\Images\Image1.png;D： \Images\Image1.xaml/assembly： My. Name/manifest： MyImageManifest. imagemanifest

- ManifestFromResources/resources:D:\Images\Image1.png;D： \Images\Image1.xaml/assembly： My. Name/guidName： MyImages/newGuids/newIds

## <a name="notes"></a>附註

- 此工具只支援 .png 和 .xaml 檔案。 將會忽略任何其他映射或檔案類型。 剖析資源時所遇到的所有不支援類型都會產生警告。 當工具完成剖析資源時，如果找不到支援的映射，則會產生錯誤。

- 藉由遵循 .png 影像的建議格式，此工具會將 .png 的大小/維度值設定為格式指定的大小，即使它與影像的實際大小不同也一樣。

- .Png 影像可以省略寬度/高度格式，但此工具將會讀取影像的實際寬度/高度，並將其用於影像的大小/維度值。

- 同樣地在相同的影像上執行這項工具。 imagemanifest 將會產生重複的資訊清單專案，因為此工具會嘗試將影像區域分割成獨立的映射，並將其新增至現有的資訊清單。

- 只應針對工具產生的資訊清單來合併 (省略/newGuids 或/newIds) 。 已透過其他方式自訂或產生的資訊清單可能無法正確地合併。

- 針對原生元件產生的資訊清單可能需要在產生後進行手動編輯，以便讓識別碼符號符合原生元件的 .rc 檔中的資源識別碼。

## <a name="sample-output"></a>範例輸出
 **簡單映射資訊清單**

 影像資訊清單將類似下列 .xml 檔案：

```xml
<?xml version="1.0" encoding="utf-8"?>
<!-- This file was generated by the ManifestFromResources tool.-->
<!-- Version: 14.0.15197 -->
<ImageManifest xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns="http://schemas.microsoft.com/VisualStudio/ImageManifestSchema/2014">
  <Symbols>
    <String Name="Resources" Value="/My.Assembly.Name;Component/Resources/Images" />
    <Guid Name="AssetsGuid" Value="{fb41b7ef-6587-480c-aa27-5b559d42cfc9}" />
    <ID Name="MyImage" Value="0" />
  </Symbols>
  <Images>
    <Image Guid="$(AssetsGuid)" ID="$(MyImage)">
      <Source Uri="$(Resources)/Xaml/MyImage.xaml" />
      <Source Uri="$(Resources)/Png/MyImage.16.16.png">
        <Size Value="16" />
      </Source>
    </Image>
  </Images>
  <ImageLists />
</ImageManifest>
```

 **影像帶的影像資訊清單**

 影像區的影像資訊清單將類似下列 .xml 檔案：

```xml
<?xml version="1.0" encoding="utf-8"?>
<!-- This file was generated by the ManifestFromResources tool.-->
<!-- Version: 14.0.15197 -->
<ImageManifest xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns="http://schemas.microsoft.com/VisualStudio/ImageManifestSchema/2014">
  <Symbols>
    <String Name="Resources" Value="/My.Assembly.Name;Component/Resources/ImageStrip" />
    <Guid Name="AssetsGuid" Value="{fb41b7ef-6587-480c-aa27-5b559d42cfc9}" />
    <ID Name="MyImageStrip_0" Value="1" />
    <ID Name="MyImageStrip_1" Value="2" />
    <ID Name="MyImageStrip" Value="3" />
  </Symbols>
  <Images>
    <Image Guid="$(AssetsGuid)" ID="$(MyImageStrip_0)">
      <Source Uri="$(Resources)/MyImageStrip_0.png">
        <Size Value="16" />
      </Source>
    </Image>
    <Image Guid="$(AssetsGuid)" ID="$(MyImageStrip_1)">
      <Source Uri="$(Resources)/MyImageStrip_1.png">
        <Size Value="16" />
      </Source>
    </Image>
  </Images>
  <ImageLists>
    <ImageList Guid="$(AssetsGuid)" ID="$(MyImageStrip)">
      <ContainedImage Guid="$(AssetsGuid)" ID="$(MyImageStrip_0)" />
      <ContainedImage Guid="$(AssetsGuid)" ID="$(MyImageStrip_1)" />
    </ImageList>
  </ImageLists>
</ImageManifest>
```

 **原生元件映射資源的映射資訊清單**

 原生映射的映射資訊清單將類似下列 .xml 檔案：

```xml
<?xml version="1.0" encoding="utf-8"?>
<!-- This file was generated by the ManifestFromResources tool.-->
<!-- Version: 14.0.15198 -->
<ImageManifest xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns="http://schemas.microsoft.com/VisualStudio/ImageManifestSchema/2014">
  <Symbols>
    <String Name="Resources" Value="..\Assembly\Folder\My.Assembly.Name" />
    <Guid Name="AssetsGuid" Value="{442d8739-efde-46a4-8f29-e3a1e5e7f8b4}" />
    <ID Name="MyImage1" Value="0" />
    <ID Name="MyImage2" Value="1" />
  </Symbols>
  <Images>
    <Image Guid="$(AssetsGuid)" ID="$(MyImage1)">
      <Source Uri="$(Resources)">
        <Size Value="16" />
        <NativeResource ID="$(MyImage1)" Type="PNG" />
      </Source>
    </Image>
    <Image Guid="$(AssetsGuid)" ID="$(MyImage2)">
      <Source Uri="$(Resources)">
        <Size Value="16" />
        <NativeResource ID="$(MyImage2)" Type="PNG" />
      </Source>
    </Image>
  </Images>
  <ImageLists />
</ImageManifest>
```
