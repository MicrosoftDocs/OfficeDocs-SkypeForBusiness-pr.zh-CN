---
title: 导入 CcConfiguration
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 10/11/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 461361a0-9aa9-469d-ace0-dc70b95cd4a3
description: 将 Skype 商务云连接器版配置从本地文件导入到云连接器宿主服务器上。
ms.openlocfilehash: 46f4099258ce4090fa23ec980801e55f7300895f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="import-ccconfiguration"></a><span data-ttu-id="5cdaa-103">导入 CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="5cdaa-103">Import-CcConfiguration</span></span>
 
<span data-ttu-id="5cdaa-104">将 Skype 商务云连接器版配置从本地文件导入到云连接器宿主服务器上。</span><span class="sxs-lookup"><span data-stu-id="5cdaa-104">Imports the Skype for Business Cloud Connector Edition configuration from a local file to the Cloud Connector host server.</span></span>
  
```

Import-CcConfiguration [-Force] [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="5cdaa-105">示例</span><span class="sxs-lookup"><span data-stu-id="5cdaa-105">Examples</span></span>
<span data-ttu-id="5cdaa-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="5cdaa-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="5cdaa-107">示例 1</span><span class="sxs-lookup"><span data-stu-id="5cdaa-107">Example 1</span></span>

<span data-ttu-id="5cdaa-108">下面的示例将从云连接器实例的设备目录 CloudConnector.ini 复制到 %SystemDrive%\ProgramData\CloudConnector 目录中：</span><span class="sxs-lookup"><span data-stu-id="5cdaa-108">The following example copies the CloudConnector.ini from the appliance directory of the Cloud Connector instance to %SystemDrive%\ProgramData\CloudConnector directory:</span></span>
  
```
Import-CcConfiguration
```

## <a name="detailed-description"></a><span data-ttu-id="5cdaa-109">详细说明</span><span class="sxs-lookup"><span data-stu-id="5cdaa-109">Detailed Description</span></span>
<span data-ttu-id="5cdaa-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="5cdaa-110"></span></span>

<span data-ttu-id="5cdaa-111">此 cmdlet 将云接口装置的设备目录 CloudConnector.ini 复制到 %SystemDrive%\ProgramData\CloudConnector 目录。</span><span class="sxs-lookup"><span data-stu-id="5cdaa-111">This cmdlet copies the CloudConnector.ini from the appliance directory of the Cloud Connector appliance to the %SystemDrive%\ProgramData\CloudConnector directory.</span></span> <span data-ttu-id="5cdaa-112">设备目录通过使用 Set-CcApplianceDirectory cmdlet 来指定。</span><span class="sxs-lookup"><span data-stu-id="5cdaa-112">The appliance directory is specified by using the Set-CcApplianceDirectory cmdlet.</span></span> <span data-ttu-id="5cdaa-113">该 cmdlet 将覆盖任何现有文件，%systemdrive%\programdata\cloudconnector 中。</span><span class="sxs-lookup"><span data-stu-id="5cdaa-113">The cmdlet will overwrite any existing file in %SystemDrive%\ProgramData\CloudConnector.</span></span> <span data-ttu-id="5cdaa-114">本命令适用于云连接器版本 2.0.1 版及更高版本。</span><span class="sxs-lookup"><span data-stu-id="5cdaa-114">This command applies to Cloud Connector Edition version 2.0.1 and later.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="5cdaa-115">参数</span><span class="sxs-lookup"><span data-stu-id="5cdaa-115">Parameters</span></span>
<span data-ttu-id="5cdaa-116"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="5cdaa-116"></span></span>

|<span data-ttu-id="5cdaa-117">**参数**</span><span class="sxs-lookup"><span data-stu-id="5cdaa-117">**Parameter**</span></span>|<span data-ttu-id="5cdaa-118">**必填**</span><span class="sxs-lookup"><span data-stu-id="5cdaa-118">**Required**</span></span>|<span data-ttu-id="5cdaa-119">**类型**</span><span class="sxs-lookup"><span data-stu-id="5cdaa-119">**Type**</span></span>|<span data-ttu-id="5cdaa-120">**说明**</span><span class="sxs-lookup"><span data-stu-id="5cdaa-120">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5cdaa-121">强制</span><span class="sxs-lookup"><span data-stu-id="5cdaa-121">Force</span></span>  <br/> |<span data-ttu-id="5cdaa-122">可选</span><span class="sxs-lookup"><span data-stu-id="5cdaa-122">Optional</span></span>  <br/> |<span data-ttu-id="5cdaa-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="5cdaa-123">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="5cdaa-124">覆盖现有文件中 %SystemDrive%\ProgramData\CloudConnector 而不另行通知。</span><span class="sxs-lookup"><span data-stu-id="5cdaa-124">Overwrite existing file in %SystemDrive%\ProgramData\CloudConnector without notification.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="5cdaa-125">输入类型</span><span class="sxs-lookup"><span data-stu-id="5cdaa-125">Input Types</span></span>
<span data-ttu-id="5cdaa-126"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="5cdaa-126"></span></span>

<span data-ttu-id="5cdaa-127">无。</span><span class="sxs-lookup"><span data-stu-id="5cdaa-127">None.</span></span> <span data-ttu-id="5cdaa-128">导入 CcConfiguration cmdlet 不接受管道的输入。</span><span class="sxs-lookup"><span data-stu-id="5cdaa-128">The Import-CcConfiguration cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="5cdaa-129">返回类型</span><span class="sxs-lookup"><span data-stu-id="5cdaa-129">Return Types</span></span>
<span data-ttu-id="5cdaa-130"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="5cdaa-130"></span></span>

<span data-ttu-id="5cdaa-131">无。</span><span class="sxs-lookup"><span data-stu-id="5cdaa-131">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5cdaa-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5cdaa-132">See also</span></span>
<span data-ttu-id="5cdaa-133"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="5cdaa-133"></span></span>

<span data-ttu-id="5cdaa-134">导出 CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="5cdaa-134">Export-CcConfiguration</span></span>
  

