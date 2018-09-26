---
title: 为试点池部署配置 DNS 记录
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 部署试点池之前, 必须更新试点池的 DNS 主机 A 条目。 若要成功完成此过程，您应登录到服务器或域的 Domain Admins 组成员或 DnsAdmins 组的成员。
ms.openlocfilehash: 13492f7972e127de7a8200a0dbe933c72aba2da7
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "25029893"
---
# <a name="configure-dns-records-for-pilot-pool-deployment"></a><span data-ttu-id="0d0aa-104">为试点池部署配置 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="0d0aa-104">Configure DNS records for pilot pool deployment</span></span>

<span data-ttu-id="0d0aa-105">部署试点池之前, 必须更新试点池的 DNS 主机 A 条目。</span><span class="sxs-lookup"><span data-stu-id="0d0aa-105">Before deploying the pilot pool, you must update the DNS Host A entries for the pilot pool.</span></span> <span data-ttu-id="0d0aa-106">若要成功完成此过程，您应登录到服务器或域的 Domain Admins 组成员或 DnsAdmins 组的成员。</span><span class="sxs-lookup"><span data-stu-id="0d0aa-106">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
  
### <a name="to-configure-dns-host-a-records"></a><span data-ttu-id="0d0aa-107">配置 DNS 主机 A 记录</span><span class="sxs-lookup"><span data-stu-id="0d0aa-107">To configure DNS Host A records</span></span>

1. <span data-ttu-id="0d0aa-108">在域名系统 (DNS) 服务器上，单击**开始**，单击**管理工具**，然后单击**DNS**。</span><span class="sxs-lookup"><span data-stu-id="0d0aa-108">On the Domain Name System (DNS) server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>
    
2. <span data-ttu-id="0d0aa-109">在您的域的控制台树中，展开**正向查找区域**，，然后右键单击在其中安装业务服务器 2019年的 Skype 的域。</span><span class="sxs-lookup"><span data-stu-id="0d0aa-109">In the console tree for your domain, expand **Forward Lookup Zones**, and then right-click the domain in which Skype for Business Server 2019 will be installed.</span></span>
    
3. <span data-ttu-id="0d0aa-110">单击**新建主机 （A 或 AAAA）**。</span><span class="sxs-lookup"><span data-stu-id="0d0aa-110">Click **New Host (A or AAAA)**.</span></span>
    
4. <span data-ttu-id="0d0aa-111">单击**名称**中，键入 （从记录中定义的且不需要输入的 A 记录的一部分的区域假定域名称） 的业务服务器 2019年池 Skype 的主机名。</span><span class="sxs-lookup"><span data-stu-id="0d0aa-111">Click **Name**, type the host name for the Skype for Business Server 2019 pool (the domain name is assumed from the zone that the record is defined in and does not need to be entered as part of the A record).</span></span>
    
5. <span data-ttu-id="0d0aa-112">单击**IP 地址**，然后键入前端池的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="0d0aa-112">Click **IP Address**, and then type the IP address for the Front End pool.</span></span>
    
6. <span data-ttu-id="0d0aa-113">单击**添加主机**，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="0d0aa-113">Click **Add Host**, and then click **OK**.</span></span> 
    
7. <span data-ttu-id="0d0aa-114">完成后，单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="0d0aa-114">When you are finished, click **Done**.</span></span>
    

