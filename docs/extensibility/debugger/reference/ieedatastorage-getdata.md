---
title: IEEDataStorage：：：：的 |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEEDataStorage::GetData
helpviewer_keywords:
- IEEDataStorage::GetData
ms.assetid: 4d384039-73d4-40b4-ace6-a2474c546397
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 62a1295aeb2a6afad51dee0f1015e3ab01d13fbb
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/02/2020
ms.locfileid: "80718205"
---
# <a name="ieedatastoragegetdata"></a>IEEDataStorage::GetData
從物件中抓取指定的位元組數目。

## <a name="syntax"></a>語法

```cpp
HRESULT GetData(
   ULONG  dataSize,
   ULONG* sizeGotten,
   BYTE*  data
);
```

```csharp
int GetData(
   uint     dataSize,
   out uint sizeGotten,
   byte[]   data
);
```

## <a name="parameters"></a>參數
`dataSize`\
在要抓取的位元組數目 (`data` 陣列必須至少保留此位元組數目) 。

`sizeGotten`\
擴展傳回實際取出的位元組數目。

`data`\
[in，out]要在要求的資料中填入的陣列。

## <a name="return-value"></a>傳回值
 如果成功，則傳回， `S_OK` 否則傳回錯誤碼。

## <a name="remarks"></a>備註
 這種方法的建議使用方式是將所有資料位元組都取出至本機陣列，因為無法在抓取進程中略過超過位元組。 在此情況下，參數 `dataSize` 應該是 [GetSize](../../../extensibility/debugger/reference/ieedatastorage-getsize.md) 方法所傳回的值。

## <a name="see-also"></a>另請參閱
- [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md)
- [GetSize](../../../extensibility/debugger/reference/ieedatastorage-getsize.md)
