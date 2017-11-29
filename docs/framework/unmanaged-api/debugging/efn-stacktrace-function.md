---
title: "_EFN_StackTrace 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: _EFN_StackTrace
api_location: mscordbi.dll
api_type: COM
f1_keywords: _EFN_StackTrace
helpviewer_keywords: _EFN_StackTrace function [.NET Framework debugging]
ms.assetid: caea7754-867c-4360-a65c-5ced4408fd9d
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 031812b2c286c5647afb9c88882f22e2c7c3addf
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="efnstacktrace-function"></a><span data-ttu-id="8474e-102">_EFN_StackTrace 函数</span><span class="sxs-lookup"><span data-stu-id="8474e-102">_EFN_StackTrace Function</span></span>
<span data-ttu-id="8474e-103">提供托管堆栈跟踪的文本表示形式以及 `CONTEXT` 记录的数组，其中每项对应非托管代码和托管代码之间的每个转换。</span><span class="sxs-lookup"><span data-stu-id="8474e-103">Provides a text representation of a managed stack trace and an array of `CONTEXT` records, one for each transition between unmanaged and managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8474e-104">语法</span><span class="sxs-lookup"><span data-stu-id="8474e-104">Syntax</span></span>  
  
```  
HRESULT CALLBACK _EFN_StackTrace(  
    [in]  PDEBUG_CLIENT  Client,  
    [out] WCHAR          wszTextOut[],  
    [out] size_t         *puiTextLength,  
    [out] LPVOID         pTransitionContexts,  
    [out] size_t         *puiTransitionContextCount,  
    [in]  size_t         uiSizeOfContext,  
    [in]  DWORD          Flags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8474e-105">参数</span><span class="sxs-lookup"><span data-stu-id="8474e-105">Parameters</span></span>  
 `Client`  
 <span data-ttu-id="8474e-106">[in]正在调试客户端。</span><span class="sxs-lookup"><span data-stu-id="8474e-106">[in] The client being debugged.</span></span>  
  
 `wszTextOut`  
 <span data-ttu-id="8474e-107">[out]文本表示形式的堆栈跟踪。</span><span class="sxs-lookup"><span data-stu-id="8474e-107">[out] The text representation of the stack trace.</span></span>  
  
 `puiTextLength`  
 <span data-ttu-id="8474e-108">[out]中的字符数的指针`wszTextOut`。</span><span class="sxs-lookup"><span data-stu-id="8474e-108">[out] A pointer to the number of characters in `wszTextOut`.</span></span>  
  
 `pTransitionContexts`  
 <span data-ttu-id="8474e-109">[out]转换上下文的数组。</span><span class="sxs-lookup"><span data-stu-id="8474e-109">[out] The array of transition contexts.</span></span>  
  
 `puiTransitionContextCount`  
 <span data-ttu-id="8474e-110">[out]指向数组中的转换上下文的数的指针。</span><span class="sxs-lookup"><span data-stu-id="8474e-110">[out] A pointer to the number of transition contexts in the array.</span></span>  
  
 `uiSizeOfContext`  
 <span data-ttu-id="8474e-111">[in]上下文结构的大小。</span><span class="sxs-lookup"><span data-stu-id="8474e-111">[in] The size of the context structure.</span></span>  
  
 `Flags`  
 <span data-ttu-id="8474e-112">[in]设置为 0 或 SOS_STACKTRACE_SHOWADDRESSES (0x01) 以显示 EBP 寄存器和每个前面的输入堆栈指针 (ESP)`module!functionname`行。</span><span class="sxs-lookup"><span data-stu-id="8474e-112">[in] Set to either 0 or SOS_STACKTRACE_SHOWADDRESSES (0x01) to show the EBP register and the enter stack pointer (ESP) in front of each `module!functionname` line.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8474e-113">备注</span><span class="sxs-lookup"><span data-stu-id="8474e-113">Remarks</span></span>  
 <span data-ttu-id="8474e-114">`_EFN_StackTrace`结构可以从 WinDbg 编程接口进行调用。</span><span class="sxs-lookup"><span data-stu-id="8474e-114">The `_EFN_StackTrace` structure can be called from a WinDbg programmatic interface.</span></span> <span data-ttu-id="8474e-115">参数的用法如下：</span><span class="sxs-lookup"><span data-stu-id="8474e-115">Parameters are used as follows:</span></span>  
  
-   <span data-ttu-id="8474e-116">如果`wszTextOut`为 null 和`puiTextLength`是不为 null，则该函数将返回的字符串长度以`puiTextLength`。</span><span class="sxs-lookup"><span data-stu-id="8474e-116">If `wszTextOut` is null and `puiTextLength` is not null, the function returns the string length in `puiTextLength`.</span></span>  
  
-   <span data-ttu-id="8474e-117">如果`wszTextOut`是不为 null，函数将存储中的文本`wszTextOut`所指示的位置到`puiTextLength`。</span><span class="sxs-lookup"><span data-stu-id="8474e-117">If `wszTextOut` is not null, the function stores text in `wszTextOut` up to the location indicated by `puiTextLength`.</span></span> <span data-ttu-id="8474e-118">成功返回如果没有足够的空间中的缓冲区或返回 E_OUTOFMEMORY 如果缓冲区长度不足。</span><span class="sxs-lookup"><span data-stu-id="8474e-118">It returns successfully if there was enough room in the buffer, or returns E_OUTOFMEMORY if the buffer was not long enough.</span></span>  
  
-   <span data-ttu-id="8474e-119">如果该函数的转换部分将被忽略`pTransitionContexts`和`puiTransitionContextCount`都为 null。</span><span class="sxs-lookup"><span data-stu-id="8474e-119">The transition portion of the function is ignored if `pTransitionContexts` and `puiTransitionContextCount` are both null.</span></span> <span data-ttu-id="8474e-120">在这种情况下，函数提供与只有函数名称的文本输出的调用方。</span><span class="sxs-lookup"><span data-stu-id="8474e-120">In this case, the function provides callers with text output of only the function names.</span></span>  
  
-   <span data-ttu-id="8474e-121">如果`pTransitionContexts`为 null 和`puiTransitionContextCount`是不为 null，则该函数将返回所需数量的上下文中的条目`puiTransitionContextCount`。</span><span class="sxs-lookup"><span data-stu-id="8474e-121">If `pTransitionContexts` is null and `puiTransitionContextCount` is not null, the function returns the necessary number of context entries in `puiTransitionContextCount`.</span></span>  
  
-   <span data-ttu-id="8474e-122">如果`pTransitionContexts`是不为 null，函数会将其视为数组的长度的结构`puiTransitionContextCount`。</span><span class="sxs-lookup"><span data-stu-id="8474e-122">If `pTransitionContexts` is not null, the function treats it as an array of structures of length `puiTransitionContextCount`.</span></span> <span data-ttu-id="8474e-123">通过给定的结构大小`uiSizeOfContext`，而且的大小必须[SimpleContext](../../../../docs/framework/unmanaged-api/debugging/stacktrace-simplecontext-structure.md)或`CONTEXT`体系结构。</span><span class="sxs-lookup"><span data-stu-id="8474e-123">The structure size is given by `uiSizeOfContext`, and must be the size of [SimpleContext](../../../../docs/framework/unmanaged-api/debugging/stacktrace-simplecontext-structure.md) or `CONTEXT` for the architecture.</span></span>  
  
-   <span data-ttu-id="8474e-124">`wszTextOut`是编写采用以下格式：</span><span class="sxs-lookup"><span data-stu-id="8474e-124">`wszTextOut` is written in the following format:</span></span>  
  
    ```  
    "<ModuleName>!<Function Name>[+<offset in hex>]  
    ...  
    (TRANSITION)  
    ..."  
    ```  
  
-   <span data-ttu-id="8474e-125">如果以十六进制表示偏移量为 0x0，则写入没有偏移量。</span><span class="sxs-lookup"><span data-stu-id="8474e-125">If the offset in hex is 0x0, no offset is written.</span></span>  
  
-   <span data-ttu-id="8474e-126">如果没有任何托管的代码的线程上当前上下文中，该函数将返回 SOS_E_NOMANAGEDCODE。</span><span class="sxs-lookup"><span data-stu-id="8474e-126">If there is no managed code on the thread currently in context, the function returns SOS_E_NOMANAGEDCODE.</span></span>  
  
-   <span data-ttu-id="8474e-127">`Flags`参数为 0 或 SOS_STACKTRACE_SHOWADDRESSES 若要查看每个前面的 EBP 和 ESP`module!functionname`行。</span><span class="sxs-lookup"><span data-stu-id="8474e-127">The `Flags` parameter is either 0 or SOS_STACKTRACE_SHOWADDRESSES to see EBP and ESP in front of each `module!functionname` line.</span></span> <span data-ttu-id="8474e-128">默认情况下，则为 0。</span><span class="sxs-lookup"><span data-stu-id="8474e-128">By default, it is 0.</span></span>  
  
    ```  
    #define SOS_STACKTRACE_SHOWADDRESSES   0x00000001  
    ```  
  
## <a name="requirements"></a><span data-ttu-id="8474e-129">要求</span><span class="sxs-lookup"><span data-stu-id="8474e-129">Requirements</span></span>  
 <span data-ttu-id="8474e-130">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8474e-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8474e-131">**标头：** SOS_Stacktrace.h</span><span class="sxs-lookup"><span data-stu-id="8474e-131">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="8474e-132">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8474e-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8474e-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8474e-133">See Also</span></span>  
 [<span data-ttu-id="8474e-134">调试全局静态函数</span><span class="sxs-lookup"><span data-stu-id="8474e-134">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)