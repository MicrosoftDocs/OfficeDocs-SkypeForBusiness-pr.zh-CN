---
title: Set-CcSiteDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/23/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b1cd89fd-6968-4ace-a4aa-c4105231cf7b
description: Set-CcSiteDirectory cmdlet 用于设置将存储 Skype for Business 云连接器版本的站点级别配置文件的目录。 该文件夹将包含基本 VHD 和云连接器配置文件。
ms.openlocfilehash: 1e66c735e888fe9d5701b8f71baf462ec449acd4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824186"
---
# <a name="set-ccsitedirectory"></a><span data-ttu-id="bb7de-104">Set-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="bb7de-104">Set-CcSiteDirectory</span></span>
 
<span data-ttu-id="bb7de-105">Set-CcSiteDirectory cmdlet 用于设置将存储 Skype for Business 云连接器版本的站点级别配置文件的目录。</span><span class="sxs-lookup"><span data-stu-id="bb7de-105">The Set-CcSiteDirectory cmdlet sets the directory where site level configuration files for Skype for Business Cloud Connector Edition will be stored.</span></span> <span data-ttu-id="bb7de-106">该文件夹将包含基本 VHD 和云连接器配置文件。</span><span class="sxs-lookup"><span data-stu-id="bb7de-106">The folder will contain the base VHD and Cloud Connector configuration files.</span></span>
  
<span data-ttu-id="bb7de-107">此 cmdlet 适用于 Skype for Business 云连接器版本 1.4.1、1.4.2。</span><span class="sxs-lookup"><span data-stu-id="bb7de-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Set-CcSiteDirectory [[-Path] <string>]
```

## <a name="examples"></a><span data-ttu-id="bb7de-108">示例</span><span class="sxs-lookup"><span data-stu-id="bb7de-108">Examples</span></span>
<span data-ttu-id="bb7de-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="bb7de-109"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="bb7de-110">示例 1</span><span class="sxs-lookup"><span data-stu-id="bb7de-110">Example 1</span></span>

<span data-ttu-id="bb7de-111">以下示例将网站根目录设置为\\SiteShare\CloudConnector：</span><span class="sxs-lookup"><span data-stu-id="bb7de-111">The following example sets the site root directory to \\SiteShare\CloudConnector:</span></span>
  
```powershell
Set-CcSiteDirectory -Path "\\SiteShare\CloudConnector"
```

## <a name="detailed-description"></a><span data-ttu-id="bb7de-112">详细说明</span><span class="sxs-lookup"><span data-stu-id="bb7de-112">Detailed Description</span></span>
<span data-ttu-id="bb7de-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="bb7de-113"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="bb7de-114">为了提供网关相关性和高可用性，可以将云连接器装置合并到网站中。</span><span class="sxs-lookup"><span data-stu-id="bb7de-114">To provide gateway affinity and high availability, Cloud Connector appliances can be combined in sites.</span></span> <span data-ttu-id="bb7de-115">用户被分配到网站，而不是云连接器设备。</span><span class="sxs-lookup"><span data-stu-id="bb7de-115">Users are assigned to sites instead of Cloud Connector appliances.</span></span> <span data-ttu-id="bb7de-116">每个网站都有一个共享文件夹，其中存储了基本 VHD 和云连接器安装文件。</span><span class="sxs-lookup"><span data-stu-id="bb7de-116">Each site has a shared folder where the base VHD and Cloud Connector installation files are stored.</span></span> <span data-ttu-id="bb7de-117">设备在部署过程中会使用此文件夹。</span><span class="sxs-lookup"><span data-stu-id="bb7de-117">Appliances use this folder during the deployment.</span></span> <span data-ttu-id="bb7de-118">此文件夹应与云连接器网站中的所有其他设备共享。</span><span class="sxs-lookup"><span data-stu-id="bb7de-118">This folder should be shared with all other appliances in a Cloud Connector site.</span></span>
  
<span data-ttu-id="bb7de-119">默认文件夹为 C:\Users\%userprofile%\CloudConnector\SiteRoot。</span><span class="sxs-lookup"><span data-stu-id="bb7de-119">The default folder is C:\Users\%userprofile%\CloudConnector\SiteRoot.</span></span> <span data-ttu-id="bb7de-120">可以使用 Get-CcSiteDirectory cmdlet 查看路径。</span><span class="sxs-lookup"><span data-stu-id="bb7de-120">The path can be viewed by using the Get-CcSiteDirectory cmdlet.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="bb7de-121">参数</span><span class="sxs-lookup"><span data-stu-id="bb7de-121">Parameters</span></span>
<span data-ttu-id="bb7de-122"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="bb7de-122"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="bb7de-123">**参数**</span><span class="sxs-lookup"><span data-stu-id="bb7de-123">**Parameter**</span></span>|<span data-ttu-id="bb7de-124">**必需**</span><span class="sxs-lookup"><span data-stu-id="bb7de-124">**Required**</span></span>|<span data-ttu-id="bb7de-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="bb7de-125">**Type**</span></span>|<span data-ttu-id="bb7de-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="bb7de-126">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="bb7de-127">路径</span><span class="sxs-lookup"><span data-stu-id="bb7de-127">Path</span></span> <br/> | <span data-ttu-id="bb7de-128">必需</span><span class="sxs-lookup"><span data-stu-id="bb7de-128">Required</span></span> <br/> | <span data-ttu-id="bb7de-129">System.String</span><span class="sxs-lookup"><span data-stu-id="bb7de-129">System.String</span></span> <br/> |<span data-ttu-id="bb7de-130">提供将存储云连接器网站文件的文件夹的路径。</span><span class="sxs-lookup"><span data-stu-id="bb7de-130">Provides the path to the folder where Cloud Connector site files will be stored.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="bb7de-131">输入类型</span><span class="sxs-lookup"><span data-stu-id="bb7de-131">Input Types</span></span>
<span data-ttu-id="bb7de-132"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="bb7de-132"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="bb7de-133">无。</span><span class="sxs-lookup"><span data-stu-id="bb7de-133">None.</span></span> <span data-ttu-id="bb7de-134">Set-CcSiteDirectory cmdlet 不接受主线输入。</span><span class="sxs-lookup"><span data-stu-id="bb7de-134">The Set-CcSiteDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="bb7de-135">返回类型</span><span class="sxs-lookup"><span data-stu-id="bb7de-135">Return Types</span></span>
<span data-ttu-id="bb7de-136"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="bb7de-136"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="bb7de-137">无</span><span class="sxs-lookup"><span data-stu-id="bb7de-137">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="bb7de-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bb7de-138">See also</span></span>
<span data-ttu-id="bb7de-139"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="bb7de-139"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="bb7de-140">Get-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="bb7de-140">Get-CcSiteDirectory</span></span>](get-ccsitedirectory.md)
  

