---
title: Lync Server 2013：定义 Survivable Branch Appliance 或 Survivable Branch Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Define a Survivable Branch Appliance or Server
ms:assetid: 1f49cfbe-30b3-4600-af15-47cb2f58d18a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398280(v=OCS.15)
ms:contentKeyID: 48183583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dadaa26f6a951995906ed29ffd0615da16066928
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830719"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-survivable-branch-appliance-or-server-in-lync-server-2013"></a><span data-ttu-id="e0f52-102">在 Lync Server 2013 中定义 Survivable Branch Appliance 或 Survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="e0f52-102">Define a Survivable Branch Appliance or Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e0f52-103">_**主题上次修改时间:** 2012-10-07_</span><span class="sxs-lookup"><span data-stu-id="e0f52-103">_**Topic Last Modified:** 2012-10-07_</span></span>

<span data-ttu-id="e0f52-104">如果在将 Survivable 分支装置或服务器添加到拓扑中时未定义该装置或服务器, 请在中心站点执行此过程。</span><span class="sxs-lookup"><span data-stu-id="e0f52-104">Perform this procedure at the central site if you did not define the Survivable Branch Appliance or Server when you added it to your topology.</span></span>

<div>

## <a name="to-define-a-survivable-branch-appliance-or-survivable-branch-server"></a><span data-ttu-id="e0f52-105">定义 Survivable 分支装置或 Survivable 分支服务器</span><span class="sxs-lookup"><span data-stu-id="e0f52-105">To define a Survivable Branch Appliance or Survivable Branch Server</span></span>

1.  <span data-ttu-id="e0f52-106">单击 "**开始**", 单击 "**所有程序**", 单击 " **Microsoft Lync server 2013**", 然后单击 " **Lync server 拓扑生成器**"。</span><span class="sxs-lookup"><span data-stu-id="e0f52-106">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="e0f52-107">在控制台树中, 展开中心网站, 展开 "**分支网站**", 然后展开您计划在其中部署 Survivable 分支装置或 Survivable 分支服务器的分支站点的名称。</span><span class="sxs-lookup"><span data-stu-id="e0f52-107">In the console tree, expand the central site, expand **Branch sites**, and then expand the name of the branch site where you plan to deploy the Survivable Branch Appliance or Survivable Branch Server.</span></span>

3.  <span data-ttu-id="e0f52-108">右键单击 " **Survivable 分支装置**", 然后单击 "**新建 Survivable 分支装置**"。</span><span class="sxs-lookup"><span data-stu-id="e0f52-108">Right-click **Survivable Branch Appliances**, and then click **New Survivable Branch Appliance**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e0f52-109"><STRONG>Survivable 分支装置</STRONG>可用于定义 Survivable 分支服务器和 Survivable 分支装置。</span><span class="sxs-lookup"><span data-stu-id="e0f52-109"><STRONG>Survivable Branch Appliances</STRONG> is where you define Survivable Branch Servers and Survivable Branch Appliances.</span></span>

    
    </div>

4.  <span data-ttu-id="e0f52-110">在 "**定义 Survivable 分支装置**" 对话框中, 单击 " **FQDN**", 键入将在此分支站点上部署的 Survivable 分支装置或 Survivable 分支服务器的完全限定的域名 (FQDN), 然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="e0f52-110">In the **Define Survivable Branch Appliance** dialog box, click **FQDN**, type the fully qualified domain name (FQDN) of the Survivable Branch Appliance or Survivable Branch Server you will deploy at this branch site, and then click **Next**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e0f52-111">如果要定义 Survivable 分支设备, 则在<STRONG>FQDN</STRONG>中输入的名称必须与分配给<STRONG>ServicePrincipalName</STRONG>属性的 Survivable 分支装置 FQDN 相同。</span><span class="sxs-lookup"><span data-stu-id="e0f52-111">If you are defining a Survivable Branch Appliance, the name you enter in <STRONG>FQDN</STRONG> must be the same as the Survivable Branch Appliance FQDN you assigned to the <STRONG>servicePrincipalName</STRONG> attribute.</span></span> <span data-ttu-id="e0f52-112">有关详细信息, 请参阅<A href="lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md">在 Lync Server 2013 中将 Survivable 分支装置添加到 Active Directory</A>。</span><span class="sxs-lookup"><span data-stu-id="e0f52-112">For details, see <A href="lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md">Add a Survivable Branch Appliance to Active Directory in Lync Server 2013</A>.</span></span>

    
    </div>

5.  <span data-ttu-id="e0f52-113">单击 "**前端池**", 单击此 Survivable 分支设备或 Survivable 分支服务器将连接到的中心网站上的前端服务器 (用户服务池), 然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="e0f52-113">Click **Front End pool**, click the Front End Server (User Services pool) at the central site that this Survivable Branch Appliance or Survivable Branch Server will connect to, and then click **Next**.</span></span>

6.  <span data-ttu-id="e0f52-114">单击 "**边缘服务器**", 单击此 Survivable 分支装置或 Survivable 分支服务器将连接到分支站点的远程用户的 PSTN 连接, 然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="e0f52-114">Click **Edge Server**, click the Edge pool that this Survivable Branch Appliance or Survivable Branch Server will connect to provide PSTN connectivity to remote users of the branch site, and then click **Next**.</span></span>

7.  <span data-ttu-id="e0f52-115">单击 "**网关 FQDN" 或 "IP 地址**", 然后键入与 Survivable 分支装置或 Survivable 分支服务器关联的网关对等的 FQDN 或 IP 地址, 以便路由入站或出站 PSTN 呼叫。</span><span class="sxs-lookup"><span data-stu-id="e0f52-115">Click **Gateway FQDN or IP Address**, and then type the FQDN or IP address of the gateway peer that the Survivable Branch Appliance or Survivable Branch Server is associated with for routing inbound or outbound PSTN calls.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e0f52-116">如果你要定义 Survivable 分支设备, 这是 Survivable 分支设备中的中介服务器将连接到 PSTN 连接的网关。</span><span class="sxs-lookup"><span data-stu-id="e0f52-116">If you are defining a Survivable Branch Appliance, this is the gateway to which the Mediation Server inside the Survivable Branch Appliance will connect for PSTN connectivity.</span></span>

    
    </div>

8.  <span data-ttu-id="e0f52-117">单击 "**用于 IP/PSTN 网关的侦听端口**", 然后接受默认端口。</span><span class="sxs-lookup"><span data-stu-id="e0f52-117">Click **Listening Port for IP/PSTN Gateway**, and then accept the default port.</span></span>

9.  <span data-ttu-id="e0f52-118">在**Sip 传输协议**中, 单击 Survivable 分支装置或 Survivable 分支服务器将使用的传输协议, 然后单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="e0f52-118">In **Sip Transport Protocol**, click the transport protocol the Survivable Branch Appliance or Survivable Branch Server will use, and then click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e0f52-119">出于安全考虑, 强烈建议你使用传输层安全 (TLS)。</span><span class="sxs-lookup"><span data-stu-id="e0f52-119">For security reasons, we strongly recommend that you use Transport Layer Security (TLS).</span></span> <span data-ttu-id="e0f52-120">如果你要定义 Survivable 分支设备, 请参阅 Survivable 分支设备供应商文档, 以验证你的 Survivable 分支设备是否支持 TLS 协议。</span><span class="sxs-lookup"><span data-stu-id="e0f52-120">If you are defining a Survivable Branch Appliance, refer to your Survivable Branch Appliance vendor documentation to verify that your Survivable Branch Appliance supports the TLS protocol.</span></span>

    
    </div>

10. <span data-ttu-id="e0f52-121">在控制台树中, 右键单击新的 Survivable 分支装置或服务器, 单击 "**拓扑**", 然后单击 "**发布**"。</span><span class="sxs-lookup"><span data-stu-id="e0f52-121">In the console tree, right-click the new Survivable Branch Appliance or Server, click **Topology**, and then click **Publish**.</span></span>

<span data-ttu-id="e0f52-122">**下一步**:[使用 Lync Server 2013 部署 Survivable 分支装置或服务器-分支站点任务](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)</span><span class="sxs-lookup"><span data-stu-id="e0f52-122">**Next step**: [Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

