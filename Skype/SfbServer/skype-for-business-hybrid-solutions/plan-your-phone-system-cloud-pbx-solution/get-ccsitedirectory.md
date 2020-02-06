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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a243758e-6774-4437-ad2e-d5cea5f04eb6
description: Get-CcSiteDirectory cmdlet 显示存储站点级别配置文件的当前目录。 该文件夹包含基本 VHD 和 Skype for Business 云连接器版本安装文件。 此文件夹应与云连接器网站的所有其他装置共享。
ms.openlocfilehash: 6722b66f6c71feec158adaf442f9e57ef9943c84
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799862"
---
# <a name="get-ccsitedirectory"></a><span data-ttu-id="87ac5-105">Get-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="87ac5-105">Get-CcSiteDirectory</span></span>
 
<span data-ttu-id="87ac5-106">Get-CcSiteDirectory cmdlet 显示存储站点级别配置文件的当前目录。</span><span class="sxs-lookup"><span data-stu-id="87ac5-106">The Get-CcSiteDirectory cmdlet shows the current directory where site level configuration files are stored.</span></span> <span data-ttu-id="87ac5-107">该文件夹包含基本 VHD 和 Skype for Business 云连接器版本安装文件。</span><span class="sxs-lookup"><span data-stu-id="87ac5-107">The folder contains the base VHD and Skype for Business Cloud Connector Edition installation files.</span></span> <span data-ttu-id="87ac5-108">此文件夹应与云连接器网站的所有其他装置共享。</span><span class="sxs-lookup"><span data-stu-id="87ac5-108">This folder should be shared with all other appliances of a Cloud Connector site.</span></span>
  
<span data-ttu-id="87ac5-109">此 cmdlet 适用于云连接器版本 1.4.1、1.4.2。</span><span class="sxs-lookup"><span data-stu-id="87ac5-109">This cmdlet applies to Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Get-CcSiteDirectory
```

## <a name="parameters"></a><span data-ttu-id="87ac5-110">参数</span><span class="sxs-lookup"><span data-stu-id="87ac5-110">Parameters</span></span>

<span data-ttu-id="87ac5-111">无</span><span class="sxs-lookup"><span data-stu-id="87ac5-111">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="87ac5-112">示例</span><span class="sxs-lookup"><span data-stu-id="87ac5-112">Examples</span></span>
<span data-ttu-id="87ac5-113"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="87ac5-113"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="87ac5-114">示例 1</span><span class="sxs-lookup"><span data-stu-id="87ac5-114">Example 1</span></span>

<span data-ttu-id="87ac5-115">以下示例显示了存储云连接器组件的配置和虚拟机文件的当前文件夹：</span><span class="sxs-lookup"><span data-stu-id="87ac5-115">The following example shows the current folder where the configuration and virtual machines files of Cloud Connector components are stored:</span></span>
  
```powershell
Get-CcSiteDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="87ac5-116">详细说明</span><span class="sxs-lookup"><span data-stu-id="87ac5-116">Detailed Description</span></span>
<span data-ttu-id="87ac5-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="87ac5-117"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="87ac5-118">为了提供网关相关性和高可用性，可以将云连接器装置合并到网站中。</span><span class="sxs-lookup"><span data-stu-id="87ac5-118">To provide gateway affinity and high availability, Cloud Connector appliances can be combined in sites.</span></span> <span data-ttu-id="87ac5-119">用户被分配到网站，而不是云连接器设备。</span><span class="sxs-lookup"><span data-stu-id="87ac5-119">Users are assigned to sites instead of Cloud Connector appliances.</span></span> <span data-ttu-id="87ac5-120">每个网站都有一个共享文件夹，其中存储了基本 VHD 和云连接器安装文件。</span><span class="sxs-lookup"><span data-stu-id="87ac5-120">Each site has a shared folder where the base VHD and Cloud Connector installation files are stored.</span></span> <span data-ttu-id="87ac5-121">设备在部署过程中会使用此文件夹。</span><span class="sxs-lookup"><span data-stu-id="87ac5-121">Appliances use this folder during the deployment.</span></span> <span data-ttu-id="87ac5-122">默认文件夹为 C:\Users\%userprofile%\CloudConnector\SiteRoot。</span><span class="sxs-lookup"><span data-stu-id="87ac5-122">The default folder is C:\Users\%userprofile%\CloudConnector\SiteRoot.</span></span> <span data-ttu-id="87ac5-123">可使用 Set-CcSiteDirectory cmdlet 更改此路径。</span><span class="sxs-lookup"><span data-stu-id="87ac5-123">You can change the path by using the Set-CcSiteDirectory cmdlet.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="87ac5-124">输入类型</span><span class="sxs-lookup"><span data-stu-id="87ac5-124">Input Types</span></span>
<span data-ttu-id="87ac5-125"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="87ac5-125"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="87ac5-p104">无。Get-CcSiteDirectory cmdlet 不接受主线输入。</span><span class="sxs-lookup"><span data-stu-id="87ac5-p104">None. The Get-CcSiteDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="87ac5-128">返回类型</span><span class="sxs-lookup"><span data-stu-id="87ac5-128">Return Types</span></span>
<span data-ttu-id="87ac5-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="87ac5-129"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="87ac5-130">此命令返回文件路径。</span><span class="sxs-lookup"><span data-stu-id="87ac5-130">This command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="87ac5-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="87ac5-131">See also</span></span>
<span data-ttu-id="87ac5-132"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="87ac5-132"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="87ac5-133">Set-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="87ac5-133">Set-CcSiteDirectory</span></span>](set-ccsitedirectory.md)
  

