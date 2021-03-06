---
title: Define 元素 |Microsoft Docs
description: Define 元素定義符號名稱和值組。 條件式屬性可以評估此符號。
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- VSCT XML schema elements, Define
- Define element (VSCT XML schema)
ms.assetid: 5aee74e3-de41-4dc6-9618-93e158af56dd
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a427371afe55b6ea4ee20f658e683b9dcdb8fbe2
ms.sourcegitcommit: d10f37dfdba5d826e7451260c8370fd1efa2c4e4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/10/2020
ms.locfileid: "96996236"
---
# <a name="define-element"></a>Define 元素
定義符號名稱和值組。 條件式屬性可以評估此符號。 如需詳細資訊，請參閱 [條件式屬性](../extensibility/vsct-xml-schema-conditional-attributes.md)。 另請參閱 [符號元素](../extensibility/symbols-element.md)。

## <a name="syntax"></a>語法

```
<Define name="Mode" value="Standard" />
```

## <a name="attributes-and-elements"></a>屬性和元素
 下列章節說明屬性、子元素和父元素。

### <a name="attributes"></a>屬性

|屬性|描述|
|---------------|-----------------|
|NAME|必要。 符號的名稱：<br /><br /> name = "Mode"|
|值|必要。 符號的值：<br /><br /> 值 = "Standard"|
|條件|選擇性。 如需詳細資訊，請參閱 [條件式屬性](../extensibility/vsct-xml-schema-conditional-attributes.md)。|

### <a name="child-elements"></a>子元素
 無。

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|[CommandTable 元素](../extensibility/commandtable-element.md)|定義代表 VSPackage 提供給整合式開發環境 (IDE) 命令的所有元素。 例如，功能表項目、功能表、工具列和下拉式方塊。|

## <a name="example"></a>範例

```
<Define name="DEMO_UI"/>
<Define name="MODE" value="Standard"/>
```

## <a name="see-also"></a>另請參閱
- [Visual Studio 命令表格 (. .vsct) 檔](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)
