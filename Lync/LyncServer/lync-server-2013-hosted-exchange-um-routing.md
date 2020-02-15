---
title: Lync Server 2013：托管 Exchange UM 路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange UM routing
ms:assetid: 6c90dc8b-6aef-4ce8-b483-37c7b5a553c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398512(v=OCS.15)
ms:contentKeyID: 48184422
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 57efdcebe52f9b32f30c22ebcbf107d3cd9d8a7d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008374"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-um-routing-in-lync-server-2013"></a><span data-ttu-id="45305-102">Lync Server 2013 中的托管 Exchange UM 路由</span><span class="sxs-lookup"><span data-stu-id="45305-102">Hosted Exchange UM routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="45305-103">_**上次修改的主题：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="45305-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="45305-104">Exchange UM 路由应用程序在前端服务器上运行，以将呼叫路由到本地 Microsoft Exchange Server 统一消息（UM）部署或托管 Exchange UM 服务。</span><span class="sxs-lookup"><span data-stu-id="45305-104">The Exchange UM Routing application runs on the Front End Server to route calls, either to an on-premises Microsoft Exchange Server Unified Messaging (UM) deployment or to hosted Exchange UM service.</span></span>

<div>

## <a name="the-exum-routing-application"></a><span data-ttu-id="45305-105">ExUM 路由应用程序</span><span class="sxs-lookup"><span data-stu-id="45305-105">The ExUM Routing Application</span></span>

<span data-ttu-id="45305-106">Lync Server 2013 Exchange UM 路由应用程序使用用户帐户设置中的信息和托管的语音邮件策略参数来确定如何路由托管语音邮件的呼叫，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="45305-106">The Lync Server 2013 Exchange UM Routing application uses information from user account settings and from hosted voice mail policy parameters to determine how to route calls for hosted voice messaging, as shown in the following diagram.</span></span>

<span data-ttu-id="45305-107">**混合部署 Exchange UM 路由示例**</span><span class="sxs-lookup"><span data-stu-id="45305-107">**Example of mixed deployment Exchange UM routing**</span></span>

<span data-ttu-id="45305-108">![本地 Lync Server Exchange UM 部署](images/Gg398512.75258286-1f23-487b-bf46-d8538e7d540e(OCS.15).jpg "本地 Lync Server Exchange UM 部署")</span><span class="sxs-lookup"><span data-stu-id="45305-108">![On-premises Lync Server Exchange UM deployment](images/Gg398512.75258286-1f23-487b-bf46-d8538e7d540e(OCS.15).jpg "On-premises Lync Server Exchange UM deployment")</span></span>

<span data-ttu-id="45305-109">可以将 Exchange UM 路由配置为将呼叫路由到启用了本地 Exchange UM 的用户、已启用托管 Exchange UM 的用户或两者的组合。</span><span class="sxs-lookup"><span data-stu-id="45305-109">Exchange UM routing can be configured to route calls to users who are enabled for on-premises Exchange UM, to users who are enabled for hosted Exchange UM, or to a combination of the two.</span></span>

<span data-ttu-id="45305-110">例如，假设 Roy 的邮箱和 Exchange UM 服务托管在本地 Exchange 部署中。</span><span class="sxs-lookup"><span data-stu-id="45305-110">For example, suppose that Roy’s mailbox and Exchange UM service are homed in an on-premises Exchange deployment.</span></span>

  - <span data-ttu-id="45305-111">来自 Roy 的用户帐户的代理地址信息提供了 ExUM 路由应用程序用来将他的呼叫路由到内部部署 Exchange UM 服务器的信息。</span><span class="sxs-lookup"><span data-stu-id="45305-111">The proxy address information from Roy’s user account provides the information that the ExUM Routing application uses to route his calls to an on-premises Exchange UM server.</span></span>

<span data-ttu-id="45305-112">Alice 的邮箱和 Exchange UM 服务位于托管的 Exchange 服务提供商的数据中心。</span><span class="sxs-lookup"><span data-stu-id="45305-112">Alice’s mailbox and Exchange UM service are located at a hosted Exchange service provider’s data center.</span></span> <span data-ttu-id="45305-113">Exchange UM 呼叫的路由配置如下：</span><span class="sxs-lookup"><span data-stu-id="45305-113">Routing for her Exchange UM calls is configured as follows:</span></span>

  - <span data-ttu-id="45305-114">Alice 的用户帐户的 msExchUCVoiceMailSettings 属性中设置的值通知 ExUM 路由应用程序，在托管语音邮件策略中检查路由详细信息。</span><span class="sxs-lookup"><span data-stu-id="45305-114">The values set in the msExchUCVoiceMailSettings attribute of Alice’s user account tell the ExUM Routing application to check for routing details in a hosted voice mail policy.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="45305-115">MsExchUCVoiceMailSettings 属性的值可由 Exchange 服务提供商或 Lync Server 2013 管理员进行设置。</span><span class="sxs-lookup"><span data-stu-id="45305-115">The value of the msExchUCVoiceMailSettings attribute can be set by either the Exchange service provider or the Lync Server 2013 administrator.</span></span> <span data-ttu-id="45305-116">在上图所示的示例中，"值（CsHostedVoiceMail = 1）" 由 Lync Server 2013 管理员设置为为 Alice 启用托管语音邮件。</span><span class="sxs-lookup"><span data-stu-id="45305-116">In the example shown in the preceding diagram, the value (CsHostedVoiceMail=1) was set by the Lync Server 2013 administrator to enable hosted voice mail for Alice.</span></span> <span data-ttu-id="45305-117">有关此属性的详细信息，请参阅<A href="lync-server-2013-hosted-exchange-user-management.md">Lync Server 2013 中的托管 Exchange 用户管理</A>。</span><span class="sxs-lookup"><span data-stu-id="45305-117">For details about this attribute, see <A href="lync-server-2013-hosted-exchange-user-management.md">Hosted Exchange user management in Lync Server 2013</A>.</span></span>

    
    </div>

  - <span data-ttu-id="45305-118">分配给 Alice 的用户帐户的托管语音邮件策略提供了路由详细信息：</span><span class="sxs-lookup"><span data-stu-id="45305-118">The hosted voice mail policy that is assigned to Alice’s user account provides routing details:</span></span>
    
      - <span data-ttu-id="45305-119">目标是托管 Exchange UM 服务提供商（ls。ExUm.\<在\>此示例中为 hostedExchangeServer）。</span><span class="sxs-lookup"><span data-stu-id="45305-119">Destination is the hosted Exchange UM service provider (ls.ExUm.\<hostedExchangeServer\>.com in this example).</span></span>
    
      - <span data-ttu-id="45305-120">组织由租户 Id 标识，这些 Id 是位于 ls 上的 Exchange Server 租户的 SIP 消息的路由 Fqdn。ExUm.\<hostedExchangeServer\>（在此示例中为 corp.contoso.com 和 corp.litwareinc.com）。</span><span class="sxs-lookup"><span data-stu-id="45305-120">Organizations are identified by the tenant IDs, which are the routing FQDNs for SIP messages for Exchange Server tenants that are located on ls.ExUm.\<hostedExchangeServer\>.com (corp.contoso.com and corp.litwareinc.com in this example).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="45305-121">Exchange Online 的 FQDN 为 exap.um.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="45305-121">The FQDN for Exchange Online is exap.um.outlook.com.</span></span>

        
        </div>
        
        <span data-ttu-id="45305-122">有关详细信息，请参阅[Lync Server 2013 中的托管语音邮件策略](lync-server-2013-hosted-voice-mail-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="45305-122">For details, see [Hosted voice mail policies in Lync Server 2013](lync-server-2013-hosted-voice-mail-policies.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="45305-123">如果用户帐户中同时存在 msExchUCVoiceMailSettings 属性和 UM 代理地址设置，则优先使用 msExchUCVoiceMailSettings 属性。</span><span class="sxs-lookup"><span data-stu-id="45305-123">If both the msExchUCVoiceMailSettings attribute and the UM proxy address settings are present in a user account, the msExchUCVoiceMailSettings attribute takes precedence.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

