---
title: 转换-CcIsoToVhdx
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 216abec2-d354-4ee3-9999-0a6b350a4a5f
description: Convert-CcIsoToVhdx cmdlet 使用客户提供的 Windows Server 2012 R2 ISO 文件创建基本虚拟硬盘文件 (VHDX)。该 VHDX 文件将在部署 Skype for Business 云连接器版本过程中使用。
ms.openlocfilehash: 9bf27e7161a3d5c74cc972df12246c36226be8cc
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="convert-ccisotovhdx"></a><span data-ttu-id="1fb80-104">转换-CcIsoToVhdx</span><span class="sxs-lookup"><span data-stu-id="1fb80-104">Convert-CcIsoToVhdx</span></span>
 
<span data-ttu-id="1fb80-p102">Convert-CcIsoToVhdx cmdlet 使用客户提供的 Windows Server 2012 R2 ISO 文件创建基本虚拟硬盘文件 (VHDX)。该 VHDX 文件将在部署 Skype for Business 云连接器版本过程中使用。</span><span class="sxs-lookup"><span data-stu-id="1fb80-p102">The Convert-CcIsoToVhdx cmdlet creates a base virtual hard disk file (VHDX) using a customer supplied Windows Server 2012 R2 ISO file. The VHDX file will be used during the deployment of Skype for Business Cloud Connector Edition.</span></span>
  
```
Convert-CcIsoToVhdx [[-IsoFilePath] <string>] [-GeneralizeOnly] [-PauseBeforeUpdate]
```

## <a name="parameters"></a><span data-ttu-id="1fb80-107">参数</span><span class="sxs-lookup"><span data-stu-id="1fb80-107">Parameters</span></span>

|<span data-ttu-id="1fb80-108">**参数**</span><span class="sxs-lookup"><span data-stu-id="1fb80-108">**Parameter**</span></span>|<span data-ttu-id="1fb80-109">**必填**</span><span class="sxs-lookup"><span data-stu-id="1fb80-109">**Required**</span></span>|<span data-ttu-id="1fb80-110">**类型**</span><span class="sxs-lookup"><span data-stu-id="1fb80-110">**Type**</span></span>|<span data-ttu-id="1fb80-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="1fb80-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1fb80-112">IsoFilePath</span><span class="sxs-lookup"><span data-stu-id="1fb80-112">IsoFilePath</span></span>  <br/> | <span data-ttu-id="1fb80-113">必需</span><span class="sxs-lookup"><span data-stu-id="1fb80-113">Required</span></span> <br/> |<span data-ttu-id="1fb80-114">System.String</span><span class="sxs-lookup"><span data-stu-id="1fb80-114">System.String</span></span>  <br/> | <span data-ttu-id="1fb80-115"> Windows Server 2012 R2 ISO 文件的路径。</span><span class="sxs-lookup"><span data-stu-id="1fb80-115">The path to the Windows Server 2012 R2 ISO file.</span></span> <br/> |
|<span data-ttu-id="1fb80-116">GeneralizeOnly</span><span class="sxs-lookup"><span data-stu-id="1fb80-116">GeneralizeOnly</span></span>  <br/> |<span data-ttu-id="1fb80-117">可选</span><span class="sxs-lookup"><span data-stu-id="1fb80-117">Optional</span></span>  <br/> |<span data-ttu-id="1fb80-118">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="1fb80-118">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="1fb80-p103">如果在 Windows 更新过程中，转换失败，可以尝试手动配置网络/代理并更新 Windows。完成手动操作后，结合 -GeneralizeOnly 参数运行此 cmdlet，它将完成其余作业。</span><span class="sxs-lookup"><span data-stu-id="1fb80-p103">If the conversion process fails during Windows update, you can try to configure a network/proxy and update Windows manually. After the manual work is done, you can run this cmdlet with the -GeneralizeOnly parameter and it will complete the remaining jobs.</span></span>  <br/> |
|<span data-ttu-id="1fb80-121">PauseBeforeUpdate</span><span class="sxs-lookup"><span data-stu-id="1fb80-121">PauseBeforeUpdate</span></span>  <br/> |<span data-ttu-id="1fb80-122">可选</span><span class="sxs-lookup"><span data-stu-id="1fb80-122">Optional</span></span>  <br/> |<span data-ttu-id="1fb80-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="1fb80-123">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="1fb80-p104">要更新 Windows，可能需要对基本虚拟机执行一些手动网络/代理配置。如果提供此参数，转换过程将在 Windows 更新之前暂停。完成手动配置后，可以继续该过程。</span><span class="sxs-lookup"><span data-stu-id="1fb80-p104">To update Windows, some manual network/proxy configuration on the base VM might be necessary. The conversion process will pause before Windows update if this parameter is provided. After the manual configuration is done, you can resume the process.</span></span>  <br/> |
   
## <a name="examples"></a><span data-ttu-id="1fb80-127">示例</span><span class="sxs-lookup"><span data-stu-id="1fb80-127">Examples</span></span>
<span data-ttu-id="1fb80-128"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="1fb80-128"></span></span>

### <a name="example-1"></a><span data-ttu-id="1fb80-129">示例 1</span><span class="sxs-lookup"><span data-stu-id="1fb80-129">Example 1</span></span>

<span data-ttu-id="1fb80-130">以下示例使用位于“C:\Windows_Server_2012_R2-EN-US-x64.ISO”的 Windows Server 2012 R2 ISO 文件准备基本 VHDX 文件：</span><span class="sxs-lookup"><span data-stu-id="1fb80-130">The following example prepares the base VHDX file using a Windows Server 2012 R2 ISO file located at "C:\Windows_Server_2012_R2-EN-US-x64.ISO":</span></span> 
  
```
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" 
```

### <a name="example-2"></a><span data-ttu-id="1fb80-131">示例 2</span><span class="sxs-lookup"><span data-stu-id="1fb80-131">Example 2</span></span>

<span data-ttu-id="1fb80-132">如果转换 CcIsoToVhdx cmdlet 失败过程中 Windows 更新，则可能是由于不正确的网络代理配置。</span><span class="sxs-lookup"><span data-stu-id="1fb80-132">If the Convert-CcIsoToVhdx cmdlet fails during Windows update, it's probably because of incorrect network/proxy configuration.</span></span> <span data-ttu-id="1fb80-133">可以按照错误消息中的说明操作，登录基本虚拟机来手动修复问题并更新 Windows。</span><span class="sxs-lookup"><span data-stu-id="1fb80-133">You can follow the instructions in the error message and log on to the base virtual machine to fix the issue and update Windows manually.</span></span> <span data-ttu-id="1fb80-134">完成手动操作后，重新结合 -GeneralizeOnly 参数运行该 cmdlet 以完成其余作业：</span><span class="sxs-lookup"><span data-stu-id="1fb80-134">After the manual work is done, run the cmdlet again with the -GeneralizeOnly parameter to complete the remaining jobs:</span></span> 
  
```
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -GeneralizeOnly
```

### <a name="example-3"></a><span data-ttu-id="1fb80-135">示例 3</span><span class="sxs-lookup"><span data-stu-id="1fb80-135">Example 3</span></span>

<span data-ttu-id="1fb80-136">如果需要执行手动配置来更新 Windows，你可以使用 -PauseBeforeUpdate 参数。</span><span class="sxs-lookup"><span data-stu-id="1fb80-136">If manual configuration is necessary to update Windows, you can use the -PauseBeforeUpdate parameter.</span></span> <span data-ttu-id="1fb80-137">使用此参数，Windows 更新过程之前，将暂停云连接器。</span><span class="sxs-lookup"><span data-stu-id="1fb80-137">With this parameter, Cloud Connector will pause before the Windows update process.</span></span> <span data-ttu-id="1fb80-138">之后你可以完成手动配置并继续转换过程，如下所示：</span><span class="sxs-lookup"><span data-stu-id="1fb80-138">You can then complete the manual configuration and resume the conversion process as follows:</span></span>
  
```
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -PauseBeforeUpdate 
```

## <a name="detailed-description"></a><span data-ttu-id="1fb80-139">详细说明</span><span class="sxs-lookup"><span data-stu-id="1fb80-139">Detailed Description</span></span>
<span data-ttu-id="1fb80-140"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="1fb80-140"></span></span>

<span data-ttu-id="1fb80-141">将 CcIsoToVhdx cmdlet 创建 VM 首先，安装云连接器取决于，然后再安装 Windows 更新某些基本组件的基础。</span><span class="sxs-lookup"><span data-stu-id="1fb80-141">The Convert-CcIsoToVhdx cmdlet creates a base VM first, installs some basic components that Cloud Connector depends on, and then installs Windows updates.</span></span> <span data-ttu-id="1fb80-142">最后，其泛化虚拟机 (sysprep) 以获取云接口装置的虚拟机将使用基 VHDX 文件。</span><span class="sxs-lookup"><span data-stu-id="1fb80-142">Finally, it generalizes the virtual machine (sysprep) to get a base VHDX file that will be used by the virtual machines of a Cloud Connector appliance.</span></span> 
  
## <a name="input-types"></a><span data-ttu-id="1fb80-143">输入类型</span><span class="sxs-lookup"><span data-stu-id="1fb80-143">Input Types</span></span>
<span data-ttu-id="1fb80-144"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="1fb80-144"></span></span>

<span data-ttu-id="1fb80-p108">无。Convert-CcIsoToVhdx cmdlet 不接受主线输入。</span><span class="sxs-lookup"><span data-stu-id="1fb80-p108">None. The Convert-CcIsoToVhdx cmdlet does not accept pipelined input.</span></span> 
  
## <a name="return-types"></a><span data-ttu-id="1fb80-147">返回类型</span><span class="sxs-lookup"><span data-stu-id="1fb80-147">Return Types</span></span>
<span data-ttu-id="1fb80-148"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="1fb80-148"></span></span>

<span data-ttu-id="1fb80-149">无</span><span class="sxs-lookup"><span data-stu-id="1fb80-149">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1fb80-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1fb80-150">See also</span></span>
<span data-ttu-id="1fb80-151"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="1fb80-151"></span></span>

<span data-ttu-id="1fb80-152">无</span><span class="sxs-lookup"><span data-stu-id="1fb80-152">None</span></span>
  

