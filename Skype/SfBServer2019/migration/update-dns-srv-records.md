---
title: 更新 DNS SRV 记录
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
description: 若要成功完成此过程，您应以 Domain Admins 组成员或 DnsAdmins 组成员的身份登录到服务器或域。
ms.openlocfilehash: 26bb80618868a2bec03d1de32f6c010869b8cf8c
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753264"
---
# <a name="update-dns-srv-records"></a><span data-ttu-id="949d9-103">更新 DNS SRV 记录</span><span class="sxs-lookup"><span data-stu-id="949d9-103">Update DNS SRV records</span></span>

<span data-ttu-id="949d9-104">若要成功完成此过程，您应以 Domain Admins 组成员或 DnsAdmins 组成员的身份登录到服务器或域。</span><span class="sxs-lookup"><span data-stu-id="949d9-104">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
  
<span data-ttu-id="949d9-105">本主题介绍了如何在迁移到 Skype for business Server 2019 之后更新域名系统（DNS）记录。</span><span class="sxs-lookup"><span data-stu-id="949d9-105">This topic describes how to update the Domain Name System (DNS) records after migrating to Skype for Business Server 2019.</span></span> <span data-ttu-id="949d9-106">在所有用户都已移动到 Skype for business Server 2019 中，但在旧池或控制器退役之前，必须在每个 SIP 域的内部 DNS 中更新 DNS SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="949d9-106">After all users have been moved to Skype for Business Server 2019, but before the legacy pool or Director is decommissioned, you must update the DNS SRV records in your internal DNS for every SIP domain.</span></span> <span data-ttu-id="949d9-107">此过程假定内部 DNS 具有 SIP 用户域的区域。</span><span class="sxs-lookup"><span data-stu-id="949d9-107">This procedure assumes that your internal DNS has zones for your SIP user domains.</span></span>
  
## <a name="to-configure-a-dns-srv-record"></a><span data-ttu-id="949d9-108">配置 DNS SRV 记录</span><span class="sxs-lookup"><span data-stu-id="949d9-108">To configure a DNS SRV record</span></span>

1. <span data-ttu-id="949d9-109">在 DNS 服务器上，单击“开始”\*\*\*\*，再单击“管理工具”\*\*\*\*，然后单击“DNS”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="949d9-109">On the DNS server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>
    
2. <span data-ttu-id="949d9-110">在您的 SIP 域的控制台树中，展开 "**正向查找区域**"，展开安装了 Skype For business Server 2019 的 SIP 域，然后导航到 " **_tcp** " 设置。</span><span class="sxs-lookup"><span data-stu-id="949d9-110">In the console tree for your SIP domain, expand **Forward Lookup Zones**, expand the SIP domain in which Skype for Business Server 2019 is installed, and navigate to the **_tcp** setting.</span></span> 
    
3. <span data-ttu-id="949d9-111">在右侧窗格中，右键单击 " **_sipinternaltls** "，然后选择 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="949d9-111">In the right pane, right-click **_sipinternaltls** and select **Properties**.</span></span>
    
4. <span data-ttu-id="949d9-112">在**提供此服务的主机**中，将主机 FQDN 更新为指向 Skype For business Server 2019 池。</span><span class="sxs-lookup"><span data-stu-id="949d9-112">In **Host offering this service**, update the host FQDN to point to the Skype for Business Server 2019 pool.</span></span>
    
5. <span data-ttu-id="949d9-113">单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="949d9-113">Click **OK**.</span></span>
    
## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a><span data-ttu-id="949d9-114">验证是否可以解析前端池或 Standard Edition Server 的 FQDN</span><span class="sxs-lookup"><span data-stu-id="949d9-114">To verify that the FQDN of the Front End pool or Standard Edition server can be resolved</span></span>

1. <span data-ttu-id="949d9-115">登录到域中的客户端计算机。</span><span class="sxs-lookup"><span data-stu-id="949d9-115">Log on to a client computer in the domain.</span></span>
    
2. <span data-ttu-id="949d9-116">单击“开始”\*\*\*\*，再单击“运行”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="949d9-116">Click **Start**, and then click **Run**.</span></span>
    
3. <span data-ttu-id="949d9-117">在 "**打开**" 框中，键入 cmd，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="949d9-117">In the **Open** box, type cmd, and then click **OK**.</span></span>
    
4. <span data-ttu-id="949d9-118">在命令提示符处，键入 nslookup _\<FQDN of the Front End pool\>_ 或 _\<FQDN of the Standard Edition server\>_ ，然后按 enter。</span><span class="sxs-lookup"><span data-stu-id="949d9-118">At the command prompt, type nslookup _\<FQDN of the Front End pool\>_ or  _\<FQDN of the Standard Edition server\>_, and then press ENTER.</span></span>
    
5. <span data-ttu-id="949d9-119">验证是否收到一个解析为 FQDN 的相应 IP 地址的答复。</span><span class="sxs-lookup"><span data-stu-id="949d9-119">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>
    

