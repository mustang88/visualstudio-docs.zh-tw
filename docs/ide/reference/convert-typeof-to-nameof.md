---
title: 將 typeof 轉換為 nameof
ms.date: 08/12/2020
ms.topic: reference
author: m-redding
ms.author: midumont
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- dotnet
ms.openlocfilehash: 96bd4d67302fb09e5c1cb7837ad73b345ad88c81
ms.sourcegitcommit: f4b49f1fc50ffcb39c6b87e2716b4dc7085c7fb5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/05/2020
ms.locfileid: "93400320"
---
# <a name="convert-typeof-to-nameof"></a>將 `typeof` 轉換為 `nameof`

此重構適用於：

- C#
- Visual Basic

事項 **：** 可讓您在 c # 中將的實例轉換成， `typeof(<QualifiedType>).Name` `nameof(<QualifiedType>)` 並 `GetType(<QualifiedType>).Name` `NameOf(<QualifiedType>)` 在 Visual Basic 中將的實例轉換為。

時機 **：** Where 的所有實例都 `typeof(<QualifiedType>).Name` `someType` 不是泛型型別。 這項排除是必要的，因為此案例不會傳回與相同的字串值 `nameof(<QualifiedType>)` 。 Visual Basic 實例也是如此。

**原因：** 使用 `nameof` 而不是的名稱 `type` 可避免與抓取物件相關的反映 `type` ，而且是撰寫它的更實際方式。

## <a name="how-to"></a>操作方式

1. 將游標放在 `typeof(<QualifiedType>).Name` c # 或 Visual Basic 中的實例內 `GetType(<QualifiedType>).Name` 。

2. 按下 **Ctrl** + **。** 以觸發 [快速動作與重構] 功能表。

3. 選取下列其中一個選項：

    - C#
      <br>Select **將 ' typeof ' 轉換成 ' nameof '** ： ![ 將 typeof 轉換成 nameof](media/convert-type-of.PNG)

    - Visual Basic
      <br>Select **將 ' GetType ' 轉換成 ' NameOf '** ： ![ 將 typeof 轉換成 NameOf](media/convert-get-type.PNG)

## <a name="see-also"></a>請參閱

- [重構](../refactoring-in-visual-studio.md)
