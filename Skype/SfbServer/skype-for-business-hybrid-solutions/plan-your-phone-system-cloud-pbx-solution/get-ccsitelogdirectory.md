---
title: 获得 CcSiteLogDirectory
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6625494d-1b63-4d99-a589-c8c69c4addba
description: Get-CcSiteLogDirectory cmdlet 显示存储 Skype for Business 云连接器版本的站点级别日志的当前目录。
ms.openlocfilehash: 68d89200ac8bf2aec32db45752d62d7ae205b830
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="get-ccsitelogdirectory"></a><span data-ttu-id="7d181-103">获得 CcSiteLogDirectory</span><span class="sxs-lookup"><span data-stu-id="7d181-103">Get-CcSiteLogDirectory</span></span>
 
<span data-ttu-id="7d181-104">Get-CcSiteLogDirectory cmdlet 显示存储 Skype for Business 云连接器版本的站点级别日志的当前目录。</span><span class="sxs-lookup"><span data-stu-id="7d181-104">The Get-CcSiteLogDirectory cmdlet shows the current directory where the site level logs for Skype for Business Cloud Connector Edition are stored.</span></span> 
  
<span data-ttu-id="7d181-105">此 cmdlet 适用于 Skype for Business 云连接器版本 1.4.1、1.4.2。</span><span class="sxs-lookup"><span data-stu-id="7d181-105">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```
Get-CcSiteLogDirectory
```

## <a name="parameters"></a><span data-ttu-id="7d181-106">参数</span><span class="sxs-lookup"><span data-stu-id="7d181-106">Parameters</span></span>

<span data-ttu-id="7d181-107">无</span><span class="sxs-lookup"><span data-stu-id="7d181-107">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="7d181-108">示例</span><span class="sxs-lookup"><span data-stu-id="7d181-108">Examples</span></span>
<span data-ttu-id="7d181-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="7d181-109"></span></span>

### <a name="example-1"></a><span data-ttu-id="7d181-110">示例 1</span><span class="sxs-lookup"><span data-stu-id="7d181-110">Example 1</span></span>

<span data-ttu-id="7d181-111">下面的示例显示当前文件夹云连接器站点的日志文件的存储位置：</span><span class="sxs-lookup"><span data-stu-id="7d181-111">The following example shows the current folder where the log files for the Cloud Connector site are stored:</span></span>
  
```
Get-CcSiteLogDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="7d181-112">详细说明</span><span class="sxs-lookup"><span data-stu-id="7d181-112">Detailed Description</span></span>
<span data-ttu-id="7d181-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="7d181-113"></span></span>

<span data-ttu-id="7d181-114">默认的文件夹是 C:\Users\%userprofile%\CloudConnector\SiteRoot\Logs。</span><span class="sxs-lookup"><span data-stu-id="7d181-114">The default folder is C:\Users\%userprofile%\CloudConnector\SiteRoot\Logs.</span></span> <span data-ttu-id="7d181-115">可以通过运行 Set-CcSiteDirectory cmdlet 来更改文件夹。</span><span class="sxs-lookup"><span data-stu-id="7d181-115">You can change the folder by running the Set-CcSiteDirectory cmdlet.</span></span> <span data-ttu-id="7d181-116">没有只更改日志文件夹位置而不更改站点目录的单独 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7d181-116">There is no separate cmdlet that changes only the log folder location without changing the site directory.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="7d181-117">输入类型</span><span class="sxs-lookup"><span data-stu-id="7d181-117">Input Types</span></span>
<span data-ttu-id="7d181-118"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="7d181-118"></span></span>

<span data-ttu-id="7d181-p102">无。Get-CcSiteLogDirectory cmdlet 不接受主线输入。</span><span class="sxs-lookup"><span data-stu-id="7d181-p102">None. The Get-CcSiteLogDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="7d181-121">返回类型</span><span class="sxs-lookup"><span data-stu-id="7d181-121">Return Types</span></span>
<span data-ttu-id="7d181-122"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="7d181-122"></span></span>

<span data-ttu-id="7d181-123">该命令返回文件路径。</span><span class="sxs-lookup"><span data-stu-id="7d181-123">The command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7d181-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7d181-124">See also</span></span>
<span data-ttu-id="7d181-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="7d181-125"></span></span>

[<span data-ttu-id="7d181-126">一组 CcSiteDirectory</span><span class="sxs-lookup"><span data-stu-id="7d181-126">Set-CcSiteDirectory</span></span>](set-ccsitedirectory.md)
  

