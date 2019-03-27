---
title: Get-CcSiteDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a243758e-6774-4437-ad2e-d5cea5f04eb6
description: Get-CcSiteDirectory cmdlet 显示存储站点级别配置文件的当前目录。 该文件夹包含基本 VHD 和 Skype for Business 云连接器版本安装文件。 应与云连接器网站的所有其他设备共享该文件夹。
ms.openlocfilehash: d0869f3cbd1c43e523107a0ff8dce6fd769889a8
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30882395"
---
# <a name="get-ccsitedirectory"></a><span data-ttu-id="86aa2-105">Get-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="86aa2-105">Get-CcSiteDirectory</span></span>
 
<span data-ttu-id="86aa2-106">Get-CcSiteDirectory cmdlet 显示存储站点级别配置文件的当前目录。</span><span class="sxs-lookup"><span data-stu-id="86aa2-106">The Get-CcSiteDirectory cmdlet shows the current directory where site level configuration files are stored.</span></span> <span data-ttu-id="86aa2-107">该文件夹包含基本 VHD 和 Skype for Business 云连接器版本安装文件。</span><span class="sxs-lookup"><span data-stu-id="86aa2-107">The folder contains the base VHD and Skype for Business Cloud Connector Edition installation files.</span></span> <span data-ttu-id="86aa2-108">应与云连接器网站的所有其他设备共享该文件夹。</span><span class="sxs-lookup"><span data-stu-id="86aa2-108">This folder should be shared with all other appliances of a Cloud Connector site.</span></span>
  
<span data-ttu-id="86aa2-109">此 cmdlet 适用于云连接器版本 1.4.1、1.4.2。</span><span class="sxs-lookup"><span data-stu-id="86aa2-109">This cmdlet applies to Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```
Get-CcSiteDirectory
```

## <a name="parameters"></a><span data-ttu-id="86aa2-110">参数</span><span class="sxs-lookup"><span data-stu-id="86aa2-110">Parameters</span></span>

<span data-ttu-id="86aa2-111">无</span><span class="sxs-lookup"><span data-stu-id="86aa2-111">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="86aa2-112">示例</span><span class="sxs-lookup"><span data-stu-id="86aa2-112">Examples</span></span>
<span data-ttu-id="86aa2-113"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="86aa2-113"></span></span>

### <a name="example-1"></a><span data-ttu-id="86aa2-114">示例 1</span><span class="sxs-lookup"><span data-stu-id="86aa2-114">Example 1</span></span>

<span data-ttu-id="86aa2-115">下面的示例显示当前文件夹云连接器组件配置和虚拟机文件的存储位置：</span><span class="sxs-lookup"><span data-stu-id="86aa2-115">The following example shows the current folder where the configuration and virtual machines files of Cloud Connector components are stored:</span></span>
  
```
Get-CcSiteDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="86aa2-116">详细说明</span><span class="sxs-lookup"><span data-stu-id="86aa2-116">Detailed Description</span></span>
<span data-ttu-id="86aa2-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="86aa2-117"></span></span>

<span data-ttu-id="86aa2-118">若要提供网关关联和高可用性，可以在网站中结合云连接器 appliance。</span><span class="sxs-lookup"><span data-stu-id="86aa2-118">To provide gateway affinity and high availability, Cloud Connector appliances can be combined in sites.</span></span> <span data-ttu-id="86aa2-119">用户分配到网站而不是云连接器 appliance。</span><span class="sxs-lookup"><span data-stu-id="86aa2-119">Users are assigned to sites instead of Cloud Connector appliances.</span></span> <span data-ttu-id="86aa2-120">每个网站具有基本 VHD 和云连接器安装文件的存储位置的共享的文件夹。</span><span class="sxs-lookup"><span data-stu-id="86aa2-120">Each site has a shared folder where the base VHD and Cloud Connector installation files are stored.</span></span> <span data-ttu-id="86aa2-121">设备在部署过程中会使用此文件夹。</span><span class="sxs-lookup"><span data-stu-id="86aa2-121">Appliances use this folder during the deployment.</span></span> <span data-ttu-id="86aa2-122">默认文件夹已 C:\Users\%userprofile%\CloudConnector\SiteRoot。</span><span class="sxs-lookup"><span data-stu-id="86aa2-122">The default folder is C:\Users\%userprofile%\CloudConnector\SiteRoot.</span></span> <span data-ttu-id="86aa2-123">可使用 Set-CcSiteDirectory cmdlet 更改此路径。</span><span class="sxs-lookup"><span data-stu-id="86aa2-123">You can change the path by using the Set-CcSiteDirectory cmdlet.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="86aa2-124">输入类型</span><span class="sxs-lookup"><span data-stu-id="86aa2-124">Input Types</span></span>
<span data-ttu-id="86aa2-125"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="86aa2-125"></span></span>

<span data-ttu-id="86aa2-p104">无。Get-CcSiteDirectory cmdlet 不接受主线输入。</span><span class="sxs-lookup"><span data-stu-id="86aa2-p104">None. The Get-CcSiteDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="86aa2-128">返回类型</span><span class="sxs-lookup"><span data-stu-id="86aa2-128">Return Types</span></span>
<span data-ttu-id="86aa2-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="86aa2-129"></span></span>

<span data-ttu-id="86aa2-130">此命令返回文件路径。</span><span class="sxs-lookup"><span data-stu-id="86aa2-130">This command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="86aa2-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="86aa2-131">See also</span></span>
<span data-ttu-id="86aa2-132"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="86aa2-132"></span></span>

[<span data-ttu-id="86aa2-133">Set-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="86aa2-133">Set-CcSiteDirectory</span></span>](set-ccsitedirectory.md)
  

