---
title: Lync Server 2013：配置与 Lync Online 的联盟
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure federation with Lync Online
ms:assetid: a10bd1d5-c003-46db-9f57-7d55d3fa08da
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205126(v=OCS.15)
ms:contentKeyID: 48184946
ms.date: 08/15/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba9179f05918504df15a18b35b9c411f23919330
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726572"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-federation-of-lync-server-2013-with-lync-online"></a><span data-ttu-id="b4f13-102">配置 Lync Server 2013 与 Lync Online 的联合</span><span class="sxs-lookup"><span data-stu-id="b4f13-102">Configure federation of Lync Server 2013 with Lync Online</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b4f13-103">_**主题上次修改时间：** 2016-08-15_</span><span class="sxs-lookup"><span data-stu-id="b4f13-103">_**Topic Last Modified:** 2016-08-15_</span></span>

<span data-ttu-id="b4f13-104">按照本部分中的步骤配置本地部署和 Skype for Business Online 之间的互操作性。</span><span class="sxs-lookup"><span data-stu-id="b4f13-104">Follow the steps in this section to configure interoperability between your on-premises deployment and Skype for Business Online.</span></span>

<span id="a"></span>

<div>

## <a name="configure-your-on-premises-edge-service-for-federation-with-skype-for-business-online"></a><span data-ttu-id="b4f13-105">为具有 Skype for business Online 的联盟配置本地边缘服务</span><span class="sxs-lookup"><span data-stu-id="b4f13-105">Configure Your On-Premises Edge Service for Federation with Skype for Business Online</span></span>

<span data-ttu-id="b4f13-106">联合身份验证允许本地部署中的用户与你的组织中的 Office 365 用户通信。</span><span class="sxs-lookup"><span data-stu-id="b4f13-106">Federation allows users in your on-premises deployment to communicate with Office 365 users in your organization.</span></span> <span data-ttu-id="b4f13-107">若要配置联盟，请运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="b4f13-107">To configure federation, run the following cmdlets:</span></span>

   ```powershell
    Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $True
   ```

   ```powershell
    New-CSHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
   ```

</div>

<span id="b"></span>

<div>

## <a name="configure-your-skype-for-business-online-tenant-for-a-shared-sip-address-space"></a><span data-ttu-id="b4f13-108">为共享 SIP 地址空间配置 Skype for Business Online 租户</span><span class="sxs-lookup"><span data-stu-id="b4f13-108">Configure Your Skype for Business Online Tenant for a Shared SIP Address Space</span></span>

<span data-ttu-id="b4f13-109">会话初始协议 (SIP) 地址是网络上每个用户的唯一标识符，类似于电话号码或电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="b4f13-109">A Session Initiation Protocol (SIP) address is a unique identifier for each user on a network, similar to a phone number or an email address.</span></span> <span data-ttu-id="b4f13-110">在尝试将 Lync 用户从本地移动到 Skype for Business Online 之前，你需要将 Office 365 租户配置为与本地部署共享共享会话启动协议（SIP）地址空间。</span><span class="sxs-lookup"><span data-stu-id="b4f13-110">Before you try to move Lync users from on-premises to Skype for Business Online, you’ll need to configure your Office 365 tenant to share the Shared Session Initiation Protocol (SIP) address space with your on-premises deployment.</span></span> <span data-ttu-id="b4f13-111">如果未进行此配置，您可能会看到以下错误消息：</span><span class="sxs-lookup"><span data-stu-id="b4f13-111">If this is not configured, you may see the following error message:</span></span>

<span data-ttu-id="b4f13-112">Move-CsUser : HostedMigration 错误: Error=(510), 描述=(没有为此用户的租户启用共享 sip 地址空间。)</span><span class="sxs-lookup"><span data-stu-id="b4f13-112">Move-CsUser : HostedMigration fault: Error=(510), Description=(This user’s tenant is not enabled for shared sip address space.)</span></span>

<span data-ttu-id="b4f13-113">若要配置共享 SIP 地址空间，请建立与 Skype for Business Online 的远程 PowerShell 会话，然后运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="b4f13-113">To configure a shared SIP address space, establish a remote PowerShell session with Skype for Business Online, and then run the following cmdlet:</span></span>
```powershell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```
<span data-ttu-id="b4f13-114">若要建立与 Skype for Business Online 的远程 PowerShell 会话，首先需要安装适用于 Windows PowerShell 的 Skype for Business Online 模块，可在此处下载： [http://go.microsoft.com/fwlink/p/?LinkId=391911](http://go.microsoft.com/fwlink/p/?linkid=391911)。</span><span class="sxs-lookup"><span data-stu-id="b4f13-114">To establish a remote PowerShell session with Skype for Business Online, you first need to install the Skype for Business Online module for Windows PowerShell, which you can get here: [http://go.microsoft.com/fwlink/p/?LinkId=391911](http://go.microsoft.com/fwlink/p/?linkid=391911).</span></span>

<span data-ttu-id="b4f13-115">安装该模块后，您可以使用下列 cmdlet 建立远程会话：</span><span class="sxs-lookup"><span data-stu-id="b4f13-115">After you install the module, you can establish a remote session with the following cmdlets:</span></span>

   ```powershell
    Import-Module LyncOnlineConnector
   ```

   ```powershell
    $cred = Get-Credential
   ``` 

   ```powershell
    $CSSession = New-CsOnlineSession -Credential $cred
   ```

   ```powershell
    Import-PSSession $CSSession -AllowClobber
   ```

<span data-ttu-id="b4f13-116">有关如何建立与 Skype for Business Online 的远程 PowerShell 会话的详细信息，请参阅[使用 Windows PowerShell 连接到 skype for Business online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="b4f13-116">For more information about how to establish a remote PowerShell session with Skype for Business Online, see [Connecting to Skype for Business Online by using Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

<span data-ttu-id="b4f13-117">有关使用 Skype for Business Online PowerShell 模块的详细信息，请参阅[使用 Windows PowerShell 管理 skype For Business online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="b4f13-117">For more information about using the Skype for Business Online PowerShell module, see [Using Windows PowerShell to manage Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b4f13-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b4f13-118">See Also</span></span>


[<span data-ttu-id="b4f13-119">新-CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="b4f13-119">New-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

