---
title: GetVstoSolutionMetadata 函式
description: 瞭解 GetVstoSolutionMetadata API 如何支援 Office 基礎結構，而且不適合直接從程式碼使用。
ms.custom: SEO-VS-2020
ms.date: 02/02/2017
ms.topic: reference
dev_langs:
- VB
- CSharp
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 205bde9352e2a037b4a08108d8cfce3460034e66
ms.sourcegitcommit: ce85cff795df29e2bd773b4346cd718dccda5337
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/08/2020
ms.locfileid: "96845033"
---
# <a name="getvstosolutionmetadata-function"></a>GetVstoSolutionMetadata 函式
  此 API 支援 Office 基礎結構，而且不適合直接從程式碼使用。

## <a name="syntax"></a>語法

```csharp
HRESULT WINAPI GetVstoSolutionMetadata(
    LPCWSTR lpwszSolutionMetadataKey,
    ISolutionMetadata** ppSolutionInfo
);
```

### <a name="parameters"></a>參數

|參數|描述|
|---------------|-----------------|
|*lpwszSolutionMetadataKey*|請勿使用。|
|*ppSolutionInfo*|請勿使用。|

## <a name="return-value"></a>傳回值
 如果函式成功，它會傳回 **S_OK**。 如果函式失敗，則會傳回錯誤碼。
