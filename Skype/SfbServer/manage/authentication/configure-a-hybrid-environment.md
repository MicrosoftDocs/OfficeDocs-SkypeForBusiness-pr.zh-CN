---
title: 在 Skype for Business Server 2015 中配置混合环境
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 700639ec-5264-4449-a8a6-d7386fad8719
description: 摘要： 配置混合环境中业务服务器 2015 Skype。
ms.openlocfilehash: 4798839bd001e6320870d7ca97ba99108e3b32de
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2018
ms.locfileid: "19570183"
---
# <a name="configure-a-hybrid-environment-in-skype-for-business-server-2015"></a><span data-ttu-id="ab7b4-103">在 Skype for Business Server 2015 中配置混合环境</span><span class="sxs-lookup"><span data-stu-id="ab7b4-103">Configure a hybrid environment in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="ab7b4-104">**摘要：** 配置混合环境中的业务服务器 2015 Skype。</span><span class="sxs-lookup"><span data-stu-id="ab7b4-104">**Summary:** Configure Skype for Business Server 2015 in a hybrid environment.</span></span>
  
<span data-ttu-id="ab7b4-105">在混合配置中，某些用户驻留在本地安装的 Skype 的业务服务器 2015年时其他用户都驻留在 Office 365 版本的 Skype 业务服务器。</span><span class="sxs-lookup"><span data-stu-id="ab7b4-105">In a hybrid configuration, some of your users are homed on an on-premises installation of Skype for Business Server 2015 while other users are homed on the Office 365 version of Skype for Business Server.</span></span> <span data-ttu-id="ab7b4-106">要在混合环境中配置服务器到服务器身份验证，您必须首先配置业务服务器 2015 信任 Office 365 授权服务器的 Skype 您的本地的安装。</span><span class="sxs-lookup"><span data-stu-id="ab7b4-106">In order to configure server-to-server authentication in a hybrid environment, you must first configure your on-premises installation of Skype for Business Server 2015 to trust the Office 365 authorization server.</span></span> <span data-ttu-id="ab7b4-107">可以通过运行以下 Skype 业务 Server 命令行管理程序脚本来执行此过程中的初始步骤：</span><span class="sxs-lookup"><span data-stu-id="ab7b4-107">The initial step in this process can be carried out by running the following Skype for Business Server Management Shell script:</span></span>
  
```
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

<span data-ttu-id="ab7b4-p102">请记住，租户的领域名称通常与组织名称不同；实际上，领域名称几乎始终与租户 ID 相同。为此，脚本中的第一行用于返回指定租户（此示例中为 fabrikam.com）的 TenantId 属性的值，然后将该名称分配给变量 $TenantId：</span><span class="sxs-lookup"><span data-stu-id="ab7b4-p102">Keep in mind that the realm name for a tenant is typically different than the organization name; in fact, the realm name is almost always the same as the tenant ID. Because of that, the first line in the script is used to return the value of the TenantId property for the specified tenant (in this case, fabrikam.com) and then assign that name to the variable $TenantId:</span></span>
  
```
$TenantID = (Get-CsTenant -DisplayName "Fabrikam.com").TenantId
```

<span data-ttu-id="ab7b4-110">脚本完成后，然后必须配置的业务服务器 2015 Skype 和授权服务器之间的信任关系和 Exchange 2013 和授权服务器之间的第二个信任关系。</span><span class="sxs-lookup"><span data-stu-id="ab7b4-110">After the script completes, you must then configure a trust relationship between Skype for Business Server 2015 and the authorization server, and a second trust relationship between Exchange 2013 and the authorization server.</span></span> <span data-ttu-id="ab7b4-111">这只能使用 Microsoft Online Services cmdlet 来完成。</span><span class="sxs-lookup"><span data-stu-id="ab7b4-111">This can only be done by using the Microsoft Online Services cmdlets.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ab7b4-112">如果你尚未安装 Microsoft Online Services cmdlet，则你需要先完成两项操作，然后再继续。</span><span class="sxs-lookup"><span data-stu-id="ab7b4-112">If you have not installed the Microsoft Online Services cmdlets, you will need to do two things before proceeding.</span></span> <span data-ttu-id="ab7b4-113">首先，下载并安装 64 位版本的 Microsoft Online Services 登录助手。</span><span class="sxs-lookup"><span data-stu-id="ab7b4-113">First, download and install the 64-bit version of the Microsoft Online Services Sign-in Assistant.</span></span> <span data-ttu-id="ab7b4-114">安装完成后，下载并安装 Microsoft Online Services 模块用于 Windows PowerShell 的 64 位版本。</span><span class="sxs-lookup"><span data-stu-id="ab7b4-114">After installation is complete, download and install the 64-bit version of the Microsoft Online Services Module for Windows PowerShell.</span></span> <span data-ttu-id="ab7b4-115">Office 365 网站上可找到的安装和使用 Microsoft Online Services 模块的详细的信息。</span><span class="sxs-lookup"><span data-stu-id="ab7b4-115">Detailed information for installing and using the Microsoft Online Services Module can be found on the Office 365 web site.</span></span> <span data-ttu-id="ab7b4-116">这些说明将还告诉您如何配置单一登录、 联盟和 Office 365 和 Active Directory 之间的同步。</span><span class="sxs-lookup"><span data-stu-id="ab7b4-116">These instructions will also tell you how to configure single sign-on, federation, and synchronization between Office 365 and Active Directory.</span></span> 
  
<span data-ttu-id="ab7b4-117">如果您未安装这些 cmdlet，您的脚本将失败，因为 Get-CsTenant cmdlet 不可用。</span><span class="sxs-lookup"><span data-stu-id="ab7b4-117">If you have not installed these cmdlets your script will fail because the Get-CsTenant cmdlet will not be available.</span></span>
  
<span data-ttu-id="ab7b4-118">配置 Office 365 后和业务服务器 2015年和 Exchange 2013，都在服务主体的 Skype 创建 Office 365 后，您将需要使用这些服务主体注册您的凭据。</span><span class="sxs-lookup"><span data-stu-id="ab7b4-118">After you have configured Office 365, and after you have created Office 365 service principals for Skype for Business Server 2015 and Exchange 2013, you will then need to register your credentials with these service principals.</span></span> <span data-ttu-id="ab7b4-119">为此，您必须先获取另存为 .CER 文件的 X.509 Base64。</span><span class="sxs-lookup"><span data-stu-id="ab7b4-119">In order to do this, you must first obtain an X.509 Base64 saved as a .CER file.</span></span> <span data-ttu-id="ab7b4-120">然后，此证书都将应用于 Office 365 服务主体。</span><span class="sxs-lookup"><span data-stu-id="ab7b4-120">This certificate will then be applied to the Office 365 service principals.</span></span>
  
<span data-ttu-id="ab7b4-121">当获取 X.509 证书时，启动 Microsoft Online Services 模块 （单击**开始**，单击**所有程序**，都单击**Microsoft Online Services**，然后都单击**Microsoft Online Services 模块 for WindowsPowerShell**)。</span><span class="sxs-lookup"><span data-stu-id="ab7b4-121">When you have obtained the X.509 certificate, start the Microsoft Online Services Module (click **Start**, click **All Programs**, click **Microsoft Online Services**, and then click **Microsoft Online Services Module for Windows PowerShell**).</span></span> <span data-ttu-id="ab7b4-122">服务模块打开后，键入以下内容以导入 Microsoft Online Windows PowerShell 模块包含可用于管理的服务主体的 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="ab7b4-122">After the Services Module opens, type the following to import the Microsoft Online Windows PowerShell module containing the cmdlets that can be used to manage service principals:</span></span>
  
```
Import-Module MSOnlineExtended
```

<span data-ttu-id="ab7b4-123">导入该模块后，键入以下命令并按 ENTER 以连接到 Office 365:</span><span class="sxs-lookup"><span data-stu-id="ab7b4-123">When the module has been imported, type the following command and then press ENTER in order to connect to Office 365:</span></span>
  
```
Connect-MsolService
```

<span data-ttu-id="ab7b4-124">按 Enter 后，随即出现一个凭据对话框。</span><span class="sxs-lookup"><span data-stu-id="ab7b4-124">After you press ENTER, a credentials dialog box will appear.</span></span> <span data-ttu-id="ab7b4-125">在对话框中，输入您的 Office 365 用户名和密码，然后单击确定。</span><span class="sxs-lookup"><span data-stu-id="ab7b4-125">Enter your Office 365 user name and password in the dialog box, and then click OK.</span></span>
  
<span data-ttu-id="ab7b4-126">只要您连接到 Office 365，您可以然后运行以下命令来返回有关您的服务主体的信息：</span><span class="sxs-lookup"><span data-stu-id="ab7b4-126">As soon as you are connected to Office 365, you can then run the following command in order to return information about your service principals:</span></span>
  
```
Get-MsolServicePrincipal
```

<span data-ttu-id="ab7b4-127">您应获得与以下信息类似的所有服务主体的相关信息：</span><span class="sxs-lookup"><span data-stu-id="ab7b4-127">You should get back information similar to this for all your service principals:</span></span>
  
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

<span data-ttu-id="ab7b4-128">下一步是导入、编码和分配 X.509 证书。</span><span class="sxs-lookup"><span data-stu-id="ab7b4-128">The next step is to import, encode, and assign the X.509 certificate.</span></span> <span data-ttu-id="ab7b4-129">若要导入和编码证书，请使用以下 Windows PowerShell 命令，确保指定的完整文件路径您。CER 文件导入方法致电时：</span><span class="sxs-lookup"><span data-stu-id="ab7b4-129">To import and encode the certificate, use the following Windows PowerShell commands, being sure to specify the complete file path to your .CER file when you call the Import method:</span></span>
  
```
$certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
$certificate.Import("C:\Certificates\Office365.cer")
$binaryValue = $certificate.GetRawCertData()
$credentialsValue = [System.Convert]::ToBase64String($binaryValue)
```

<span data-ttu-id="ab7b4-130">导入证书并将其编码后，您然后可以将证书分配给您的 Office 365 服务主体。</span><span class="sxs-lookup"><span data-stu-id="ab7b4-130">After the certificate has been imported and encoded, you can then assign the certificate to your Office 365 service principals.</span></span> <span data-ttu-id="ab7b4-131">为此，首先使用 Get-MsolServicePrincipal 业务服务器 Skype 和 Microsoft Exchange 服务主体; 检索 AppPrincipalId 属性的值AppPrincipalId 属性的值将用于标识其分配证书的服务主体。</span><span class="sxs-lookup"><span data-stu-id="ab7b4-131">To do that, first use the Get-MsolServicePrincipal to retrieve the value of the AppPrincipalId property for both the Skype for Business Server and the Microsoft Exchange service principals; the value of the AppPrincipalId property will be used to identify the service principal being assigned the certificate.</span></span> <span data-ttu-id="ab7b4-132">AppPrincipalId 属性值的 Skype 业务服务器 2015年手中，使用以下命令业务服务器的证书分配给 Skype 的 Office 365 版本：</span><span class="sxs-lookup"><span data-stu-id="ab7b4-132">With the AppPrincipalId property value for Skype for Business Server 2015 in hand, use the following command to assign the certificate to the Office 365 version of Skype for Business Server:</span></span>
  
```
New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue 
```

<span data-ttu-id="ab7b4-133">您然后应重复该命令，这次使用 Exchange 2013 的 AppPrincipalId 属性值。</span><span class="sxs-lookup"><span data-stu-id="ab7b4-133">You should then repeat the command, this time using the AppPrincipalId property value for Exchange 2013.</span></span>
  
<span data-ttu-id="ab7b4-134">如果您稍后需要删除该证书，可通过先检索证书的 KeyId 来执行此操作：</span><span class="sxs-lookup"><span data-stu-id="ab7b4-134">If you later need to delete that certificate, you can do so by first retrieving the KeyId for the certificate:</span></span>
  
```
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="ab7b4-135">此命令将返回与以下内容类似的数据：</span><span class="sxs-lookup"><span data-stu-id="ab7b4-135">That command will return data like this one:</span></span>
  
<pre>
Type      : Asymmetric
Value     : 
KeyId     : bc2795f3-2387-4543-a95d-f92c85c7a1b0
StartDate : 6/1/2012 8:00:00 AM
EndDate   : 5/31/2013 8:00:00 AM
Usage     : Verify
</pre>

<span data-ttu-id="ab7b4-136">然后，您可以使用与以下内容类似的命令删除该证书：</span><span class="sxs-lookup"><span data-stu-id="ab7b4-136">You can then delete the certificate by using a command similar to this:</span></span>
  
```
Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0
```

<span data-ttu-id="ab7b4-137">除了分配证书，您必须配置 Exchange Online 服务主体，并将您的本地版本的 Skype 业务服务器 2015年外部 Web 服务 url 配置为 Office 365 服务主体。</span><span class="sxs-lookup"><span data-stu-id="ab7b4-137">In addition to assigning a certificate, you must also configure the Exchange Online Service Principal and configure your on-premises version of Skype for Business Server 2015 external Web services URLs as an Office 365 service principal.</span></span> <span data-ttu-id="ab7b4-138">可通过执行下面两条命令达到此目的。</span><span class="sxs-lookup"><span data-stu-id="ab7b4-138">That can be done by carrying out the following two commands.</span></span> 
  
<span data-ttu-id="ab7b4-139">以下示例中，在 lync.contoso.com 是业务服务器池的 Skype 的外部 Web 服务 URL。</span><span class="sxs-lookup"><span data-stu-id="ab7b4-139">In the following example, lync.contoso.com is the external Web services URL for the Skype for Business Server pool.</span></span> <span data-ttu-id="ab7b4-140">您应重复这些步骤以添加在部署中的所有外部 Web 服务 Url。</span><span class="sxs-lookup"><span data-stu-id="ab7b4-140">You should repeat these steps to add all the external Web services URLs in the deployment.</span></span>
  
```
Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
$lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
$lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/lync.contoso.com")
Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames
```