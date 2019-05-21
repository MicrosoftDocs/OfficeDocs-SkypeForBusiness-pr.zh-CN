---
title: 为试点池部署配置 DNS 记录
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 在部署试验池之前, 必须为试验池更新 DNS 主机的条目。 若要成功完成此过程, 你应作为域管理员组的成员或 DnsAdmins 组的成员登录到服务器或域。
ms.openlocfilehash: 3b8485564f3ea7f37a06b5c4d13c9450ba0a2694
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34289621"
---
# <a name="configure-dns-records-for-pilot-pool-deployment"></a><span data-ttu-id="20cc4-104">为试点池部署配置 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="20cc4-104">Configure DNS records for pilot pool deployment</span></span>

<span data-ttu-id="20cc4-105">在部署试验池之前, 必须为试验池更新 DNS 主机的条目。</span><span class="sxs-lookup"><span data-stu-id="20cc4-105">Before deploying the pilot pool, you must update the DNS Host A entries for the pilot pool.</span></span> <span data-ttu-id="20cc4-106">若要成功完成此过程, 你应作为域管理员组的成员或 DnsAdmins 组的成员登录到服务器或域。</span><span class="sxs-lookup"><span data-stu-id="20cc4-106">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
  
### <a name="to-configure-dns-host-a-records"></a><span data-ttu-id="20cc4-107">配置 DNS 主机 A 记录</span><span class="sxs-lookup"><span data-stu-id="20cc4-107">To configure DNS Host A records</span></span>

1. <span data-ttu-id="20cc4-108">在 "域名系统 (DNS)" 服务器上, 单击 "**开始**", 单击 "**管理工具**", 然后单击 " **DNS**"。</span><span class="sxs-lookup"><span data-stu-id="20cc4-108">On the Domain Name System (DNS) server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>
    
2. <span data-ttu-id="20cc4-109">在您的域的控制台树中, 展开 "**正向查找区域**", 然后右键单击将在其中安装 Skype For business Server 2019 的域。</span><span class="sxs-lookup"><span data-stu-id="20cc4-109">In the console tree for your domain, expand **Forward Lookup Zones**, and then right-click the domain in which Skype for Business Server 2019 will be installed.</span></span>
    
3. <span data-ttu-id="20cc4-110">单击 "**新建主机 (A 或 AAAA)**"。</span><span class="sxs-lookup"><span data-stu-id="20cc4-110">Click **New Host (A or AAAA)**.</span></span>
    
4. <span data-ttu-id="20cc4-111">单击 "**名称**", 键入 Skype For business Server 2019 池的主机名 (从在其中定义记录的区域中假定为域名, 并且不需要将其输入为 A 记录的一部分)。</span><span class="sxs-lookup"><span data-stu-id="20cc4-111">Click **Name**, type the host name for the Skype for Business Server 2019 pool (the domain name is assumed from the zone that the record is defined in and does not need to be entered as part of the A record).</span></span>
    
5. <span data-ttu-id="20cc4-112">单击 " **IP 地址**", 然后键入前端池的 ip 地址。</span><span class="sxs-lookup"><span data-stu-id="20cc4-112">Click **IP Address**, and then type the IP address for the Front End pool.</span></span>
    
6. <span data-ttu-id="20cc4-113">单击 "**添加主机**", 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="20cc4-113">Click **Add Host**, and then click **OK**.</span></span> 
    
7. <span data-ttu-id="20cc4-114">完成后, 单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="20cc4-114">When you are finished, click **Done**.</span></span>
    

