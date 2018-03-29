---
title: 一组 CcCredential
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 784ff94a-4b33-4dbd-ba74-27acc3eb6954
description: Set-CcCredential cmdlet 用于设置当前 Skype for Business 云连接器版本部署的凭据。
ms.openlocfilehash: 7680f863ccf082ddb8359c7d3fcefc2c058b6a40
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="set-cccredential"></a><span data-ttu-id="cb4f4-103">一组 CcCredential</span><span class="sxs-lookup"><span data-stu-id="cb4f4-103">Set-CcCredential</span></span>
 
<span data-ttu-id="cb4f4-104">Set-CcCredential cmdlet 用于设置当前 Skype for Business 云连接器版本部署的凭据。</span><span class="sxs-lookup"><span data-stu-id="cb4f4-104">The Set-CcCredential cmdlet sets the credential of the current Skype for Business Cloud Connector Edition deployment.</span></span> 
  
<span data-ttu-id="cb4f4-105">与云连接器 2.0 及更高版本，此 cmdlet 还可以设置帐户信息为虚拟机管理员和域管理员。</span><span class="sxs-lookup"><span data-stu-id="cb4f4-105">With Cloud Connector version 2.0 and later, this cmdlet can also set the account information for the virtual machine administrator and for the domain administrator.</span></span>
  
```
Set-CcCredential [[-AccountType] <string> {TenantAdmin}]
```

## <a name="examples"></a><span data-ttu-id="cb4f4-106">示例</span><span class="sxs-lookup"><span data-stu-id="cb4f4-106">Examples</span></span>
<span data-ttu-id="cb4f4-107"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="cb4f4-107"></span></span>

### <a name="example-1"></a><span data-ttu-id="cb4f4-108">示例 1</span><span class="sxs-lookup"><span data-stu-id="cb4f4-108">Example 1</span></span>

<span data-ttu-id="cb4f4-109">以下示例为租户管理员指定帐户名称和密码：</span><span class="sxs-lookup"><span data-stu-id="cb4f4-109">The following example specifies the account name and password for the tenant administrator:</span></span>
  
```
Set-CcCredential -AccountType "TenantAdmin"
```

## <a name="detailed-description"></a><span data-ttu-id="cb4f4-110">详细说明</span><span class="sxs-lookup"><span data-stu-id="cb4f4-110">Detailed Description</span></span>
<span data-ttu-id="cb4f4-111"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="cb4f4-111"></span></span>

<span data-ttu-id="cb4f4-112">Set-CcCredential cmdlet 用于为租户管理员设置帐户名称和密码。</span><span class="sxs-lookup"><span data-stu-id="cb4f4-112">The Set-CcCredential cmdlet sets the account name and password for the tenant administrator.</span></span> <span data-ttu-id="cb4f4-113">在 2.0 之前的版本中，该管理员必须 Office 365 全局管理员。</span><span class="sxs-lookup"><span data-stu-id="cb4f4-113">For releases prior to 2.0, this administrator must be an Office 365 Global Administrator.</span></span> <span data-ttu-id="cb4f4-114">云连接器使用此帐户设置为 Office 365 租户配置的配置参数，并更新设备状态，获取配置信息。</span><span class="sxs-lookup"><span data-stu-id="cb4f4-114">Cloud Connector uses this account to get configuration information, set configuration parameters, and update appliance status to the Office 365 tenant configuration.</span></span> <span data-ttu-id="cb4f4-115">与版本 2.0 和更高版本，您还可以使用此 cmdlet 更新的 VmAdmin 和 DomainAdmin 帐户的密码。</span><span class="sxs-lookup"><span data-stu-id="cb4f4-115">With release 2.0 and later, you can also use this cmdlet to update the passwords for the VmAdmin and DomainAdmin accounts.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="cb4f4-116">参数</span><span class="sxs-lookup"><span data-stu-id="cb4f4-116">Parameters</span></span>
<span data-ttu-id="cb4f4-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="cb4f4-117"></span></span>

|<span data-ttu-id="cb4f4-118">**参数**</span><span class="sxs-lookup"><span data-stu-id="cb4f4-118">**Parameter**</span></span>|<span data-ttu-id="cb4f4-119">**必填**</span><span class="sxs-lookup"><span data-stu-id="cb4f4-119">**Required**</span></span>|<span data-ttu-id="cb4f4-120">**类型**</span><span class="sxs-lookup"><span data-stu-id="cb4f4-120">**Type**</span></span>|<span data-ttu-id="cb4f4-121">**说明**</span><span class="sxs-lookup"><span data-stu-id="cb4f4-121">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="cb4f4-122">AccountType</span><span class="sxs-lookup"><span data-stu-id="cb4f4-122">AccountType</span></span> <br/> | <span data-ttu-id="cb4f4-123">必需</span><span class="sxs-lookup"><span data-stu-id="cb4f4-123">Required</span></span> <br/> |<span data-ttu-id="cb4f4-124">System.String</span><span class="sxs-lookup"><span data-stu-id="cb4f4-124">System.String</span></span>  <br/> | <span data-ttu-id="cb4f4-125">参数值必须为“TenantAdmin”、“VmAdmin”或“DomainAdmin”。</span><span class="sxs-lookup"><span data-stu-id="cb4f4-125">Parameter value must be "TenantAdmin", "VmAdmin", or "DomainAdmin".</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="cb4f4-126">输入类型</span><span class="sxs-lookup"><span data-stu-id="cb4f4-126">Input Types</span></span>
<span data-ttu-id="cb4f4-127"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="cb4f4-127"></span></span>

<span data-ttu-id="cb4f4-p102">无。Set-CcCredential cmdlet 不接受主线输入。</span><span class="sxs-lookup"><span data-stu-id="cb4f4-p102">None. The Set-CcCredential cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="cb4f4-130">返回类型</span><span class="sxs-lookup"><span data-stu-id="cb4f4-130">Return Types</span></span>
<span data-ttu-id="cb4f4-131"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="cb4f4-131"></span></span>

<span data-ttu-id="cb4f4-132">无</span><span class="sxs-lookup"><span data-stu-id="cb4f4-132">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="cb4f4-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cb4f4-133">See also</span></span>
<span data-ttu-id="cb4f4-134"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="cb4f4-134"></span></span>

[<span data-ttu-id="cb4f4-135">获得 CcCredential</span><span class="sxs-lookup"><span data-stu-id="cb4f4-135">Get-CcCredential</span></span>](get-cccredential.md)
  

