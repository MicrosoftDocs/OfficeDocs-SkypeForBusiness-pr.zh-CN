---
title: Export-CcRootCertificate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1499e33c-6a7c-46b9-b9a1-f78d7853b45d
description: 'Export-CcRootCertificate cmdlet 用于将根 CA 证书导出到 Skype for Business 云连接器版本主机服务器上的一个本地文件。 '
ms.openlocfilehash: 2b252eba4688deb790d85b0c3663b09a9e85e7b9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41800912"
---
# <a name="export-ccrootcertificate"></a><span data-ttu-id="ed26b-103">Export-CcRootCertificate</span><span class="sxs-lookup"><span data-stu-id="ed26b-103">Export-CcRootCertificate</span></span>
 
<span data-ttu-id="ed26b-104">Export-CcRootCertificate cmdlet 用于将根 CA 证书导出到 Skype for Business 云连接器版本主机服务器上的一个本地文件。 </span><span class="sxs-lookup"><span data-stu-id="ed26b-104">The Export-CcRootCertificate cmdlet exports the root CA certificate to a local file on the Skype for Business Cloud Connector Edition host server.</span></span> 
  
```powershell
Export-CcRootCertificate [[-Path] <string>]
```

## <a name="examples"></a><span data-ttu-id="ed26b-105">示例</span><span class="sxs-lookup"><span data-stu-id="ed26b-105">Examples</span></span>
<span data-ttu-id="ed26b-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="ed26b-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="ed26b-107">示例 1</span><span class="sxs-lookup"><span data-stu-id="ed26b-107">Example 1</span></span>

<span data-ttu-id="ed26b-p101">以下示例将 Path 参数设置为目录路径，而非文件路径。 它将生成文件 c:\test\CCERootCertificates.p7b。</span><span class="sxs-lookup"><span data-stu-id="ed26b-p101">The following example sets the Path parameter as a directory path—not a file path. It generates the file c:\test\CCERootCertificates.p7b.</span></span>
  
```powershell
Export-CcRootCertificate -Path "C:\test" 
```

## <a name="detailed-description"></a><span data-ttu-id="ed26b-110">详细说明</span><span class="sxs-lookup"><span data-stu-id="ed26b-110">Detailed Description</span></span>
<span data-ttu-id="ed26b-111"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="ed26b-111"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="ed26b-p102">使用 Export-CcRootCertificate cmdlet 可以将根和中间证书保存到文件路径。 这在发生灾难恢复的情况下很有用。 </span><span class="sxs-lookup"><span data-stu-id="ed26b-p102">The Export-CcRootCertificate cmdlet allows you to save the root and intermediate certificates to a file path. This can be useful in case of a disaster recovery scenario.</span></span> 
  
## <a name="parameters"></a><span data-ttu-id="ed26b-114">参数</span><span class="sxs-lookup"><span data-stu-id="ed26b-114">Parameters</span></span>
<span data-ttu-id="ed26b-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="ed26b-115"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="ed26b-116">**参数**</span><span class="sxs-lookup"><span data-stu-id="ed26b-116">**Parameter**</span></span>|<span data-ttu-id="ed26b-117">**必需**</span><span class="sxs-lookup"><span data-stu-id="ed26b-117">**Required**</span></span>|<span data-ttu-id="ed26b-118">**类型**</span><span class="sxs-lookup"><span data-stu-id="ed26b-118">**Type**</span></span>|<span data-ttu-id="ed26b-119">**说明**</span><span class="sxs-lookup"><span data-stu-id="ed26b-119">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ed26b-120">路径</span><span class="sxs-lookup"><span data-stu-id="ed26b-120">Path</span></span>  <br/> |<span data-ttu-id="ed26b-121">必需</span><span class="sxs-lookup"><span data-stu-id="ed26b-121">Required</span></span>  <br/> |<span data-ttu-id="ed26b-122">System.String</span><span class="sxs-lookup"><span data-stu-id="ed26b-122">System.String</span></span>  <br/> |<span data-ttu-id="ed26b-123">将存储证书的文件路径。 </span><span class="sxs-lookup"><span data-stu-id="ed26b-123">File path where the certificate will be stored.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="ed26b-124">输入类型</span><span class="sxs-lookup"><span data-stu-id="ed26b-124">Input Types</span></span>
<span data-ttu-id="ed26b-125"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ed26b-125"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="ed26b-p103">无。 Export-CcRootCertificate cmdlet 不接受通过管道传递的输入。 </span><span class="sxs-lookup"><span data-stu-id="ed26b-p103">None. The Export-CcRootCertificate cmdlet does not accept pipelined input.</span></span> 
  
## <a name="return-types"></a><span data-ttu-id="ed26b-128">返回类型</span><span class="sxs-lookup"><span data-stu-id="ed26b-128">Return Types</span></span>
<span data-ttu-id="ed26b-129"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ed26b-129"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="ed26b-130">无</span><span class="sxs-lookup"><span data-stu-id="ed26b-130">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ed26b-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ed26b-131">See also</span></span>
<span data-ttu-id="ed26b-132"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ed26b-132"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="ed26b-133">无</span><span class="sxs-lookup"><span data-stu-id="ed26b-133">None</span></span>
  

