---
title: Get-CcVersion
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/30/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7d370abd-0c01-4490-88a1-55b42e51b663
description: 返回云连接器设备的版本。 Get-CCVersion 只能用于云连接器的主机。
ms.openlocfilehash: a7d50bbcd01dc80fe3e2202286c1adc1b5d5f9bd
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003342"
---
# <a name="get-ccversion"></a><span data-ttu-id="fa503-104">Get-CcVersion</span><span class="sxs-lookup"><span data-stu-id="fa503-104">Get-CcVersion</span></span>
 
<span data-ttu-id="fa503-p102">返回云连接器设备的版本。 Get-CCVersion 只能用于云连接器的主机。</span><span class="sxs-lookup"><span data-stu-id="fa503-p102">Returns the version of the Cloud Connector appliance. Get-CCVersion can only be used on the host machine of Cloud Connector.</span></span>
  
```powershell
Get-CcVersion [[-VersionType] <String>] [<CommonParameters>]
```

## <a name="detailed-description"></a><span data-ttu-id="fa503-107">详细说明</span><span class="sxs-lookup"><span data-stu-id="fa503-107">Detailed Description</span></span>

<span data-ttu-id="fa503-108">基于安装的 PowerShell 脚本、装置目录中的文件和在主机服务器上部署的虚拟机返回云连接器装置的版本。</span><span class="sxs-lookup"><span data-stu-id="fa503-108">Returns the version of the Cloud Connector appliance based on PowerShell scripts installed, files in the Appliance directory, and the virtual machines deployed on host server.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="fa503-109">参数</span><span class="sxs-lookup"><span data-stu-id="fa503-109">Parameters</span></span>

|<span data-ttu-id="fa503-110">**参数**</span><span class="sxs-lookup"><span data-stu-id="fa503-110">**Parameter**</span></span>|<span data-ttu-id="fa503-111">**必需**</span><span class="sxs-lookup"><span data-stu-id="fa503-111">**Required**</span></span>|<span data-ttu-id="fa503-112">**类型**</span><span class="sxs-lookup"><span data-stu-id="fa503-112">**Type**</span></span>|<span data-ttu-id="fa503-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="fa503-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fa503-114">VersionType</span><span class="sxs-lookup"><span data-stu-id="fa503-114">VersionType</span></span>  <br/> |<span data-ttu-id="fa503-115">可选</span><span class="sxs-lookup"><span data-stu-id="fa503-115">Optional</span></span>  <br/> |<span data-ttu-id="fa503-116">System.String</span><span class="sxs-lookup"><span data-stu-id="fa503-116">System.String</span></span>  <br/> |<span data-ttu-id="fa503-p103">版本类型。 参数值可为 RunningScripts、RunningBits、BackupBits 或 All。 默认值为 RunningScripts。 </span><span class="sxs-lookup"><span data-stu-id="fa503-p103">Type of version. Value of parameter can be RunningScripts, RunningBits, BackupBits or All. Default value is RunningScripts.</span></span>  <br/> |
   
## <a name="examples"></a><span data-ttu-id="fa503-120">示例</span><span class="sxs-lookup"><span data-stu-id="fa503-120">Examples</span></span>
<span data-ttu-id="fa503-121"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="fa503-121"></span></span>

### <a name="example-1"></a><span data-ttu-id="fa503-122">示例 1</span><span class="sxs-lookup"><span data-stu-id="fa503-122">Example 1</span></span>

<span data-ttu-id="fa503-123">以下示例显示打开的 PowerShell 控制台中当前正在运行的脚本的云连接器版本：</span><span class="sxs-lookup"><span data-stu-id="fa503-123">The following example shows the Cloud Connector version of the currently running script in your open PowerShell console:</span></span>
  
```powershell
Get-CcVersion
```

### <a name="example-2"></a><span data-ttu-id="fa503-124">示例 2</span><span class="sxs-lookup"><span data-stu-id="fa503-124">Example 2</span></span>

<span data-ttu-id="fa503-125">以下示例显示了部署到虚拟机的当前正在运行的二进制文件的云连接器版本。</span><span class="sxs-lookup"><span data-stu-id="fa503-125">The following example shows the Cloud Connector version of the currently running binaries deployed to the virtual machines.</span></span> <span data-ttu-id="fa503-126">可在 Hyper-v 管理器中正在运行的虚拟机名称中查看版本。</span><span class="sxs-lookup"><span data-stu-id="fa503-126">You can see the version in the running virtual machine names in Hyper-v Manager:</span></span>
  
```powershell
Get-CCVersion -VersionType RunningBits
```

## <a name="input-types"></a><span data-ttu-id="fa503-127">输入类型</span><span class="sxs-lookup"><span data-stu-id="fa503-127">Input Types</span></span>
<span data-ttu-id="fa503-128"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="fa503-128"></span></span>

<span data-ttu-id="fa503-p105">无。 Get-CcVersion cmdlet 不接受主线输入。</span><span class="sxs-lookup"><span data-stu-id="fa503-p105">None. The Get-CcVersion cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="fa503-131">返回类型</span><span class="sxs-lookup"><span data-stu-id="fa503-131">Return Types</span></span>
<span data-ttu-id="fa503-132"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="fa503-132"></span></span>

<span data-ttu-id="fa503-133">无。</span><span class="sxs-lookup"><span data-stu-id="fa503-133">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="fa503-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fa503-134">See also</span></span>
<span data-ttu-id="fa503-135"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="fa503-135"></span></span>

<span data-ttu-id="fa503-136">无。</span><span class="sxs-lookup"><span data-stu-id="fa503-136">None.</span></span>
  

