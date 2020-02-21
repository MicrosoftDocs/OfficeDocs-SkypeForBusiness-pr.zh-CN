---
title: Lync Server 2013：定义 SIP/CSTA 网关 IP 地址
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a SIP/CSTA gateway IP address
ms:assetid: ae944057-3ad6-4474-a09b-81a3d27bd50f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg602125(v=OCS.15)
ms:contentKeyID: 48185073
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f59b2d236cc9a261f07b2f2e9dc26102efff908f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205988"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="define-a-sipcsta-gateway-ip-address-in-lync-server-2013"></a><span data-ttu-id="45fbd-102">在 Lync Server 2013 中定义 SIP/CSTA 网关 IP 地址</span><span class="sxs-lookup"><span data-stu-id="45fbd-102">Define a SIP/CSTA gateway IP address in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="45fbd-103">_**上次修改的主题：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="45fbd-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="45fbd-104">如果 Lync Server 将连接到通过使用传输控制协议（TCP）连接为远程呼叫控制部署的 SIP/CSTA 网关，则必须在拓扑生成器中定义网关的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="45fbd-104">If Lync Server will connect to the SIP/CSTA gateway that you deployed for remote call control by using a Transmission Control Protocol (TCP) connection, then you must define the IP address of the gateway in Topology Builder.</span></span> <span data-ttu-id="45fbd-105">对于支持传输层安全性 (TLS) 连接的网关来说，这一步不是必需的。</span><span class="sxs-lookup"><span data-stu-id="45fbd-105">This step is not necessary for gateways that support Transport Layer Security (TLS) connections.</span></span> <span data-ttu-id="45fbd-106">对于任何支持 TLS 连接的网关，您可以跳过此过程并继续部署远程呼叫控制，方法是按照在[Lync Server 2013 中为远程呼叫控制启用 lync 用户](lync-server-2013-enable-lync-users-for-remote-call-control.md)中的步骤。</span><span class="sxs-lookup"><span data-stu-id="45fbd-106">For any gateway that supports TLS connections, you can skip this procedure and continue deployment of remote call control by following the steps in [Enable Lync users for remote call control in Lync Server 2013](lync-server-2013-enable-lync-users-for-remote-call-control.md).</span></span>

<div>

## <a name="to-define-the-sipcsta-gateway-ip-address-by-using-topology-builder"></a><span data-ttu-id="45fbd-107">使用拓扑生成器定义 SIP/CSTA 网关 IP 地址</span><span class="sxs-lookup"><span data-stu-id="45fbd-107">To define the SIP/CSTA gateway IP address by using Topology Builder</span></span>

1.  <span data-ttu-id="45fbd-108">以 Domain Admins 组和 RTCUniversalServerAdmins 组成员的身份登录安装了拓扑生成器的计算机。</span><span class="sxs-lookup"><span data-stu-id="45fbd-108">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="45fbd-109">启动拓扑生成器：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server 拓扑生成器**"。</span><span class="sxs-lookup"><span data-stu-id="45fbd-109">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

3.  <span data-ttu-id="45fbd-110">选择相应的选项以下载现有拓扑。</span><span class="sxs-lookup"><span data-stu-id="45fbd-110">Choose the option to download an existing topology.</span></span>

4.  <span data-ttu-id="45fbd-111">展开“受信任的应用程序服务器”\*\*\*\* 节点。</span><span class="sxs-lookup"><span data-stu-id="45fbd-111">Expand the **Trusted application servers** node.</span></span>

5.  <span data-ttu-id="45fbd-112">右键单击您创建的受信任应用程序池，如在[Lync Server 2013 中为远程呼叫控制配置受信任的应用程序条目](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)中所述，然后单击**编辑属性**。</span><span class="sxs-lookup"><span data-stu-id="45fbd-112">Right-click the trusted application pool that you created, as described in [Configure a trusted application entry for remote call control in Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md), and then click **Edit Properties**.</span></span>

6.  <span data-ttu-id="45fbd-113">清除“允许将配置数据复制到此池”\*\*\*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="45fbd-113">Clear the **Enable replication of configuration data to this pool** check box.</span></span>

7.  <span data-ttu-id="45fbd-p102">单击“将服务用途限制为所选 IP 地址”\*\*\*\*。默认设置为“使用所有已配置的 IP 地址”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="45fbd-p102">Click **Limit service usage to selected IP addresses**. The default setting is **Use all configured IP addresses**.</span></span>

8.  <span data-ttu-id="45fbd-116">在“主 IP 地址”\*\*\*\* 文本框中，输入 SIP/CSTA 网关的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="45fbd-116">In the **Primary IP address** text box, enter the IP address of the SIP/CSTA gateway.</span></span>

9.  <span data-ttu-id="45fbd-117">要更新中央管理存储中的拓扑，请在控制台树中单击“Lync Server”\*\*\*\*，然后从“操作”\*\*\*\* 窗格中单击“发布”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="45fbd-117">To update the topology in the Central Management store, in the console tree, click **Lync Server**, and then, from the **Actions** pane, click **Publish**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="45fbd-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="45fbd-118">See Also</span></span>


[<span data-ttu-id="45fbd-119">在 Lync Server 2013 中为远程呼叫控制配置静态路由</span><span class="sxs-lookup"><span data-stu-id="45fbd-119">Configure a static route for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-static-route-for-remote-call-control.md)  
[<span data-ttu-id="45fbd-120">在 Lync Server 2013 中为远程呼叫控制配置受信任的应用程序条目</span><span class="sxs-lookup"><span data-stu-id="45fbd-120">Configure a trusted application entry for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

