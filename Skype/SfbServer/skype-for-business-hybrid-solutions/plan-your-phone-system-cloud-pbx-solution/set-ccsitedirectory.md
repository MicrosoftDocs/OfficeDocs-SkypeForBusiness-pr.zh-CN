---
title: 一组 CcSiteDirectory
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/23/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1cd89fd-6968-4ace-a4aa-c4105231cf7b
description: Set-CcSiteDirectory cmdlet 用于设置将存储 Skype for Business 云连接器版本的站点级别配置文件的目录。 该文件夹将包含基本 VHD 和云连接器配置文件。
ms.openlocfilehash: d34945a17f32c275240e2cef0435f6e0ca3e63a0
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="set-ccsitedirectory"></a><span data-ttu-id="f2890-104">一组 CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="f2890-104">Set-CcSiteDirectory</span></span>
 
<span data-ttu-id="f2890-105">Set-CcSiteDirectory cmdlet 用于设置将存储 Skype for Business 云连接器版本的站点级别配置文件的目录。</span><span class="sxs-lookup"><span data-stu-id="f2890-105">The Set-CcSiteDirectory cmdlet sets the directory where site level configuration files for Skype for Business Cloud Connector Edition will be stored.</span></span> <span data-ttu-id="f2890-106">该文件夹将包含基本 VHD 和云连接器配置文件。</span><span class="sxs-lookup"><span data-stu-id="f2890-106">The folder will contain the base VHD and Cloud Connector configuration files.</span></span>
  
<span data-ttu-id="f2890-107">此 cmdlet 适用于 Skype for Business 云连接器版本 1.4.1、1.4.2。</span><span class="sxs-lookup"><span data-stu-id="f2890-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```
Set-CcSiteDirectory [[-Path] <string>]
```

## <a name="examples"></a><span data-ttu-id="f2890-108">示例</span><span class="sxs-lookup"><span data-stu-id="f2890-108">Examples</span></span>
<span data-ttu-id="f2890-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="f2890-109"></span></span>

### <a name="example-1"></a><span data-ttu-id="f2890-110">示例 1</span><span class="sxs-lookup"><span data-stu-id="f2890-110">Example 1</span></span>

<span data-ttu-id="f2890-111">下面的示例设置站点根目录下\\SiteShare\CloudConnector:</span><span class="sxs-lookup"><span data-stu-id="f2890-111">The following example sets the site root directory to \\SiteShare\CloudConnector:</span></span>
  
```
Set-CcSiteDirectory -Path "\\SiteShare\CloudConnector"
```

## <a name="detailed-description"></a><span data-ttu-id="f2890-112">详细说明</span><span class="sxs-lookup"><span data-stu-id="f2890-112">Detailed Description</span></span>
<span data-ttu-id="f2890-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="f2890-113"></span></span>

<span data-ttu-id="f2890-114">若要提供网关关联和高可用性，可以在网站中组合云接头装置。</span><span class="sxs-lookup"><span data-stu-id="f2890-114">To provide gateway affinity and high availability, Cloud Connector appliances can be combined in sites.</span></span> <span data-ttu-id="f2890-115">用户被分配给站点而不是云接口装置。</span><span class="sxs-lookup"><span data-stu-id="f2890-115">Users are assigned to sites instead of Cloud Connector appliances.</span></span> <span data-ttu-id="f2890-116">每个站点都有一个共享文件夹，用于存储基本 VHD 和云连接器安装文件。</span><span class="sxs-lookup"><span data-stu-id="f2890-116">Each site has a shared folder where the base VHD and Cloud Connector installation files are stored.</span></span> <span data-ttu-id="f2890-117">装置在部署期间使用此文件夹。</span><span class="sxs-lookup"><span data-stu-id="f2890-117">Appliances use this folder during the deployment.</span></span> <span data-ttu-id="f2890-118">应与云连接器站点中的所有其他设备共享此文件夹。</span><span class="sxs-lookup"><span data-stu-id="f2890-118">This folder should be shared with all other appliances in a Cloud Connector site.</span></span>
  
<span data-ttu-id="f2890-119">默认的文件夹是 C:\Users\%userprofile%\CloudConnector\SiteRoot。</span><span class="sxs-lookup"><span data-stu-id="f2890-119">The default folder is C:\Users\%userprofile%\CloudConnector\SiteRoot.</span></span> <span data-ttu-id="f2890-120">可以使用 Get-CcSiteDirectory cmdlet 查看路径。</span><span class="sxs-lookup"><span data-stu-id="f2890-120">The path can be viewed by using the Get-CcSiteDirectory cmdlet.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="f2890-121">参数</span><span class="sxs-lookup"><span data-stu-id="f2890-121">Parameters</span></span>
<span data-ttu-id="f2890-122"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="f2890-122"></span></span>

|<span data-ttu-id="f2890-123">**参数**</span><span class="sxs-lookup"><span data-stu-id="f2890-123">**Parameter**</span></span>|<span data-ttu-id="f2890-124">**必填**</span><span class="sxs-lookup"><span data-stu-id="f2890-124">**Required**</span></span>|<span data-ttu-id="f2890-125">**类型**</span><span class="sxs-lookup"><span data-stu-id="f2890-125">**Type**</span></span>|<span data-ttu-id="f2890-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="f2890-126">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="f2890-127">路径</span><span class="sxs-lookup"><span data-stu-id="f2890-127">Path</span></span> <br/> | <span data-ttu-id="f2890-128">必需</span><span class="sxs-lookup"><span data-stu-id="f2890-128">Required</span></span> <br/> | <span data-ttu-id="f2890-129">System.String</span><span class="sxs-lookup"><span data-stu-id="f2890-129">System.String</span></span> <br/> |<span data-ttu-id="f2890-130">提供了存储云连接器网站文件的文件夹的路径。</span><span class="sxs-lookup"><span data-stu-id="f2890-130">Provides the path to the folder where Cloud Connector site files will be stored.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="f2890-131">输入类型</span><span class="sxs-lookup"><span data-stu-id="f2890-131">Input Types</span></span>
<span data-ttu-id="f2890-132"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f2890-132"></span></span>

<span data-ttu-id="f2890-133">无。</span><span class="sxs-lookup"><span data-stu-id="f2890-133">None.</span></span> <span data-ttu-id="f2890-134">Set-CcSiteDirectory cmdlet 不接受主线输入。</span><span class="sxs-lookup"><span data-stu-id="f2890-134">The Set-CcSiteDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="f2890-135">返回类型</span><span class="sxs-lookup"><span data-stu-id="f2890-135">Return Types</span></span>
<span data-ttu-id="f2890-136"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f2890-136"></span></span>

<span data-ttu-id="f2890-137">无</span><span class="sxs-lookup"><span data-stu-id="f2890-137">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f2890-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f2890-138">See also</span></span>
<span data-ttu-id="f2890-139"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f2890-139"></span></span>

[<span data-ttu-id="f2890-140">获得 CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="f2890-140">Get-CcSiteDirectory</span></span>](get-ccsitedirectory.md)
  

