---
title: 为试点池部署配置 DNS 记录
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 在部署试点池之前，必须为引导池更新 DNS 主机的条目。 若要成功完成此过程，您应以 Domain Admins 组成员或 DnsAdmins 组成员的身份登录到服务器或域。
ms.openlocfilehash: d934e3bdc46ab9deffa3c588b15ab793111c1a68
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754052"
---
# <a name="configure-dns-records-for-pilot-pool-deployment"></a><span data-ttu-id="c71e4-104">为试点池部署配置 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="c71e4-104">Configure DNS records for pilot pool deployment</span></span>

<span data-ttu-id="c71e4-105">在部署试点池之前，必须为引导池更新 DNS 主机的条目。</span><span class="sxs-lookup"><span data-stu-id="c71e4-105">Before deploying the pilot pool, you must update the DNS Host A entries for the pilot pool.</span></span> <span data-ttu-id="c71e4-106">若要成功完成此过程，您应以 Domain Admins 组成员或 DnsAdmins 组成员的身份登录到服务器或域。</span><span class="sxs-lookup"><span data-stu-id="c71e4-106">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
  
### <a name="to-configure-dns-host-a-records"></a><span data-ttu-id="c71e4-107">配置 DNS 主机 A 记录</span><span class="sxs-lookup"><span data-stu-id="c71e4-107">To configure DNS Host A records</span></span>

1. <span data-ttu-id="c71e4-108">在域名系统 (DNS) 服务器上，单击“开始”\*\*\*\*，再单击“管理工具”\*\*\*\*，然后单击“DNS”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c71e4-108">On the Domain Name System (DNS) server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>
    
2. <span data-ttu-id="c71e4-109">在您的域的控制台树中，展开 "**正向查找区域**"，然后右键单击将在其中安装 Skype For business Server 2019 的域。</span><span class="sxs-lookup"><span data-stu-id="c71e4-109">In the console tree for your domain, expand **Forward Lookup Zones**, and then right-click the domain in which Skype for Business Server 2019 will be installed.</span></span>
    
3. <span data-ttu-id="c71e4-110">单击“新建主机(A 或 AAAA)”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c71e4-110">Click **New Host (A or AAAA)**.</span></span>
    
4. <span data-ttu-id="c71e4-111">单击 "**名称**"，键入 Skype For business Server 2019 池的主机名（假定该域名来自定义该记录的区域，并且无需输入为 A 记录的一部分）。</span><span class="sxs-lookup"><span data-stu-id="c71e4-111">Click **Name**, type the host name for the Skype for Business Server 2019 pool (the domain name is assumed from the zone that the record is defined in and does not need to be entered as part of the A record).</span></span>
    
5. <span data-ttu-id="c71e4-112">单击 " **IP 地址**"，然后键入前端池的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="c71e4-112">Click **IP Address**, and then type the IP address for the Front End pool.</span></span>
    
6. <span data-ttu-id="c71e4-113">单击“添加主机”\*\*\*\*，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c71e4-113">Click **Add Host**, and then click **OK**.</span></span> 
    
7. <span data-ttu-id="c71e4-114">完成后，单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c71e4-114">When you are finished, click **Done**.</span></span>
    

