---
title: 配置中介服务器
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Configure Mediation Server
ms:assetid: 583236fd-33cd-4045-81df-baa58ed07779
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204913(v=OCS.15)
ms:contentKeyID: 48184207
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82da1720cab2e6895c53565da17c9411faabdfbd
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754530"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-mediation-server"></a><span data-ttu-id="3a366-102">配置中介服务器</span><span class="sxs-lookup"><span data-stu-id="3a366-102">Configure Mediation Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3a366-103">_**上次修改的主题：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="3a366-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="3a366-104">此过程详细介绍了将 Lync Server 2013 池配置为使用 Lync Server 2013 中介服务器（而不是旧版 Office 通信服务器 2007 R2 中介服务器）的步骤。</span><span class="sxs-lookup"><span data-stu-id="3a366-104">This procedure details the steps to configure the Lync Server 2013 pool to use the Lync Server 2013 Mediation Server, instead of the legacy Office Communications Server 2007 R2 Mediation Server.</span></span>

<span data-ttu-id="3a366-105">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span><span class="sxs-lookup"><span data-stu-id="3a366-105">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="3a366-106">It is also possible to delegate the proper administrator rights and permissions for adding server roles.</span><span class="sxs-lookup"><span data-stu-id="3a366-106">It is also possible to delegate the proper administrator rights and permissions for adding server roles.</span></span> <span data-ttu-id="3a366-107">For details, see Delegate Setup Permissions in the Standard Edition server or Enterprise Edition server Deployment documentation.</span><span class="sxs-lookup"><span data-stu-id="3a366-107">For details, see Delegate Setup Permissions in the Standard Edition server or Enterprise Edition server Deployment documentation.</span></span> <span data-ttu-id="3a366-108">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span><span class="sxs-lookup"><span data-stu-id="3a366-108">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3a366-109">有关查找适用于 Lync Server 2013 的合格 PSTN 网关、IP Pbx 和 SIP 中继服务的最新信息，请参阅 at 中的 "Microsoft 统一通信开放互操作性计划" <A href="https://go.microsoft.com/fwlink/p/?linkid=206015">https://go.microsoft.com/fwlink/p/?linkId=206015</A> 。</span><span class="sxs-lookup"><span data-stu-id="3a366-109">For the latest information on finding qualified PSTN gateways, IP-PBXs, and SIP trunking services that work with Lync Server 2013, see "Microsoft Unified Communications Open Interoperability Program" at <A href="https://go.microsoft.com/fwlink/p/?linkid=206015">https://go.microsoft.com/fwlink/p/?linkId=206015</A>.</span></span>



</div>

<div>

## <a name="to-configure-mediation-server-using-topology-builder"></a><span data-ttu-id="3a366-110">使用拓扑生成器配置中介服务器</span><span class="sxs-lookup"><span data-stu-id="3a366-110">To configure Mediation Server Using Topology Builder</span></span>

1.  <span data-ttu-id="3a366-111">从拓扑生成器中打开现有拓扑。</span><span class="sxs-lookup"><span data-stu-id="3a366-111">Open an existing topology from Topology Builder.</span></span>

2.  <span data-ttu-id="3a366-112">在左窗格中，导航到“PSTN 网关”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3a366-112">In the left pane, navigate to **PSTN gateways**.</span></span>

3.  <span data-ttu-id="3a366-113">右键单击“PSTN 网关”\*\*\*\*，然后单击“新建 IP/PSTN 网关”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3a366-113">Right-click **PSTN gateways**, and then click **New IP/PSTN Gateway**.</span></span>

4.  <span data-ttu-id="3a366-114">参考以下信息，完成“定义新的 IP/PSTN 网关”\*\*\*\* 页：</span><span class="sxs-lookup"><span data-stu-id="3a366-114">Complete the **Define New IP/PSTN Gateway** page with the following information:</span></span>
    
      - <span data-ttu-id="3a366-115">Enter the gateway FQDN or IP address.</span><span class="sxs-lookup"><span data-stu-id="3a366-115">Enter the gateway FQDN or IP address.</span></span> <span data-ttu-id="3a366-116">The FQDN of the gateway is required if the gateway uses the TLS protocol.</span><span class="sxs-lookup"><span data-stu-id="3a366-116">The FQDN of the gateway is required if the gateway uses the TLS protocol.</span></span>
    
      - <span data-ttu-id="3a366-117">接受“IP/PSTN 网关的侦听端口”\*\*\*\* 的默认值，或者输入新侦听端口（如果已修改）。</span><span class="sxs-lookup"><span data-stu-id="3a366-117">Accept the default value of the **Listening port for IP/PSTN gateway** or enter the new listening port if it was modified.</span></span>
    
      - <span data-ttu-id="3a366-118">设置“SIP 传输协议”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3a366-118">Set the **Sip Transport Protocol**.</span></span>

5.  <span data-ttu-id="3a366-119">在左窗格中，导航到“Enterprise Edition 前端池”\*\*\*\* 或“Standard Edition Server”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3a366-119">In the left pane, navigate to the **Enterprise Edition Front End pool** or the **Standard Edition Server**.</span></span>

6.  <span data-ttu-id="3a366-120">右键单击该池，然后单击“编辑属性”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3a366-120">Right-click the pool, and then click **Edit Properties**.</span></span>

7.  <span data-ttu-id="3a366-121">在“中介服务器”\*\*\*\* 下，设置“侦听端口”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3a366-121">Under **Mediation Server**, set the **Listening ports**.</span></span>

8.  <span data-ttu-id="3a366-122">接下来，选择新创建的 PSTN 网关，然后单击“添加”\*\*\*\*，以关联该网关。</span><span class="sxs-lookup"><span data-stu-id="3a366-122">Next, associate the newly created PSTN gateway by selecting it and clicking **Add**.</span></span>

9.  <span data-ttu-id="3a366-123">在“拓扑生成器”\*\*\*\* 中，选择最顶层节点“Lync Server”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3a366-123">In **Topology Builder**, select the top-most node **Lync Server**.</span></span>

10. <span data-ttu-id="3a366-124">从“操作”\*\*\*\* 菜单中，选择“发布拓扑”\*\*\*\*，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3a366-124">From the **Action** menu, select **Publish Topology** and then click **Next**.</span></span>

11. <span data-ttu-id="3a366-125">“发布向导”\*\*\*\* 完成时，单击“完成”\*\*\*\* 关闭向导。</span><span class="sxs-lookup"><span data-stu-id="3a366-125">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3a366-126">请务必填写下一个主题，将<A href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">语音路由更改为使用新的 Lync server 2013 中介服务器</A>，以确保语音路由指向正确的中介服务器。</span><span class="sxs-lookup"><span data-stu-id="3a366-126">It is important that you complete the next topic, <A href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">Change voice routes to use the new Lync Server 2013 Mediation Server</A> to ensure that the voice routes are pointing to the correct Mediation Server.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

