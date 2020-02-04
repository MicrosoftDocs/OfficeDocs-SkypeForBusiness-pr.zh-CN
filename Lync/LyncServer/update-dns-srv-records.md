---
title: 更新 DNS SRV 记录
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Update DNS SRV records
ms:assetid: 9542b91a-108c-4980-89ec-634905cbbf26
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688139(v=OCS.15)
ms:contentKeyID: 49733739
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e00093859a6e252c019183617b4548dfc00218a6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738614"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="update-dns-srv-records"></a><span data-ttu-id="dd40e-102">更新 DNS SRV 记录</span><span class="sxs-lookup"><span data-stu-id="dd40e-102">Update DNS SRV records</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dd40e-103">_**主题上次修改时间：** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="dd40e-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="dd40e-104">若要成功完成此过程，你应作为域管理员组的成员或 DnsAdmins 组的成员登录到服务器或域。</span><span class="sxs-lookup"><span data-stu-id="dd40e-104">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="dd40e-105">本主题介绍了迁移到 Lync Server 2013 后如何更新域名系统（DNS）记录。</span><span class="sxs-lookup"><span data-stu-id="dd40e-105">This topic describes how to update the Domain Name System (DNS) records after migrating to Lync Server 2013.</span></span> <span data-ttu-id="dd40e-106">将所有用户移到 Lync Server 2013 之后，但在取消旧版 Lync Server 2010 池或控制器之前，必须在每个 SIP 域的内部 DNS 中更新 DNS SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="dd40e-106">After all users have been moved to Lync Server 2013, but before the legacy Lync Server 2010 pool or Director is decommissioned, you must update the DNS SRV records in your internal DNS for every SIP domain.</span></span> <span data-ttu-id="dd40e-107">此过程假定你的内部 DNS 具有适用于你的 SIP 用户域的区域。</span><span class="sxs-lookup"><span data-stu-id="dd40e-107">This procedure assumes that your internal DNS has zones for your SIP user domains.</span></span>

<span data-ttu-id="dd40e-108">**配置 DNS SRV 记录**</span><span class="sxs-lookup"><span data-stu-id="dd40e-108">**To configure a DNS SRV record**</span></span>

1.  <span data-ttu-id="dd40e-109">在 DNS 服务器上，单击 "**开始**"，单击 "**管理工具**"，然后单击 " **DNS**"。</span><span class="sxs-lookup"><span data-stu-id="dd40e-109">On the DNS server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="dd40e-110">在 SIP 域的控制台树中，展开 "**正向查找区域**"，展开安装了 Lync Server 2013 的 SIP 域，然后导航到\*\* \_tcp\*\*设置。</span><span class="sxs-lookup"><span data-stu-id="dd40e-110">In the console tree for your SIP domain, expand **Forward Lookup Zones**, expand the SIP domain in which Lync Server 2013 is installed, and navigate to the **\_tcp** setting.</span></span>

3.  <span data-ttu-id="dd40e-111">在右窗格中，右键单击 " \*\* \_sipinternaltls\*\* "，然后选择 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="dd40e-111">In the right pane, right click **\_sipinternaltls** and select **Properties**.</span></span>

4.  <span data-ttu-id="dd40e-112">在**提供此服务的主机**中，更新主机 FQDN 以指向 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="dd40e-112">In **Host offering this service**, update the host FQDN to point to the Lync Server 2013 pool.</span></span>

5.  <span data-ttu-id="dd40e-113">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="dd40e-113">Click **OK**.</span></span>

<span data-ttu-id="dd40e-114">**验证是否可以解析前端池或标准版服务器的 FQDN**</span><span class="sxs-lookup"><span data-stu-id="dd40e-114">**To verify that the FQDN of the Front End pool or Standard Edition server can be resolved**</span></span>

1.  <span data-ttu-id="dd40e-115">登录到域中的客户端计算机。</span><span class="sxs-lookup"><span data-stu-id="dd40e-115">Log on to a client computer in the domain.</span></span>

2.  <span data-ttu-id="dd40e-116">单击 **“开始”**，然后单击 **“运行”**。</span><span class="sxs-lookup"><span data-stu-id="dd40e-116">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="dd40e-117">在 "**打开**" 框中，键入**cmd**，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="dd40e-117">In the **Open** box, type **cmd**, and then click **OK**.</span></span>

4.  <span data-ttu-id="dd40e-118">在命令提示符处，键入 " **nslookup** \<FQDN" （标准版\>服务器\<\>的前端池或 fqdn），然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="dd40e-118">At the command prompt, type **nslookup** \<FQDN of the Front End pool\> or \<FQDN of the Standard Edition server\>, and then press ENTER.</span></span>

5.  <span data-ttu-id="dd40e-119">验证您是否收到了解析为 FQDN 的相应 IP 地址的答复。</span><span class="sxs-lookup"><span data-stu-id="dd40e-119">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

