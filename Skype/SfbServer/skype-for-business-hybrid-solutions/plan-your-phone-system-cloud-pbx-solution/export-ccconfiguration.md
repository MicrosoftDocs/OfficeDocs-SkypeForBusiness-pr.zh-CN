---
title: 导出 CcConfiguration
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e3775bd6-682c-4f62-aafc-974fe3a65c61
description: 用于将 Skype for Business 云连接器版本配置导出到 Skype for Business 云连接器版本主机服务器上的一个本地文件。
ms.openlocfilehash: dfabf5f486190b13acd18f0ffcf67f9b7e37052c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="export-ccconfiguration"></a><span data-ttu-id="fdc89-103">导出 CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="fdc89-103">Export-CcConfiguration</span></span>
 
<span data-ttu-id="fdc89-104">用于将 Skype for Business 云连接器版本配置导出到 Skype for Business 云连接器版本主机服务器上的一个本地文件。</span><span class="sxs-lookup"><span data-stu-id="fdc89-104">Exports the Skype for Business Cloud Connector Edition configuration to a local file on the Skype for Business Cloud Connector Edition host server.</span></span>
  
```
Export-CcConfiguration [-Path] <String> [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="fdc89-105">示例</span><span class="sxs-lookup"><span data-stu-id="fdc89-105">Examples</span></span>
<span data-ttu-id="fdc89-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="fdc89-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="fdc89-107">示例 1</span><span class="sxs-lookup"><span data-stu-id="fdc89-107">Example 1</span></span>

<span data-ttu-id="fdc89-108">以下示例将 Path 参数设置为一个完整文件路径并将配置导出至该文件。</span><span class="sxs-lookup"><span data-stu-id="fdc89-108">The following example sets the Path parameter as a full file path and exports configurations to that file.</span></span>
  
```
Export-CcConfiguration -Path "C:\test\CloudConnector.ini" 
```

## <a name="detailed-description"></a><span data-ttu-id="fdc89-109">详细说明</span><span class="sxs-lookup"><span data-stu-id="fdc89-109">Detailed Description</span></span>
<span data-ttu-id="fdc89-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="fdc89-110"></span></span>

<span data-ttu-id="fdc89-111">Export-CcConfiguration cmdlet 允许你将云连接器配置保存到选定路径中的某个文件。</span><span class="sxs-lookup"><span data-stu-id="fdc89-111">The Export-CcConfiguration cmdlet allows you to save the Cloud Connector configuration to a file in a selected path.</span></span> <span data-ttu-id="fdc89-112">此命令在云连接器版本 2.0 版中引入。</span><span class="sxs-lookup"><span data-stu-id="fdc89-112">This command was introduced in Cloud Connector Edition version 2.0.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="fdc89-113">参数</span><span class="sxs-lookup"><span data-stu-id="fdc89-113">Parameters</span></span>
<span data-ttu-id="fdc89-114"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="fdc89-114"></span></span>

|<span data-ttu-id="fdc89-115">**参数**</span><span class="sxs-lookup"><span data-stu-id="fdc89-115">**Parameter**</span></span>|<span data-ttu-id="fdc89-116">**必填**</span><span class="sxs-lookup"><span data-stu-id="fdc89-116">**Required**</span></span>|<span data-ttu-id="fdc89-117">**类型**</span><span class="sxs-lookup"><span data-stu-id="fdc89-117">**Type**</span></span>|<span data-ttu-id="fdc89-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="fdc89-118">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fdc89-119">路径</span><span class="sxs-lookup"><span data-stu-id="fdc89-119">Path</span></span>  <br/> |<span data-ttu-id="fdc89-120">必需</span><span class="sxs-lookup"><span data-stu-id="fdc89-120">Required</span></span>  <br/> |<span data-ttu-id="fdc89-121">System.String</span><span class="sxs-lookup"><span data-stu-id="fdc89-121">System.String</span></span>  <br/> |<span data-ttu-id="fdc89-122">将存储云连接器配置的完整文件路径。</span><span class="sxs-lookup"><span data-stu-id="fdc89-122">Full file path where the Cloud Connector configurations will be stored.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="fdc89-123">输入类型</span><span class="sxs-lookup"><span data-stu-id="fdc89-123">Input Types</span></span>
<span data-ttu-id="fdc89-124"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="fdc89-124"></span></span>

<span data-ttu-id="fdc89-125">无。</span><span class="sxs-lookup"><span data-stu-id="fdc89-125">None.</span></span> <span data-ttu-id="fdc89-126">Export-CcConfiguration cmdlet 不接受主线输入。</span><span class="sxs-lookup"><span data-stu-id="fdc89-126">The Export-CcConfiguration cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="fdc89-127">返回类型</span><span class="sxs-lookup"><span data-stu-id="fdc89-127">Return Types</span></span>
<span data-ttu-id="fdc89-128"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="fdc89-128"></span></span>

<span data-ttu-id="fdc89-129">无。</span><span class="sxs-lookup"><span data-stu-id="fdc89-129">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="fdc89-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fdc89-130">See also</span></span>
<span data-ttu-id="fdc89-131"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="fdc89-131"></span></span>

<span data-ttu-id="fdc89-132">导入 CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="fdc89-132">Import-CcConfiguration</span></span>
  

