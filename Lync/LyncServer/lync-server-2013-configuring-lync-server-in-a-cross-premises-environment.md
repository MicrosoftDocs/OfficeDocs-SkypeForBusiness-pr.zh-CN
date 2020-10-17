---
title: Lync Server 2013：在跨界环境中配置 Lync Server
description: Lync Server 2013：在跨界环境中配置 Lync Server。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Microsoft Lync Server 2013 in a cross-premises environment
ms:assetid: 700639ec-5264-4449-a8a6-d7386fad8719
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204990(v=OCS.15)
ms:contentKeyID: 48184449
ms.date: 02/21/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e1ec978cd8e0e34c01c1d5cabb5bba42debd16fd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570858"
---
# <a name="configuring-microsoft-lync-server-2013-in-a-cross-premises-environment"></a><span data-ttu-id="4bfd6-103">在跨界环境中配置 Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4bfd6-103">Configuring Microsoft Lync Server 2013 in a cross-premises environment</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4bfd6-104">_**上次修改的主题：** 2017-02-21_</span><span class="sxs-lookup"><span data-stu-id="4bfd6-104">_**Topic Last Modified:** 2017-02-21_</span></span>

<span data-ttu-id="4bfd6-105">在跨内部部署配置中，某些用户驻留在 Microsoft Lync Server 2013 的本地安装中，而其他用户托管在 Microsoft 365 或 Office 365 版本的 Lync Server 上。</span><span class="sxs-lookup"><span data-stu-id="4bfd6-105">In a cross-premise configuration, some of your users are homed on an on-premises installation of Microsoft Lync Server 2013 while other users are homed on the Microsoft 365 or Office 365 version of Lync Server.</span></span> <span data-ttu-id="4bfd6-106">为了在跨界环境中配置服务器到服务器的身份验证，您必须首先将 Lync Server 2013 的本地安装配置为信任 Microsoft 365 授权服务器。</span><span class="sxs-lookup"><span data-stu-id="4bfd6-106">In order to configure server-to-server authentication in a cross-premises environment, you must first configure your on-premises installation of Lync Server 2013 to trust the Microsoft 365 Authorization server.</span></span> <span data-ttu-id="4bfd6-107">此过程的初始步骤可通过运行以下 Lync Server 命令行管理程序脚本执行：</span><span class="sxs-lookup"><span data-stu-id="4bfd6-107">The initial step in this process can be carried out by running the following Lync Server Management Shell script:</span></span>

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

<span data-ttu-id="4bfd6-p102">请记住，租户的领域名称通常与组织名称不同；实际上，领域名称几乎始终与租户 ID 相同。为此，脚本中的第一行用于返回指定租户（此示例中为 fabrikam.com）的 TenantId 属性的值，然后将该名称分配给变量 $TenantId：</span><span class="sxs-lookup"><span data-stu-id="4bfd6-p102">Keep in mind that the realm name for a tenant is typically different than the organization name; in fact, the realm name is almost always the same as the tenant ID. Because of that, the first line in the script is used to return the value of the TenantId property for the specified tenant (in this case, fabrikam.com) and then assign that name to the variable $TenantId:</span></span>

    $TenantID = (Get-CsTenant -DisplayName "Fabrikam.com").TenantId

<span data-ttu-id="4bfd6-110">脚本完成后，您必须配置 Lync Server 2013 与授权服务器之间的信任关系，以及 Exchange 2013 和授权服务器之间的第二个信任关系。</span><span class="sxs-lookup"><span data-stu-id="4bfd6-110">After the script completes you must then configure a trust relationship between Lync Server 2013 and the authorization server, and a second trust relationship between Exchange 2013 and the authorization server.</span></span> <span data-ttu-id="4bfd6-111">只能通过 Microsoft Online Services cmdlet 做到这一点。</span><span class="sxs-lookup"><span data-stu-id="4bfd6-111">This can only be done by using the Microsoft Online Services cmdlets.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4bfd6-112">如果您尚未安装 Microsoft Online Services cmdlet，则您需要先完成两项操作，然后再继续。</span><span class="sxs-lookup"><span data-stu-id="4bfd6-112">If you have not installed the Microsoft Online Services cmdlets you will need to do two things before proceeding.</span></span> <span data-ttu-id="4bfd6-113">首先，下载并安装 64 位版本的 Microsoft Online Services 登录助手。</span><span class="sxs-lookup"><span data-stu-id="4bfd6-113">First, download and install the 64-bit version of the Microsoft Online Services Sign-in Assistant.</span></span> <span data-ttu-id="4bfd6-114">安装完成后，下载并安装适用于 Windows PowerShell 的64位版本的 Microsoft Online Services 模块。</span><span class="sxs-lookup"><span data-stu-id="4bfd6-114">After installation is complete, download and install the 64-bit version of the Microsoft Online Services Module for Windows PowerShell.</span></span> <span data-ttu-id="4bfd6-115">可以在 Microsoft 365 或 Office 365 网站上找到有关安装和使用 Microsoft Online Services 模块的详细信息。</span><span class="sxs-lookup"><span data-stu-id="4bfd6-115">Detailed information for installing and using the Microsoft Online Services Module can be found on the Microsoft 365 or Office 365 web site.</span></span> <span data-ttu-id="4bfd6-116">这些说明还将告诉你如何在 Microsoft 365 或 Office 36 与 Active Directory 之间配置单一登录、联合和同步。</span><span class="sxs-lookup"><span data-stu-id="4bfd6-116">These instructions will also tell you how to configure single sign-on, federation, and synchronization between Microsoft 365 or Office 36 and Active Directory.</span></span><BR><span data-ttu-id="4bfd6-117">如果尚未安装这些 cmdlet，则脚本将失败，因为 Get-CsTenant cmdlet 将不可用。</span><span class="sxs-lookup"><span data-stu-id="4bfd6-117">If you have not installed these cmdlets your script will fail because the Get-CsTenant cmdlet will not be available.</span></span>



</div>

<span data-ttu-id="4bfd6-118">配置 Microsoft 365 并在为 Lync Server 2013 和 Exchange 2013 创建 Microsoft 365 或 Office 365 服务主体之后，您需要使用这些服务主体注册您的凭据。</span><span class="sxs-lookup"><span data-stu-id="4bfd6-118">After you have configured Microsoft 365, and after you have created Microsoft 365 or Office 365 service principals for Lync Server 2013 and Exchange 2013, you will then need to register your credentials with these service principals.</span></span> <span data-ttu-id="4bfd6-119">为此，您必须先获取另存为 .CER 文件的 X.509 Base64。</span><span class="sxs-lookup"><span data-stu-id="4bfd6-119">In order to do this, you must first obtain an X.509 Base64 saved as a .CER file.</span></span> <span data-ttu-id="4bfd6-120">此证书将应用于 Microsoft 365 或 Office 365 服务主体。</span><span class="sxs-lookup"><span data-stu-id="4bfd6-120">This certificate will then be applied to the Microsoft 365 or Office 365 service principals.</span></span>

<span data-ttu-id="4bfd6-121">获取 x.509 证书后，启动 Microsoft Online Services 模块 (依次单击 " **开始**"、" **所有程序**"、" **microsoft Online Services**" 和 " **Windows PowerShell) 的 microsoft online services 模块** "。</span><span class="sxs-lookup"><span data-stu-id="4bfd6-121">When you have obtained the X.509 certificate, start the Microsoft Online Services Module (click **Start**, click **All Programs**, click **Microsoft Online Services**, and then click **Microsoft Online Services Module for Windows PowerShell**).</span></span> <span data-ttu-id="4bfd6-122">在服务模块打开后，键入以下命令以导入包含可用于管理服务主体的 cmdlet 的 Microsoft Online Windows PowerShell 模块：</span><span class="sxs-lookup"><span data-stu-id="4bfd6-122">After the Services Module opens, type the following to import the Microsoft Online Windows PowerShell module containing the cmdlets that can be used to manage service principals:</span></span>

    Import-Module MSOnlineExtended

<span data-ttu-id="4bfd6-123">导入该模块后，键入以下命令，然后按 ENTER 键以连接到 Microsoft 365：</span><span class="sxs-lookup"><span data-stu-id="4bfd6-123">When the module has been imported, type the following command and then press ENTER in order to connect to Microsoft 365:</span></span>

    Connect-MsolService

<span data-ttu-id="4bfd6-124">按 Enter 后，随即出现一个凭据对话框。</span><span class="sxs-lookup"><span data-stu-id="4bfd6-124">After you press ENTER, a credentials dialog box will appear.</span></span> <span data-ttu-id="4bfd6-125">在对话框中输入 Microsoft 365 或 Office 365 用户名和密码，然后单击 "确定"。</span><span class="sxs-lookup"><span data-stu-id="4bfd6-125">Enter your Microsoft 365 or Office 365 user name and password in the dialog box, and then click OK.</span></span>

<span data-ttu-id="4bfd6-126">一旦连接到 Microsoft 365，您就可以运行以下命令来返回有关您的服务主体的信息：</span><span class="sxs-lookup"><span data-stu-id="4bfd6-126">As soon as you are connected to Microsoft 365 you can then run the following command in order to return information about your service principals:</span></span>

    Get-MsolServicePrincipal

<span data-ttu-id="4bfd6-127">您应获得与以下信息类似的所有服务主体的相关信息：</span><span class="sxs-lookup"><span data-stu-id="4bfd6-127">You should get back information similar to this for all your service principals:</span></span>

    ExtensionData        : System.Runtime.Serialization.ExtensionDataObject
    AccountEnabled       : True
    Addresses            : {}
    AppPrincipalId       : 00000004-0000-0ff1-ce00-000000000000
    DisplayName          : Microsoft Lync Server
    ObjectId             : aada5fbd-c0ae-442a-8c0b-36fec40602e2
    ServicePrincipalName : LyncServer/litwareinc.com
    TrustedForDelegation : True

<span data-ttu-id="4bfd6-128">下一步是导入、编码和分配 X.509 证书。</span><span class="sxs-lookup"><span data-stu-id="4bfd6-128">The next step is to import, encode, and assign the X.509 certificate.</span></span> <span data-ttu-id="4bfd6-129">若要导入和编码证书，请使用以下 Windows PowerShell 命令，确保指定了的完整文件路径。CER 文件调用 Import 方法时：</span><span class="sxs-lookup"><span data-stu-id="4bfd6-129">To import and encode the certificate, use the following Windows PowerShell commands, being sure to specify the complete file path to your .CER file when you call the Import method:</span></span>

    $certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
    $certificate.Import("C:\Certificates\Office365.cer")
    $binaryValue = $certificate.GetRawCertData()
    $credentialsValue = [System.Convert]::ToBase64String($binaryValue)

<span data-ttu-id="4bfd6-130">在导入并编码证书后，您可以将证书分配给 Microsoft 365 服务主体。</span><span class="sxs-lookup"><span data-stu-id="4bfd6-130">After the certificate has been imported and encoded, you can then assign the certificate to your Microsoft 365 service principals.</span></span> <span data-ttu-id="4bfd6-131">为此，请先使用 Get-MsolServicePrincipal 检索针对 Lync Server 和 Microsoft Exchange 服务主体的 AppPrincipalId 属性的值；AppPrincipalId 属性的值将用于标识分配了证书的服务主体。</span><span class="sxs-lookup"><span data-stu-id="4bfd6-131">To do that, first use the Get-MsolServicePrincipal to retrieve the value of the AppPrincipalId property for both the Lync Server and the Microsoft Exchange service principals; the value of the AppPrincipalId property will be used to identify the service principal being assigned the certificate.</span></span> <span data-ttu-id="4bfd6-132">使用 Lync Server 2013 的 AppPrincipalId 属性值，使用以下命令将证书分配给 Microsoft 365 版本的 Lync Server ("起始日期" 和 "结束时间" 属性应对应于证书) 的有效期：</span><span class="sxs-lookup"><span data-stu-id="4bfd6-132">With the AppPrincipalId property value for Lync Server 2013 in hand, use the following command to assign the certificate to the Microsoft 365 version of Lync Server (the StartDate and EndDate properties should correspond to the validity period for the certificate):</span></span>

    New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue -StartDate 6/1/2012 -EndDate 5/31/2013

<span data-ttu-id="4bfd6-133">然后，您应该重复该命令，这次使用的是 Exchange 2013 的 AppPrincipalId 属性值。</span><span class="sxs-lookup"><span data-stu-id="4bfd6-133">You should then repeat the command, this time using the AppPrincipalId property value for Exchange 2013.</span></span>

<span data-ttu-id="4bfd6-134">如果您稍后需要删除该证书，可通过先检索证书的 KeyId 来执行此操作：</span><span class="sxs-lookup"><span data-stu-id="4bfd6-134">If you later need to delete that certificate, you can do so by first retrieving the KeyId for the certificate:</span></span>

    Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000

<span data-ttu-id="4bfd6-135">此命令将返回与以下内容类似的数据：</span><span class="sxs-lookup"><span data-stu-id="4bfd6-135">That command will return data like this one:</span></span>

    Type      : Asymmetric
    Value     : 
    KeyId     : bc2795f3-2387-4543-a95d-f92c85c7a1b0
    StartDate : 6/1/2012 8:00:00 AM
    EndDate   : 5/31/2013 8:00:00 AM
    Usage     : Verify

<span data-ttu-id="4bfd6-136">然后，您可以使用与以下内容类似的命令删除该证书：</span><span class="sxs-lookup"><span data-stu-id="4bfd6-136">You can then delete the certificate by using a command similar to this:</span></span>

    Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0

<span data-ttu-id="4bfd6-137">除了分配证书之外，还必须通过为本地版本的 Lync Server 2013 添加服务器主体名称，从而为 Exchange Online 配置 Microsoft 365 服务主体。</span><span class="sxs-lookup"><span data-stu-id="4bfd6-137">In addition to assigning a certificate you must also configure the Microsoft 365 Service Principal for Exchange Online by adding the Server Principal Name for your on-premise version of Lync Server 2013.</span></span> <span data-ttu-id="4bfd6-138">可通过在 Microsoft Online Services PowerShell 会话中运行以下四行来实现此目的：</span><span class="sxs-lookup"><span data-stu-id="4bfd6-138">This can be done by running the following four lines in a Microsoft Online Services PowerShell session:</span></span>

    Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
    
    $lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
    $lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/lync.contoso.com")
    Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames

</div>

<span> </span>

</div>

</div>

</div>

