---
title: 为 Skype for business Server 混合环境配置服务器到服务器身份验证
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 700639ec-5264-4449-a8a6-d7386fad8719
description: 摘要：为 Skype for business Server 混合环境配置服务器到服务器身份验证。
ms.openlocfilehash: 6cc408677af4629d36b577da4ae38cd420195483
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221676"
---
# <a name="configure-server-to-server-authentication-for-a-skype-for-business-server-hybrid-environment"></a><span data-ttu-id="3ab78-103">为 Skype for business Server 混合环境配置服务器到服务器身份验证。</span><span class="sxs-lookup"><span data-stu-id="3ab78-103">Configure server-to-server authentication for a Skype for Business Server hybrid environment.</span></span>

<span data-ttu-id="3ab78-104">**摘要：** 为 Skype for business Server 混合环境配置服务器到服务器身份验证。</span><span class="sxs-lookup"><span data-stu-id="3ab78-104">**Summary:** Configure server-to-server authentication for Skype for Business Server hybrid environment.</span></span>

<span data-ttu-id="3ab78-105">在混合配置中，您的一些用户驻留在 Skype for business Server 的本地安装中，而其他用户托管在 Microsoft 365 或 Office 365 版本的 Skype for business Server 中。</span><span class="sxs-lookup"><span data-stu-id="3ab78-105">In a hybrid configuration, some of your users are homed on an on-premises installation of Skype for Business Server while other users are homed on the Microsoft 365 or Office 365 version of Skype for Business Server.</span></span> <span data-ttu-id="3ab78-106">若要在混合环境中配置服务器到服务器身份验证，必须首先将 Skype for Business 服务器的本地安装配置为信任授权服务器。</span><span class="sxs-lookup"><span data-stu-id="3ab78-106">In order to configure server-to-server authentication in a hybrid environment, you must first configure your on-premises installation of Skype for Business Server to trust the authorization server.</span></span> <span data-ttu-id="3ab78-107">此过程的初始步骤可通过运行以下 Skype for Business Server 命令行管理程序脚本执行：</span><span class="sxs-lookup"><span data-stu-id="3ab78-107">The initial step in this process can be carried out by running the following Skype for Business Server Management Shell script:</span></span>

```PowerShell
$TenantID = (Get-CsTenant -Filter {DisplayName -eq "Fabrikam.com"}).TenantId

$sts = Get-CsOAuthServer microsoft.sts -ErrorAction SilentlyContinue

   if ($sts -eq $null)
      {
         New-CsOAuthServer microsoft.sts -MetadataUrl "https://accounts.accesscontrol.windows.net/$TenantId/metadata/json/1"
      }
   else
      {
         if ($sts.MetadataUrl -ne  "https://accounts.accesscontrol.windows.net/$TenantId/metadata/json/1")
            {
               Remove-CsOAuthServer microsoft.sts
               New-CsOAuthServer microsoft.sts -MetadataUrl "https://accounts.accesscontrol.windows.net/$TenantId/metadata/json/1"
            }
        }

$exch = Get-CsPartnerApplication microsoft.exchange -ErrorAction SilentlyContinue

if ($exch -eq $null)
   {
      New-CsPartnerApplication -Identity microsoft.exchange -ApplicationIdentifier 00000002-0000-0ff1-ce00-000000000000 -ApplicationTrustLevel Full -UseOAuthServer
    }
else
    {
       if ($exch.ApplicationIdentifier -ne "00000002-0000-0ff1-ce00-000000000000")
          {
             Remove-CsPartnerApplication microsoft.exchange
             New-CsPartnerApplication -Identity microsoft.exchange -ApplicationIdentifier 00000002-0000-0ff1-ce00-000000000000 -ApplicationTrustLevel Full -UseOAuthServer 
          }
       else
          {
             Set-CsPartnerApplication -Identity microsoft.exchange -ApplicationTrustLevel Full -UseOAuthServer
          }
   }

Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="3ab78-p102">请记住，租户的领域名称通常与组织名称不同；实际上，领域名称几乎始终与租户 ID 相同。为此，脚本中的第一行用于返回指定租户（此示例中为 fabrikam.com）的 TenantId 属性的值，然后将该名称分配给变量 $TenantId：</span><span class="sxs-lookup"><span data-stu-id="3ab78-p102">Keep in mind that the realm name for a tenant is typically different than the organization name; in fact, the realm name is almost always the same as the tenant ID. Because of that, the first line in the script is used to return the value of the TenantId property for the specified tenant (in this case, fabrikam.com) and then assign that name to the variable $TenantId:</span></span>

```PowerShell
$TenantID = (Get-CsTenant -Filter {DisplayName -eq "Fabrikam.com"}).TenantId
```

<span data-ttu-id="3ab78-110">若要执行此脚本，您必须已安装 Skype for Business Online PowerShell 模块，并使用此模块连接到你的租户。</span><span class="sxs-lookup"><span data-stu-id="3ab78-110">To execute this script, you must have installed Skype for Business Online PowerShell module and connect to your tenant with this module.</span></span> <span data-ttu-id="3ab78-111">如果尚未安装这些 cmdlet，则脚本将失败，因为 Get-cstenant cmdlet 将不可用。</span><span class="sxs-lookup"><span data-stu-id="3ab78-111">If you have not installed these cmdlets your script will fail because the Get-CsTenant cmdlet will not be available.</span></span> <span data-ttu-id="3ab78-112">脚本完成后，您必须配置 Skype for Business Server 和授权服务器之间的信任关系，以及 Exchange 2013/2016 与授权服务器之间的第二个信任关系。</span><span class="sxs-lookup"><span data-stu-id="3ab78-112">After the script completes, you must then configure a trust relationship between Skype for Business Server and the authorization server, and a second trust relationship between Exchange 2013/2016 and the authorization server.</span></span> <span data-ttu-id="3ab78-113">只能通过 Microsoft Online Services cmdlet 做到这一点。</span><span class="sxs-lookup"><span data-stu-id="3ab78-113">This can only be done by using the Microsoft Online Services cmdlets.</span></span>

> [!NOTE]
> <span data-ttu-id="3ab78-114">如果尚未安装 Microsoft Online Services cmdlet，则需要使用 cmdlet 从 PowerShell 存储库中安装它 `install-module MSOnline` 。</span><span class="sxs-lookup"><span data-stu-id="3ab78-114">If you have not installed the Microsoft Online Services cmdlets, you will need to install it from the PowerShell repository with the cmdlet `install-module MSOnline`.</span></span> <span data-ttu-id="3ab78-115">可在 Microsoft 365 网站上找到有关安装和使用 Microsoft Online Services 模块的详细信息。</span><span class="sxs-lookup"><span data-stu-id="3ab78-115">Detailed information for installing and using the Microsoft Online Services Module can be found on the Microsoft 365 web site.</span></span> <span data-ttu-id="3ab78-116">这些说明还将告诉你如何在 Microsoft 365 或 Office 365 与 Active Directory 之间配置单一登录、联合和同步。</span><span class="sxs-lookup"><span data-stu-id="3ab78-116">These instructions will also tell you how to configure single sign-on, federation, and synchronization between Microsoft 365 or Office 365 and Active Directory.</span></span> 



<span data-ttu-id="3ab78-117">在配置了 Microsoft 365 或 Office 365 之后，以及在为 Skype for Business Server 和 Exchange 2013 创建 Microsoft 365 或 Office 365 服务主体之后，您将需要使用这些服务主体注册凭据。</span><span class="sxs-lookup"><span data-stu-id="3ab78-117">After you have configured Microsoft 365 or Office 365, and after you have created Microsoft 365 or Office 365 service principals for Skype for Business Server and Exchange 2013, you will then need to register your credentials with these service principals.</span></span> <span data-ttu-id="3ab78-118">若要执行此操作，必须首先获取一个 x.509 Base64 证书另存为。CER 文件。</span><span class="sxs-lookup"><span data-stu-id="3ab78-118">In order to do this, you must first obtain an X.509 Base64 certificate saved as a .CER file.</span></span> <span data-ttu-id="3ab78-119">此证书将应用于 Microsoft 365 或 Office 365 服务主体。</span><span class="sxs-lookup"><span data-stu-id="3ab78-119">This certificate will then be applied to the Microsoft 365 or Office 365 service principals.</span></span>

<span data-ttu-id="3ab78-120">获取 x.509 证书后，打开 PowerShell 控制台，然后导入 Microsoft Online Windows PowerShell 模块，其中包含可用于管理服务主体的 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="3ab78-120">When you have obtained the X.509 certificate, open PowerShell console and import the Microsoft Online Windows PowerShell module containing the cmdlets that can be used to manage service principals:</span></span>

```PowerShell
Import-Module MSOnline
```

<span data-ttu-id="3ab78-121">导入该模块后，键入以下命令，然后按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="3ab78-121">When the module has been imported, type the following command and then press ENTER:</span></span>

```PowerShell
Connect-MsolService
```

<span data-ttu-id="3ab78-122">按 Enter 后，随即出现一个凭据对话框。</span><span class="sxs-lookup"><span data-stu-id="3ab78-122">After you press ENTER, a credentials dialog box will appear.</span></span> <span data-ttu-id="3ab78-123">在对话框中输入 Microsoft 365 或 Office 365 用户名和密码，然后单击 "确定"。</span><span class="sxs-lookup"><span data-stu-id="3ab78-123">Enter your Microsoft 365 or Office 365 user name and password in the dialog box, and then click OK.</span></span>

<span data-ttu-id="3ab78-124">当您连接到 Microsoft 365 或 Office 365 之后，您就可以运行以下命令来返回有关您的服务主体的信息：</span><span class="sxs-lookup"><span data-stu-id="3ab78-124">As soon as you are connected to Microsoft 365 or Office 365, you can then run the following command in order to return information about your service principals:</span></span>

```PowerShell
Get-MsolServicePrincipal
```

<span data-ttu-id="3ab78-125">您应获得与以下信息类似的所有服务主体的相关信息：</span><span class="sxs-lookup"><span data-stu-id="3ab78-125">You should get back information similar to this for all your service principals:</span></span>

<pre>
ExtensionData        : System.Runtime.Serialization.ExtensionDataObject
AccountEnabled       : True
Addresses            : {}
AppPrincipalId       : 00000004-0000-0ff1-ce00-000000000000
DisplayName          : Skype for Business Server
ObjectId             : aada5fbd-c0ae-442a-8c0b-36fec40602e2
ServicePrincipalName : SkypeForBusinessServer/litwareinc.com
TrustedForDelegation : True
</pre>

<span data-ttu-id="3ab78-126">下一步是导入、编码和分配 X.509 证书。</span><span class="sxs-lookup"><span data-stu-id="3ab78-126">The next step is to import, encode, and assign the X.509 certificate.</span></span> <span data-ttu-id="3ab78-127">若要导入和编码证书，请使用以下 Windows PowerShell 命令，确保指定了的完整文件路径。CER 文件调用 Import 方法时：</span><span class="sxs-lookup"><span data-stu-id="3ab78-127">To import and encode the certificate, use the following Windows PowerShell commands, being sure to specify the complete file path to your .CER file when you call the Import method:</span></span>

```PowerShell
$certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
$certificate.Import("C:\Certificates\Office365.cer")
$binaryValue = $certificate.GetRawCertData()
$credentialsValue = [System.Convert]::ToBase64String($binaryValue) 
```

<span data-ttu-id="3ab78-128">在导入并编码证书后，您可以将证书分配给您的 Microsoft 365 或 Office 365 服务主体。</span><span class="sxs-lookup"><span data-stu-id="3ab78-128">After the certificate has been imported and encoded, you can then assign the certificate to your Microsoft 365 or Office 365 service principals.</span></span> <span data-ttu-id="3ab78-129">为此，请首先使用 New-msolserviceprincipal 检索 Skype for Business Server 和 Microsoft Exchange 服务主体的 AppPrincipalId 属性的值;AppPrincipalId 属性的值将用于标识为其分配证书的服务主体。</span><span class="sxs-lookup"><span data-stu-id="3ab78-129">To do that, first use the Get-MsolServicePrincipal to retrieve the value of the AppPrincipalId property for both the Skype for Business Server and the Microsoft Exchange service principals; the value of the AppPrincipalId property will be used to identify the service principal being assigned the certificate.</span></span> <span data-ttu-id="3ab78-130">使用适用于 Skype for business Server 的 AppPrincipalId 属性值，请使用以下命令将证书分配到 Skype For Business Online 版本：</span><span class="sxs-lookup"><span data-stu-id="3ab78-130">With the AppPrincipalId property value for Skype for Business Server in hand, use the following command to assign the certificate to Skype For Business Online version:</span></span>

```PowerShell
New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue 
```

<span data-ttu-id="3ab78-131">然后，您应该重复该命令，这次使用的是 Exchange 2013 的 AppPrincipalId 属性值。</span><span class="sxs-lookup"><span data-stu-id="3ab78-131">You should then repeat the command, this time using the AppPrincipalId property value for Exchange 2013.</span></span>

<span data-ttu-id="3ab78-132">如果您稍后需要删除该证书（例如，如果它已过期），您可以通过先检索证书的 KeyId 来执行此操作：</span><span class="sxs-lookup"><span data-stu-id="3ab78-132">If you later need to delete that certificate, for example if it has expired, you can do so by first retrieving the KeyId for the certificate:</span></span>

```PowerShell
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="3ab78-133">此命令将返回与以下内容类似的数据：</span><span class="sxs-lookup"><span data-stu-id="3ab78-133">That command will return data like this one:</span></span>

<pre>
Type      : Asymmetric
Value     : 
KeyId     : bc2795f3-2387-4543-a95d-f92c85c7a1b0
StartDate : 6/1/2012 8:00:00 AM
EndDate   : 5/31/2013 8:00:00 AM
Usage     : Verify
</pre>

<span data-ttu-id="3ab78-134">然后，您可以使用与以下内容类似的命令删除该证书：</span><span class="sxs-lookup"><span data-stu-id="3ab78-134">You can then delete the certificate by using a command similar to this:</span></span>

```PowerShell
Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0
```

<span data-ttu-id="3ab78-135">除了分配证书之外，还必须配置 Exchange Online 服务主体，并将本地版本的 Skype for Business Server 外部 Web 服务 Url 配置为 Microsoft 365 或 Office 365 服务主体。</span><span class="sxs-lookup"><span data-stu-id="3ab78-135">In addition to assigning a certificate, you must also configure the Exchange Online Service Principal and configure your on-premises version of Skype for Business Server external Web services URLs as a Microsoft 365 or Office 365 service principal.</span></span> <span data-ttu-id="3ab78-136">为此，可以执行以下两个命令。</span><span class="sxs-lookup"><span data-stu-id="3ab78-136">That can be done by carrying out the following two commands.</span></span> 

<span data-ttu-id="3ab78-137">在以下示例中，Pool1ExternalWebFQDN.contoso.com 是 Skype for Business Server 池的外部 Web 服务 URL。</span><span class="sxs-lookup"><span data-stu-id="3ab78-137">In the following example, Pool1ExternalWebFQDN.contoso.com is the external Web services URL for the Skype for Business Server pool.</span></span> <span data-ttu-id="3ab78-138">应重复这些步骤以添加部署中的所有外部 Web 服务 Url。</span><span class="sxs-lookup"><span data-stu-id="3ab78-138">You should repeat these steps to add all the external Web services URLs in the deployment.</span></span>

```PowerShell
Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
$lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
$lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/Pool1ExternalWebFQDN.contoso.com")
Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames
```
