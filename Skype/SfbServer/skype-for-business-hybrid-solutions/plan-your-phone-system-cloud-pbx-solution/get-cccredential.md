---
title: Get-CcCredential
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b2b5aefb-a08d-4bec-9204-76597d413849
description: Get-CcCredential cmdlet 用于返回当前 Skype for Business 云连接器版本部署的凭据。
ms.openlocfilehash: 651190f31ad44e0bb2375bbf4a70951c2011e1a7
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30898393"
---
# <a name="get-cccredential"></a><span data-ttu-id="52d37-103">Get-CcCredential</span><span class="sxs-lookup"><span data-stu-id="52d37-103">Get-CcCredential</span></span>
 
<span data-ttu-id="52d37-104">Get-CcCredential cmdlet 用于返回当前 Skype for Business 云连接器版本部署的凭据。</span><span class="sxs-lookup"><span data-stu-id="52d37-104">The Get-CcCredential cmdlet returns the credential of the current Skype for Business Cloud Connector Edition deployment.</span></span> 
  
<span data-ttu-id="52d37-105">使用版本 2.0 及更高版本，您还可以使用-DisplayPassword 参数 TenantAdmin、 DomainAdmin，和 VMAdmin 显示相应的密码。</span><span class="sxs-lookup"><span data-stu-id="52d37-105">With Version 2.0 and later, you can also use the -DisplayPassword parameter to show the passwords for TenantAdmin, DomainAdmin, and VMAdmin.</span></span>
  
```
Get-CcCredential [[-AccountType] <string> {VmAdmin | DomainAdmin | SafeModeAdmin | ExternalCert | TenantAdmin}]
```

## <a name="examples"></a><span data-ttu-id="52d37-106">示例</span><span class="sxs-lookup"><span data-stu-id="52d37-106">Examples</span></span>
<span data-ttu-id="52d37-107"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="52d37-107"></span></span>

### <a name="example-1"></a><span data-ttu-id="52d37-108">示例 1</span><span class="sxs-lookup"><span data-stu-id="52d37-108">Example 1</span></span>

<span data-ttu-id="52d37-109">以下示例返回云连接器虚拟机域的域管理员凭据：</span><span class="sxs-lookup"><span data-stu-id="52d37-109">The following example returns the credential of the domain administrator of the Cloud Connector virtual machine domain:</span></span>
  
```
Get-CcCredential -AccountType DomainAdmin
```

## <a name="detailed-description"></a><span data-ttu-id="52d37-110">详细说明</span><span class="sxs-lookup"><span data-stu-id="52d37-110">Detailed Description</span></span>
<span data-ttu-id="52d37-111"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="52d37-111"></span></span>

<span data-ttu-id="52d37-p101">Get-CcCredential cmdlet 用于返回有关指定帐户类型的凭据信息。这些凭据由部署当前设备时运行 Register-CcAppliance 和 Install-CcAppliance cmdlet 的管理员指定。</span><span class="sxs-lookup"><span data-stu-id="52d37-p101">The Get-CcCredential cmdlet returns the credential information about the specified account type. These credentials are specified by the administrator who runs the Register-CcAppliance and Install-CcAppliance cmdlets when deploying the current appliance.</span></span> 
  
<span data-ttu-id="52d37-p102">Get-CcCredential cmdlet 返回 System.Management.Automation.PSCredential 对象的实例。返回对象的密码属性是 System.Security.SecureString。</span><span class="sxs-lookup"><span data-stu-id="52d37-p102">The Get-CcCredential cmdlet returns an instance of the System.Management.Automation.PSCredential object. The password property of the return object is System.Security.SecureString.</span></span>
  
<span data-ttu-id="52d37-116">如果你希望获得域管理员密码的明文，请确保密码由你的当前登录帐户在主机服务器上输入，然后以管理员身份打开 PowerShell 控制台并运行以下脚本：</span><span class="sxs-lookup"><span data-stu-id="52d37-116">If you want to get the clear text of the domain administrator password, be sure the password is input by your current logon account on the host server, and then open a PowerShell console as administrator and run the below script:</span></span>
  
```
$cred = Get-CcCredential -AccountType DomainAdmin
$password =  $cred.Password
$bstr = [System.Runtime.InteropServices.Marshal]::SecureStringToBSTR($password);
$text = [System.Runtime.InteropServices.Marshal]::PtrToStringAuto($bstr);
[System.Runtime.InteropServices.Marshal]::ZeroFreeBSTR($bstr);
Write-Host $text
```

## <a name="parameters"></a><span data-ttu-id="52d37-117">参数</span><span class="sxs-lookup"><span data-stu-id="52d37-117">Parameters</span></span>
<span data-ttu-id="52d37-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="52d37-118"></span></span>

|<span data-ttu-id="52d37-119">**参数**</span><span class="sxs-lookup"><span data-stu-id="52d37-119">**Parameter**</span></span>|<span data-ttu-id="52d37-120">**必需**</span><span class="sxs-lookup"><span data-stu-id="52d37-120">**Required**</span></span>|<span data-ttu-id="52d37-121">**类型**</span><span class="sxs-lookup"><span data-stu-id="52d37-121">**Type**</span></span>|<span data-ttu-id="52d37-122">**说明**</span><span class="sxs-lookup"><span data-stu-id="52d37-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="52d37-123">AccountType</span><span class="sxs-lookup"><span data-stu-id="52d37-123">AccountType</span></span> <br/> |<span data-ttu-id="52d37-124">必需</span><span class="sxs-lookup"><span data-stu-id="52d37-124">Required</span></span>  <br/> | <span data-ttu-id="52d37-125">System.String</span><span class="sxs-lookup"><span data-stu-id="52d37-125">System.String</span></span> <br/> | <span data-ttu-id="52d37-126">AccountType 值可以是以下项之一：</span><span class="sxs-lookup"><span data-stu-id="52d37-126">AccountType value can be one of the following:</span></span> <br/>  <span data-ttu-id="52d37-127">VmAdmin： 云连接器虚拟机的本地管理员。</span><span class="sxs-lookup"><span data-stu-id="52d37-127">VmAdmin: the local administrator of Cloud Connector virtual machines.</span></span> <br/>  <span data-ttu-id="52d37-128">DomainAdmin：云连接器虚拟机域的域管理员。</span><span class="sxs-lookup"><span data-stu-id="52d37-128">DomainAdmin: Domain administrator of Cloud Connector virtual machine domain.</span></span> <br/>  <span data-ttu-id="52d37-129">SafeModeAdmin：云连接器虚拟机域控制器的 SafeModeAdmin。</span><span class="sxs-lookup"><span data-stu-id="52d37-129">SafeModeAdmin: SafeModeAdmin of Cloud Connector virtual machine domain controller.</span></span> <br/>  <span data-ttu-id="52d37-130">ExternalCert：边缘服务器上安装的外部证书的帐户。</span><span class="sxs-lookup"><span data-stu-id="52d37-130">ExternalCert: Account of external certificate installed on the Edge Server.</span></span> <br/>  <span data-ttu-id="52d37-131">TenantAdmin：O365 租户的管理员。</span><span class="sxs-lookup"><span data-stu-id="52d37-131">TenantAdmin: Administrator of the O365 tenant.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="52d37-132">输入类型</span><span class="sxs-lookup"><span data-stu-id="52d37-132">Input Types</span></span>
<span data-ttu-id="52d37-133"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="52d37-133"></span></span>

<span data-ttu-id="52d37-p103">无。Get-CcCredential cmdlet 不接受主线输入。</span><span class="sxs-lookup"><span data-stu-id="52d37-p103">None. The Get-CcCredential cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="52d37-136">返回类型</span><span class="sxs-lookup"><span data-stu-id="52d37-136">Return Types</span></span>
<span data-ttu-id="52d37-137"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="52d37-137"></span></span>

<span data-ttu-id="52d37-138">Get-CcCredential cmdlet 返回 System.Management.Automation.PSCredential 对象的实例。</span><span class="sxs-lookup"><span data-stu-id="52d37-138">The Get-CcCredential cmdlet returns an instance of the System.Management.Automation.PSCredential object.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="52d37-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="52d37-139">See also</span></span>
<span data-ttu-id="52d37-140"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="52d37-140"></span></span>

[<span data-ttu-id="52d37-141">Set-CcCredential</span><span class="sxs-lookup"><span data-stu-id="52d37-141">Set-CcCredential</span></span>](set-cccredential.md)
  

