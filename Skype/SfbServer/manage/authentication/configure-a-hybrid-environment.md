---
title: 为 Skype for business Server 混合环境配置服务器到服务器身份验证
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 700639ec-5264-4449-a8a6-d7386fad8719
description: 摘要：为 Skype for business Server 混合环境配置服务器到服务器身份验证。
ms.openlocfilehash: 5d56f098589355b85f942a6b1eb80d8ab6c03225
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992349"
---
# <a name="configure-server-to-server-authentication-for-a-skype-for-business-server-hybrid-environment"></a><span data-ttu-id="7606f-103">为 Skype for business Server 混合环境配置服务器到服务器身份验证。</span><span class="sxs-lookup"><span data-stu-id="7606f-103">Configure server-to-server authentication for a Skype for Business Server hybrid environment.</span></span>

<span data-ttu-id="7606f-104">**摘要：** 为 Skype for business Server 混合环境配置服务器到服务器身份验证。</span><span class="sxs-lookup"><span data-stu-id="7606f-104">**Summary:** Configure server-to-server authentication for Skype for Business Server hybrid environment.</span></span>

<span data-ttu-id="7606f-105">在混合配置中，你的某些用户驻留在本地安装 Skype for Business 服务器，而其他用户托管在 Office 365 版本的 Skype for Business 服务器上。</span><span class="sxs-lookup"><span data-stu-id="7606f-105">In a hybrid configuration, some of your users are homed on an on-premises installation of Skype for Business Server while other users are homed on the Office 365 version of Skype for Business Server.</span></span> <span data-ttu-id="7606f-106">为了在混合环境中配置服务器到服务器的身份验证，必须首先配置 Skype for Business 服务器的本地安装，以信任 Office 365 授权服务器。</span><span class="sxs-lookup"><span data-stu-id="7606f-106">In order to configure server-to-server authentication in a hybrid environment, you must first configure your on-premises installation of Skype for Business Server to trust the Office 365 authorization server.</span></span> <span data-ttu-id="7606f-107">通过运行以下 Skype for Business Server Management Shell 脚本，可以执行此过程中的初始步骤：</span><span class="sxs-lookup"><span data-stu-id="7606f-107">The initial step in this process can be carried out by running the following Skype for Business Server Management Shell script:</span></span>

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

<span data-ttu-id="7606f-p102">请记住，租户的领域名称通常与组织名称不同；实际上，领域名称几乎始终与租户 ID 相同。为此，脚本中的第一行用于返回指定租户（此示例中为 fabrikam.com）的 TenantId 属性的值，然后将该名称分配给变量 $TenantId：</span><span class="sxs-lookup"><span data-stu-id="7606f-p102">Keep in mind that the realm name for a tenant is typically different than the organization name; in fact, the realm name is almost always the same as the tenant ID. Because of that, the first line in the script is used to return the value of the TenantId property for the specified tenant (in this case, fabrikam.com) and then assign that name to the variable $TenantId:</span></span>

```PowerShell
$TenantID = (Get-CsTenant -Filter {DisplayName -eq "Fabrikam.com"}).TenantId
```

<span data-ttu-id="7606f-110">若要执行此脚本，你必须已安装 Skype for Business Online PowerShell 模块并使用此模块连接到你的租户。</span><span class="sxs-lookup"><span data-stu-id="7606f-110">To execute this script, you must have installed Skype for Business Online PowerShell module and connect to your tenant with this module.</span></span> <span data-ttu-id="7606f-111">如果您未安装这些 cmdlet，您的脚本将失败，因为 Get-CsTenant cmdlet 不可用。</span><span class="sxs-lookup"><span data-stu-id="7606f-111">If you have not installed these cmdlets your script will fail because the Get-CsTenant cmdlet will not be available.</span></span> <span data-ttu-id="7606f-112">脚本完成后，必须配置 Skype for Business 服务器与授权服务器之间的信任关系，以及 Exchange 2013/2016 和授权服务器之间的第二个信任关系。</span><span class="sxs-lookup"><span data-stu-id="7606f-112">After the script completes, you must then configure a trust relationship between Skype for Business Server and the authorization server, and a second trust relationship between Exchange 2013/2016 and the authorization server.</span></span> <span data-ttu-id="7606f-113">这只能使用 Microsoft Online Services cmdlet 来完成。</span><span class="sxs-lookup"><span data-stu-id="7606f-113">This can only be done by using the Microsoft Online Services cmdlets.</span></span>

> [!NOTE]
> <span data-ttu-id="7606f-114">如果尚未安装 Microsoft Online Services cmdlet，你将需要使用 cmdlet `install-module MSOnline`从 PowerShell 存储库中安装它。</span><span class="sxs-lookup"><span data-stu-id="7606f-114">If you have not installed the Microsoft Online Services cmdlets, you will need to install it from the PowerShell repository with the cmdlet `install-module MSOnline`.</span></span> <span data-ttu-id="7606f-115">可在 Office 365 网站上找到有关安装和使用 Microsoft Online Services 模块的详细信息。</span><span class="sxs-lookup"><span data-stu-id="7606f-115">Detailed information for installing and using the Microsoft Online Services Module can be found on the Office 365 web site.</span></span> <span data-ttu-id="7606f-116">这些说明还将告诉你如何在 Office 365 和 Active Directory 之间配置单一登录、联盟和同步。</span><span class="sxs-lookup"><span data-stu-id="7606f-116">These instructions will also tell you how to configure single sign-on, federation, and synchronization between Office 365 and Active Directory.</span></span> 



<span data-ttu-id="7606f-117">配置 Office 365 后，在为 Skype for business Server 和 Exchange 2013 创建 Office 365 服务主体之后，你将需要向这些服务主体注册你的凭据。</span><span class="sxs-lookup"><span data-stu-id="7606f-117">After you have configured Office 365, and after you have created Office 365 service principals for Skype for Business Server and Exchange 2013, you will then need to register your credentials with these service principals.</span></span> <span data-ttu-id="7606f-118">为此，必须首先获取一个 x.509 Base64 证书，另存为。CER 文件。</span><span class="sxs-lookup"><span data-stu-id="7606f-118">In order to do this, you must first obtain an X.509 Base64 certificate saved as a .CER file.</span></span> <span data-ttu-id="7606f-119">此证书将应用于 Office 365 服务主体。</span><span class="sxs-lookup"><span data-stu-id="7606f-119">This certificate will then be applied to the Office 365 service principals.</span></span>

<span data-ttu-id="7606f-120">获取 x.509 证书后，打开 PowerShell 控制台并导入包含可用于管理服务主体的 cmdlet 的 Microsoft Online Windows PowerShell 模块：</span><span class="sxs-lookup"><span data-stu-id="7606f-120">When you have obtained the X.509 certificate, open PowerShell console and import the Microsoft Online Windows PowerShell module containing the cmdlets that can be used to manage service principals:</span></span>

```PowerShell
Import-Module MSOnline
```

<span data-ttu-id="7606f-121">导入模块后，键入以下命令，然后按 ENTER 以连接到 Office 365：</span><span class="sxs-lookup"><span data-stu-id="7606f-121">When the module has been imported, type the following command and then press ENTER in order to connect to Office 365:</span></span>

```PowerShell
Connect-MsolService
```

<span data-ttu-id="7606f-122">按 Enter 后，随即出现一个凭据对话框。</span><span class="sxs-lookup"><span data-stu-id="7606f-122">After you press ENTER, a credentials dialog box will appear.</span></span> <span data-ttu-id="7606f-123">在对话框中输入 Office 365 的用户名和密码，然后单击 "确定"。</span><span class="sxs-lookup"><span data-stu-id="7606f-123">Enter your Office 365 user name and password in the dialog box, and then click OK.</span></span>

<span data-ttu-id="7606f-124">连接到 Office 365 后，你可以立即运行以下命令以返回有关你的服务主体的信息：</span><span class="sxs-lookup"><span data-stu-id="7606f-124">As soon as you are connected to Office 365, you can then run the following command in order to return information about your service principals:</span></span>

```PowerShell
Get-MsolServicePrincipal
```

<span data-ttu-id="7606f-125">您应获得与以下信息类似的所有服务主体的相关信息：</span><span class="sxs-lookup"><span data-stu-id="7606f-125">You should get back information similar to this for all your service principals:</span></span>

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

<span data-ttu-id="7606f-126">下一步是导入、编码和分配 X.509 证书。</span><span class="sxs-lookup"><span data-stu-id="7606f-126">The next step is to import, encode, and assign the X.509 certificate.</span></span> <span data-ttu-id="7606f-127">若要导入和编码证书，请使用以下 Windows PowerShell 命令，确保为你指定完整的文件路径。在调用 Import 方法时的 CER 文件：</span><span class="sxs-lookup"><span data-stu-id="7606f-127">To import and encode the certificate, use the following Windows PowerShell commands, being sure to specify the complete file path to your .CER file when you call the Import method:</span></span>

```PowerShell
$certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
$certificate.Import("C:\Certificates\Office365.cer")
$binaryValue = $certificate.GetRawCertData()
$credentialsValue = [System.Convert]::ToBase64String($binaryValue)
```

<span data-ttu-id="7606f-128">在证书导入和编码后，你可以将证书分配给你的 Office 365 服务主体。</span><span class="sxs-lookup"><span data-stu-id="7606f-128">After the certificate has been imported and encoded, you can then assign the certificate to your Office 365 service principals.</span></span> <span data-ttu-id="7606f-129">若要执行此操作，请首先使用 MsolServicePrincipal 检索 Skype for business 服务器和 Microsoft Exchange 服务主体的 AppPrincipalId 属性的值;AppPrincipalId 属性的值将用于标识分配了证书的服务主体。</span><span class="sxs-lookup"><span data-stu-id="7606f-129">To do that, first use the Get-MsolServicePrincipal to retrieve the value of the AppPrincipalId property for both the Skype for Business Server and the Microsoft Exchange service principals; the value of the AppPrincipalId property will be used to identify the service principal being assigned the certificate.</span></span> <span data-ttu-id="7606f-130">使用 Skype for business 服务器的 AppPrincipalId 属性值，使用以下命令将证书分配到 Skype For business Online 版本：</span><span class="sxs-lookup"><span data-stu-id="7606f-130">With the AppPrincipalId property value for Skype for Business Server in hand, use the following command to assign the certificate to Skype For Business Online version:</span></span>

```PowerShell
New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue 
```

<span data-ttu-id="7606f-131">然后，你应该使用 Exchange 2013 的 AppPrincipalId 属性值，重复该命令。</span><span class="sxs-lookup"><span data-stu-id="7606f-131">You should then repeat the command, this time using the AppPrincipalId property value for Exchange 2013.</span></span>

<span data-ttu-id="7606f-132">如果您以后需要删除该证书（例如，它已过期），您可以通过首先检索证书的 KeyId 来执行此操作：</span><span class="sxs-lookup"><span data-stu-id="7606f-132">If you later need to delete that certificate, for example if it has expired, you can do so by first retrieving the KeyId for the certificate:</span></span>

```PowerShell
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="7606f-133">此命令将返回与以下内容类似的数据：</span><span class="sxs-lookup"><span data-stu-id="7606f-133">That command will return data like this one:</span></span>

<pre>
Type      : Asymmetric
Value     : 
KeyId     : bc2795f3-2387-4543-a95d-f92c85c7a1b0
StartDate : 6/1/2012 8:00:00 AM
EndDate   : 5/31/2013 8:00:00 AM
Usage     : Verify
</pre>

<span data-ttu-id="7606f-134">然后，您可以使用与以下内容类似的命令删除该证书：</span><span class="sxs-lookup"><span data-stu-id="7606f-134">You can then delete the certificate by using a command similar to this:</span></span>

```PowerShell
Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0
```

<span data-ttu-id="7606f-135">除了分配证书之外，还必须配置 Exchange Online 服务主体，并将本地版本的 Skype for Business 服务器外部 Web 服务 Url 配置为 Office 365 服务主体。</span><span class="sxs-lookup"><span data-stu-id="7606f-135">In addition to assigning a certificate, you must also configure the Exchange Online Service Principal and configure your on-premises version of Skype for Business Server external Web services URLs as an Office 365 service principal.</span></span> <span data-ttu-id="7606f-136">可通过执行下面两条命令达到此目的。</span><span class="sxs-lookup"><span data-stu-id="7606f-136">That can be done by carrying out the following two commands.</span></span> 

<span data-ttu-id="7606f-137">在以下示例中，Pool1ExternalWebFQDN.contoso.com 是 Skype for business 服务器池的外部 Web 服务 URL。</span><span class="sxs-lookup"><span data-stu-id="7606f-137">In the following example, Pool1ExternalWebFQDN.contoso.com is the external Web services URL for the Skype for Business Server pool.</span></span> <span data-ttu-id="7606f-138">应重复这些步骤来添加部署中的所有外部 Web 服务 Url。</span><span class="sxs-lookup"><span data-stu-id="7606f-138">You should repeat these steps to add all the external Web services URLs in the deployment.</span></span>

```PowerShell
Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
$lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
$lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/Pool1ExternalWebFQDN.contoso.com")
Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames
```
