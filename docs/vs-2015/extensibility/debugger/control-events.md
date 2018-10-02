---
title: 控制事件 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], events
ms.assetid: 0fc63484-5fb6-4887-9ea4-1905b459ca9d
caps.latest.revision: 8
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 7ac93da53f21b56df38a6ad597d7c4911075a670
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/22/2018
ms.locfileid: "47498750"
---
# <a name="control-events"></a>控制項事件
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主題的最新的版本可從[控制項事件](https://docs.microsoft.com/visualstudio/extensibility/debugger/control-events)。  
  
您必須在受控制的程式執行期間傳送事件。 所有事件都會使用在傳送[IDebugEvent2](../../extensibility/debugger/reference/idebugevent2.md)介面，並且具有會要求您實作的屬性[IDebugEvent2::GetAttributes](../../extensibility/debugger/reference/idebugevent2-getattributes.md)方法。  
  
## <a name="additional-methods"></a>其他方法  
 某些事件會需要其他方法，的實作，如下所示：  
  
-   傳送[IDebugEngineCreateEvent2](../../extensibility/debugger/reference/idebugenginecreateevent2.md)介面初始化偵錯引擎 (DE) 時，要求您實作[IDebugEngineCreateEvent2::GetEngine](../../extensibility/debugger/reference/idebugenginecreateevent2-getengine.md)方法。  
  
-   執行控制項必須實作這類控制項事件中當做[IDebugBreakEvent2](../../extensibility/debugger/reference/idebugbreakevent2.md)並[IDebugStepCompleteEvent2](../../extensibility/debugger/reference/idebugstepcompleteevent2.md)介面。 **IDebugBreakEvent2**只需要非同步中斷。  
  
-   逐步執行函式必須實作[IDebugStepCompleteEvent2](../../extensibility/debugger/reference/idebugstepcompleteevent2.md)介面和其方法。  
  
 衍生自中斷點的事件都需要實作[IDebugBreakpointErrorEvent2](../../extensibility/debugger/reference/idebugbreakpointerrorevent2.md)， [IDebugBreakpointEvent2](../../extensibility/debugger/reference/idebugbreakpointevent2.md)，並[IDebugBreakpointBoundEvent2](../../extensibility/debugger/reference/idebugbreakpointboundevent2.md)介面，以及[IDebugBreakpointBoundEvent2::GetPendingBreakpoint](../../extensibility/debugger/reference/idebugbreakpointboundevent2-getpendingbreakpoint.md)並[EnumBoundBreakpoints](../../extensibility/debugger/reference/idebugbreakpointboundevent2-enumboundbreakpoints.md)方法。  
  
 非同步運算式評估會要求您實作[IDebugExpressionEvaluationCompleteEvent2](../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2.md)介面及其[IDebugExpressionEvaluationCompleteEvent2::GetExpression](../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2-getexpression.md)[和 GetResult](../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2-getresult.md)方法。  
  
 同步事件需要實作[IDebugEngine2::ContinueFromSynchronousEvent](../../extensibility/debugger/reference/idebugengine2-continuefromsynchronousevent.md)方法。  
  
 針對您要寫入輸出字串樣式的引擎，您必須實作[IDebugOutputStringEvent2::GetString](../../extensibility/debugger/reference/idebugoutputstringevent2-getstring.md)方法。  
  
## <a name="see-also"></a>另請參閱  
 [執行控制和狀態評估](../../extensibility/debugger/execution-control-and-state-evaluation.md)
