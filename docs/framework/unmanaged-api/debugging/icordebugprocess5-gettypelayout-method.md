---
title: "ICorDebugProcess5::GetTypeLayout 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess5.GetTypeLayout
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess5::GetTypeLayout
helpviewer_keywords:
- ICorDebugProcess5::GetTypeLayout method [.NET Framework debugging]
- GetTypeLayout method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: bd62f5d1-e874-41f1-81e5-a29a7572c15d
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2f36b78558f8a8005735166436ad3dead28992e3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugprocess5gettypelayout-method"></a><span data-ttu-id="1918e-102">ICorDebugProcess5::GetTypeLayout 方法</span><span class="sxs-lookup"><span data-stu-id="1918e-102">ICorDebugProcess5::GetTypeLayout Method</span></span>
<span data-ttu-id="1918e-103">在根据其类型标识符的内存中获取对象的布局信息。</span><span class="sxs-lookup"><span data-stu-id="1918e-103">Gets information about the layout of an object in memory based on its type identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1918e-104">语法</span><span class="sxs-lookup"><span data-stu-id="1918e-104">Syntax</span></span>  
  
```  
HRESULT GetTypeLayout(    [in] COR_TYPEID id,     [out] COR_TYPE_LAYOUT *pLayout);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1918e-105">参数</span><span class="sxs-lookup"><span data-stu-id="1918e-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="1918e-106">[in]A [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)指定所需其布局的类型的令牌。</span><span class="sxs-lookup"><span data-stu-id="1918e-106">[in] A [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) token that specifies the type whose layout is desired.</span></span>  
  
 `pLayout`  
 <span data-ttu-id="1918e-107">[out]指向的指针[COR_TYPE_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md)包含内存中对象的布局信息的结构。</span><span class="sxs-lookup"><span data-stu-id="1918e-107">[out] A pointer to a [COR_TYPE_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md) structure that contains information about the layout of the object in memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1918e-108">备注</span><span class="sxs-lookup"><span data-stu-id="1918e-108">Remarks</span></span>  
 <span data-ttu-id="1918e-109">`ICorDebugProcess5::GetTypeLayout`方法提供了有关基于对象的信息其[COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)，返回由大量其他[ICorDebugProcess5](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)方法。</span><span class="sxs-lookup"><span data-stu-id="1918e-109">The `ICorDebugProcess5::GetTypeLayout` method provides information about an object based on its [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md), which is returned by a number of other [ICorDebugProcess5](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md) methods.</span></span> <span data-ttu-id="1918e-110">通过提供的信息[COR_TYPE_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md)通过方法来填充的结构。</span><span class="sxs-lookup"><span data-stu-id="1918e-110">The information is provided by a [COR_TYPE_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md) structure that is populated by the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1918e-111">要求</span><span class="sxs-lookup"><span data-stu-id="1918e-111">Requirements</span></span>  
 <span data-ttu-id="1918e-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1918e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1918e-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1918e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1918e-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1918e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1918e-115">**.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1918e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1918e-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1918e-116">See Also</span></span>  
 [<span data-ttu-id="1918e-117">COR_TYPE_LAYOUT 结构</span><span class="sxs-lookup"><span data-stu-id="1918e-117">COR_TYPE_LAYOUT Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md)  
 [<span data-ttu-id="1918e-118">ICorDebugProcess5 接口</span><span class="sxs-lookup"><span data-stu-id="1918e-118">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 [<span data-ttu-id="1918e-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="1918e-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)