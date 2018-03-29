---
title: 获得 CcVersion
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/30/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7d370abd-0c01-4490-88a1-55b42e51b663
description: 返回云连接器设备的版本。 Get-CCVersion 只能用于云连接器的主机。
ms.openlocfilehash: 8391264603a73e3f594122dcdd2eb62b9ba19978
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="get-ccversion"></a><span data-ttu-id="a3ab3-104">获得 CcVersion</span><span class="sxs-lookup"><span data-stu-id="a3ab3-104">Get-CcVersion</span></span>
 
<span data-ttu-id="a3ab3-105">返回云连接器设备的版本。</span><span class="sxs-lookup"><span data-stu-id="a3ab3-105">Returns the version of the Cloud Connector appliance.</span></span> <span data-ttu-id="a3ab3-106">Get-CCVersion 只能用于云连接器的主机。</span><span class="sxs-lookup"><span data-stu-id="a3ab3-106">Get-CCVersion can only be used on the host machine of Cloud Connector.</span></span>
  
```
Get-CcVersion [[-VersionType] <String>] [<CommonParameters>]
```

## <a name="detailed-description"></a><span data-ttu-id="a3ab3-107">详细说明</span><span class="sxs-lookup"><span data-stu-id="a3ab3-107">Detailed Description</span></span>

<span data-ttu-id="a3ab3-108">在装置的目录中，并在主机服务器上部署虚拟机返回云接头装置基于 PowerShell 脚本安装，文件的版本。</span><span class="sxs-lookup"><span data-stu-id="a3ab3-108">Returns the version of the Cloud Connector appliance based on PowerShell scripts installed, files in the Appliance directory, and the virtual machines deployed on host server.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="a3ab3-109">参数</span><span class="sxs-lookup"><span data-stu-id="a3ab3-109">Parameters</span></span>

|<span data-ttu-id="a3ab3-110">**参数**</span><span class="sxs-lookup"><span data-stu-id="a3ab3-110">**Parameter**</span></span>|<span data-ttu-id="a3ab3-111">**必填**</span><span class="sxs-lookup"><span data-stu-id="a3ab3-111">**Required**</span></span>|<span data-ttu-id="a3ab3-112">**类型**</span><span class="sxs-lookup"><span data-stu-id="a3ab3-112">**Type**</span></span>|<span data-ttu-id="a3ab3-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="a3ab3-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a3ab3-114">VersionType</span><span class="sxs-lookup"><span data-stu-id="a3ab3-114">VersionType</span></span>  <br/> |<span data-ttu-id="a3ab3-115">可选</span><span class="sxs-lookup"><span data-stu-id="a3ab3-115">Optional</span></span>  <br/> |<span data-ttu-id="a3ab3-116">System.String</span><span class="sxs-lookup"><span data-stu-id="a3ab3-116">System.String</span></span>  <br/> |<span data-ttu-id="a3ab3-117">版本类型。</span><span class="sxs-lookup"><span data-stu-id="a3ab3-117">Type of version.</span></span> <span data-ttu-id="a3ab3-118">参数值可为 RunningScripts、RunningBits、BackupBits 或 All。</span><span class="sxs-lookup"><span data-stu-id="a3ab3-118">Value of parameter can be RunningScripts, RunningBits, BackupBits or All.</span></span> <span data-ttu-id="a3ab3-119">默认值为 RunningScripts。</span><span class="sxs-lookup"><span data-stu-id="a3ab3-119">Default value is RunningScripts.</span></span>  <br/> |
   
## <a name="examples"></a><span data-ttu-id="a3ab3-120">示例</span><span class="sxs-lookup"><span data-stu-id="a3ab3-120">Examples</span></span>
<span data-ttu-id="a3ab3-121"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="a3ab3-121"></span></span>

### <a name="example-1"></a><span data-ttu-id="a3ab3-122">示例 1</span><span class="sxs-lookup"><span data-stu-id="a3ab3-122">Example 1</span></span>

<span data-ttu-id="a3ab3-123">下面的示例演示在您打开 PowerShell 控制台云连接器当前正在运行的脚本的版本：</span><span class="sxs-lookup"><span data-stu-id="a3ab3-123">The following example shows the Cloud Connector version of the currently running script in your open PowerShell console:</span></span>
  
```
Get-CcVersion
```

### <a name="example-2"></a><span data-ttu-id="a3ab3-124">示例 2</span><span class="sxs-lookup"><span data-stu-id="a3ab3-124">Example 2</span></span>

<span data-ttu-id="a3ab3-125">下面的示例演示云连接器版本部署到虚拟机的当前正在运行的二进制文件。</span><span class="sxs-lookup"><span data-stu-id="a3ab3-125">The following example shows the Cloud Connector version of the currently running binaries deployed to the virtual machines.</span></span> <span data-ttu-id="a3ab3-126">可在 Hyper-v 管理器中正在运行的虚拟机名称中查看版本。</span><span class="sxs-lookup"><span data-stu-id="a3ab3-126">You can see the version in the running virtual machine names in Hyper-v Manager:</span></span>
  
```
Get-CCVersion -VersionType RunningBits
```

## <a name="input-types"></a><span data-ttu-id="a3ab3-127">输入类型</span><span class="sxs-lookup"><span data-stu-id="a3ab3-127">Input Types</span></span>
<span data-ttu-id="a3ab3-128"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="a3ab3-128"></span></span>

<span data-ttu-id="a3ab3-129">无。</span><span class="sxs-lookup"><span data-stu-id="a3ab3-129">None.</span></span> <span data-ttu-id="a3ab3-130">Get-CcVersion cmdlet 不接受主线输入。</span><span class="sxs-lookup"><span data-stu-id="a3ab3-130">The Get-CcVersion cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="a3ab3-131">返回类型</span><span class="sxs-lookup"><span data-stu-id="a3ab3-131">Return Types</span></span>
<span data-ttu-id="a3ab3-132"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="a3ab3-132"></span></span>

<span data-ttu-id="a3ab3-133">无。</span><span class="sxs-lookup"><span data-stu-id="a3ab3-133">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a3ab3-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a3ab3-134">See also</span></span>
<span data-ttu-id="a3ab3-135"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="a3ab3-135"></span></span>

<span data-ttu-id="a3ab3-136">无。</span><span class="sxs-lookup"><span data-stu-id="a3ab3-136">None.</span></span>
  

