---
title: 将服务器到服务器身份验证证书分配给 Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c7413954-2504-47f4-a073-44548aff1c0c
description: 摘要：为 Skype for Business Server 分配服务器到服务器身份验证证书。
ms.openlocfilehash: 122c2a1783fe4370027b4412ae5be8058e4914ce
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828502"
---
# <a name="assign-a-server-to-server-authentication-certificate-to-skype-for-business-server"></a><span data-ttu-id="7a0df-103">将服务器到服务器身份验证证书分配给 Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="7a0df-103">Assign a server-to-server authentication certificate to Skype for Business Server</span></span>
<span data-ttu-id="7a0df-104">**摘要：** 为 Skype for Business Server 分配服务器到服务器身份验证证书。</span><span class="sxs-lookup"><span data-stu-id="7a0df-104">**Summary:** Assign a server-to-server authentication certificate for Skype for Business Server.</span></span>
  
<span data-ttu-id="7a0df-105">若要确定是否已将服务器到服务器身份验证证书分配给 Skype for Business Server，请从 Skype for Business Server 命令行管理程序 运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="7a0df-105">To determine whether or not a server-to-server authentication certificate has already been assigned to Skype for Business Server, run the following command from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Get-CsCertificate -Type OAuthTokenIssuer
```

<span data-ttu-id="7a0df-106">如果没有返回任何证书信息，则必须在分配令牌颁发者证书后才能使用服务器到服务器身份验证。</span><span class="sxs-lookup"><span data-stu-id="7a0df-106">If no certificate information is returned you must assign a token issuer certificate before you can use server-to-server authentication.</span></span> <span data-ttu-id="7a0df-107">一般而言，任何 Skype for Business Server 证书都可以用作 OAuthTokenIssuer 证书;例如，Skype for Business Server 默认证书还可以用作 OAuthTokenIssuer 证书。</span><span class="sxs-lookup"><span data-stu-id="7a0df-107">As a general rule, any Skype for Business Server certificate can be used as your OAuthTokenIssuer certificate; for example, your Skype for Business Server default certificate can also be used as the OAuthTokenIssuer certificate.</span></span> <span data-ttu-id="7a0df-108"> (OAUthTokenIssuer 证书还可以是"主题"字段中包含 SIP 域名称的任何 Web 服务器证书。) 用于服务器到服务器身份验证的证书的主要两个要求如下：1) 必须在所有前端服务器上将同一证书配置为 OAuthTokenIssuer 证书;并且，2) 证书必须至少为 2048 位。</span><span class="sxs-lookup"><span data-stu-id="7a0df-108">(The OAUthTokenIssuer certificate can also be any Web server certificate that includes the name of your SIP domain in the Subject field.) The primary two requirements for the certificate used for server-to-server authentication are these: 1)the same certificate must be configured as the OAuthTokenIssuer certificate on all of your Front End Servers; and, 2) the certificate must be at least 2048 bits.</span></span>
  
<span data-ttu-id="7a0df-p102">如果没有可用于服务器到服务器身份验证的证书，则可以获取新证书，导入新证书，然后将该证书用于服务器到服务器身份验证。在请求并获取新证书后，可以登录到任一前端服务器并使用类似如下的 Windows PowerShell 命令导入和分配该证书：</span><span class="sxs-lookup"><span data-stu-id="7a0df-p102">If you do not have a certificate that can be used for server-to-server authentication you can obtain a new certificate, import the new certificate, and then use that certificate for server-to-server authentication. After you have requested and obtained the new certificate you can then log on to any one of your Front End Servers and use a Windows PowerShell command similar to this one to import and assign that certificate:</span></span>
  
```PowerShell
Import-CsCertificate -Identity global -Type OAuthTokenIssuer -Path C:\Certificates\ServerToServerAuth.pfx  -Password "P@ssw0rd"
```

<span data-ttu-id="7a0df-111">在上述命令中，Path 参数表示证书文件的完整路径，Password 参数表示分配给该证书的密码。</span><span class="sxs-lookup"><span data-stu-id="7a0df-111">In the preceding command the Path parameter represents the full path to the certificate file, and the Password parameter represents the password that was assigned to the certificate.</span></span> <span data-ttu-id="7a0df-112">此过程应只运行一次：Skype for Business Server 复制服务随后将自动创建一组计划任务，这些任务将解密证书，然后将证书部署到所有前端服务器。</span><span class="sxs-lookup"><span data-stu-id="7a0df-112">This procedure should be run just one time: the Skype for Business Server replication service will then automatically create a set of scheduled tasks that will decrypt and deploy the certificate to all your Front End Servers.</span></span>
  
<span data-ttu-id="7a0df-p104">您也可以使用现有证书作为服务器到服务器身份验证证书。（如前所述，默认证书可用作服务器到服务器身份验证证书。）以下 Windows PowerShell 命令对可检索默认证书的 Thumbprint 属性的值，然后使用该值使默认证书成为服务器到服务器身份验证证书：</span><span class="sxs-lookup"><span data-stu-id="7a0df-p104">Alternatively, you can use an existing certificate as your server-to-server authentication certificate. (As noted, the default certificate can be used as the server-to-server authentication certificate.) The following pair of Windows PowerShell commands retrieve the value of the default certificate's Thumbprint property, then use that value to make the default certificate the server-to-server authentication certificate:</span></span>
  
```PowerShell
$x = (Get-CsCertificate -Type Default).Thumbprint
Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x
```

<span data-ttu-id="7a0df-115">在上述命令中，所检索的证书配置为用作全局服务器到服务器身份验证证书；这意味着该证书将被复制到所有前端服务器并被这些服务器使用。</span><span class="sxs-lookup"><span data-stu-id="7a0df-115">In the preceding command, the retrieved certificate is configured to function as the global server-to-server authentication certificate; that means that the certificate will be replicated to, and used by, all your Front End Servers.</span></span> <span data-ttu-id="7a0df-116">再强调一次，此命令只应在其中一台前端服务器上运行一次。</span><span class="sxs-lookup"><span data-stu-id="7a0df-116">Again, this command should only be run one time, and only on one of your Front End Servers.</span></span> <span data-ttu-id="7a0df-117">尽管所有前端服务器都必须使用相同证书，但您不应在每台前端服务器上都配置 OAuthTokenIssuer 证书。</span><span class="sxs-lookup"><span data-stu-id="7a0df-117">Although all Front End Servers must use the same certificate, you should not configure the OAuthTokenIssuer certificate on each Front End Server.</span></span> <span data-ttu-id="7a0df-118">相反，请配置证书一次，然后让 Skype for Business Server 复制服务器负责将证书复制到每台服务器。</span><span class="sxs-lookup"><span data-stu-id="7a0df-118">Instead, configure the certificate once, then let the Skype for Business Server replication server take care of copying that certificate to each server.</span></span>
  
<span data-ttu-id="7a0df-119">该 Set-CsCertificate cmdlet 会接受该证书，并立即配置该证书以用作当前 OAuthTokenIssuer 证书。</span><span class="sxs-lookup"><span data-stu-id="7a0df-119">The Set-CsCertificate cmdlet takes the certificate in question and immediately configures that certificate to act as the current OAuthTokenIssuer certificate.</span></span> <span data-ttu-id="7a0df-120"> (Skype for Business Server 保留证书类型的两个副本：当前证书和上一个证书。) 如果需要新证书立即开始充当 OAuthTokenIssuer 证书，则应该使用 Set-CsCertificate cmdlet。</span><span class="sxs-lookup"><span data-stu-id="7a0df-120">(Skype for Business Server keeps two copies of a certificate type: the current certificate and the previous certificate.) If you need the new certificate to immediately begin to act as the OAuthTokenIssuer certificate then you should use the Set-CsCertificate cmdlet.</span></span>
  
<span data-ttu-id="7a0df-121">您还可以使用 Set-CsCertificate cmdlet“滚动”新证书。</span><span class="sxs-lookup"><span data-stu-id="7a0df-121">You can also use the Set-CsCertificate cmdlet to "roll" a new certificate.</span></span> <span data-ttu-id="7a0df-122">“滚动”证书仅意味着在指定时间点将新证书配置为成为当前 OAuthTokenIssuer 证书。</span><span class="sxs-lookup"><span data-stu-id="7a0df-122">"Rolling" a certificate simply means that you configure a new certificate to become the current OAuthTokenIssuer certificate at a specified point in time.</span></span> <span data-ttu-id="7a0df-123">例如，此命令检索默认证书，然后将该证书配置为自 2015 年 7 月 1 日起作为当前 OAuthTokenIssuer 证书接管：</span><span class="sxs-lookup"><span data-stu-id="7a0df-123">For example, this command retrieves the default certificate and then configure that certificate to take over as the current OAuthTokenIssuer certificate as of July 1, 2015:</span></span>
  
```PowerShell
$x = (Get-CsCertificate -Type Default).Thumbprint
Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x -EffectiveDate "7/1/2015" -Roll
```

<span data-ttu-id="7a0df-124">2015 年 7 月 1 日，新证书将配置为当前 OAuthTokenIssuer 证书，"旧"OAuthTokenIssuer 证书将配置为以前的证书。</span><span class="sxs-lookup"><span data-stu-id="7a0df-124">On July 1, 2015, the new certificate will be configured as the current OAuthTokenIssuer certificate and the "old" OAuthTokenIssuer certificate will be configured as the previous certificate.</span></span>
  
<span data-ttu-id="7a0df-p108">如果不想使用 Windows PowerShell，还可以使用证书 MMC 控制台从一台前端服务器中导出证书，然后在所有其他前端服务器上导入相同证书。如果执行此操作，请确保将私钥连同证书本身一起导出。</span><span class="sxs-lookup"><span data-stu-id="7a0df-p108">If you do not want to use Windows PowerShell you can also use the Certificates MMC console to export a certificate from one Front End Server and then import that same certificate on all your other Front End Servers. If you do this, make sure that you export the private key along with the certificate itself.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="7a0df-127">在这种情况下，必须在每台前端服务器上执行该过程。</span><span class="sxs-lookup"><span data-stu-id="7a0df-127">In this case, the procedure must be performed on each Front End Server.</span></span> <span data-ttu-id="7a0df-128">通过此方式导出和导入证书时，Skype for Business Server 不会将证书复制到每台前端服务器。</span><span class="sxs-lookup"><span data-stu-id="7a0df-128">When exporting and importing certificates in this manner Skype for Business Server will not replicate that certificate to each Front End Server.</span></span> 
  
<span data-ttu-id="7a0df-129">将证书导入到所有前端服务器后，可以使用 Skype for Business Server 部署向导分配该证书，而不是Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="7a0df-129">After the certificate has been imported to all your Front End Servers, that certificate can then be assigned by using the Skype for Business Server Deployment Wizard instead of Windows PowerShell.</span></span> <span data-ttu-id="7a0df-130">要使用部署向导分配证书，请在安装了部署向导的计算机上完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="7a0df-130">To assign a certificate by using the Deployment Wizard, complete the following steps on a computer where the Deployment Wizard has been installed:</span></span>
  
1. <span data-ttu-id="7a0df-131">单击"开始"，单击"所有程序"，单击 **"Skype for Business Server"，** 然后单击 **"Skype for Business Server 部署向导"。**</span><span class="sxs-lookup"><span data-stu-id="7a0df-131">Click Start, click All Programs, click **Skype for Business Server**, and then click **Skype for Business Server Deployment Wizard**.</span></span>
    
2. <span data-ttu-id="7a0df-132">在部署向导中，单击 **"安装或更新 Skype for Business Server 系统"。**</span><span class="sxs-lookup"><span data-stu-id="7a0df-132">In the Deployment Wizard, click **Install or Update Skype for Business Server System**.</span></span>
    
3. <span data-ttu-id="7a0df-133">在 Skype for Business Server页面上，单击标题为"步骤 3： 请求、安装或分配证书 **"下的"运行"按钮**。</span><span class="sxs-lookup"><span data-stu-id="7a0df-133">On the Skype for Business Server page, click the **Run** button under the heading **Step 3: Request, Install or Assign Certificates**.</span></span> <span data-ttu-id="7a0df-134"> (注意：如果已在此计算机上安装证书，则"运行"按钮将标记为"再次运行 **")**</span><span class="sxs-lookup"><span data-stu-id="7a0df-134">(Note: If you have already installed certificates on this computer then the **Run** button will be labeled **Run Again**.)</span></span>
    
4. <span data-ttu-id="7a0df-135">在证书向导中，选择 OAuthTokenIssuer 证书，然后单击“分配”。</span><span class="sxs-lookup"><span data-stu-id="7a0df-135">In the Certificate Wizard, select the **OAuthTokenIssuer** certificate and then click **Assign**.</span></span>
    
5. <span data-ttu-id="7a0df-136">在证书分配向导的“证书分配”页上，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="7a0df-136">In the Certificate Assignment wizard, on the **Certificate Assignment** page, click **Next**.</span></span>
    
6. <span data-ttu-id="7a0df-137">在“证书存储”页上，选择要用于服务器到服务器身份验证的证书，然后单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="7a0df-137">On the **Certificate Store** page, select the certificate to be used for server-to-server authentication and then click **Next**.</span></span>
    
7. <span data-ttu-id="7a0df-138">在“证书分配摘要”页上，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="7a0df-138">On the Certificate Assignment Summary page, click **Next**.</span></span>
    
8. <span data-ttu-id="7a0df-139">在“正在执行命令”页上，单击“完成”。</span><span class="sxs-lookup"><span data-stu-id="7a0df-139">On the Executing Commands page, click **Finish**.</span></span>
    
9. <span data-ttu-id="7a0df-140">关闭证书向导和部署向导。</span><span class="sxs-lookup"><span data-stu-id="7a0df-140">Close the Certificate Wizard and the Deployment Wizard.</span></span>
    

