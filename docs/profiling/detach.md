---
title: Detach | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: d9d1b52c-7f28-467d-b1e0-512afc4e46c9
author: mikejo5000
ms.author: mikejo
manager: jillfra
monikerRange: vs-2017
ms.workload:
- multiple
ms.openlocfilehash: 3251836959f41a4349851716f58f917943f10b09
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/02/2020
ms.locfileid: "85330240"
---
# <a name="detach"></a>中斷連結
VSPerfCmd.exe **Detach** 選項會中斷分析工具與指定處理序的連線，如果沒有指定任何處理序則會中斷與所有處理序的連線。 必須已使用取樣方法初始化分析。

 使用 **Detach**可以中斷使用 **Launch** 或 **Attach** 選項所啟動的分析。 使用後續的 **Attach** 命令，可以重新附加分析工具。

 **Detach** 不會關閉分析資料檔案。 使用 **Shutdown** 選項結束分析，並關閉資料檔案。

> [!NOTE]
> 如果指定 **Start** 選項和 **Crosssession** 選項，則任何 **VSPerfCmd /Attach** 或 **VSPerfCmd /Detach** 呼叫也必須指定 **Crosssession**。

## <a name="syntax"></a>語法

```cmd
VSPerfCmd.exe /Detach[:PIDs|ProcessNames]
```

#### <a name="parameters"></a>參數
 `PIDs|ProcessNames``PID`-一或多個進程的數字系統識別碼。

 `ProcessNames` - 處理序的名稱。 如果多個具名處理序執行個體正在執行，則結果將無法預期。

 以逗號分隔多個處理序。

 如果未指定任何處理序，則會中斷分析工具與所有已分析的處理序。

## <a name="valid-options"></a>有效選項
 在單一命令列上，下列 **VSPerfCmd** 選項可以與 **Attach** 選項一起使用。

 **Crosssession** 在登入工作階段以外的工作階段中，啟用分析應用程式。 如果指定 **Start** 選項和 **Crosssession** 選項，則為必要項目。

## <a name="example"></a>範例
 在此範例中，**Detach** 命令會暫停分析，而 **Shutdown** 命令會關閉分析工具資料檔案。

```cmd
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp
VSPerfCmd.exe /Launch:TestApp.exe
;REM Excercise the application
VSPerfCmd.exe /Detach
VSPerfCmd.exe /Shutdown
```

## <a name="see-also"></a>另請參閱
- [VSPerfCmd](../profiling/vsperfcmd.md)
- [分析獨立應用程式](../profiling/command-line-profiling-of-stand-alone-applications.md)
- [分析 ASP.NET web 應用程式](../profiling/command-line-profiling-of-aspnet-web-applications.md)
- [分析服務](../profiling/command-line-profiling-of-services.md)
