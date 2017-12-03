---
title: "ICorDebugExceptionDebugEvent::GetFlags 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 73225303-8852-487e-9a0e-9f0cb95e99d9
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 33534a65f7a58981abd3df324b5fe005a06669d9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugexceptiondebugeventgetflags-method"></a><span data-ttu-id="c69b0-102">ICorDebugExceptionDebugEvent::GetFlags 方法</span><span class="sxs-lookup"><span data-stu-id="c69b0-102">ICorDebugExceptionDebugEvent::GetFlags Method</span></span>
<span data-ttu-id="c69b0-103">获取指示是否可拦截异常的标志。</span><span class="sxs-lookup"><span data-stu-id="c69b0-103">Gets a flag that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c69b0-104">语法</span><span class="sxs-lookup"><span data-stu-id="c69b0-104">Syntax</span></span>  
  
```  
HRESULT GetFlags(  
   [out] CorDebugExceptionFlags *pdwFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c69b0-105">参数</span><span class="sxs-lookup"><span data-stu-id="c69b0-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="c69b0-106">[out]指向的指针[CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md)值，该值指示是否可拦截异常。</span><span class="sxs-lookup"><span data-stu-id="c69b0-106">[out] A pointer to a [CorDebugExceptionFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionflags-enumeration.md) value that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c69b0-107">备注</span><span class="sxs-lookup"><span data-stu-id="c69b0-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c69b0-108">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="c69b0-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c69b0-109">要求</span><span class="sxs-lookup"><span data-stu-id="c69b0-109">Requirements</span></span>  
 <span data-ttu-id="c69b0-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c69b0-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c69b0-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c69b0-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c69b0-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c69b0-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c69b0-113">**.NET framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c69b0-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c69b0-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c69b0-114">See Also</span></span>  
 [<span data-ttu-id="c69b0-115">ICorDebugExceptionDebugEvent 接口</span><span class="sxs-lookup"><span data-stu-id="c69b0-115">ICorDebugExceptionDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)  
 [<span data-ttu-id="c69b0-116">调试接口</span><span class="sxs-lookup"><span data-stu-id="c69b0-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)