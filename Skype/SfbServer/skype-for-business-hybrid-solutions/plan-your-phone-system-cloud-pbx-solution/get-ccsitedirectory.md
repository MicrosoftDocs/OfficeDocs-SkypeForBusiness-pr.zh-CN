---
title: Get-CcSiteDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a243758e-6774-4437-ad2e-d5cea5f04eb6
description: Get-CcSiteDirectory cmdlet 显示存储站点级别配置文件的当前目录。 该文件夹包含基本 VHD 和 Skype for Business 云连接器版本安装文件。 此文件夹应与云连接器网站的所有其他装置共享。
ms.openlocfilehash: e0b8a793f0210535a726b0bed19f240bf8b30dd9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287298"
---
# <a name="get-ccsitedirectory"></a><span data-ttu-id="3df2f-105">Get-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="3df2f-105">Get-CcSiteDirectory</span></span>
 
<span data-ttu-id="3df2f-106">Get-CcSiteDirectory cmdlet 显示存储站点级别配置文件的当前目录。</span><span class="sxs-lookup"><span data-stu-id="3df2f-106">The Get-CcSiteDirectory cmdlet shows the current directory where site level configuration files are stored.</span></span> <span data-ttu-id="3df2f-107">该文件夹包含基本 VHD 和 Skype for Business 云连接器版本安装文件。</span><span class="sxs-lookup"><span data-stu-id="3df2f-107">The folder contains the base VHD and Skype for Business Cloud Connector Edition installation files.</span></span> <span data-ttu-id="3df2f-108">此文件夹应与云连接器网站的所有其他装置共享。</span><span class="sxs-lookup"><span data-stu-id="3df2f-108">This folder should be shared with all other appliances of a Cloud Connector site.</span></span>
  
<span data-ttu-id="3df2f-109">此 cmdlet 适用于云连接器版本 1.4.1、1.4.2。</span><span class="sxs-lookup"><span data-stu-id="3df2f-109">This cmdlet applies to Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```
Get-CcSiteDirectory
```

## <a name="parameters"></a><span data-ttu-id="3df2f-110">参数</span><span class="sxs-lookup"><span data-stu-id="3df2f-110">Parameters</span></span>

<span data-ttu-id="3df2f-111">无</span><span class="sxs-lookup"><span data-stu-id="3df2f-111">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="3df2f-112">示例</span><span class="sxs-lookup"><span data-stu-id="3df2f-112">Examples</span></span>
<span data-ttu-id="3df2f-113"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="3df2f-113"></span></span>

### <a name="example-1"></a><span data-ttu-id="3df2f-114">示例 1</span><span class="sxs-lookup"><span data-stu-id="3df2f-114">Example 1</span></span>

<span data-ttu-id="3df2f-115">以下示例显示了存储云连接器组件的配置和虚拟机文件的当前文件夹:</span><span class="sxs-lookup"><span data-stu-id="3df2f-115">The following example shows the current folder where the configuration and virtual machines files of Cloud Connector components are stored:</span></span>
  
```
Get-CcSiteDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="3df2f-116">详细说明</span><span class="sxs-lookup"><span data-stu-id="3df2f-116">Detailed Description</span></span>
<span data-ttu-id="3df2f-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="3df2f-117"></span></span>

<span data-ttu-id="3df2f-118">为了提供网关相关性和高可用性, 可以将云连接器装置合并到网站中。</span><span class="sxs-lookup"><span data-stu-id="3df2f-118">To provide gateway affinity and high availability, Cloud Connector appliances can be combined in sites.</span></span> <span data-ttu-id="3df2f-119">用户被分配到网站, 而不是云连接器设备。</span><span class="sxs-lookup"><span data-stu-id="3df2f-119">Users are assigned to sites instead of Cloud Connector appliances.</span></span> <span data-ttu-id="3df2f-120">每个网站都有一个共享文件夹, 其中存储了基本 VHD 和云连接器安装文件。</span><span class="sxs-lookup"><span data-stu-id="3df2f-120">Each site has a shared folder where the base VHD and Cloud Connector installation files are stored.</span></span> <span data-ttu-id="3df2f-121">设备在部署过程中会使用此文件夹。</span><span class="sxs-lookup"><span data-stu-id="3df2f-121">Appliances use this folder during the deployment.</span></span> <span data-ttu-id="3df2f-122">默认文件夹为 C:\Users\%userprofile%\CloudConnector\SiteRoot。</span><span class="sxs-lookup"><span data-stu-id="3df2f-122">The default folder is C:\Users\%userprofile%\CloudConnector\SiteRoot.</span></span> <span data-ttu-id="3df2f-123">可使用 Set-CcSiteDirectory cmdlet 更改此路径。</span><span class="sxs-lookup"><span data-stu-id="3df2f-123">You can change the path by using the Set-CcSiteDirectory cmdlet.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="3df2f-124">输入类型</span><span class="sxs-lookup"><span data-stu-id="3df2f-124">Input Types</span></span>
<span data-ttu-id="3df2f-125"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="3df2f-125"></span></span>

<span data-ttu-id="3df2f-p104">无。Get-CcSiteDirectory cmdlet 不接受主线输入。</span><span class="sxs-lookup"><span data-stu-id="3df2f-p104">None. The Get-CcSiteDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="3df2f-128">返回类型</span><span class="sxs-lookup"><span data-stu-id="3df2f-128">Return Types</span></span>
<span data-ttu-id="3df2f-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="3df2f-129"></span></span>

<span data-ttu-id="3df2f-130">此命令返回文件路径。</span><span class="sxs-lookup"><span data-stu-id="3df2f-130">This command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3df2f-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3df2f-131">See also</span></span>
<span data-ttu-id="3df2f-132"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="3df2f-132"></span></span>

[<span data-ttu-id="3df2f-133">Set-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="3df2f-133">Set-CcSiteDirectory</span></span>](set-ccsitedirectory.md)
  

