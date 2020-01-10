---
title: Set-CcCredential
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 784ff94a-4b33-4dbd-ba74-27acc3eb6954
description: Set-CcCredential cmdlet 用于设置当前 Skype for Business 云连接器版本部署的凭据。
ms.openlocfilehash: bcb88f11fb78d995e6d8271593c2e09bb0b11d22
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003212"
---
# <a name="set-cccredential"></a><span data-ttu-id="97811-103">Set-CcCredential</span><span class="sxs-lookup"><span data-stu-id="97811-103">Set-CcCredential</span></span>
 
<span data-ttu-id="97811-104">Set-CcCredential cmdlet 用于设置当前 Skype for Business 云连接器版本部署的凭据。</span><span class="sxs-lookup"><span data-stu-id="97811-104">The Set-CcCredential cmdlet sets the credential of the current Skype for Business Cloud Connector Edition deployment.</span></span> 
  
<span data-ttu-id="97811-105">借助云连接器版本2.0 和更高版本，此 cmdlet 还可以为虚拟机管理员和域管理员设置帐户信息。</span><span class="sxs-lookup"><span data-stu-id="97811-105">With Cloud Connector version 2.0 and later, this cmdlet can also set the account information for the virtual machine administrator and for the domain administrator.</span></span>
  
```powershell
Set-CcCredential [[-AccountType] <string> {TenantAdmin}]
```

## <a name="examples"></a><span data-ttu-id="97811-106">示例</span><span class="sxs-lookup"><span data-stu-id="97811-106">Examples</span></span>
<span data-ttu-id="97811-107"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="97811-107"></span></span>

### <a name="example-1"></a><span data-ttu-id="97811-108">示例 1</span><span class="sxs-lookup"><span data-stu-id="97811-108">Example 1</span></span>

<span data-ttu-id="97811-109">以下示例为租户管理员指定帐户名称和密码：</span><span class="sxs-lookup"><span data-stu-id="97811-109">The following example specifies the account name and password for the tenant administrator:</span></span>
  
```powershell
Set-CcCredential -AccountType "TenantAdmin"
```

## <a name="detailed-description"></a><span data-ttu-id="97811-110">详细说明</span><span class="sxs-lookup"><span data-stu-id="97811-110">Detailed Description</span></span>
<span data-ttu-id="97811-111"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="97811-111"></span></span>

<span data-ttu-id="97811-112">Set-CcCredential cmdlet 用于为租户管理员设置帐户名称和密码。</span><span class="sxs-lookup"><span data-stu-id="97811-112">The Set-CcCredential cmdlet sets the account name and password for the tenant administrator.</span></span> <span data-ttu-id="97811-113">对于 2.0 版之前的版本，此管理员必须为 Office 365 全局管理员。</span><span class="sxs-lookup"><span data-stu-id="97811-113">For releases prior to 2.0, this administrator must be an Office 365 Global Administrator.</span></span> <span data-ttu-id="97811-114">云连接器使用此帐户获取配置信息、设置配置参数，并将装置状态更新到 Office 365 租户配置。</span><span class="sxs-lookup"><span data-stu-id="97811-114">Cloud Connector uses this account to get configuration information, set configuration parameters, and update appliance status to the Office 365 tenant configuration.</span></span> <span data-ttu-id="97811-115">使用版本2.0 和更高版本，你也可以使用此 cmdlet 更新 VmAdmin 和 DomainAdmin 帐户的密码。</span><span class="sxs-lookup"><span data-stu-id="97811-115">With release 2.0 and later, you can also use this cmdlet to update the passwords for the VmAdmin and DomainAdmin accounts.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="97811-116">参数</span><span class="sxs-lookup"><span data-stu-id="97811-116">Parameters</span></span>
<span data-ttu-id="97811-117"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="97811-117"></span></span>

|<span data-ttu-id="97811-118">**参数**</span><span class="sxs-lookup"><span data-stu-id="97811-118">**Parameter**</span></span>|<span data-ttu-id="97811-119">**必需**</span><span class="sxs-lookup"><span data-stu-id="97811-119">**Required**</span></span>|<span data-ttu-id="97811-120">**类型**</span><span class="sxs-lookup"><span data-stu-id="97811-120">**Type**</span></span>|<span data-ttu-id="97811-121">**说明**</span><span class="sxs-lookup"><span data-stu-id="97811-121">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="97811-122">AccountType</span><span class="sxs-lookup"><span data-stu-id="97811-122">AccountType</span></span> <br/> | <span data-ttu-id="97811-123">必需</span><span class="sxs-lookup"><span data-stu-id="97811-123">Required</span></span> <br/> |<span data-ttu-id="97811-124">System.String</span><span class="sxs-lookup"><span data-stu-id="97811-124">System.String</span></span>  <br/> | <span data-ttu-id="97811-125">参数值必须为“TenantAdmin”、“VmAdmin”或“DomainAdmin”。</span><span class="sxs-lookup"><span data-stu-id="97811-125">Parameter value must be "TenantAdmin", "VmAdmin", or "DomainAdmin".</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="97811-126">输入类型</span><span class="sxs-lookup"><span data-stu-id="97811-126">Input Types</span></span>
<span data-ttu-id="97811-127"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="97811-127"></span></span>

<span data-ttu-id="97811-p102">无。Set-CcCredential cmdlet 不接受主线输入。</span><span class="sxs-lookup"><span data-stu-id="97811-p102">None. The Set-CcCredential cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="97811-130">返回类型</span><span class="sxs-lookup"><span data-stu-id="97811-130">Return Types</span></span>
<span data-ttu-id="97811-131"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="97811-131"></span></span>

<span data-ttu-id="97811-132">无</span><span class="sxs-lookup"><span data-stu-id="97811-132">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="97811-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="97811-133">See also</span></span>
<span data-ttu-id="97811-134"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="97811-134"></span></span>

[<span data-ttu-id="97811-135">Get-CcCredential</span><span class="sxs-lookup"><span data-stu-id="97811-135">Get-CcCredential</span></span>](get-cccredential.md)
  

