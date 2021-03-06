---
title: 命令程式碼列舉值 |Microsoft Docs
description: SccGetCommandOptions 和 SccPopulateListto 的選項中會使用命令程式碼列舉值，來指出指定選項的命令。
ms.custom: SEO-VS-2020
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- command code enumerator
- source control plug-ins, command code enumeration
ms.assetid: 5d2c360c-59e4-4da8-bcb4-dd07c7441e40
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 9a831813bb975819e9152dfab4d4eefd6b440606
ms.sourcegitcommit: 5027eb5c95e1d2da6d08d208fd6883819ef52d05
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/20/2020
ms.locfileid: "94974264"
---
# <a name="command-code-enumerator"></a>命令程式碼列舉值
此列舉值用於 [SccGetCommandOptions](../extensibility/sccgetcommandoptions-function.md) 的選項和 [SccPopulateList](../extensibility/sccpopulatelist-function.md)，以指出指定選項的命令。

## <a name="syntax"></a>語法

```
enum SCCCOMMAND {
   SCC_COMMAND_GET,
   SCC_COMMAND_CHECKOUT,
   SCC_COMMAND_CHECKIN,
   SCC_COMMAND_UNCHECKOUT,
   SCC_COMMAND_ADD,
   SCC_COMMAND_REMOVE,
   SCC_COMMAND_DIFF,
   SCC_COMMAND_HISTORY,
   SCC_COMMAND_RENAME,
   SCC_COMMAND_PROPERTIES,
   SCC_COMMAND_OPTIONS
};
```

## <a name="members"></a>成員
SCC_COMMAND_GET 對應于 [SccGet](../extensibility/sccget-function.md)。

SCC_COMMAND_CHECKOUT 對應于 [SccCheckout](../extensibility/scccheckout-function.md)。

SCC_COMMAND_CHECKIN 對應于 [SccCheckin](../extensibility/scccheckin-function.md)。

SCC_COMMAND_UNCHECKOUT 對應于 [SccUncheckout](../extensibility/sccuncheckout-function.md)。

SCC_COMMAND_ADD 對應于 [SccAdd](../extensibility/sccadd-function.md)。

SCC_COMMAND_REMOVE 對應于 [SccRemove](../extensibility/sccremove-function.md)。

SCC_COMMAND_DIFF 對應于 [SccDiff](../extensibility/sccdiff-function.md)。

SCC_COMMAND_HISTORY 對應于 [SccHistory](../extensibility/scchistory-function.md)。

SCC_COMMAND_RENAME 對應于 [SccRename](../extensibility/sccrename-function.md)。

SCC_COMMAND_PROPERTIES 對應于 [SccProperties](../extensibility/sccproperties-function.md)。

SCC_COMMAND_OPTIONS 對應于 [SccSetOption](../extensibility/sccsetoption-function.md)。

## <a name="see-also"></a>另請參閱
- [原始檔控制外掛程式](../extensibility/source-control-plug-ins.md)
- [SccGetCommandOptions](../extensibility/sccgetcommandoptions-function.md)
- [SccPopulateList](../extensibility/sccpopulatelist-function.md)
