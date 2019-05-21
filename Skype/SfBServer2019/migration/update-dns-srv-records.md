---
title: 更新 DNS SRV 记录
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 若要成功完成此过程, 你应作为域管理员组的成员或 DnsAdmins 组的成员登录到服务器或域。
ms.openlocfilehash: bf9f9c3f16ceb2ee35cda8e833d468e202d5653c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34307054"
---
# <a name="update-dns-srv-records"></a><span data-ttu-id="a0eba-103">更新 DNS SRV 记录</span><span class="sxs-lookup"><span data-stu-id="a0eba-103">Update DNS SRV records</span></span>

<span data-ttu-id="a0eba-104">若要成功完成此过程, 你应作为域管理员组的成员或 DnsAdmins 组的成员登录到服务器或域。</span><span class="sxs-lookup"><span data-stu-id="a0eba-104">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
  
<span data-ttu-id="a0eba-105">本主题介绍了迁移到 Skype for Business Server 2019 后如何更新域名系统 (DNS) 记录。</span><span class="sxs-lookup"><span data-stu-id="a0eba-105">This topic describes how to update the Domain Name System (DNS) records after migrating to Skype for Business Server 2019.</span></span> <span data-ttu-id="a0eba-106">在所有用户都已移动到 Skype for Business Server 2019 之后, 在旧池或控制器停止使用之前, 必须在内部 DNS 中更新每个 SIP 域的 DNS SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="a0eba-106">After all users have been moved to Skype for Business Server 2019, but before the legacy pool or Director is decommissioned, you must update the DNS SRV records in your internal DNS for every SIP domain.</span></span> <span data-ttu-id="a0eba-107">此过程假定你的内部 DNS 具有适用于你的 SIP 用户域的区域。</span><span class="sxs-lookup"><span data-stu-id="a0eba-107">This procedure assumes that your internal DNS has zones for your SIP user domains.</span></span>
  
## <a name="to-configure-a-dns-srv-record"></a><span data-ttu-id="a0eba-108">配置 DNS SRV 记录</span><span class="sxs-lookup"><span data-stu-id="a0eba-108">To configure a DNS SRV record</span></span>

1. <span data-ttu-id="a0eba-109">在 DNS 服务器上, 单击 "**开始**", 单击 "**管理工具**", 然后单击 " **DNS**"。</span><span class="sxs-lookup"><span data-stu-id="a0eba-109">On the DNS server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>
    
2. <span data-ttu-id="a0eba-110">在你的 SIP 域的控制台树中, 展开 "**正向查找区域**", 展开安装了 Skype For business Server 2019 的 SIP 域, 然后导航到 **_tcp**设置。</span><span class="sxs-lookup"><span data-stu-id="a0eba-110">In the console tree for your SIP domain, expand **Forward Lookup Zones**, expand the SIP domain in which Skype for Business Server 2019 is installed, and navigate to the **_tcp** setting.</span></span> 
    
3. <span data-ttu-id="a0eba-111">在右窗格中, 右键单击 " **_sipinternaltls** ", 然后选择 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="a0eba-111">In the right pane, right-click **_sipinternaltls** and select **Properties**.</span></span>
    
4. <span data-ttu-id="a0eba-112">在**提供此服务的主机**中, 更新主机 FQDN 以指向 Skype For business Server 2019 池。</span><span class="sxs-lookup"><span data-stu-id="a0eba-112">In **Host offering this service**, update the host FQDN to point to the Skype for Business Server 2019 pool.</span></span>
    
5. <span data-ttu-id="a0eba-113">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="a0eba-113">Click **OK**.</span></span>
    
## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a><span data-ttu-id="a0eba-114">验证是否可以解析前端池或标准版服务器的 FQDN</span><span class="sxs-lookup"><span data-stu-id="a0eba-114">To verify that the FQDN of the Front End pool or Standard Edition server can be resolved</span></span>

1. <span data-ttu-id="a0eba-115">登录到域中的客户端计算机。</span><span class="sxs-lookup"><span data-stu-id="a0eba-115">Log on to a client computer in the domain.</span></span>
    
2. <span data-ttu-id="a0eba-116">单击 **“开始”**，然后单击 **“运行”**。</span><span class="sxs-lookup"><span data-stu-id="a0eba-116">Click **Start**, and then click **Run**.</span></span>
    
3. <span data-ttu-id="a0eba-117">在 "**打开**" 框中, 键入 cmd, 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="a0eba-117">In the **Open** box, type cmd, and then click **OK**.</span></span>
    
4. <span data-ttu-id="a0eba-118">在命令提示符处, 键入_ \<"nslookup FQDN"\> _ ( _ \<标准版服务器\>_ 的前端池或 fqdn), 然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="a0eba-118">At the command prompt, type nslookup _\<FQDN of the Front End pool\>_ or  _\<FQDN of the Standard Edition server\>_, and then press ENTER.</span></span>
    
5. <span data-ttu-id="a0eba-119">验证您是否收到了解析为 FQDN 的相应 IP 地址的答复。</span><span class="sxs-lookup"><span data-stu-id="a0eba-119">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>
    

