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
description: 将业务云连接器 Edition 配置 Skype 从本地文件导入到云连接器主机服务器上。
ms.openlocfilehash: c48ce321b4cf40626cc67de8ff32107bf08e5443
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569724"
---
# <a name="import-ccconfiguration"></a><span data-ttu-id="528eb-103">导入 CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="528eb-103">Import-CcConfiguration</span></span>
 
<span data-ttu-id="528eb-104">将业务云连接器 Edition 配置 Skype 从本地文件导入到云连接器主机服务器上。</span><span class="sxs-lookup"><span data-stu-id="528eb-104">Imports the Skype for Business Cloud Connector Edition configuration from a local file to the Cloud Connector host server.</span></span>
  
```
Import-CcConfiguration [-Force] [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="528eb-105">示例</span><span class="sxs-lookup"><span data-stu-id="528eb-105">Examples</span></span>
<span data-ttu-id="528eb-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="528eb-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="528eb-107">示例 1</span><span class="sxs-lookup"><span data-stu-id="528eb-107">Example 1</span></span>

<span data-ttu-id="528eb-108">下面的示例将从云连接器实例的装置目录 CloudConnector.ini 复制到 %SystemDrive%\ProgramData\CloudConnector 目录中：</span><span class="sxs-lookup"><span data-stu-id="528eb-108">The following example copies the CloudConnector.ini from the appliance directory of the Cloud Connector instance to %SystemDrive%\ProgramData\CloudConnector directory:</span></span>
  
```
Import-CcConfiguration
```

## <a name="detailed-description"></a><span data-ttu-id="528eb-109">详细说明</span><span class="sxs-lookup"><span data-stu-id="528eb-109">Detailed Description</span></span>
<span data-ttu-id="528eb-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="528eb-110"></span></span>

<span data-ttu-id="528eb-111">此 cmdlet 将从云连接器装置的装置目录 CloudConnector.ini 复制到 %SystemDrive%\ProgramData\CloudConnector 目录中。</span><span class="sxs-lookup"><span data-stu-id="528eb-111">This cmdlet copies the CloudConnector.ini from the appliance directory of the Cloud Connector appliance to the %SystemDrive%\ProgramData\CloudConnector directory.</span></span> <span data-ttu-id="528eb-112">设备目录通过使用 Set-CcApplianceDirectory cmdlet 来指定。</span><span class="sxs-lookup"><span data-stu-id="528eb-112">The appliance directory is specified by using the Set-CcApplianceDirectory cmdlet.</span></span> <span data-ttu-id="528eb-113">此 cmdlet 将覆盖 %systemdrive%\programdata\cloudconnector 中的任何现有文件。</span><span class="sxs-lookup"><span data-stu-id="528eb-113">The cmdlet will overwrite any existing file in %SystemDrive%\ProgramData\CloudConnector.</span></span> <span data-ttu-id="528eb-114">此命令适用于云连接器 Edition 2.0.1 版及更高版本。</span><span class="sxs-lookup"><span data-stu-id="528eb-114">This command applies to Cloud Connector Edition version 2.0.1 and later.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="528eb-115">参数</span><span class="sxs-lookup"><span data-stu-id="528eb-115">Parameters</span></span>
<span data-ttu-id="528eb-116"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="528eb-116"></span></span>

|<span data-ttu-id="528eb-117">**参数**</span><span class="sxs-lookup"><span data-stu-id="528eb-117">**Parameter**</span></span>|<span data-ttu-id="528eb-118">**必填**</span><span class="sxs-lookup"><span data-stu-id="528eb-118">**Required**</span></span>|<span data-ttu-id="528eb-119">**类型**</span><span class="sxs-lookup"><span data-stu-id="528eb-119">**Type**</span></span>|<span data-ttu-id="528eb-120">**说明**</span><span class="sxs-lookup"><span data-stu-id="528eb-120">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="528eb-121">强制</span><span class="sxs-lookup"><span data-stu-id="528eb-121">Force</span></span>  <br/> |<span data-ttu-id="528eb-122">可选</span><span class="sxs-lookup"><span data-stu-id="528eb-122">Optional</span></span>  <br/> |<span data-ttu-id="528eb-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="528eb-123">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="528eb-124">覆盖现有文件中 %SystemDrive%\ProgramData\CloudConnector 而不发出通知。</span><span class="sxs-lookup"><span data-stu-id="528eb-124">Overwrite existing file in %SystemDrive%\ProgramData\CloudConnector without notification.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="528eb-125">输入类型</span><span class="sxs-lookup"><span data-stu-id="528eb-125">Input Types</span></span>
<span data-ttu-id="528eb-126"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="528eb-126"></span></span>

<span data-ttu-id="528eb-127">无。</span><span class="sxs-lookup"><span data-stu-id="528eb-127">None.</span></span> <span data-ttu-id="528eb-128">导入 CcConfiguration cmdlet 不接受通过管道传递的输入。</span><span class="sxs-lookup"><span data-stu-id="528eb-128">The Import-CcConfiguration cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="528eb-129">返回类型</span><span class="sxs-lookup"><span data-stu-id="528eb-129">Return Types</span></span>
<span data-ttu-id="528eb-130"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="528eb-130"></span></span>

<span data-ttu-id="528eb-131">无。</span><span class="sxs-lookup"><span data-stu-id="528eb-131">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="528eb-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="528eb-132">See also</span></span>
<span data-ttu-id="528eb-133"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="528eb-133"></span></span>

<span data-ttu-id="528eb-134">导出 CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="528eb-134">Export-CcConfiguration</span></span>
  

