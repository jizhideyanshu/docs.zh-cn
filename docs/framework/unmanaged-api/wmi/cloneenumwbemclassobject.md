---
title: "CloneEnumWbemClassObject 函数 （非托管 API 参考）"
description: "CloneEnumWbemClassObject 函数创建枚举器的逻辑副本。"
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: CloneEnumWbemClassObject
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: CloneEnumWbemClassObject
helpviewer_keywords: CloneEnumWbemClassObject function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7a4103a0103a334a0e5eace32d8fcf1b365917b8
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2017
---
# <a name="cloneenumwbemclassobject-function"></a><span data-ttu-id="0d8ed-103">CloneEnumWbemClassObject 函数</span><span class="sxs-lookup"><span data-stu-id="0d8ed-103">CloneEnumWbemClassObject function</span></span>
<span data-ttu-id="0d8ed-104">生成的枚举，保留当前位置枚举中的逻辑副本。</span><span class="sxs-lookup"><span data-stu-id="0d8ed-104">Makes a logical copy of an enumerator, retaining its current position in an enumeration.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="0d8ed-105">语法</span><span class="sxs-lookup"><span data-stu-id="0d8ed-105">Syntax</span></span>  
  
```  
HRESULT CloneEnumWbemClassObject (
   [out] IEnumWbemClassObject**  ppEnum, 
   [in] DWORD                    authLevel,
   [in] DWORD                    impLevel,
   [in] IEnumWbemClassObject*    pCurrentEnumWbemClassObject, 
   [in] BSTR                     strUser,
   [in] BSTR                     strPassword,
   [in BSTR]                     strAuthority 
); 
```  

## <a name="parameters"></a><span data-ttu-id="0d8ed-106">参数</span><span class="sxs-lookup"><span data-stu-id="0d8ed-106">Parameters</span></span>

`ppEnum`  
<span data-ttu-id="0d8ed-107">[out]接收一个指针，到新[IEnumWbemClassObject](https://msdn.microsoft.com/library/aa390857(v=vs.85).aspx)。</span><span class="sxs-lookup"><span data-stu-id="0d8ed-107">[out] Receives a pointer to a new [IEnumWbemClassObject](https://msdn.microsoft.com/library/aa390857(v=vs.85).aspx).</span></span>

`authLevel`  
<span data-ttu-id="0d8ed-108">[in]授权级别中。</span><span class="sxs-lookup"><span data-stu-id="0d8ed-108">[in] The authorization level.</span></span>

<span data-ttu-id="0d8ed-109">`impLevel`[in]模拟级别。</span><span class="sxs-lookup"><span data-stu-id="0d8ed-109">`impLevel` [in] The impersonation level.</span></span>

`pCurrentEnumWbemClassObject`  
<span data-ttu-id="0d8ed-110">[out]指向的指针[IEnumWbemClassObject](https://msdn.microsoft.com/library/aa390857(v=vs.85).aspx)要克隆的实例。</span><span class="sxs-lookup"><span data-stu-id="0d8ed-110">[out] A pointer to the [IEnumWbemClassObject](https://msdn.microsoft.com/library/aa390857(v=vs.85).aspx) instance to be cloned.</span></span>

`strUser`   
<span data-ttu-id="0d8ed-111">[in]用户名。</span><span class="sxs-lookup"><span data-stu-id="0d8ed-111">[in] The user name.</span></span> <span data-ttu-id="0d8ed-112">请参阅[ConnectServerWmi](connectserverwmi.md)有关详细信息的函数。</span><span class="sxs-lookup"><span data-stu-id="0d8ed-112">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`   
<span data-ttu-id="0d8ed-113">[in]密码。</span><span class="sxs-lookup"><span data-stu-id="0d8ed-113">[in] The password.</span></span> <span data-ttu-id="0d8ed-114">请参阅[ConnectServerWmi](connectserverwmi.md)有关详细信息的函数。</span><span class="sxs-lookup"><span data-stu-id="0d8ed-114">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`   
<span data-ttu-id="0d8ed-115">[in]用户的域名。</span><span class="sxs-lookup"><span data-stu-id="0d8ed-115">[in] The domain name of the user.</span></span> <span data-ttu-id="0d8ed-116">请参阅[ConnectServerWmi](connectserverwmi.md)有关详细信息的函数。</span><span class="sxs-lookup"><span data-stu-id="0d8ed-116">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="0d8ed-117">返回值</span><span class="sxs-lookup"><span data-stu-id="0d8ed-117">Return value</span></span>

<span data-ttu-id="0d8ed-118">此函数返回以下值中定义*WbemCli.h*标头文件，或者你可以定义它们常量作为在代码中：</span><span class="sxs-lookup"><span data-stu-id="0d8ed-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="0d8ed-119">返回的常量</span><span class="sxs-lookup"><span data-stu-id="0d8ed-119">Constant</span></span>  |<span data-ttu-id="0d8ed-120">值</span><span class="sxs-lookup"><span data-stu-id="0d8ed-120">Value</span></span>  |<span data-ttu-id="0d8ed-121">描述</span><span class="sxs-lookup"><span data-stu-id="0d8ed-121">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="0d8ed-122">0x80041001</span><span class="sxs-lookup"><span data-stu-id="0d8ed-122">0x80041001</span></span> | <span data-ttu-id="0d8ed-123">发生了常规错误。</span><span class="sxs-lookup"><span data-stu-id="0d8ed-123">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="0d8ed-124">0x80041008</span><span class="sxs-lookup"><span data-stu-id="0d8ed-124">0x80041008</span></span> | <span data-ttu-id="0d8ed-125">参数无效。</span><span class="sxs-lookup"><span data-stu-id="0d8ed-125">A parameter is invalid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="0d8ed-126">0x80041006</span><span class="sxs-lookup"><span data-stu-id="0d8ed-126">0x80041006</span></span> | <span data-ttu-id="0d8ed-127">没有足够的内存可完成该操作。</span><span class="sxs-lookup"><span data-stu-id="0d8ed-127">Not enough memory is available complete the operation.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="0d8ed-128">0x80041015</span><span class="sxs-lookup"><span data-stu-id="0d8ed-128">0x80041015</span></span> | <span data-ttu-id="0d8ed-129">之间的当前进程和 WMI 的远程过程调用 (RPC) 链接失败。</span><span class="sxs-lookup"><span data-stu-id="0d8ed-129">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="0d8ed-130">0</span><span class="sxs-lookup"><span data-stu-id="0d8ed-130">0</span></span> | <span data-ttu-id="0d8ed-131">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="0d8ed-131">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="0d8ed-132">备注</span><span class="sxs-lookup"><span data-stu-id="0d8ed-132">Remarks</span></span>

<span data-ttu-id="0d8ed-133">此函数包装对的调用[IEnumWbemClassObject::Clone](https://msdn.microsoft.com/library/aa390859(v=vs.85).aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="0d8ed-133">This function wraps a call to the [IEnumWbemClassObject::Clone](https://msdn.microsoft.com/library/aa390859(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="0d8ed-134">此方法将生成仅"最大程度"的副本。</span><span class="sxs-lookup"><span data-stu-id="0d8ed-134">This method makes only a "best effort" copy.</span></span> <span data-ttu-id="0d8ed-135">由于许多 CIM 对象的动态特性，则可能的新枚举数不会枚举与源枚举器相同的对象集。</span><span class="sxs-lookup"><span data-stu-id="0d8ed-135">Due to the dynamic nature of many CIM objects, it is possible that the new enumerator does not enumerate the same set of objects as the source enumerator.</span></span>  

<span data-ttu-id="0d8ed-136">如果函数调用失败，你可以通过调用来获取其他错误信息[GetErrorInfo](geterrorinfo.md)函数。</span><span class="sxs-lookup"><span data-stu-id="0d8ed-136">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="example"></a><span data-ttu-id="0d8ed-137">示例</span><span class="sxs-lookup"><span data-stu-id="0d8ed-137">Example</span></span>

<span data-ttu-id="0d8ed-138">有关示例，请参阅[IEnumWbemClassObject::Clone](https://msdn.microsoft.com/library/aa390859(v=vs.85).aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="0d8ed-138">For an example, see the [IEnumWbemClassObject::Clone](https://msdn.microsoft.com/library/aa390859(v=vs.85).aspx) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="0d8ed-139">要求</span><span class="sxs-lookup"><span data-stu-id="0d8ed-139">Requirements</span></span>  
 <span data-ttu-id="0d8ed-140">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0d8ed-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d8ed-141">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="0d8ed-141">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="0d8ed-142">**.NET framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="0d8ed-142">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d8ed-143">请参阅</span><span class="sxs-lookup"><span data-stu-id="0d8ed-143">See also</span></span>  
[<span data-ttu-id="0d8ed-144">WMI 和性能计数器 （非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="0d8ed-144">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)