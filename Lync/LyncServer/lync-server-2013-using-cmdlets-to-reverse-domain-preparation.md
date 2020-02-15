---
title: Lync Server 2013：使用 cmdlet 还原域准备
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using cmdlets to reverse domain preparation
ms:assetid: 014dba5d-fcb3-44c9-9d63-ae0755276dac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398071(v=OCS.15)
ms:contentKeyID: 48183227
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c280cdcaa9d06b9ce7eee02cb043ecba0a9deb8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041251"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-cmdlets-to-reverse-domain-preparation-for-lync-server-2013"></a><span data-ttu-id="13e65-102">使用 cmdlet 对 Lync Server 2013 执行反向域准备</span><span class="sxs-lookup"><span data-stu-id="13e65-102">Using cmdlets to reverse domain preparation for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="13e65-103">_**上次修改的主题：** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="13e65-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="13e65-104">使用 **Disable-CsAdDomain** cmdlet 可反向执行域准备步骤。</span><span class="sxs-lookup"><span data-stu-id="13e65-104">Use the **Disable-CsAdDomain** cmdlet to reverse the domain preparation step.</span></span>

<div>

## <a name="to-use-cmdlets-to-reverse-domain-preparation"></a><span data-ttu-id="13e65-105">使用 cmdlet 反向执行域准备</span><span class="sxs-lookup"><span data-stu-id="13e65-105">To use cmdlets to reverse domain preparation</span></span>

1.  <span data-ttu-id="13e65-106">以 Domain Admins 组成员的身份登录域中的任何服务器。</span><span class="sxs-lookup"><span data-stu-id="13e65-106">Log on to any server in the domain as a member of the Domain Admins group.</span></span>

2.  <span data-ttu-id="13e65-107">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="13e65-107">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="13e65-108">以</span><span class="sxs-lookup"><span data-stu-id="13e65-108">Run:</span></span>
    
        Disable-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-Force <SwitchParameter>] 
        [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>] 
    
    <span data-ttu-id="13e65-109">例如：</span><span class="sxs-lookup"><span data-stu-id="13e65-109">For example:</span></span>
    
        Disable-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.net -Force
    
    <span data-ttu-id="13e65-110">如果 Force 参数存在，即使激活了域中的一个或多个前端服务器或 A/V 会议服务器，也会回滚域准备。</span><span class="sxs-lookup"><span data-stu-id="13e65-110">If the Force parameter is present, domain preparation is rolled back, even if one or more Front End Servers or A/V Conferencing Servers in the domain are activated.</span></span> <span data-ttu-id="13e65-111">如果 Force 参数不存在，则在域中的任何前端服务器或 A/V 会议服务器处于激活状态时，将终止域准备回滚。</span><span class="sxs-lookup"><span data-stu-id="13e65-111">If the Force parameter is not present, domain preparation rollback is terminated if any Front End Servers or A/V Conferencing Servers in the domain are activated.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="13e65-112">参数 GlobalSettingsDomainController 用于指出存储全局设置的位置。</span><span class="sxs-lookup"><span data-stu-id="13e65-112">The parameter GlobalSettingsDomainController allows you to indicate where global settings are stored.</span></span> <span data-ttu-id="13e65-113">如果设置存储在“系统”容器中（通常在全局设置尚未迁移到“配置”容器的升级部署中是这种情况），则定义 Active Directory 林的根中的某个域控制器。</span><span class="sxs-lookup"><span data-stu-id="13e65-113">If your settings are stored in the System container (which is typical with upgrade deployments that have not had the global setting migrated to the Configuration container), you define a domain controller in the root of your Active Directory forest.</span></span> <span data-ttu-id="13e65-114">如果全局设置存储在“配置”容器中（通常在新部署或设置已迁移到“配置”容器的升级部署中是这种情况），则定义林中的任何域控制器。</span><span class="sxs-lookup"><span data-stu-id="13e65-114">If the global settings are in the Configuration container (which is typical with new deployments or upgrade deployments where the settings have been migrated to the Configuration container), you define any domain controller in the forest.</span></span> <span data-ttu-id="13e65-115">如果不指定此参数，则 cmdlet 假定设置存储在配置容器中，并引用 AD&nbsp;DS 中的任何域控制器。</span><span class="sxs-lookup"><span data-stu-id="13e65-115">If you do not specify this parameter, the cmdlet assumes that the settings are stored in the Configuration container and refers to any domain controller in AD&nbsp;DS.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="13e65-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="13e65-116">See Also</span></span>


[<span data-ttu-id="13e65-117">为 Lync Server 2013 运行域准备</span><span class="sxs-lookup"><span data-stu-id="13e65-117">Running domain preparation for Lync Server 2013</span></span>](lync-server-2013-running-domain-preparation.md)  


[<span data-ttu-id="13e65-118">准备 Lync Server 2013 的域</span><span class="sxs-lookup"><span data-stu-id="13e65-118">Preparing domains for Lync Server 2013</span></span>](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

