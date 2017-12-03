---
title: "“ICor调试数据目标2”接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 13f11388-2f91-48d8-98d6-6a4a63cb5746
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 034e7d46c1b38aecdab18ea3a7d3b149b3d59369
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugdatatarget2-interface"></a><span data-ttu-id="d416a-102">“ICor调试数据目标2”接口</span><span class="sxs-lookup"><span data-stu-id="d416a-102">ICorDebugDataTarget2 Interface</span></span>
<span data-ttu-id="d416a-103">合理扩展[ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="d416a-103">Logically extends the [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d416a-104">方法</span><span class="sxs-lookup"><span data-stu-id="d416a-104">Methods</span></span>  
  
|<span data-ttu-id="d416a-105">方法</span><span class="sxs-lookup"><span data-stu-id="d416a-105">Method</span></span>|<span data-ttu-id="d416a-106">描述</span><span class="sxs-lookup"><span data-stu-id="d416a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d416a-107">CreateVirtualUnwinder 方法</span><span class="sxs-lookup"><span data-stu-id="d416a-107">CreateVirtualUnwinder Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-createvirtualunwinder-method.md)|<span data-ttu-id="d416a-108">创建一个从初始上下文（不一定是线程叶）开始展开的新堆栈开卷机。</span><span class="sxs-lookup"><span data-stu-id="d416a-108">Creates a new stack unwinder that starts unwinding from an initial context (which isn't necessarily the leaf of a thread).</span></span>|  
|[<span data-ttu-id="d416a-109">EnumerateThreadIDs 方法</span><span class="sxs-lookup"><span data-stu-id="d416a-109">EnumerateThreadIDs Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-enumeratethreadids-method.md)|<span data-ttu-id="d416a-110">返回一组活动线程 ID。</span><span class="sxs-lookup"><span data-stu-id="d416a-110">Returns a list of active thread IDs.</span></span>|  
|[<span data-ttu-id="d416a-111">GetImageFromPointer 方法</span><span class="sxs-lookup"><span data-stu-id="d416a-111">GetImageFromPointer Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-getimagefrompointer-method.md)|<span data-ttu-id="d416a-112">返回该模块地址中的模块基址和大小。</span><span class="sxs-lookup"><span data-stu-id="d416a-112">Returns the module base address and size from an address in that module.</span></span>|  
|[<span data-ttu-id="d416a-113">GetImageLocation 方法</span><span class="sxs-lookup"><span data-stu-id="d416a-113">GetImageLocation Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-getimagelocation-method.md)|<span data-ttu-id="d416a-114">返回模块基址中的模块路径。</span><span class="sxs-lookup"><span data-stu-id="d416a-114">Returns the path of a module from the module's base address.</span></span>|  
|[<span data-ttu-id="d416a-115">GetSymbolProviderForImage 方法</span><span class="sxs-lookup"><span data-stu-id="d416a-115">GetSymbolProviderForImage Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-getsymbolproviderforimage-method.md)|<span data-ttu-id="d416a-116">返回该模块基址中的模块符号提供程序。</span><span class="sxs-lookup"><span data-stu-id="d416a-116">Returns the symbol-provider for a module from the base address of that module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d416a-117">备注</span><span class="sxs-lookup"><span data-stu-id="d416a-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d416a-118">此接口仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="d416a-118">This interface is available with .NET Native only.</span></span> <span data-ttu-id="d416a-119">如果在 .NET Native 外为 ICorDebug 方案实现此接口，则公共语言运行时将忽略此接口。</span><span class="sxs-lookup"><span data-stu-id="d416a-119">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d416a-120">要求</span><span class="sxs-lookup"><span data-stu-id="d416a-120">Requirements</span></span>  
 <span data-ttu-id="d416a-121">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d416a-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d416a-122">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d416a-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d416a-123">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d416a-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d416a-124">**.NET framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d416a-124">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d416a-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d416a-125">See Also</span></span>  
 [<span data-ttu-id="d416a-126">调试接口</span><span class="sxs-lookup"><span data-stu-id="d416a-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="d416a-127">调试</span><span class="sxs-lookup"><span data-stu-id="d416a-127">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)