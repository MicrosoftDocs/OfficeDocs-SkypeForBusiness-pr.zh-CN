---
title: 更新 DNS SRV 记录
description: 更新 DNS SRV 记录。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Update DNS SRV records
ms:assetid: 9542b91a-108c-4980-89ec-634905cbbf26
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688139(v=OCS.15)
ms:contentKeyID: 49733739
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 24161074e8f3bcf7e296a957588eeb59d5f2ad1b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579588"
---
# <a name="update-dns-srv-records"></a><span data-ttu-id="f6e74-103">更新 DNS SRV 记录</span><span class="sxs-lookup"><span data-stu-id="f6e74-103">Update DNS SRV records</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f6e74-104">_**上次修改的主题：** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="f6e74-104">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="f6e74-105">若要成功完成此过程，您应以 Domain Admins 组成员或 DnsAdmins 组成员的身份登录到服务器或域。</span><span class="sxs-lookup"><span data-stu-id="f6e74-105">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="f6e74-106">本主题介绍了如何在迁移到 Lync Server 2013 之后更新域名系统 (DNS) 记录。</span><span class="sxs-lookup"><span data-stu-id="f6e74-106">This topic describes how to update the Domain Name System (DNS) records after migrating to Lync Server 2013.</span></span> <span data-ttu-id="f6e74-107">在将所有用户移动到 Lync Server 2013 之后，但在取消旧版 Lync Server 2010 池或控制器之前，必须在每个 SIP 域的内部 DNS 中更新 DNS SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="f6e74-107">After all users have been moved to Lync Server 2013, but before the legacy Lync Server 2010 pool or Director is decommissioned, you must update the DNS SRV records in your internal DNS for every SIP domain.</span></span> <span data-ttu-id="f6e74-108">此过程假定内部 DNS 具有 SIP 用户域的区域。</span><span class="sxs-lookup"><span data-stu-id="f6e74-108">This procedure assumes that your internal DNS has zones for your SIP user domains.</span></span>

<span data-ttu-id="f6e74-109">**配置 DNS SRV 记录**</span><span class="sxs-lookup"><span data-stu-id="f6e74-109">**To configure a DNS SRV record**</span></span>

1.  <span data-ttu-id="f6e74-110">在 DNS 服务器上，单击“开始”\*\*\*\*，再单击“管理工具”\*\*\*\*，然后单击“DNS”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f6e74-110">On the DNS server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="f6e74-111">在您的 SIP 域的控制台树中，展开 "**正向查找区域**"，展开安装了 Lync Server 2013 的 SIP 域，然后导航到 " \*\* \_ tcp\*\* " 设置。</span><span class="sxs-lookup"><span data-stu-id="f6e74-111">In the console tree for your SIP domain, expand **Forward Lookup Zones**, expand the SIP domain in which Lync Server 2013 is installed, and navigate to the **\_tcp** setting.</span></span>

3.  <span data-ttu-id="f6e74-112">在右侧窗格中，右键单击 " \*\* \_ sipinternaltls\*\* "，然后选择 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="f6e74-112">In the right pane, right click **\_sipinternaltls** and select **Properties**.</span></span>

4.  <span data-ttu-id="f6e74-113">在 **提供此服务的主机**中，将主机 FQDN 更新为指向 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="f6e74-113">In **Host offering this service**, update the host FQDN to point to the Lync Server 2013 pool.</span></span>

5.  <span data-ttu-id="f6e74-114">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f6e74-114">Click **OK**.</span></span>

<span data-ttu-id="f6e74-115">**验证是否可以解析前端池或 Standard Edition Server 的 FQDN**</span><span class="sxs-lookup"><span data-stu-id="f6e74-115">**To verify that the FQDN of the Front End pool or Standard Edition server can be resolved**</span></span>

1.  <span data-ttu-id="f6e74-116">登录到域中的一台客户端计算机。</span><span class="sxs-lookup"><span data-stu-id="f6e74-116">Log on to a client computer in the domain.</span></span>

2.  <span data-ttu-id="f6e74-117">单击“开始”\*\*\*\*，然后单击“运行”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f6e74-117">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="f6e74-118">在“打开”\*\*\*\* 框中，键入 **cmd**，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f6e74-118">In the **Open** box, type **cmd**, and then click **OK**.</span></span>

4.  <span data-ttu-id="f6e74-119">在命令提示符处，键入 **nslookup** \<FQDN of the Front End pool\> 或 \<FQDN of the Standard Edition server\> ，然后按 enter。</span><span class="sxs-lookup"><span data-stu-id="f6e74-119">At the command prompt, type **nslookup** \<FQDN of the Front End pool\> or \<FQDN of the Standard Edition server\>, and then press ENTER.</span></span>

5.  <span data-ttu-id="f6e74-120">验证是否收到一个解析为 FQDN 的相应 IP 地址的答复。</span><span class="sxs-lookup"><span data-stu-id="f6e74-120">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

