---
title: Get-CcSiteLogDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6625494d-1b63-4d99-a589-c8c69c4addba
description: Get-CcSiteLogDirectory cmdlet 显示存储 Skype for Business 云连接器版本的站点级别日志的当前目录。
ms.openlocfilehash: bc47c2ea2d81e70538305daa98f97a35cf3d9e0a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287284"
---
# <a name="get-ccsitelogdirectory"></a><span data-ttu-id="10acc-103">Get-CcSiteLogDirectory</span><span class="sxs-lookup"><span data-stu-id="10acc-103">Get-CcSiteLogDirectory</span></span>
 
<span data-ttu-id="10acc-104">Get-CcSiteLogDirectory cmdlet 显示存储 Skype for Business 云连接器版本的站点级别日志的当前目录。</span><span class="sxs-lookup"><span data-stu-id="10acc-104">The Get-CcSiteLogDirectory cmdlet shows the current directory where the site level logs for Skype for Business Cloud Connector Edition are stored.</span></span> 
  
<span data-ttu-id="10acc-105">此 cmdlet 适用于 Skype for Business 云连接器版本 1.4.1、1.4.2。</span><span class="sxs-lookup"><span data-stu-id="10acc-105">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```
Get-CcSiteLogDirectory
```

## <a name="parameters"></a><span data-ttu-id="10acc-106">参数</span><span class="sxs-lookup"><span data-stu-id="10acc-106">Parameters</span></span>

<span data-ttu-id="10acc-107">无</span><span class="sxs-lookup"><span data-stu-id="10acc-107">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="10acc-108">示例</span><span class="sxs-lookup"><span data-stu-id="10acc-108">Examples</span></span>
<span data-ttu-id="10acc-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="10acc-109"></span></span>

### <a name="example-1"></a><span data-ttu-id="10acc-110">示例 1</span><span class="sxs-lookup"><span data-stu-id="10acc-110">Example 1</span></span>

<span data-ttu-id="10acc-111">以下示例显示了用于存储云连接器网站的日志文件的当前文件夹:</span><span class="sxs-lookup"><span data-stu-id="10acc-111">The following example shows the current folder where the log files for the Cloud Connector site are stored:</span></span>
  
```
Get-CcSiteLogDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="10acc-112">详细说明</span><span class="sxs-lookup"><span data-stu-id="10acc-112">Detailed Description</span></span>
<span data-ttu-id="10acc-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="10acc-113"></span></span>

<span data-ttu-id="10acc-114">默认文件夹为 C:\Users\%userprofile%\CloudConnector\SiteRoot\Logs。</span><span class="sxs-lookup"><span data-stu-id="10acc-114">The default folder is C:\Users\%userprofile%\CloudConnector\SiteRoot\Logs.</span></span> <span data-ttu-id="10acc-115">可以通过运行 Set-CcSiteDirectory cmdlet 来更改文件夹。</span><span class="sxs-lookup"><span data-stu-id="10acc-115">You can change the folder by running the Set-CcSiteDirectory cmdlet.</span></span> <span data-ttu-id="10acc-116">没有只更改日志文件夹位置而不更改站点目录的单独 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="10acc-116">There is no separate cmdlet that changes only the log folder location without changing the site directory.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="10acc-117">输入类型</span><span class="sxs-lookup"><span data-stu-id="10acc-117">Input Types</span></span>
<span data-ttu-id="10acc-118"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="10acc-118"></span></span>

<span data-ttu-id="10acc-p102">无。Get-CcSiteLogDirectory cmdlet 不接受主线输入。</span><span class="sxs-lookup"><span data-stu-id="10acc-p102">None. The Get-CcSiteLogDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="10acc-121">返回类型</span><span class="sxs-lookup"><span data-stu-id="10acc-121">Return Types</span></span>
<span data-ttu-id="10acc-122"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="10acc-122"></span></span>

<span data-ttu-id="10acc-123">该命令返回文件路径。</span><span class="sxs-lookup"><span data-stu-id="10acc-123">The command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="10acc-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="10acc-124">See also</span></span>
<span data-ttu-id="10acc-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="10acc-125"></span></span>

[<span data-ttu-id="10acc-126">Set-CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="10acc-126">Set-CcSiteDirectory</span></span>](set-ccsitedirectory.md)
  

