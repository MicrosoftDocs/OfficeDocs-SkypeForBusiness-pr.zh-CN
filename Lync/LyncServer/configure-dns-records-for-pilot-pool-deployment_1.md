---
title: 为试点池部署配置 DNS 记录
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure DNS records for pilot pool deployment
ms:assetid: 5c7a6e10-e1e9-4479-9bf9-d4a3e2e09ff0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688072(v=OCS.15)
ms:contentKeyID: 49733666
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bbc77ddf3b0bb1d58eadc43424e638e4c59608e1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136110"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-dns-records-for-pilot-pool-deployment"></a><span data-ttu-id="aa3b6-102">为试点池部署配置 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="aa3b6-102">Configure DNS records for pilot pool deployment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aa3b6-103">_**上次修改的主题：** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="aa3b6-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="aa3b6-104">在部署 Lync Server 2013 试点池之前，必须为引导池更新 DNS 主机的条目。</span><span class="sxs-lookup"><span data-stu-id="aa3b6-104">Prior to deploying the Lync Server 2013 pilot pool, you must update the DNS Host A entries for the pilot pool.</span></span> <span data-ttu-id="aa3b6-105">要成功完成此过程，应至少以 Domain Admins 组或 DNSAdmins 组成员的身份登录到服务器或域。</span><span class="sxs-lookup"><span data-stu-id="aa3b6-105">To successfully complete this procedure, you should be logged on to the server or domain at minimum as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="aa3b6-106">**配置 DNS 主机 A 记录**</span><span class="sxs-lookup"><span data-stu-id="aa3b6-106">**To configure DNS Host A records**</span></span>

1.  <span data-ttu-id="aa3b6-107">在域名系统 (DNS) 服务器上，单击“开始”\*\*\*\*，再单击“管理工具”\*\*\*\*，然后单击“DNS”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="aa3b6-107">On the Domain Name System (DNS) server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="aa3b6-108">在您的域的控制台树中，展开 "**正向查找区域**"，然后右键单击将在其中安装 Lync Server 2013 的域。</span><span class="sxs-lookup"><span data-stu-id="aa3b6-108">In the console tree for your domain, expand **Forward Lookup Zones**, and then right-click the domain in which Lync Server 2013 will be installed.</span></span>

3.  <span data-ttu-id="aa3b6-109">单击“新建主机(A 或 AAAA)”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="aa3b6-109">Click **New Host (A or AAAA)**.</span></span>

4.  <span data-ttu-id="aa3b6-110">单击“名称”\*\*\*\*，键入池的主机名（根据在其中定义记录的区域采用域名，但不需要输入域名作为 A 记录的一部分）。</span><span class="sxs-lookup"><span data-stu-id="aa3b6-110">Click **Name**, type the host name for the pool (the domain name is assumed from the zone that the record is defined in and does not need to be entered as part of the A record).</span></span>

5.  <span data-ttu-id="aa3b6-111">单击 " **IP 地址**"，键入前端池的 ip 地址。</span><span class="sxs-lookup"><span data-stu-id="aa3b6-111">Click **IP Address**, type the IP address for the Front End pool.</span></span>

6.  <span data-ttu-id="aa3b6-112">单击“添加主机”\*\*\*\*，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="aa3b6-112">Click **Add Host**, and then click **OK**.</span></span>

7.  <span data-ttu-id="aa3b6-113">完成后，单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="aa3b6-113">When you are finished, click **Done**.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

