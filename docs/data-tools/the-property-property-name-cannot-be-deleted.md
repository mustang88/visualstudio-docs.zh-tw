---
title: 無法刪除屬性
description: 無法刪除屬性。 查看此 Visual Studio 物件關聯式設計工具 (O/R 設計工具) 訊息的相關資訊。
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: error-reference
ms.assetid: 55873f74-7834-4ec1-8815-eeeb65618d87
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: bdca9758116c551604b5f75f141c15107c1fc890
ms.sourcegitcommit: 72a49c10a872ab45ec6c6d7c4ac7521be84526ff
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/20/2020
ms.locfileid: "94998356"
---
# <a name="the-property-property-name-cannot-be-deleted"></a>無法刪除屬性 \<property name>

\<property name>無法刪除屬性，因為它設定為和之間繼承的 **鑒別子屬性** \<class name>\<class name>

選取的屬性已為在錯誤訊息指出的類別 (Class) 之間的繼承設定為 **鑑別子屬性**。 如果屬性已參與資料類別之間的繼承組態，就無法刪除屬性。

將 **鑑別子屬性** 設定為資料類別的不同屬性，就可以成功刪除要刪的屬性。

## <a name="to-correct-this-error"></a>更正這個錯誤

1. 在 **O/R 設計工具** 中，選取在錯誤訊息指出的資料類別之間連線的繼承線。

2. 將 [鑑別子屬性] 設定為不同屬性。

3. 試著再次刪除屬性。

## <a name="see-also"></a>另請參閱

- [Visual Studio 中的 LINQ to SQL 工具](../data-tools/linq-to-sql-tools-in-visual-studio2.md)