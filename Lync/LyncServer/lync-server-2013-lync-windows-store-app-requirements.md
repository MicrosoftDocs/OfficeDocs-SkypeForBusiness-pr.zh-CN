---
title: Lync Server 2013： Lync Windows 应用商店应用要求
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
ms.openlocfilehash: 9cc1ab2b397111cef1040592f29a11d55e5f1f64
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765320"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-windows-store-app-requirements-for-lync-server-2013"></a><span data-ttu-id="640b8-102">Lync Server 2013 的 lync Windows 应用商店应用要求</span><span class="sxs-lookup"><span data-stu-id="640b8-102">Lync Windows Store app requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="640b8-103">_**主题上次修改时间：** 2013-12-03_</span><span class="sxs-lookup"><span data-stu-id="640b8-103">_**Topic Last Modified:** 2013-12-03_</span></span>

<span data-ttu-id="640b8-104">具有 Lync Server 的本地部署的组织必须满足以下要求才能支持 Lync Windows 应用商店应用。</span><span class="sxs-lookup"><span data-stu-id="640b8-104">Organizations with an on-premises deployment of Lync Server must meet the following requirements to support Lync Windows Store app.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="640b8-105">对于 lync server 2010，请运行 lync server 2010 的累积更新：年2月2012（可在<A class=uri href="http://go.microsoft.com/fwlink/?linkid=3052%26kbid=2670352"> http://go.microsoft.com/fwlink/?linkid=3052&ampkbid = 2670352</A>）或更高版本的所有服务器上运行。</span><span class="sxs-lookup"><span data-stu-id="640b8-105">For Lync Server 2010, run the cumulative update for Lync Server 2010: February 2012 (available at <A class=uri href="http://go.microsoft.com/fwlink/?linkid=3052%26kbid=2670352">http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2670352</A>) or later on all servers.</span></span> <span data-ttu-id="640b8-106">若要使用户能够加入会议，请运行 Lync Server 2010 的累积更新：服务器上的10月2012（适用于<A class=uri href="http://go.microsoft.com/fwlink/?linkid=3052%26kbid=2737915"> http://go.microsoft.com/fwlink/?linkid=3052&amp; kbid = 2737915</A>）。</span><span class="sxs-lookup"><span data-stu-id="640b8-106">To enable users to join meetings, run the cumulative update for Lync Server 2010: October 2012 (available at <A class=uri href="http://go.microsoft.com/fwlink/?linkid=3052%26kbid=2737915">http://go.microsoft.com/fwlink/?linkid=3052&amp;kbid=2737915</A>) on the servers.</span></span>



</div>

  - <span data-ttu-id="640b8-107">在服务器上启用自动发现、Lync Web App 和 Web 票证服务。</span><span class="sxs-lookup"><span data-stu-id="640b8-107">Enable the Autodiscover, Lync Web App, and Web Ticket services on the server.</span></span>

  - <span data-ttu-id="640b8-108">在前端服务器或前端池上启用证书身份验证。</span><span class="sxs-lookup"><span data-stu-id="640b8-108">Enable certificate authentication on the Front End Server or Front End pool.</span></span> <span data-ttu-id="640b8-109">（前端服务器或前端池中的用户注册过程通常称为注册机构。）有关详细信息，请参阅[在 Lync Server 2013 中创建注册机构配置设置](lync-server-2013-create-registrar-configuration-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="640b8-109">(The user registration process on the Front End Server or Front End pool is often referred to as the registrar.) For details, see [Create Registrar configuration settings in Lync Server 2013](lync-server-2013-create-registrar-configuration-settings.md).</span></span>

  - <span data-ttu-id="640b8-110">为自动发现服务发布 DNS 别名（CNAME）资源记录。</span><span class="sxs-lookup"><span data-stu-id="640b8-110">Publish the DNS alias (CNAME) resource records for the Autodiscover service.</span></span>

  - <span data-ttu-id="640b8-111">不再需要确保颁发给 Lync 服务器的证书的证书吊销列表（CRL）分发点（CDP）指向 HTTP 资源，而不是 LDAP 资源。</span><span class="sxs-lookup"><span data-stu-id="640b8-111">It is no longer a requirement to make sure the Certificate Revocation List (CRL) Distribution Point (CDP) for the certificates issued to Lync server points to an HTTP resource instead of an LDAP resource.</span></span> <span data-ttu-id="640b8-112">但是，请确保客户端计算机安装了最新的 Windows 更新。</span><span class="sxs-lookup"><span data-stu-id="640b8-112">However, make sure that client computers have the latest Windows updates installed.</span></span>

  - <span data-ttu-id="640b8-113">配置企业中的 HTTP 代理以允许 Lync server 相关的 HTTP 流量。</span><span class="sxs-lookup"><span data-stu-id="640b8-113">Configure HTTP proxies in the enterprise to allow Lync server related HTTP traffic.</span></span><span data-ttu-id="640b8-114">为自动发现、Lync Web App 和 WebTicket 服务添加例外（如有必要）。</span><span class="sxs-lookup"><span data-stu-id="640b8-114">  Add exceptions for the Autodiscover, Lync Web App, and WebTicket services, if necessary.</span></span>

  - <span data-ttu-id="640b8-115">在客户端上，安装 Windows 8.1 和最新版本的 Lync Windows 应用商店应用以修复通常在使用多个域时出现的登录问题（例如，当 SIP URI **userA@domainZ.com** ，而边缘服务器为**sip.domainX.com**）时。</span><span class="sxs-lookup"><span data-stu-id="640b8-115">On clients, install Windows 8.1 and the latest version of Lync Windows Store app to fix a sign-in issue that generally occurs when using multiple domains (for example, when the SIP URI is **userA@domainZ.com** but the Edge Server is **sip.domainX.com**).</span></span>

<span data-ttu-id="640b8-116">如果你的组织订阅了 Lync Online 或 Office 365，并且你使用自己的域名，则必须执行一些额外的步骤来设置你的网络，以便自动发现 Lync 服务器。</span><span class="sxs-lookup"><span data-stu-id="640b8-116">If your organization subscribes to Lync Online or Office 365 and you are using your own domain name, you must take some extra steps to set up your network for autodiscovery of the Lync servers.</span></span> <span data-ttu-id="640b8-117">在移动设备上，Lync Windows 应用商店应用和 Lync 的网络配置要求相同。</span><span class="sxs-lookup"><span data-stu-id="640b8-117">The network configuration requirements are the same for Lync Windows Store app and Lync on mobile devices.</span></span> <span data-ttu-id="640b8-118">请按照 Office 365 wiki 文章 "设置 Lync 移动设备" 中的说明 "设置网络" 中的说明进行操作[http://go.microsoft.com/fwlink/?LinkId=271822](http://go.microsoft.com/fwlink/?linkid=271822)。</span><span class="sxs-lookup"><span data-stu-id="640b8-118">Follow the instructions “Set up your network” in the Office 365 wiki article “Set up Lync mobile devices,” available at [http://go.microsoft.com/fwlink/?LinkId=271822](http://go.microsoft.com/fwlink/?linkid=271822).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="640b8-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="640b8-119">See Also</span></span>


[<span data-ttu-id="640b8-120">在 Lync Server 2013 中部署 Lync Windows 应用商店应用</span><span class="sxs-lookup"><span data-stu-id="640b8-120">Deploying Lync Windows Store app in Lync Server 2013</span></span>](lync-server-2013-deploying-lync-windows-store-app.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

