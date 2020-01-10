---
title: Import-CcConfiguration
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 10/11/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 461361a0-9aa9-469d-ace0-dc70b95cd4a3
description: 将 Skype for Business Cloud Connector Edition 配置从本地文件导入到云连接器主机服务器。
ms.openlocfilehash: c72a72351ecb6936832bc5d6a2493c5fa8dfe324
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003332"
---
# <a name="import-ccconfiguration"></a><span data-ttu-id="08c44-103">Import-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="08c44-103">Import-CcConfiguration</span></span>
 
<span data-ttu-id="08c44-104">将 Skype for Business Cloud Connector Edition 配置从本地文件导入到云连接器主机服务器。</span><span class="sxs-lookup"><span data-stu-id="08c44-104">Imports the Skype for Business Cloud Connector Edition configuration from a local file to the Cloud Connector host server.</span></span>
  
```powershell
Import-CcConfiguration [-Force] [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="08c44-105">示例</span><span class="sxs-lookup"><span data-stu-id="08c44-105">Examples</span></span>
<span data-ttu-id="08c44-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="08c44-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="08c44-107">示例 1</span><span class="sxs-lookup"><span data-stu-id="08c44-107">Example 1</span></span>

<span data-ttu-id="08c44-108">下面的示例将 CloudConnector 从云连接器实例的装置目录复制到%SystemDrive%\ProgramData\CloudConnector 目录：</span><span class="sxs-lookup"><span data-stu-id="08c44-108">The following example copies the CloudConnector.ini from the appliance directory of the Cloud Connector instance to %SystemDrive%\ProgramData\CloudConnector directory:</span></span>
  
```powershell
Import-CcConfiguration
```

## <a name="detailed-description"></a><span data-ttu-id="08c44-109">详细说明</span><span class="sxs-lookup"><span data-stu-id="08c44-109">Detailed Description</span></span>
<span data-ttu-id="08c44-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="08c44-110"></span></span>

<span data-ttu-id="08c44-111">此 cmdlet 将 CloudConnector 从云连接器装置的装置目录复制到%SystemDrive%\ProgramData\CloudConnector 目录。</span><span class="sxs-lookup"><span data-stu-id="08c44-111">This cmdlet copies the CloudConnector.ini from the appliance directory of the Cloud Connector appliance to the %SystemDrive%\ProgramData\CloudConnector directory.</span></span> <span data-ttu-id="08c44-112">设备目录通过使用 Set-CcApplianceDirectory cmdlet 来指定。</span><span class="sxs-lookup"><span data-stu-id="08c44-112">The appliance directory is specified by using the Set-CcApplianceDirectory cmdlet.</span></span> <span data-ttu-id="08c44-113">此 cmdlet 将覆盖%SystemDrive%\ProgramData\CloudConnector. 中的任何现有文件</span><span class="sxs-lookup"><span data-stu-id="08c44-113">The cmdlet will overwrite any existing file in %SystemDrive%\ProgramData\CloudConnector.</span></span> <span data-ttu-id="08c44-114">此命令适用于云连接器版本2.0.1 及更高版本。</span><span class="sxs-lookup"><span data-stu-id="08c44-114">This command applies to Cloud Connector Edition version 2.0.1 and later.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="08c44-115">参数</span><span class="sxs-lookup"><span data-stu-id="08c44-115">Parameters</span></span>
<span data-ttu-id="08c44-116"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="08c44-116"></span></span>

|<span data-ttu-id="08c44-117">**参数**</span><span class="sxs-lookup"><span data-stu-id="08c44-117">**Parameter**</span></span>|<span data-ttu-id="08c44-118">**必需**</span><span class="sxs-lookup"><span data-stu-id="08c44-118">**Required**</span></span>|<span data-ttu-id="08c44-119">**类型**</span><span class="sxs-lookup"><span data-stu-id="08c44-119">**Type**</span></span>|<span data-ttu-id="08c44-120">**说明**</span><span class="sxs-lookup"><span data-stu-id="08c44-120">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="08c44-121">Force</span><span class="sxs-lookup"><span data-stu-id="08c44-121">Force</span></span>  <br/> |<span data-ttu-id="08c44-122">可选</span><span class="sxs-lookup"><span data-stu-id="08c44-122">Optional</span></span>  <br/> |<span data-ttu-id="08c44-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="08c44-123">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="08c44-124">在%SystemDrive%\ProgramData\CloudConnector 中覆盖现有文件，但不发出通知。</span><span class="sxs-lookup"><span data-stu-id="08c44-124">Overwrite existing file in %SystemDrive%\ProgramData\CloudConnector without notification.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="08c44-125">输入类型</span><span class="sxs-lookup"><span data-stu-id="08c44-125">Input Types</span></span>
<span data-ttu-id="08c44-126"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="08c44-126"></span></span>

<span data-ttu-id="08c44-127">无。</span><span class="sxs-lookup"><span data-stu-id="08c44-127">None.</span></span> <span data-ttu-id="08c44-128">CcConfiguration cmdlet 不接受流水线输入。</span><span class="sxs-lookup"><span data-stu-id="08c44-128">The Import-CcConfiguration cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="08c44-129">返回类型</span><span class="sxs-lookup"><span data-stu-id="08c44-129">Return Types</span></span>
<span data-ttu-id="08c44-130"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="08c44-130"></span></span>

<span data-ttu-id="08c44-131">无。</span><span class="sxs-lookup"><span data-stu-id="08c44-131">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="08c44-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="08c44-132">See also</span></span>
<span data-ttu-id="08c44-133"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="08c44-133"></span></span>

<span data-ttu-id="08c44-134">Export-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="08c44-134">Export-CcConfiguration</span></span>
  

