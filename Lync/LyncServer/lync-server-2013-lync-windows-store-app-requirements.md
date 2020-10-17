---
title: Lync Server 2013： Lync Windows 应用商店应用要求
description: Lync Server 2013： Lync Windows 应用商店应用要求。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Windows Store app requirements
ms:assetid: 5f2e0a40-8450-4f61-b6f6-913fc1906020
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ823129(v=OCS.15)
ms:contentKeyID: 50120200
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 17e8705a55625bcf0ad099ead1000a82c994d867
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566498"
---
# <a name="lync-windows-store-app-requirements-for-lync-server-2013"></a><span data-ttu-id="de29f-103">Lync Server 2013 的 lync Windows 应用商店应用程序要求</span><span class="sxs-lookup"><span data-stu-id="de29f-103">Lync Windows Store app requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="de29f-104">_**上次修改的主题：** 2013-12-03_</span><span class="sxs-lookup"><span data-stu-id="de29f-104">_**Topic Last Modified:** 2013-12-03_</span></span>

<span data-ttu-id="de29f-105">具有 Lync Server 的本地部署的组织必须满足以下要求才能支持 Lync Windows 应用商店应用。</span><span class="sxs-lookup"><span data-stu-id="de29f-105">Organizations with an on-premises deployment of Lync Server must meet the following requirements to support Lync Windows Store app.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="de29f-106">对于 Lync Server 2010，请运行 Lync Server 2010 的累积更新：2月 2012 (在所有服务器上都可用<A class=uri href="https://go.microsoft.com/fwlink/?linkid=3052%26kbid=2670352"> https://go.microsoft.com/fwlink/?linkid=3052&amp ; http://go.microsoft.com/fwlink/?linkid=3052&kbid=823018 = 2670352</A>) 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="de29f-106">For Lync Server 2010, run the cumulative update for Lync Server 2010: February 2012 (available at <A class=uri href="https://go.microsoft.com/fwlink/?linkid=3052%26kbid=2670352">https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2670352</A>) or later on all servers.</span></span> <span data-ttu-id="de29f-107">若要使用户能够加入会议，请运行 Lync Server 2010 的累积更新：10月 2012 (<A class=uri href="https://go.microsoft.com/fwlink/?linkid=3052%26kbid=2737915"> https://go.microsoft.com/fwlink/?linkid=3052&amp ; http://go.microsoft.com/fwlink/?linkid=3052&kbid=823018 = 2737915</A>) 在服务器上可用。</span><span class="sxs-lookup"><span data-stu-id="de29f-107">To enable users to join meetings, run the cumulative update for Lync Server 2010: October 2012 (available at <A class=uri href="https://go.microsoft.com/fwlink/?linkid=3052%26kbid=2737915">https://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2737915</A>) on the servers.</span></span>



</div>

  - <span data-ttu-id="de29f-108">在服务器上启用自动发现、Lync Web 应用和 Web 票证服务。</span><span class="sxs-lookup"><span data-stu-id="de29f-108">Enable the Autodiscover, Lync Web App, and Web Ticket services on the server.</span></span>

  - <span data-ttu-id="de29f-109">在前端服务器或前端池上启用证书身份验证。</span><span class="sxs-lookup"><span data-stu-id="de29f-109">Enable certificate authentication on the Front End Server or Front End pool.</span></span> <span data-ttu-id="de29f-110"> (前端服务器或前端池上的用户注册过程通常称为 "注册器"。 ) 有关详细信息，请参阅 [在 Lync Server 2013 中创建注册器配置设置](lync-server-2013-create-registrar-configuration-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="de29f-110">(The user registration process on the Front End Server or Front End pool is often referred to as the registrar.) For details, see [Create Registrar configuration settings in Lync Server 2013](lync-server-2013-create-registrar-configuration-settings.md).</span></span>

  - <span data-ttu-id="de29f-111">为自动发现服务 (CNAME) 资源记录发布 DNS 别名。</span><span class="sxs-lookup"><span data-stu-id="de29f-111">Publish the DNS alias (CNAME) resource records for the Autodiscover service.</span></span>

  - <span data-ttu-id="de29f-112">不再要求确保颁发给 Lync server 的证书的证书吊销列表 (CRL) 分发点 (CDP) 指向 HTTP 资源，而不是 LDAP 资源。</span><span class="sxs-lookup"><span data-stu-id="de29f-112">It is no longer a requirement to make sure the Certificate Revocation List (CRL) Distribution Point (CDP) for the certificates issued to Lync server points to an HTTP resource instead of an LDAP resource.</span></span> <span data-ttu-id="de29f-113">但是，请确保客户端计算机安装了最新的 Windows 更新。</span><span class="sxs-lookup"><span data-stu-id="de29f-113">However, make sure that client computers have the latest Windows updates installed.</span></span>

  - <span data-ttu-id="de29f-114">配置企业中的 HTTP 代理以允许与 Lync server 相关的 HTTP 流量。</span><span class="sxs-lookup"><span data-stu-id="de29f-114">Configure HTTP proxies in the enterprise to allow Lync server related HTTP traffic.</span></span><span data-ttu-id="de29f-115">如有必要，请添加自动发现、Lync Web App 和 Web 票证服务的例外。</span><span class="sxs-lookup"><span data-stu-id="de29f-115">  Add exceptions for the Autodiscover, Lync Web App, and WebTicket services, if necessary.</span></span>

  - <span data-ttu-id="de29f-116">在客户端上，安装 Windows 8.1 和最新版本的 Lync Windows 应用商店应用程序，修复通常会在使用多个域时出现的登录问题 (例如，当 SIP URI 为 **userA@domainZ.com** ，而边缘服务器 **sip.domainX.com**) 。</span><span class="sxs-lookup"><span data-stu-id="de29f-116">On clients, install Windows 8.1 and the latest version of Lync Windows Store app to fix a sign-in issue that generally occurs when using multiple domains (for example, when the SIP URI is **userA@domainZ.com** but the Edge Server is **sip.domainX.com**).</span></span>

<span data-ttu-id="de29f-117">如果你的组织订阅 Lync Online 或 Microsoft 365，并且你使用的是你自己的域名，则必须执行一些额外的步骤来设置你的网络以自动发现 Lync 服务器。</span><span class="sxs-lookup"><span data-stu-id="de29f-117">If your organization subscribes to Lync Online or Microsoft 365 and you are using your own domain name, you must take some extra steps to set up your network for autodiscovery of the Lync servers.</span></span> <span data-ttu-id="de29f-118">在移动设备上，Lync Windows 应用商店应用和 Lync 的网络配置要求相同。</span><span class="sxs-lookup"><span data-stu-id="de29f-118">The network configuration requirements are the same for Lync Windows Store app and Lync on mobile devices.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="de29f-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="de29f-119">See Also</span></span>


[<span data-ttu-id="de29f-120">在 Lync Server 2013 中部署 Lync Windows 应用商店应用</span><span class="sxs-lookup"><span data-stu-id="de29f-120">Deploying Lync Windows Store app in Lync Server 2013</span></span>](lync-server-2013-deploying-lync-windows-store-app.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>
