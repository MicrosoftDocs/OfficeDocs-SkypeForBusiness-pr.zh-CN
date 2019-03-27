---
title: Import-CcConfiguration
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 10/11/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 461361a0-9aa9-469d-ace0-dc70b95cd4a3
description: 将业务云连接器 Edition 配置 Skype 从本地文件导入到云连接器主机服务器上。
ms.openlocfilehash: 497568f45fad6b4363581785bf0be95eabfeaebf
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30896621"
---
# <a name="import-ccconfiguration"></a><span data-ttu-id="4f82c-103">Import-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="4f82c-103">Import-CcConfiguration</span></span>
 
<span data-ttu-id="4f82c-104">将业务云连接器 Edition 配置 Skype 从本地文件导入到云连接器主机服务器上。</span><span class="sxs-lookup"><span data-stu-id="4f82c-104">Imports the Skype for Business Cloud Connector Edition configuration from a local file to the Cloud Connector host server.</span></span>
  
```
Import-CcConfiguration [-Force] [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="4f82c-105">示例</span><span class="sxs-lookup"><span data-stu-id="4f82c-105">Examples</span></span>
<span data-ttu-id="4f82c-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="4f82c-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="4f82c-107">示例 1</span><span class="sxs-lookup"><span data-stu-id="4f82c-107">Example 1</span></span>

<span data-ttu-id="4f82c-108">下面的示例将从云连接器实例的装置目录 CloudConnector.ini 复制到 %SystemDrive%\ProgramData\CloudConnector 目录中：</span><span class="sxs-lookup"><span data-stu-id="4f82c-108">The following example copies the CloudConnector.ini from the appliance directory of the Cloud Connector instance to %SystemDrive%\ProgramData\CloudConnector directory:</span></span>
  
```
Import-CcConfiguration
```

## <a name="detailed-description"></a><span data-ttu-id="4f82c-109">详细说明</span><span class="sxs-lookup"><span data-stu-id="4f82c-109">Detailed Description</span></span>
<span data-ttu-id="4f82c-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="4f82c-110"></span></span>

<span data-ttu-id="4f82c-111">此 cmdlet 将从云连接器装置的装置目录 CloudConnector.ini 复制到 %SystemDrive%\ProgramData\CloudConnector 目录中。</span><span class="sxs-lookup"><span data-stu-id="4f82c-111">This cmdlet copies the CloudConnector.ini from the appliance directory of the Cloud Connector appliance to the %SystemDrive%\ProgramData\CloudConnector directory.</span></span> <span data-ttu-id="4f82c-112">设备目录通过使用 Set-CcApplianceDirectory cmdlet 来指定。</span><span class="sxs-lookup"><span data-stu-id="4f82c-112">The appliance directory is specified by using the Set-CcApplianceDirectory cmdlet.</span></span> <span data-ttu-id="4f82c-113">此 cmdlet 将覆盖 %systemdrive%\programdata\cloudconnector 中的任何现有文件。</span><span class="sxs-lookup"><span data-stu-id="4f82c-113">The cmdlet will overwrite any existing file in %SystemDrive%\ProgramData\CloudConnector.</span></span> <span data-ttu-id="4f82c-114">此命令适用于云连接器 Edition 2.0.1 版及更高版本。</span><span class="sxs-lookup"><span data-stu-id="4f82c-114">This command applies to Cloud Connector Edition version 2.0.1 and later.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="4f82c-115">参数</span><span class="sxs-lookup"><span data-stu-id="4f82c-115">Parameters</span></span>
<span data-ttu-id="4f82c-116"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="4f82c-116"></span></span>

|<span data-ttu-id="4f82c-117">**参数**</span><span class="sxs-lookup"><span data-stu-id="4f82c-117">**Parameter**</span></span>|<span data-ttu-id="4f82c-118">**必需**</span><span class="sxs-lookup"><span data-stu-id="4f82c-118">**Required**</span></span>|<span data-ttu-id="4f82c-119">**类型**</span><span class="sxs-lookup"><span data-stu-id="4f82c-119">**Type**</span></span>|<span data-ttu-id="4f82c-120">**说明**</span><span class="sxs-lookup"><span data-stu-id="4f82c-120">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4f82c-121">Force</span><span class="sxs-lookup"><span data-stu-id="4f82c-121">Force</span></span>  <br/> |<span data-ttu-id="4f82c-122">可选</span><span class="sxs-lookup"><span data-stu-id="4f82c-122">Optional</span></span>  <br/> |<span data-ttu-id="4f82c-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="4f82c-123">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="4f82c-124">覆盖现有文件中 %SystemDrive%\ProgramData\CloudConnector 而不发出通知。</span><span class="sxs-lookup"><span data-stu-id="4f82c-124">Overwrite existing file in %SystemDrive%\ProgramData\CloudConnector without notification.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="4f82c-125">输入类型</span><span class="sxs-lookup"><span data-stu-id="4f82c-125">Input Types</span></span>
<span data-ttu-id="4f82c-126"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="4f82c-126"></span></span>

<span data-ttu-id="4f82c-127">无。</span><span class="sxs-lookup"><span data-stu-id="4f82c-127">None.</span></span> <span data-ttu-id="4f82c-128">导入 CcConfiguration cmdlet 不接受通过管道传递的输入。</span><span class="sxs-lookup"><span data-stu-id="4f82c-128">The Import-CcConfiguration cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="4f82c-129">返回类型</span><span class="sxs-lookup"><span data-stu-id="4f82c-129">Return Types</span></span>
<span data-ttu-id="4f82c-130"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="4f82c-130"></span></span>

<span data-ttu-id="4f82c-131">无。</span><span class="sxs-lookup"><span data-stu-id="4f82c-131">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4f82c-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4f82c-132">See also</span></span>
<span data-ttu-id="4f82c-133"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="4f82c-133"></span></span>

<span data-ttu-id="4f82c-134">Export-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="4f82c-134">Export-CcConfiguration</span></span>
  

