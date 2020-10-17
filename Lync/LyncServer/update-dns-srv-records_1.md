---
title: 更新 DNS SRV 记录
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Update DNS SRV records
ms:assetid: a29149aa-30cc-4a59-af98-fb95c2385cce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688161(v=OCS.15)
ms:contentKeyID: 49733765
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cf77df16b7681cf6cfd3c1608f1adb40e2e09f43
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527189"
---
# <a name="update-dns-srv-records"></a><span data-ttu-id="c2a79-102">更新 DNS SRV 记录</span><span class="sxs-lookup"><span data-stu-id="c2a79-102">Update DNS SRV records</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c2a79-103">_**上次修改的主题：** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="c2a79-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="c2a79-104">若要成功完成此过程，您应以 Domain Admins 组成员或 DnsAdmins 组成员的身份登录到服务器或域。</span><span class="sxs-lookup"><span data-stu-id="c2a79-104">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="c2a79-105">本主题介绍了如何在迁移到 Lync Server 2013 之后更新域名系统 (DNS) 记录。</span><span class="sxs-lookup"><span data-stu-id="c2a79-105">This topic describes how to update the Domain Name System (DNS) records after migrating to Lync Server 2013.</span></span> <span data-ttu-id="c2a79-106">在将所有用户移动到 Lync Server 2013 之后，但在旧版 Office 通信服务器 2007 R2 池或控制器停止之前，必须在每个 SIP 域的内部 DNS 中更新 DNS SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="c2a79-106">After all users have been moved to Lync Server 2013, but before the legacy Office Communications Server 2007 R2 pool or Director is decommissioned, you must update the DNS SRV records in your internal DNS for every SIP domain.</span></span> <span data-ttu-id="c2a79-107">此过程假定内部 DNS 具有 SIP 用户域的区域。</span><span class="sxs-lookup"><span data-stu-id="c2a79-107">This procedure assumes that your internal DNS has zones for your SIP user domains.</span></span>

<span data-ttu-id="c2a79-108">**配置 DNS SRV 记录**</span><span class="sxs-lookup"><span data-stu-id="c2a79-108">**To configure a DNS SRV record**</span></span>

1.  <span data-ttu-id="c2a79-109">在 DNS 服务器上，单击“开始”\*\*\*\*，再单击“管理工具”\*\*\*\*，然后单击“DNS”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c2a79-109">On the DNS server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="c2a79-110">在您的 SIP 域的控制台树中，展开 "**正向查找区域**"，展开安装了 Lync Server 2013 的 SIP 域，然后导航到 " \*\* \_ tcp\*\* " 设置。</span><span class="sxs-lookup"><span data-stu-id="c2a79-110">In the console tree for your SIP domain, expand **Forward Lookup Zones**, expand the SIP domain in which Lync Server 2013 is installed, and navigate to the **\_tcp** setting.</span></span>

3.  <span data-ttu-id="c2a79-111">在右侧窗格中，右键单击 " \*\* \_ sipinternaltls\*\* "，然后选择 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="c2a79-111">In the right pane, right click **\_sipinternaltls** and select **Properties**.</span></span>

4.  <span data-ttu-id="c2a79-112">在 **提供此服务的主机**中，将主机 FQDN 更新为指向 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="c2a79-112">In **Host offering this service**, update the host FQDN to point to the Lync Server 2013 pool.</span></span>

5.  <span data-ttu-id="c2a79-113">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c2a79-113">Click **OK**.</span></span>

<span data-ttu-id="c2a79-114">**验证是否可以解析前端池或 Standard Edition Server 的 FQDN**</span><span class="sxs-lookup"><span data-stu-id="c2a79-114">**To verify that the FQDN of the Front End pool or Standard Edition server can be resolved**</span></span>

1.  <span data-ttu-id="c2a79-115">登录到域中的一台客户端计算机。</span><span class="sxs-lookup"><span data-stu-id="c2a79-115">Log on to a client computer in the domain.</span></span>

2.  <span data-ttu-id="c2a79-116">单击“开始”\*\*\*\*，然后单击“运行”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c2a79-116">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="c2a79-117">在“打开”\*\*\*\* 框中，键入 **cmd**，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c2a79-117">In the **Open** box, type **cmd**, and then click **OK**.</span></span>

4.  <span data-ttu-id="c2a79-118">在命令提示符处，键入 **nslookup** \<FQDN of the Front End pool\> 或 \<FQDN of the Standard Edition server\> ，然后按 enter。</span><span class="sxs-lookup"><span data-stu-id="c2a79-118">At the command prompt, type **nslookup** \<FQDN of the Front End pool\> or \<FQDN of the Standard Edition server\>, and then press ENTER.</span></span>

5.  <span data-ttu-id="c2a79-119">验证是否收到一个解析为 FQDN 的相应 IP 地址的答复。</span><span class="sxs-lookup"><span data-stu-id="c2a79-119">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

