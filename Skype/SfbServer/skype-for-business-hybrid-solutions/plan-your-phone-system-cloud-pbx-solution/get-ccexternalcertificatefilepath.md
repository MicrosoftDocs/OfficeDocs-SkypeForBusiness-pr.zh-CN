---
title: Get-CcExternalCertificateFilePath
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 62fdc9cc-e82e-463f-b8b3-05d5c6482ea2
description: Get-CcExternalCertificateFilePath cmdlet 将返回 Skype for Business 云连接器版本部署的外部证书文件路径。 用户准备此证书。
ms.openlocfilehash: ed725814380741aade73166d01025650dfa78538
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287319"
---
# <a name="get-ccexternalcertificatefilepath"></a><span data-ttu-id="029cb-104">Get-CcExternalCertificateFilePath</span><span class="sxs-lookup"><span data-stu-id="029cb-104">Get-CcExternalCertificateFilePath</span></span>
 
<span data-ttu-id="029cb-p102">Get-CcExternalCertificateFilePath cmdlet 将返回 Skype for Business 云连接器版本部署的外部证书文件路径。用户准备此证书。</span><span class="sxs-lookup"><span data-stu-id="029cb-p102">The Get-CcExternalCertificateFilePath cmdlet returns the external certificate file path for the Skype for Business Cloud Connector Edition deployment. The user prepares this certificate.</span></span>
  
<span data-ttu-id="029cb-107">此 cmdlet 适用于 Skype for Business 云连接器版本 1.4.1、1.4.2。</span><span class="sxs-lookup"><span data-stu-id="029cb-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```
Get-CcExternalCertificateFilePath [[-Target] <string> {EdgeServer | MediationServer}]
```

## <a name="examples"></a><span data-ttu-id="029cb-108">示例</span><span class="sxs-lookup"><span data-stu-id="029cb-108">Examples</span></span>
<span data-ttu-id="029cb-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="029cb-109"></span></span>

### <a name="example-1"></a><span data-ttu-id="029cb-110">示例 1</span><span class="sxs-lookup"><span data-stu-id="029cb-110">Example 1</span></span>

<span data-ttu-id="029cb-111">以下示例显示了边缘服务器的证书路径：</span><span class="sxs-lookup"><span data-stu-id="029cb-111">The following example shows the path of the certificate for the Edge Server:</span></span>
  
```
Get-CcExternalCertificateFilePath -Target EdgeServer
```

### <a name="example-2"></a><span data-ttu-id="029cb-112">示例 2</span><span class="sxs-lookup"><span data-stu-id="029cb-112">Example 2</span></span>

<span data-ttu-id="029cb-113">以下示例显示了为中介服务器设置的证书：</span><span class="sxs-lookup"><span data-stu-id="029cb-113">The following example shows the certificate set for the Mediation Server:</span></span>
  
```
Get-CcExternalCertificateFilePath -Target MediationServer
```

## <a name="detailed-description"></a><span data-ttu-id="029cb-114">详细说明</span><span class="sxs-lookup"><span data-stu-id="029cb-114">Detailed Description</span></span>
<span data-ttu-id="029cb-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="029cb-115"></span></span>

<span data-ttu-id="029cb-p103">在部署期间或在修改拓扑时，需要为边缘服务器证书指定路径，也可以选择为中介服务器证书指定路径。如果将在网关与中介服务器之间使用 TLS，则需要中介服务器的证书。要更改路径，请使用 Set-CcExternalCertificateFilePath cmdlet。</span><span class="sxs-lookup"><span data-stu-id="029cb-p103">During deployment or when modifying the topology, you need to specify the path for the Edge Server certificate, and, optionally, for the Mediation Server. The certificate for the Mediation Server is required if TLS will be used between the gateway (s) and the Mediation Server. To change the path, use the Set-CcExternalCertificateFilePath cmdlet.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="029cb-119">参数</span><span class="sxs-lookup"><span data-stu-id="029cb-119">Parameters</span></span>
<span data-ttu-id="029cb-120"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="029cb-120"></span></span>

|<span data-ttu-id="029cb-121">**参数**</span><span class="sxs-lookup"><span data-stu-id="029cb-121">**Parameter**</span></span>|<span data-ttu-id="029cb-122">**必需**</span><span class="sxs-lookup"><span data-stu-id="029cb-122">**Required**</span></span>|<span data-ttu-id="029cb-123">**类型**</span><span class="sxs-lookup"><span data-stu-id="029cb-123">**Type**</span></span>|<span data-ttu-id="029cb-124">**说明**</span><span class="sxs-lookup"><span data-stu-id="029cb-124">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="029cb-125">目标</span><span class="sxs-lookup"><span data-stu-id="029cb-125">Target</span></span>  <br/> |<span data-ttu-id="029cb-126">可选</span><span class="sxs-lookup"><span data-stu-id="029cb-126">Optional</span></span>  <br/> | <span data-ttu-id="029cb-127">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="029cb-127">System.Management.Automation.SwitchParameter</span></span> <br/> |<span data-ttu-id="029cb-p104">要求的文件路径类型。类型包括：</span><span class="sxs-lookup"><span data-stu-id="029cb-p104">Type of file path requested. Types include:</span></span>  <br/> <span data-ttu-id="029cb-130">EdgeServer（默认设置）</span><span class="sxs-lookup"><span data-stu-id="029cb-130">EdgeServer (default)</span></span>  <br/> <span data-ttu-id="029cb-131">MediationServer</span><span class="sxs-lookup"><span data-stu-id="029cb-131">MediationServer</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="029cb-132">输入类型</span><span class="sxs-lookup"><span data-stu-id="029cb-132">Input Types</span></span>
<span data-ttu-id="029cb-133"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="029cb-133"></span></span>

<span data-ttu-id="029cb-134">Get-CcExternalCertificateFilePath cmdlet 不接受主线输入。</span><span class="sxs-lookup"><span data-stu-id="029cb-134">The Get-CcExternalCertificateFilePath cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="029cb-135">返回类型</span><span class="sxs-lookup"><span data-stu-id="029cb-135">Return Types</span></span>
<span data-ttu-id="029cb-136"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="029cb-136"></span></span>

<span data-ttu-id="029cb-137">该命令返回文件路径。</span><span class="sxs-lookup"><span data-stu-id="029cb-137">The command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="029cb-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="029cb-138">See also</span></span>
<span data-ttu-id="029cb-139"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="029cb-139"></span></span>

[<span data-ttu-id="029cb-140">Set-CcExternalCertificateFilePath</span><span class="sxs-lookup"><span data-stu-id="029cb-140">Set-CcExternalCertificateFilePath</span></span>](set-ccexternalcertificatefilepath.md)
  

