---
title: SuspendTracking | Microsoft Docs
description: 瞭解 MSBuild >suspendtracking 的語法、需求和傳回值，這會在目前的內容中暫停追蹤。
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: conceptual
apiname:
- SuspendTracking
apilocation:
- filetracker.dll
apitype: COM
helpviewer_keywords:
- SuspendTracking
ms.assetid: f5e06e5a-8083-444c-99c1-07ba834226b5
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 164e1a11c7d107bf1d98419d77fdc50ed353f93b
ms.sourcegitcommit: 1a36533f385e50c05f661f440380fda6386ed3c1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/30/2020
ms.locfileid: "93048091"
---
# <a name="suspendtracking"></a>SuspendTracking

在目前的內容中暫停追蹤。

## <a name="syntax"></a>語法

```cpp
HRESULT WINAPI SuspendTracking(void);
```

## <a name="return-value"></a>傳回值

 如已暫停追蹤，則為 **HRESULT** 和已設定的 **SUCCEEDED** 位元。

## <a name="requirements"></a>規格需求

 **標頭：** *FileTracker.h*

## <a name="see-also"></a>請參閱

- [ResumeTracking](../msbuild/resumetracking.md)