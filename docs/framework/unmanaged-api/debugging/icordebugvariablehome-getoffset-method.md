---
title: "ICorDebugVariableHome::GetOffset 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name: ICorDebugVariableHome.GetOffset
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugVariableHome::GetOffset
helpviewer_keywords:
- ICorDebugVariableHome::GetOffset method [.NET Framework debugging]
- GetOffset method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: f025c2e5-3f6c-4be8-9ffe-c8b214617dfe
topic_type: apiref
caps.latest.revision: "3"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0ddedc83e4e51cf12a3f8a0504d90bda7f944a6d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugvariablehomegetoffset-method"></a><span data-ttu-id="4e17b-102">ICorDebugVariableHome::GetOffset 方法</span><span class="sxs-lookup"><span data-stu-id="4e17b-102">ICorDebugVariableHome::GetOffset Method</span></span>
<span data-ttu-id="4e17b-103">获取从基寄存器变量的偏移量。</span><span class="sxs-lookup"><span data-stu-id="4e17b-103">Gets the offset from the base register for a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e17b-104">语法</span><span class="sxs-lookup"><span data-stu-id="4e17b-104">Syntax</span></span>  
  
```  
HRESULT GetOffset(  
    [out] LONG *pOffset  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4e17b-105">参数</span><span class="sxs-lookup"><span data-stu-id="4e17b-105">Parameters</span></span>  
 `pOffset`  
 <span data-ttu-id="4e17b-106">[out]从基寄存器的偏移量。</span><span class="sxs-lookup"><span data-stu-id="4e17b-106">[out] The offset from the base register.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4e17b-107">返回值</span><span class="sxs-lookup"><span data-stu-id="4e17b-107">Return Value</span></span>  
 <span data-ttu-id="4e17b-108">该方法返回以下值：</span><span class="sxs-lookup"><span data-stu-id="4e17b-108">The method returns the following values:</span></span>  
  
|<span data-ttu-id="4e17b-109">值</span><span class="sxs-lookup"><span data-stu-id="4e17b-109">Value</span></span>|<span data-ttu-id="4e17b-110">描述</span><span class="sxs-lookup"><span data-stu-id="4e17b-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="4e17b-111">该变量是在注册相对内存位置。</span><span class="sxs-lookup"><span data-stu-id="4e17b-111">The variable is in a register-relative memory location.</span></span>|  
|`E_FAIL`|<span data-ttu-id="4e17b-112">变量不是在注册相对内存位置。</span><span class="sxs-lookup"><span data-stu-id="4e17b-112">The variable is not in a register-relative memory location.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4e17b-113">要求</span><span class="sxs-lookup"><span data-stu-id="4e17b-113">Requirements</span></span>  
 <span data-ttu-id="4e17b-114">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4e17b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e17b-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4e17b-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4e17b-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4e17b-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4e17b-117">**.NET framework 版本：**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e17b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e17b-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4e17b-118">See Also</span></span>  
 [<span data-ttu-id="4e17b-119">ICorDebugVariableHome 接口</span><span class="sxs-lookup"><span data-stu-id="4e17b-119">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)