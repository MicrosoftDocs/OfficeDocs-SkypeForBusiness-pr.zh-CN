---
title: Set-CcExternalCertificateFilePath
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 443d071e-633e-4337-b20b-f30cdfbd4aaf
description: Set-CcExternalCertificateFilePath cmdlet 指定中介服务器或边缘服务器的证书的存储路径。
ms.openlocfilehash: bc22771c20277d9de99660551864d600f06b3acc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286983"
---
# <a name="set-ccexternalcertificatefilepath"></a><span data-ttu-id="ff0c6-103">Set-CcExternalCertificateFilePath</span><span class="sxs-lookup"><span data-stu-id="ff0c6-103">Set-CcExternalCertificateFilePath</span></span>
 
<span data-ttu-id="ff0c6-104">Set-CcExternalCertificateFilePath cmdlet 指定中介服务器或边缘服务器的证书的存储路径。</span><span class="sxs-lookup"><span data-stu-id="ff0c6-104">The Set-CcExternalCertificateFilePath cmdlet specifies the path where the certificate for the Mediation Server or Edge Server is stored.</span></span>
  
<span data-ttu-id="ff0c6-p101">在部署过程中或添加 Skype for Business 云连接器版本的新设备时，需要此证书。该命令还用于在部署后为中介服务器导入新证书。</span><span class="sxs-lookup"><span data-stu-id="ff0c6-p101">This certificate is required during deployment or when adding new appliances of Skype for Business Cloud Connector Edition. The command also allows importing a new certificate for the Mediation Server after the deployment.</span></span>
  
<span data-ttu-id="ff0c6-107">此 cmdlet 适用于 Skype for Business 云连接器版本 1.4.1、1.4.2。</span><span class="sxs-lookup"><span data-stu-id="ff0c6-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```
Set-CcExternalCertificateFilePath [-Target] <string> {EdgeServer | MediationServer} [-Path] <string> [-Import]  [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="ff0c6-108">示例</span><span class="sxs-lookup"><span data-stu-id="ff0c6-108">Examples</span></span>
<span data-ttu-id="ff0c6-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="ff0c6-109"></span></span>

### <a name="example-1"></a><span data-ttu-id="ff0c6-110">示例 1</span><span class="sxs-lookup"><span data-stu-id="ff0c6-110">Example 1</span></span>

<span data-ttu-id="ff0c6-111">以下示例设置边缘服务器的证书路径：</span><span class="sxs-lookup"><span data-stu-id="ff0c6-111">The following example sets the path of the certificate for the Edge Server:</span></span>
  
```
Set-CcExternalCertificateFilePath -Target EdgeServer -Path C:\CloudConnector\Certificates\AdatumPublicEdge.pfx
```

### <a name="example-2"></a><span data-ttu-id="ff0c6-112">示例 2</span><span class="sxs-lookup"><span data-stu-id="ff0c6-112">Example 2</span></span>

<span data-ttu-id="ff0c6-113">以下示例设置中介服务器的证书路径：</span><span class="sxs-lookup"><span data-stu-id="ff0c6-113">The next example sets the path of the certificate for the Mediation Server:</span></span>
  
```
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx
```

### <a name="example-3"></a><span data-ttu-id="ff0c6-114">示例 3</span><span class="sxs-lookup"><span data-stu-id="ff0c6-114">Example 3</span></span>

<span data-ttu-id="ff0c6-115">以下示例更新中介服务器的证书：</span><span class="sxs-lookup"><span data-stu-id="ff0c6-115">The next example updates the certificate for the Mediation Server:</span></span>
  
```
Set-CcExternalCertificateFilePath -Target MediationServer -Path C:\CloudConnector\Certificates\AdatumPublicMediation.pfx -Import
```

## <a name="detailed-description"></a><span data-ttu-id="ff0c6-116">详细说明</span><span class="sxs-lookup"><span data-stu-id="ff0c6-116">Detailed Description</span></span>
<span data-ttu-id="ff0c6-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="ff0c6-117"></span></span>

<span data-ttu-id="ff0c6-118">在部署过程中或修改拓扑时，需要为边缘服务器证书指定路径，也可以选择为中介服务器证书指定路径。</span><span class="sxs-lookup"><span data-stu-id="ff0c6-118">During the deployment, or while modifying the topology, you need to specify the path for the Edge Server certificate, and optionally for the Mediation Server certificate.</span></span> 
  
<span data-ttu-id="ff0c6-119">如果将在网关与中介服务器之间使用 TLS，需要中介服务器的证书。</span><span class="sxs-lookup"><span data-stu-id="ff0c6-119">The certificate for the Mediation Server is required if TLS will be used between the gateway (s) and the Mediation Server.</span></span> <span data-ttu-id="ff0c6-120">部署云连接器设备并希望部署 TLS 时, 只能指定将在中介服务器上部署的证书的路径。</span><span class="sxs-lookup"><span data-stu-id="ff0c6-120">When you deploy a Cloud Connector appliance and want to deploy TLS, you can only specify the path to the certificate that will be deployed on the Mediation Server.</span></span> <span data-ttu-id="ff0c6-121">但是，如果你希望更新已部署的设备上的中介证书，则需要指定路径和 -Import 参数。</span><span class="sxs-lookup"><span data-stu-id="ff0c6-121">However, if you want to update the Mediation certificate on an already deployed appliance, you need to specify the path and the -Import parameter.</span></span> <span data-ttu-id="ff0c6-122">要查看参数，请使用 Get-CCExternalCertificateFilePath cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ff0c6-122">To see the path, use the Get-CCExternalCertificateFilePath cmdlet.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="ff0c6-123">参数</span><span class="sxs-lookup"><span data-stu-id="ff0c6-123">Parameters</span></span>
<span data-ttu-id="ff0c6-124"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="ff0c6-124"></span></span>

|<span data-ttu-id="ff0c6-125">**参数**</span><span class="sxs-lookup"><span data-stu-id="ff0c6-125">**Parameter**</span></span>|<span data-ttu-id="ff0c6-126">**必需**</span><span class="sxs-lookup"><span data-stu-id="ff0c6-126">**Required**</span></span>|<span data-ttu-id="ff0c6-127">**类型**</span><span class="sxs-lookup"><span data-stu-id="ff0c6-127">**Type**</span></span>|<span data-ttu-id="ff0c6-128">**说明**</span><span class="sxs-lookup"><span data-stu-id="ff0c6-128">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="ff0c6-129">目标</span><span class="sxs-lookup"><span data-stu-id="ff0c6-129">Target</span></span> <br/> | <span data-ttu-id="ff0c6-130">必需</span><span class="sxs-lookup"><span data-stu-id="ff0c6-130">Required</span></span> <br/> |<span data-ttu-id="ff0c6-131">System.String</span><span class="sxs-lookup"><span data-stu-id="ff0c6-131">System.String</span></span>  <br/> |<span data-ttu-id="ff0c6-p103">要求的文件路径类型。类型包括：</span><span class="sxs-lookup"><span data-stu-id="ff0c6-p103">Type of file path requested. Types include:</span></span>  <br/> <span data-ttu-id="ff0c6-134">EdgeServer（默认设置）</span><span class="sxs-lookup"><span data-stu-id="ff0c6-134">EdgeServer (default)</span></span>  <br/> <span data-ttu-id="ff0c6-135">MediationServer</span><span class="sxs-lookup"><span data-stu-id="ff0c6-135">MediationServer</span></span>  <br/> |
|<span data-ttu-id="ff0c6-136">导入</span><span class="sxs-lookup"><span data-stu-id="ff0c6-136">Import</span></span>  <br/> |<span data-ttu-id="ff0c6-137">可选</span><span class="sxs-lookup"><span data-stu-id="ff0c6-137">Optional</span></span>  <br/> |<span data-ttu-id="ff0c6-138">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="ff0c6-138">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="ff0c6-p104">指示必须将证书导入中介服务器。如果是首次部署设备，则不需要此参数。如果你要更改已部署的版本上的现有证书，则需要此参数。</span><span class="sxs-lookup"><span data-stu-id="ff0c6-p104">Indicates that the certificate must be imported to the Mediation Server. This parameter is not needed if you deploy an appliance for first time. The parameter is required if you want to change the existing certificate on an already deployed version.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="ff0c6-142">输入类型</span><span class="sxs-lookup"><span data-stu-id="ff0c6-142">Input Types</span></span>
<span data-ttu-id="ff0c6-143"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ff0c6-143"></span></span>

<span data-ttu-id="ff0c6-144">Set-CcExternalCertificateFilePath cmdlet 不接受主线输入。</span><span class="sxs-lookup"><span data-stu-id="ff0c6-144">The Set-CcExternalCertificateFilePath cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="ff0c6-145">返回类型</span><span class="sxs-lookup"><span data-stu-id="ff0c6-145">Return Types</span></span>
<span data-ttu-id="ff0c6-146"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ff0c6-146"></span></span>

<span data-ttu-id="ff0c6-147">无</span><span class="sxs-lookup"><span data-stu-id="ff0c6-147">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ff0c6-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ff0c6-148">See also</span></span>
<span data-ttu-id="ff0c6-149"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ff0c6-149"></span></span>

[<span data-ttu-id="ff0c6-150">Get-CcExternalCertificateFilePath</span><span class="sxs-lookup"><span data-stu-id="ff0c6-150">Get-CcExternalCertificateFilePath</span></span>](get-ccexternalcertificatefilepath.md)
  

