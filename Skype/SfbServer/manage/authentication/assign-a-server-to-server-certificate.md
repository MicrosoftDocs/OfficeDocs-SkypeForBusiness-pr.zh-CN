---
title: 将服务器对服务器身份验证证书分配给 Skype for Business Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c7413954-2504-47f4-a073-44548aff1c0c
description: 摘要： 将分配用于业务服务器 2015 Skype 的服务器到服务器身份验证证书。
ms.openlocfilehash: 7bc697d9c45b55708ffb3fa20f04fbeb3eec9de9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="assign-a-server-to-server-authentication-certificate-to-skype-for-business-server-2015"></a><span data-ttu-id="8d157-103">将服务器对服务器身份验证证书分配给 Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="8d157-103">Assign a server-to-server authentication certificate to Skype for Business Server 2015</span></span>
<span data-ttu-id="8d157-104">**摘要：**为业务服务器 2015年的 Skype 分配的服务器到服务器身份验证证书。</span><span class="sxs-lookup"><span data-stu-id="8d157-104">**Summary:** Assign a server-to-server authentication certificate for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="8d157-105">若要确定服务器到服务器身份验证证书已被分配到 Skype 的业务服务器 2015年，请从 Skype 的业务服务器管理外壳程序运行下面的命令：</span><span class="sxs-lookup"><span data-stu-id="8d157-105">To determine whether or not a server-to-server authentication certificate has already been assigned to Skype for Business Server 2015, run the following command from the Skype for Business Server Management Shell:</span></span>
  
```
Get-CsCertificate -Type OAuthTokenIssuer
```

<span data-ttu-id="8d157-106">如果没有返回任何证书信息，则必须在分配令牌颁发者证书后才能使用服务器到服务器身份验证。</span><span class="sxs-lookup"><span data-stu-id="8d157-106">If no certificate information is returned you must assign a token issuer certificate before you can use server-to-server authentication.</span></span> <span data-ttu-id="8d157-107">作为一般规则，任何 Skype 业务服务器 2015年证书可作为 OAuthTokenIssuer 证书;例如，您的 Skype 业务服务器 2015年默认证书也可以用作 OAuthTokenIssuer 证书。</span><span class="sxs-lookup"><span data-stu-id="8d157-107">As a general rule, any Skype for Business Server 2015 certificate can be used as your OAuthTokenIssuer certificate; for example, your Skype for Business Server 2015 default certificate can also be used as the OAuthTokenIssuer certificate.</span></span> <span data-ttu-id="8d157-108">（OAUthTokenIssuer 证书还可以任意 Web 服务器证书的主题字段中包含 SIP 域的名称。这些用于服务器到服务器的身份验证的证书的主要两个要求是： 1) 相同的证书必须配置为 OAuthTokenIssuer 证书对所有您前端服务器;并且，2） 证书必须至少为 2048 位。</span><span class="sxs-lookup"><span data-stu-id="8d157-108">(The OAUthTokenIssuer certificate can also be any Web server certificate that includes the name of your SIP domain in the Subject field.) The primary two requirements for the certificate used for server-to-server authentication are these: 1)the same certificate must be configured as the OAuthTokenIssuer certificate on all of your Front End Servers; and, 2) the certificate must be at least 2048 bits.</span></span>
  
<span data-ttu-id="8d157-109">如果没有可用于服务器到服务器身份验证的证书，则可以获取新证书，导入新证书，然后将该证书用于服务器到服务器身份验证。</span><span class="sxs-lookup"><span data-stu-id="8d157-109">If you do not have a certificate that can be used for server-to-server authentication you can obtain a new certificate, import the new certificate, and then use that certificate for server-to-server authentication.</span></span> <span data-ttu-id="8d157-110">在请求和获取新的证书后可以再登录上的任何一种您前端服务器和使用与此类似的 Windows PowerShell 命令导入并分配该证书：</span><span class="sxs-lookup"><span data-stu-id="8d157-110">After you have requested and obtained the new certificate you can then log on to any one of your Front End Servers and use a Windows PowerShell command similar to this one to import and assign that certificate:</span></span>
  
```
Import-CsCertificate -Identity global -Type OAuthTokenIssuer -Path C:\Certificates\ServerToServerAuth.pfx  -Password "P@ssw0rd"
```

<span data-ttu-id="8d157-111">在上述命令中，Path 参数表示证书文件的完整路径，Password 参数表示分配给该证书的密码。</span><span class="sxs-lookup"><span data-stu-id="8d157-111">In the preceding command the Path parameter represents the full path to the certificate file, and the Password parameter represents the password that was assigned to the certificate.</span></span> <span data-ttu-id="8d157-112">应执行此过程只需一次： 业务服务器复制服务 Skype 然后将自动创建一套调度任务，它们将解密并部署到所有您前端服务器的证书。</span><span class="sxs-lookup"><span data-stu-id="8d157-112">This procedure should be run just one time: the Skype for Business Server replication service will then automatically create a set of scheduled tasks that will decrypt and deploy the certificate to all your Front End Servers.</span></span>
  
<span data-ttu-id="8d157-113">您也可以使用现有证书作为服务器到服务器身份验证证书。</span><span class="sxs-lookup"><span data-stu-id="8d157-113">Alternatively, you can use an existing certificate as your server-to-server authentication certificate.</span></span> <span data-ttu-id="8d157-114">（如上所述，默认证书可作为服务器到服务器身份验证证书。）以下两个 Windows PowerShell 命令检索属性的值的默认证书指纹，则使用此值将作为默认证书的服务器到服务器身份验证证书：</span><span class="sxs-lookup"><span data-stu-id="8d157-114">(As noted, the default certificate can be used as the server-to-server authentication certificate.) The following pair of Windows PowerShell commands retrieve the value of the default certificate's Thumbprint property, then use that value to make the default certificate the server-to-server authentication certificate:</span></span>
  
```
$x = (Get-CsCertificate -Type Default).Thumbprint
Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x
```

<span data-ttu-id="8d157-115">在上述命令中，检索到的证书配置为充当全球的服务器到服务器身份验证证书;这意味着将复制到中，并由所有您前端服务器证书。</span><span class="sxs-lookup"><span data-stu-id="8d157-115">In the preceding command, the retrieved certificate is configured to function as the global server-to-server authentication certificate; that means that the certificate will be replicated to, and used by, all your Front End Servers.</span></span> <span data-ttu-id="8d157-116">同样，一次，并且只在一种您前端服务器应该只运行该命令。</span><span class="sxs-lookup"><span data-stu-id="8d157-116">Again, this command should only be run one time, and only on one of your Front End Servers.</span></span> <span data-ttu-id="8d157-117">尽管所有前端服务器必须使用相同的证书，则不应该在每个前端服务器上配置的 OAuthTokenIssuer 证书。</span><span class="sxs-lookup"><span data-stu-id="8d157-117">Although all Front End Servers must use the same certificate, you should not configure the OAuthTokenIssuer certificate on each Front End Server.</span></span> <span data-ttu-id="8d157-118">相反，一次，配置证书，然后让为业务服务器 2015年复制服务器负责将该证书复制到每个服务器的 Skype。</span><span class="sxs-lookup"><span data-stu-id="8d157-118">Instead, configure the certificate once, then let the Skype for Business Server 2015 replication server take care of copying that certificate to each server.</span></span>
  
<span data-ttu-id="8d157-119">设置 CsCertificate cmdlet 采用证书问题，并立即配置该证书作为当前 OAuthTokenIssuer 证书。</span><span class="sxs-lookup"><span data-stu-id="8d157-119">The Set-CsCertificate cmdlet takes the certificate in question and immediately configures that certificate to act as the current OAuthTokenIssuer certificate.</span></span> <span data-ttu-id="8d157-120">(业务服务器 2015年的 Skype 保存的证书类型的两个副本： 当前的证书和以前的证书。)如果您需要立即开始充当 OAuthTokenIssuer 证书，则应使用组 CsCertificate cmdlet 的新证书。</span><span class="sxs-lookup"><span data-stu-id="8d157-120">(Skype for Business Server 2015 keeps two copies of a certificate type: the current certificate and the previous certificate.) If you need the new certificate to immediately begin to act as the OAuthTokenIssuer certificate then you should use the Set-CsCertificate cmdlet.</span></span>
  
<span data-ttu-id="8d157-p107">您还可以使用 Set-CsCertificate cmdlet“滚动”新证书。“滚动”证书仅意味着在指定时间点将新证书配置为成为当前 OAuthTokenIssuer 证书。例如，以下命令将检索默认证书，然后将该证书配置为从 2015 年 7 月 1 日起成为当前 OAuthTokenIssuer 证书：</span><span class="sxs-lookup"><span data-stu-id="8d157-p107">You can also use the Set-CsCertificate cmdlet to "roll" a new certificate. "Rolling" a certificate simply means that you configure a new certificate to become the current OAuthTokenIssuer certificate at a specified point in time. For example, this command retrieves the default certificate and then configure that certificate to take over as the current OAuthTokenIssuer certificate as of July 1, 2015:</span></span>
  
```
$x = (Get-CsCertificate -Type Default).Thumbprint
Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x -EffectiveDate "7/1/2015" -Roll
```

<span data-ttu-id="8d157-124">在 2015 年 7 月 1 日，新证书将配置为当前 OAuthTokenIssuer 证书，“旧”OAuthTokenIssuer 证书将配置为上一个证书。</span><span class="sxs-lookup"><span data-stu-id="8d157-124">On July 1, 2015 the new certificate will be configured as the current OAuthTokenIssuer certificate and the "old" OAuthTokenIssuer certificate will be configured as the previous certificate.</span></span>
  
<span data-ttu-id="8d157-125">如果您不想使用 Windows PowerShell 您还可以使用证书的 MMC 控制台来从一个前端服务器中导出一个证书，然后将同一证书导入所有您其他前端服务器上。</span><span class="sxs-lookup"><span data-stu-id="8d157-125">If you do not want to use Windows PowerShell you can also use the Certificates MMC console to export a certificate from one Front End Server and then import that same certificate on all your other Front End Servers.</span></span> <span data-ttu-id="8d157-126">如果执行此操作，请确保将私钥连同证书本身一起导出。</span><span class="sxs-lookup"><span data-stu-id="8d157-126">If you do this, make sure that you export the private key along with the certificate itself.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="8d157-127">在这种情况下，必须在每个前端服务器上执行该过程。</span><span class="sxs-lookup"><span data-stu-id="8d157-127">In this case, the procedure must be performed on each Front End Server.</span></span> <span data-ttu-id="8d157-128">当导出和导入证书以这种方式的业务服务器 2015 Skype 不会为每个前端服务器复制该证书。</span><span class="sxs-lookup"><span data-stu-id="8d157-128">When exporting and importing certificates in this manner Skype for Business Server 2015 will not replicate that certificate to each Front End Server.</span></span> 
  
<span data-ttu-id="8d157-129">证书导入到所有您前端服务器后，然后可以通过 Skype 业务服务器部署向导，而不是 Windows PowerShell 分配该证书。</span><span class="sxs-lookup"><span data-stu-id="8d157-129">After the certificate has been imported to all your Front End Servers, that certificate can then be assigned by using the Skype for Business Server Deployment Wizard instead of Windows PowerShell.</span></span> <span data-ttu-id="8d157-130">要使用部署向导分配证书，请在安装了部署向导的计算机上完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="8d157-130">To assign a certificate by using the Deployment Wizard, complete the following steps on a computer where the Deployment Wizard has been installed:</span></span>
  
1. <span data-ttu-id="8d157-131">单击开始，单击所有程序，都单击**业务服务器 2015年的 Skype**，，然后都单击**Skype 业务服务器部署向导**。</span><span class="sxs-lookup"><span data-stu-id="8d157-131">Click Start, click All Programs, click **Skype for Business Server 2015**, and then click **Skype for Business Server Deployment Wizard**.</span></span>
    
2. <span data-ttu-id="8d157-132">在部署向导中，单击**安装或更新 Skype 业务服务器系统**。</span><span class="sxs-lookup"><span data-stu-id="8d157-132">In the Deployment Wizard, click **Install or Update Skype for Business Server System**.</span></span>
    
3. <span data-ttu-id="8d157-133">在 Skype 业务服务器 2015年页，在标题下单击**运行**按钮**第 3 步： 安装或分配证书请求**。</span><span class="sxs-lookup"><span data-stu-id="8d157-133">On the Skype for Business Server 2015 page, click the **Run** button under the heading **Step 3: Request, Install or Assign Certificates**.</span></span> <span data-ttu-id="8d157-134">(注意： 如果本计算机上已安装的证书，然后将**再次运行**标记为**运行**按钮。)</span><span class="sxs-lookup"><span data-stu-id="8d157-134">(Note: If you have already installed certificates on this computer then the **Run** button will be labeled **Run Again**.)</span></span>
    
4. <span data-ttu-id="8d157-135">在证书向导中，选择 OAuthTokenIssuer**** 证书，然后单击“分配”****。</span><span class="sxs-lookup"><span data-stu-id="8d157-135">In the Certificate Wizard, select the **OAuthTokenIssuer** certificate and then click **Assign**.</span></span>
    
5. <span data-ttu-id="8d157-136">在证书分配向导的“证书分配”****页上，单击“下一步”****。</span><span class="sxs-lookup"><span data-stu-id="8d157-136">In the Certificate Assignment wizard, on the **Certificate Assignment** page, click **Next**.</span></span>
    
6. <span data-ttu-id="8d157-137">在“证书存储”****页上，选择要用于服务器到服务器身份验证的证书，然后单击“下一步”****。</span><span class="sxs-lookup"><span data-stu-id="8d157-137">On the **Certificate Store** page, select the certificate to be used for server-to-server authentication and then click **Next**.</span></span>
    
7. <span data-ttu-id="8d157-138">在“证书分配摘要”页上，单击“下一步”****。</span><span class="sxs-lookup"><span data-stu-id="8d157-138">On the Certificate Assignment Summary page, click **Next**.</span></span>
    
8. <span data-ttu-id="8d157-139">在“正在执行命令”页上，单击“完成”****。</span><span class="sxs-lookup"><span data-stu-id="8d157-139">On the Executing Commands page, click **Finish**.</span></span>
    
9. <span data-ttu-id="8d157-140">关闭证书向导和部署向导。</span><span class="sxs-lookup"><span data-stu-id="8d157-140">Close the Certificate Wizard and the Deployment Wizard.</span></span>
    

