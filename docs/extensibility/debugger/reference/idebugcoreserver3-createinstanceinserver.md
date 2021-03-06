---
title: IDebugCoreServer3：： CreateInstanceInServer |Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugCoreServer3::CreateInstanceInServer
helpviewer_keywords:
- IDebugCoreServer3::CreateInstanceInServer
ms.assetid: 76f36bae-f6ab-413c-a8a9-8808bfeba05b
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 2346bb76fe604265a309a51f48b734fc6f2ab8d0
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/02/2020
ms.locfileid: "80733013"
---
# <a name="idebugcoreserver3createinstanceinserver"></a>IDebugCoreServer3::CreateInstanceInServer
在伺服器上建立 debug 引擎的實例。

## <a name="syntax"></a>語法

```cpp
HRESULT CreateInstanceInServer(
   LPCWSTR  szDll,
   WORD     wLangId,
   REFCLSID clsidObject,
   REFIID   riid,
   void**   ppvObject
);
```

```csharp
int CreateInstanceInServer(
   string     szDll,
   ushort     wLangID,
   ref Guid   clsidObject,
   ref Guid   riid,
   out IntPtr ppvObject
);
```

## <a name="parameters"></a>參數
`szDll`\
在執行參數中指定之 CLSID 的 dll 路徑 `clsidObject` 。 如果是 `NULL` ，則會呼叫 COM 的函式 `CoCreateInstance` 。

`wLangId`\
在偵錯工具引擎的地區設定。 如果不應該呼叫 [SetLocale](../../../extensibility/debugger/reference/idebugengine2-setlocale.md) 方法，這可以是0。

`clsidObject`\
在要建立之偵錯工具引擎的 CLSID。

`riid`\
在要從類別物件中取出的特定介面介面識別碼。

`ppvObject`\
[out] `IUnknown` 來自具現化物件的介面。 將此物件轉型或封送處理至所需的介面。

## <a name="return-value"></a>傳回值
 如果成功，則傳回， `S_OK` 否則傳回錯誤碼。

## <a name="see-also"></a>另請參閱
- [IDebugCoreServer3](../../../extensibility/debugger/reference/idebugcoreserver3.md)
- [SetLocale](../../../extensibility/debugger/reference/idebugengine2-setlocale.md)
