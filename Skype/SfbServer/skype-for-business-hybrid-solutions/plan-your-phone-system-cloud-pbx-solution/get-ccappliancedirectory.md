---
title: Get-CcApplianceDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c2fda202-db2f-4122-b630-7df11a697c5f
description: Get-CcApplianceDirectory cmdlet 用于检索 Skype for Business 云连接器版本主机服务器上的工作目录。所有部署文件都存储在此目录中。
ms.openlocfilehash: ada1b587b738d882f81557e61438d6642aa03fff
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287389"
---
# <a name="get-ccappliancedirectory"></a><span data-ttu-id="50307-104">Get-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="50307-104">Get-CcApplianceDirectory</span></span>
 
<span data-ttu-id="50307-p102">Get-CcApplianceDirectory cmdlet 用于检索 Skype for Business 云连接器版本主机服务器上的工作目录。所有部署文件都存储在此目录中。</span><span class="sxs-lookup"><span data-stu-id="50307-p102">The Get-CcApplianceDirectory cmdlet retrieves the working directory on the Skype for Business Cloud Connector Edition host server. All deployment files are stored in this directory.</span></span> 
  
<span data-ttu-id="50307-107">此 cmdlet 适用于 Skype for Business 云连接器版本 1.4.1、1.4.2。</span><span class="sxs-lookup"><span data-stu-id="50307-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```
Get-CcApplianceDirectory
```

## <a name="parameters"></a><span data-ttu-id="50307-108">参数</span><span class="sxs-lookup"><span data-stu-id="50307-108">Parameters</span></span>

<span data-ttu-id="50307-109">无</span><span class="sxs-lookup"><span data-stu-id="50307-109">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="50307-110">示例</span><span class="sxs-lookup"><span data-stu-id="50307-110">Examples</span></span>
<span data-ttu-id="50307-111"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="50307-111"></span></span>

### <a name="example-1"></a><span data-ttu-id="50307-112">示例 1</span><span class="sxs-lookup"><span data-stu-id="50307-112">Example 1</span></span>

<span data-ttu-id="50307-113">以下示例显示存储云连接器组件的配置和虚拟机文件的当前文件夹:</span><span class="sxs-lookup"><span data-stu-id="50307-113">The following example shows the current folder where configuration and virtual machine files of Cloud Connector components are stored:</span></span>
  
```
Get-CcApplianceDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="50307-114">详细说明</span><span class="sxs-lookup"><span data-stu-id="50307-114">Detailed Description</span></span>
<span data-ttu-id="50307-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="50307-115"></span></span>

<span data-ttu-id="50307-116">CcApplianceDirectory cmdlet 显示为云连接器设备存储所有配置和虚拟机文件、日志和外部证书的位置。</span><span class="sxs-lookup"><span data-stu-id="50307-116">The Get-CcApplianceDirectory cmdlet shows where all configuration and virtual machine files, logs, and external certificates are stored for the Cloud Connector appliance.</span></span>
  
<span data-ttu-id="50307-117">每个云连接器设备都有四个组件: 中介服务器、中央管理存储、边缘服务器和域控制器。</span><span class="sxs-lookup"><span data-stu-id="50307-117">Each Cloud Connector appliance has four components: Mediation Server, Central Management Store, Edge Server, and a Domain Controller.</span></span> <span data-ttu-id="50307-118">默认文件夹为 C:\Users\%userprofile%\CloudConnector\ApplianceRoot。</span><span class="sxs-lookup"><span data-stu-id="50307-118">The default folder is C:\Users\%userprofile%\CloudConnector\ApplianceRoot.</span></span> <span data-ttu-id="50307-119">可以使用 Set-CCApplianceDirectory cmdlet 更改此文件夹。</span><span class="sxs-lookup"><span data-stu-id="50307-119">You can change this folder by using the Set-CCApplianceDirectory cmdlet.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="50307-120">输入类型</span><span class="sxs-lookup"><span data-stu-id="50307-120">Input Types</span></span>
<span data-ttu-id="50307-121"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="50307-121"></span></span>

<span data-ttu-id="50307-p104">无。Get-CCApplianceDirectory cmdlet 不接受主线输入。</span><span class="sxs-lookup"><span data-stu-id="50307-p104">None. The Get-CCApplianceDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="50307-124">返回类型</span><span class="sxs-lookup"><span data-stu-id="50307-124">Return Types</span></span>
<span data-ttu-id="50307-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="50307-125"></span></span>

<span data-ttu-id="50307-126">该命令返回文件路径。</span><span class="sxs-lookup"><span data-stu-id="50307-126">The command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="50307-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="50307-127">See also</span></span>
<span data-ttu-id="50307-128"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="50307-128"></span></span>

[<span data-ttu-id="50307-129">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="50307-129">Set-CcApplianceDirectory</span></span>](set-ccappliancedirectory.md)
  

