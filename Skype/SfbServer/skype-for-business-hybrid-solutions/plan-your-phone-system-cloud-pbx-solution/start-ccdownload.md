---
title: Start-CcDownload
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 19338a34-1bfb-4787-b057-5e34a333711d
description: Start-CcDownload cmdlet 可同步下载 Skype for Business 云连接器版本 bits 和 msi 文件。
ms.openlocfilehash: 184c15d1932a179bb9ae07da515eeacfc115dfae
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286941"
---
# <a name="start-ccdownload"></a><span data-ttu-id="a4da3-103">Start-CcDownload</span><span class="sxs-lookup"><span data-stu-id="a4da3-103">Start-CcDownload</span></span>
 
<span data-ttu-id="a4da3-104">Start-CcDownload cmdlet 可同步下载 Skype for Business 云连接器版本 bits 和 msi 文件。</span><span class="sxs-lookup"><span data-stu-id="a4da3-104">The Start-CcDownload cmdlet downloads the Skype for Business Cloud Connector Edition bits and msi file synchronously.</span></span>
  
<span data-ttu-id="a4da3-105">使用云连接器 2.0 版和更高版本时，你还可以指定 DownloadBitsOnly 参数。</span><span class="sxs-lookup"><span data-stu-id="a4da3-105">With Cloud Connector version 2.0 and later, you can also specify the DownloadBitsOnly parameter.</span></span>
  
```
Start-CcDownload [[-DownloadUrlRoot] <string>] [-DownloadBitsOnly]  [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="a4da3-106">示例</span><span class="sxs-lookup"><span data-stu-id="a4da3-106">Examples</span></span>
<span data-ttu-id="a4da3-107"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="a4da3-107"></span></span>

### <a name="example-1"></a><span data-ttu-id="a4da3-108">示例 1</span><span class="sxs-lookup"><span data-stu-id="a4da3-108">Example 1</span></span>

<span data-ttu-id="a4da3-109">以下示例从云连接器公共下载网站同步下载云连接器位和 msi 文件:</span><span class="sxs-lookup"><span data-stu-id="a4da3-109">The following example downloads the Cloud Connector bits and msi file synchronously from the Cloud Connector public download site:</span></span>
  
```
Start-CcDownload
```

### <a name="example-2"></a><span data-ttu-id="a4da3-110">示例 2</span><span class="sxs-lookup"><span data-stu-id="a4da3-110">Example 2</span></span>

<span data-ttu-id="a4da3-111">下一个示例从私人下载网站同步下载云连接器位和 msi 文件:</span><span class="sxs-lookup"><span data-stu-id="a4da3-111">The next example downloads the Cloud Connector bits and msi file synchronously from a private download site:</span></span>
  
```
Start-CcDownload -DownloadUrlRoot "http://downloadserver/cloudconnector/latest"
```

### <a name="example-3"></a><span data-ttu-id="a4da3-112">示例 3</span><span class="sxs-lookup"><span data-stu-id="a4da3-112">Example 3</span></span>

<span data-ttu-id="a4da3-113">第三个示例将从私有下载站点中同步下载云连接器 bits 和 msi 文件。</span><span class="sxs-lookup"><span data-stu-id="a4da3-113">The third example downloads the Cloud Connector bits and msi file synchronously from a private download site.</span></span>
  
```
Start-CcDownload -DownloadBitsOnly
```

## <a name="detailed-description"></a><span data-ttu-id="a4da3-114">详细说明</span><span class="sxs-lookup"><span data-stu-id="a4da3-114">Detailed Description</span></span>
<span data-ttu-id="a4da3-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="a4da3-115"></span></span>

<span data-ttu-id="a4da3-116">如果下载网站中有新版本可用, CcDownload 将从下载网站下载并安装 msi 文件, 然后同步下载云连接器位。</span><span class="sxs-lookup"><span data-stu-id="a4da3-116">If there's a new version available in the download site, Start-CcDownload will download and install the msi file from the download site, and then download the Cloud Connector bits synchronously.</span></span> <span data-ttu-id="a4da3-117">如果没有新版本的 msi 文件，Start-CcDownload 将只下载云连接器 bits。</span><span class="sxs-lookup"><span data-stu-id="a4da3-117">If there is no new version of the msi file, Start-CcDownload will download the Cloud Connector bits only.</span></span> <span data-ttu-id="a4da3-118">如果已下载云连接器 bits，则不执行 Start-CcDownload。</span><span class="sxs-lookup"><span data-stu-id="a4da3-118">If the Cloud Connector bits are already downloaded, Start-CcDownload does not execute.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="a4da3-119">参数</span><span class="sxs-lookup"><span data-stu-id="a4da3-119">Parameters</span></span>
<span data-ttu-id="a4da3-120"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="a4da3-120"></span></span>

|<span data-ttu-id="a4da3-121">**参数**</span><span class="sxs-lookup"><span data-stu-id="a4da3-121">**Parameter**</span></span>|<span data-ttu-id="a4da3-122">**必需**</span><span class="sxs-lookup"><span data-stu-id="a4da3-122">**Required**</span></span>|<span data-ttu-id="a4da3-123">**类型**</span><span class="sxs-lookup"><span data-stu-id="a4da3-123">**Type**</span></span>|<span data-ttu-id="a4da3-124">**说明**</span><span class="sxs-lookup"><span data-stu-id="a4da3-124">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a4da3-125">DownloadUrlRoot </span><span class="sxs-lookup"><span data-stu-id="a4da3-125">DownloadUrlRoot</span></span>  <br/> | <span data-ttu-id="a4da3-126">可选</span><span class="sxs-lookup"><span data-stu-id="a4da3-126">Optional</span></span> <br/> |<span data-ttu-id="a4da3-127">System.String</span><span class="sxs-lookup"><span data-stu-id="a4da3-127">System.String</span></span>  <br/> | <span data-ttu-id="a4da3-128">专用下载网站中的特定版本的云连接器的完整 URL。</span><span class="sxs-lookup"><span data-stu-id="a4da3-128">The full URL of a specific version of Cloud Connector in the private download site.</span></span> <span data-ttu-id="a4da3-129">使用此参数时要小心, 请务必注意你正在下载的云连接器版本。</span><span class="sxs-lookup"><span data-stu-id="a4da3-129">Use this parameter with caution—be sure you are aware of which version of Cloud Connector you are downloading.</span></span> <br/> |
|<span data-ttu-id="a4da3-130">DownloadBitsOnly </span><span class="sxs-lookup"><span data-stu-id="a4da3-130">DownloadBitsOnly</span></span>  <br/> |<span data-ttu-id="a4da3-131">可选</span><span class="sxs-lookup"><span data-stu-id="a4da3-131">Optional</span></span>  <br/> |<span data-ttu-id="a4da3-132">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="a4da3-132">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="a4da3-133">跳过从下载站点下载和安装 MSI 的步骤，只下载云连接器 bits。</span><span class="sxs-lookup"><span data-stu-id="a4da3-133">Skip the step to download and install MSI from download site, download the Cloud Connector bits only.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="a4da3-134">输入类型</span><span class="sxs-lookup"><span data-stu-id="a4da3-134">Input Types</span></span>
<span data-ttu-id="a4da3-135"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="a4da3-135"></span></span>

<span data-ttu-id="a4da3-p103">无。 Start-CcDownload cmdlet 不接受主线输入。</span><span class="sxs-lookup"><span data-stu-id="a4da3-p103">None. The Start-CcDownload cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="a4da3-138">返回类型</span><span class="sxs-lookup"><span data-stu-id="a4da3-138">Return Types</span></span>
<span data-ttu-id="a4da3-139"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="a4da3-139"></span></span>

<span data-ttu-id="a4da3-140">无</span><span class="sxs-lookup"><span data-stu-id="a4da3-140">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a4da3-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a4da3-141">See also</span></span>
<span data-ttu-id="a4da3-142"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="a4da3-142"></span></span>

<span data-ttu-id="a4da3-143">无</span><span class="sxs-lookup"><span data-stu-id="a4da3-143">None</span></span>
  

