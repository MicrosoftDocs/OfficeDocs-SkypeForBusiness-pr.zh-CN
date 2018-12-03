---
title: 配置中介服务器
TOCTitle: Configure Mediation Server
ms:assetid: 583236fd-33cd-4045-81df-baa58ed07779
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204913(v=OCS.15)
ms:contentKeyID: 48184207
ms.date: 07/23/2014
mtps_version: v=OCS.15
ms.openlocfilehash: 143d98cebc151473b790246bc78d75e6e2f4185a
ms.sourcegitcommit: a599bdd5057c4fc38e14b4f14961e1a6bf08ee8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/05/2018
ms.locfileid: "27128164"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-mediation-server"></a><span data-ttu-id="8a7b8-102">配置中介服务器</span><span class="sxs-lookup"><span data-stu-id="8a7b8-102">Configure Mediation Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="8a7b8-103">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="8a7b8-103"></span></span>

<span data-ttu-id="8a7b8-104">_**主题上次修改时间：** 2012年-09-28_</span><span class="sxs-lookup"><span data-stu-id="8a7b8-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="8a7b8-105">该过程详细说明 Lync Server 2013 池配置为使用 Lync Server 2013 中介服务器，而不是旧 Office Communications Server 2007 R2 中介服务器的步骤。</span><span class="sxs-lookup"><span data-stu-id="8a7b8-105">This procedure details the steps to configure the Lync Server 2013 pool to use the Lync Server 2013 Mediation Server, instead of the legacy Office Communications Server 2007 R2 Mediation Server.</span></span>

<span data-ttu-id="8a7b8-106">若要成功发布、 启用或禁用拓扑时添加或删除服务器角色，应以 RTCUniversalServerAdmins 和 Domain Admins 组成员的用户身份登录。</span><span class="sxs-lookup"><span data-stu-id="8a7b8-106">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="8a7b8-107">还有可能要委派的相应的管理员权限和权限添加服务器角色。</span><span class="sxs-lookup"><span data-stu-id="8a7b8-107">It is also possible to delegate the proper administrator rights and permissions for adding server roles.</span></span> <span data-ttu-id="8a7b8-108">有关详细信息，请参阅 Standard Edition server 或 Enterprise Edition server 部署文档中的委派安装权限。</span><span class="sxs-lookup"><span data-stu-id="8a7b8-108">For details, see Delegate Setup Permissions in the Standard Edition server or Enterprise Edition server Deployment documentation.</span></span> <span data-ttu-id="8a7b8-109">其他配置更改，需要的只是 RTCUniversalServerAdmins 组中的成员。</span><span class="sxs-lookup"><span data-stu-id="8a7b8-109">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8a7b8-110">查找合格的 PSTN 网关、 Ip-pbx 和 SIP 中继服务的使用 Lync Server 2013 的最新信息，请参阅"Microsoft 统一通信开放互操作性计划"在<A href="http://go.microsoft.com/fwlink/p/?linkid=206015">http://go.microsoft.com/fwlink/p/?linkId=206015</A>。</span><span class="sxs-lookup"><span data-stu-id="8a7b8-110">For the latest information on finding qualified PSTN gateways, IP-PBXs, and SIP trunking services that work with Lync Server 2013, see "Microsoft Unified Communications Open Interoperability Program" at <A href="http://go.microsoft.com/fwlink/p/?linkid=206015">http://go.microsoft.com/fwlink/p/?linkId=206015</A>.</span></span>



</div>

<div>

## <a name="to-configure-mediation-server-using-topology-builder"></a><span data-ttu-id="8a7b8-111">配置中介服务器使用拓扑生成器</span><span class="sxs-lookup"><span data-stu-id="8a7b8-111">To configure Mediation Server Using Topology Builder</span></span>

1.  <span data-ttu-id="8a7b8-112">从拓扑生成器中打开现有拓扑。</span><span class="sxs-lookup"><span data-stu-id="8a7b8-112">Open an existing topology from Topology Builder.</span></span>

2.  <span data-ttu-id="8a7b8-113">在左窗格中，导航到**PSTN 网关**。</span><span class="sxs-lookup"><span data-stu-id="8a7b8-113">In the left pane, navigate to **PSTN gateways**.</span></span>

3.  <span data-ttu-id="8a7b8-114">**PSTN 网关**，右键单击，然后单击**新建 IP/PSTN 网关**。</span><span class="sxs-lookup"><span data-stu-id="8a7b8-114">Right-click **PSTN gateways**, and then click **New IP/PSTN Gateway**.</span></span>

4.  <span data-ttu-id="8a7b8-115">完成**定义新的 IP/PSTN 网关**页上的以下信息：</span><span class="sxs-lookup"><span data-stu-id="8a7b8-115">Complete the **Define New IP/PSTN Gateway** page with the following information:</span></span>
    
      - <span data-ttu-id="8a7b8-116">输入的网关 FQDN 或 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="8a7b8-116">Enter the gateway FQDN or IP address.</span></span> <span data-ttu-id="8a7b8-117">如果网关使用 TLS 协议，则需要使用网关的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="8a7b8-117">The FQDN of the gateway is required if the gateway uses the TLS protocol.</span></span>
    
      - <span data-ttu-id="8a7b8-118">接受默认值的**IP/PSTN 网关的侦听端口**或输入新的侦听端口，如果已修改。</span><span class="sxs-lookup"><span data-stu-id="8a7b8-118">Accept the default value of the **Listening port for IP/PSTN gateway** or enter the new listening port if it was modified.</span></span>
    
      - <span data-ttu-id="8a7b8-119">设置**Sip 传输协议**。</span><span class="sxs-lookup"><span data-stu-id="8a7b8-119">Set the **Sip Transport Protocol**.</span></span>

5.  <span data-ttu-id="8a7b8-120">在左窗格中，导航到**Enterprise Edition 前端池**或**Standard Edition Server**。</span><span class="sxs-lookup"><span data-stu-id="8a7b8-120">In the left pane, navigate to the **Enterprise Edition Front End pool** or the **Standard Edition Server**.</span></span>

6.  <span data-ttu-id="8a7b8-121">右键单击池，，，然后单击**编辑属性**。</span><span class="sxs-lookup"><span data-stu-id="8a7b8-121">Right-click the pool, and then click **Edit Properties**.</span></span>

7.  <span data-ttu-id="8a7b8-122">在**中介服务器\*\*\*\*侦听端口**的设置。</span><span class="sxs-lookup"><span data-stu-id="8a7b8-122">Under **Mediation Server**, set the **Listening ports**.</span></span>

8.  <span data-ttu-id="8a7b8-123">接下来，通过选择并单击**添加**关联的新创建的 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="8a7b8-123">Next, associate the newly created PSTN gateway by selecting it and clicking **Add**.</span></span>

9.  <span data-ttu-id="8a7b8-124">在**拓扑生成器**中，选择顶层节点**Lync Server**。</span><span class="sxs-lookup"><span data-stu-id="8a7b8-124">In **Topology Builder**, select the top-most node **Lync Server**.</span></span>

10. <span data-ttu-id="8a7b8-125">从**操作**菜单中，选择**发布拓扑**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="8a7b8-125">From the **Action** menu, select **Publish Topology** and then click **Next**.</span></span>

11. <span data-ttu-id="8a7b8-126">**发布向导**完成后，单击**完成**以关闭向导。</span><span class="sxs-lookup"><span data-stu-id="8a7b8-126">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8a7b8-127">请务必完成下一主题，<A href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">更改语音路由以使用新的 Lync Server 2013 中介服务器</A>，以确保语音路由指向正确的中介服务器。</span><span class="sxs-lookup"><span data-stu-id="8a7b8-127">It is important that you complete the next topic, <A href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">Change voice routes to use the new Lync Server 2013 Mediation Server</A> to ensure that the voice routes are pointing to the correct Mediation Server.</span></span>



<span data-ttu-id="8a7b8-128"></div>

</div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="8a7b8-128"></span></span></div>

