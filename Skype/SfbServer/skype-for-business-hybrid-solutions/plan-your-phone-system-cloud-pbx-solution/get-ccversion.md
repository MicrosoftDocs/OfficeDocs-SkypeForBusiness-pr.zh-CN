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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7d370abd-0c01-4490-88a1-55b42e51b663
description: 返回云连接器设备的版本。 Get-CCVersion 只能用于云连接器的主机。
ms.openlocfilehash: 706b480c2f8e277b7f41fe28e88cc062fea6603a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799842"
---
# <a name="get-ccversion"></a><span data-ttu-id="5e0a0-104">Get-CcVersion</span><span class="sxs-lookup"><span data-stu-id="5e0a0-104">Get-CcVersion</span></span>
 
<span data-ttu-id="5e0a0-p102">返回云连接器设备的版本。 Get-CCVersion 只能用于云连接器的主机。</span><span class="sxs-lookup"><span data-stu-id="5e0a0-p102">Returns the version of the Cloud Connector appliance. Get-CCVersion can only be used on the host machine of Cloud Connector.</span></span>
  
```powershell
Get-CcVersion [[-VersionType] <String>] [<CommonParameters>]
```

## <a name="detailed-description"></a><span data-ttu-id="5e0a0-107">详细说明</span><span class="sxs-lookup"><span data-stu-id="5e0a0-107">Detailed Description</span></span>

<span data-ttu-id="5e0a0-108">基于安装的 PowerShell 脚本、装置目录中的文件和在主机服务器上部署的虚拟机返回云连接器装置的版本。</span><span class="sxs-lookup"><span data-stu-id="5e0a0-108">Returns the version of the Cloud Connector appliance based on PowerShell scripts installed, files in the Appliance directory, and the virtual machines deployed on host server.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="5e0a0-109">参数</span><span class="sxs-lookup"><span data-stu-id="5e0a0-109">Parameters</span></span>

|<span data-ttu-id="5e0a0-110">**参数**</span><span class="sxs-lookup"><span data-stu-id="5e0a0-110">**Parameter**</span></span>|<span data-ttu-id="5e0a0-111">**必需**</span><span class="sxs-lookup"><span data-stu-id="5e0a0-111">**Required**</span></span>|<span data-ttu-id="5e0a0-112">**类型**</span><span class="sxs-lookup"><span data-stu-id="5e0a0-112">**Type**</span></span>|<span data-ttu-id="5e0a0-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="5e0a0-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5e0a0-114">VersionType</span><span class="sxs-lookup"><span data-stu-id="5e0a0-114">VersionType</span></span>  <br/> |<span data-ttu-id="5e0a0-115">可选</span><span class="sxs-lookup"><span data-stu-id="5e0a0-115">Optional</span></span>  <br/> |<span data-ttu-id="5e0a0-116">System.String</span><span class="sxs-lookup"><span data-stu-id="5e0a0-116">System.String</span></span>  <br/> |<span data-ttu-id="5e0a0-p103">版本类型。 参数值可为 RunningScripts、RunningBits、BackupBits 或 All。 默认值为 RunningScripts。 </span><span class="sxs-lookup"><span data-stu-id="5e0a0-p103">Type of version. Value of parameter can be RunningScripts, RunningBits, BackupBits or All. Default value is RunningScripts.</span></span>  <br/> |
   
## <a name="examples"></a><span data-ttu-id="5e0a0-120">示例</span><span class="sxs-lookup"><span data-stu-id="5e0a0-120">Examples</span></span>
<span data-ttu-id="5e0a0-121"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="5e0a0-121"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="5e0a0-122">示例 1</span><span class="sxs-lookup"><span data-stu-id="5e0a0-122">Example 1</span></span>

<span data-ttu-id="5e0a0-123">以下示例显示打开的 PowerShell 控制台中当前正在运行的脚本的云连接器版本：</span><span class="sxs-lookup"><span data-stu-id="5e0a0-123">The following example shows the Cloud Connector version of the currently running script in your open PowerShell console:</span></span>
  
```powershell
Get-CcVersion
```

### <a name="example-2"></a><span data-ttu-id="5e0a0-124">示例 2</span><span class="sxs-lookup"><span data-stu-id="5e0a0-124">Example 2</span></span>

<span data-ttu-id="5e0a0-125">以下示例显示了部署到虚拟机的当前正在运行的二进制文件的云连接器版本。</span><span class="sxs-lookup"><span data-stu-id="5e0a0-125">The following example shows the Cloud Connector version of the currently running binaries deployed to the virtual machines.</span></span> <span data-ttu-id="5e0a0-126">可在 Hyper-v 管理器中正在运行的虚拟机名称中查看版本。</span><span class="sxs-lookup"><span data-stu-id="5e0a0-126">You can see the version in the running virtual machine names in Hyper-v Manager:</span></span>
  
```powershell
Get-CCVersion -VersionType RunningBits
```

## <a name="input-types"></a><span data-ttu-id="5e0a0-127">输入类型</span><span class="sxs-lookup"><span data-stu-id="5e0a0-127">Input Types</span></span>
<span data-ttu-id="5e0a0-128"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="5e0a0-128"><a name="Examples"> </a></span></span>

<span data-ttu-id="5e0a0-p105">无。 Get-CcVersion cmdlet 不接受主线输入。</span><span class="sxs-lookup"><span data-stu-id="5e0a0-p105">None. The Get-CcVersion cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="5e0a0-131">返回类型</span><span class="sxs-lookup"><span data-stu-id="5e0a0-131">Return Types</span></span>
<span data-ttu-id="5e0a0-132"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="5e0a0-132"><a name="Examples"> </a></span></span>

<span data-ttu-id="5e0a0-133">无。</span><span class="sxs-lookup"><span data-stu-id="5e0a0-133">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5e0a0-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5e0a0-134">See also</span></span>
<span data-ttu-id="5e0a0-135"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="5e0a0-135"><a name="Examples"> </a></span></span>

<span data-ttu-id="5e0a0-136">无。</span><span class="sxs-lookup"><span data-stu-id="5e0a0-136">None.</span></span>
  

