---
title: 导出 CcConfigurationSampleFile
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0aaacc05-3430-4579-acbf-d7c7670c3864
description: Export-CcConfigurationSampleFile cmdlet 用于将 Skype for Business 云连接器版本示例配置文件 (.ini) 导出到云连接器设备的设备目录。你可以修改和重命名该文件以用于你的部署。
ms.openlocfilehash: f91b9c7eb8ade4e5edcf1c83c5ddef205e0f3721
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="export-ccconfigurationsamplefile"></a><span data-ttu-id="66b7b-104">导出 CcConfigurationSampleFile</span><span class="sxs-lookup"><span data-stu-id="66b7b-104">Export-CcConfigurationSampleFile</span></span>
 
<span data-ttu-id="66b7b-p102">Export-CcConfigurationSampleFile cmdlet 用于将 Skype for Business 云连接器版本示例配置文件 (.ini) 导出到云连接器设备的设备目录。你可以修改和重命名该文件以用于你的部署。</span><span class="sxs-lookup"><span data-stu-id="66b7b-p102">The Export-CcConfigurationSampleFile cmdlet exports a Skype for Business Cloud Connector Edition sample configuration file (.ini) to the appliance directory of a Cloud Connector appliance. You can modify and rename the file to use for your deployment.</span></span>
  
<span data-ttu-id="66b7b-107">此 cmdlet 适用于 Skype for Business 云连接器版本 1.4.1、1.4.2。</span><span class="sxs-lookup"><span data-stu-id="66b7b-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```
Export-CcConfigurationSampleFile
```

## <a name="parameters"></a><span data-ttu-id="66b7b-108">参数</span><span class="sxs-lookup"><span data-stu-id="66b7b-108">Parameters</span></span>

<span data-ttu-id="66b7b-109">无</span><span class="sxs-lookup"><span data-stu-id="66b7b-109">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="66b7b-110">示例</span><span class="sxs-lookup"><span data-stu-id="66b7b-110">Examples</span></span>
<span data-ttu-id="66b7b-111"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="66b7b-111"></span></span>

### <a name="example-1"></a><span data-ttu-id="66b7b-112">示例 1</span><span class="sxs-lookup"><span data-stu-id="66b7b-112">Example 1</span></span>

<span data-ttu-id="66b7b-113">下面的示例从 Microsoft 网站下载一个示例配置文件并将其写入云接口装置的设备目录：</span><span class="sxs-lookup"><span data-stu-id="66b7b-113">The following example downloads a sample configuration file from the Microsoft site and writes it to the appliance directory of the Cloud Connector appliance:</span></span>
  
```
Export-CcConfigurationSampleFile
```

## <a name="detailed-description"></a><span data-ttu-id="66b7b-114">详细说明</span><span class="sxs-lookup"><span data-stu-id="66b7b-114">Detailed Description</span></span>
<span data-ttu-id="66b7b-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="66b7b-115"></span></span>

<span data-ttu-id="66b7b-116">当前版本的云接头要求您提供几个参数的.ini 文件。例如，参数如云接头组件、 组件名称、 网关参数等的虚拟机的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="66b7b-116">The current version of Cloud Connector requires you to provide several parameters in the .ini file; for example, parameters such as the IP addresses of virtual machines for the Cloud Connector components, component names, gateway parameters, and so on.</span></span>
  
<span data-ttu-id="66b7b-117">此 cmdlet，云连接器的主机上运行时将从 Microsoft 网站下载示例.ini 文件与配置示例。</span><span class="sxs-lookup"><span data-stu-id="66b7b-117">This cmdlet, when run on the host machine of Cloud Connector, downloads a sample .ini file with configuration examples from the Microsoft site.</span></span> <span data-ttu-id="66b7b-118">该 cmdlet 将文件写入云接口装置的设备目录。</span><span class="sxs-lookup"><span data-stu-id="66b7b-118">The cmdlet writes the file to the appliance directory of the Cloud Connector appliance.</span></span> <span data-ttu-id="66b7b-119">设备目录通过使用 Set-CcApplianceDirectory cmdlet 来指定。</span><span class="sxs-lookup"><span data-stu-id="66b7b-119">The appliance directory is specified by using the Set-CcApplianceDirectory cmdlet.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="66b7b-120">输入类型</span><span class="sxs-lookup"><span data-stu-id="66b7b-120">Input Types</span></span>
<span data-ttu-id="66b7b-121"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="66b7b-121"></span></span>

<span data-ttu-id="66b7b-p104">无。Export-CcConfigurationSampleFile cmdlet 不接受主线输入。</span><span class="sxs-lookup"><span data-stu-id="66b7b-p104">None. The Export-CcConfigurationSampleFile cmdlet does not accept pipelined input.</span></span> 
  
## <a name="return-types"></a><span data-ttu-id="66b7b-124">返回类型</span><span class="sxs-lookup"><span data-stu-id="66b7b-124">Return Types</span></span>
<span data-ttu-id="66b7b-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="66b7b-125"></span></span>

<span data-ttu-id="66b7b-126">无</span><span class="sxs-lookup"><span data-stu-id="66b7b-126">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="66b7b-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="66b7b-127">See also</span></span>
<span data-ttu-id="66b7b-128"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="66b7b-128"></span></span>

[<span data-ttu-id="66b7b-129">一组 CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="66b7b-129">Set-CcApplianceDirectory</span></span>](set-ccappliancedirectory.md)
  

