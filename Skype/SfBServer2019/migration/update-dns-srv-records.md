---
title: 更新 DNS SRV 记录
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 若要成功完成此过程，您应登录到服务器或域的 Domain Admins 组成员或 DnsAdmins 组的成员。
ms.openlocfilehash: f298db10f7030482b604734a1719756af4071ce2
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027226"
---
# <a name="update-dns-srv-records"></a><span data-ttu-id="68a98-103">更新 DNS SRV 记录</span><span class="sxs-lookup"><span data-stu-id="68a98-103">Update DNS SRV records</span></span>

<span data-ttu-id="68a98-104">若要成功完成此过程，您应登录到服务器或域的 Domain Admins 组成员或 DnsAdmins 组的成员。</span><span class="sxs-lookup"><span data-stu-id="68a98-104">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
  
<span data-ttu-id="68a98-105">本主题介绍如何在迁移到 Skype for Business Server 2019 后更新的域名系统 (DNS) 记录。</span><span class="sxs-lookup"><span data-stu-id="68a98-105">This topic describes how to update the Domain Name System (DNS) records after migrating to Skype for Business Server 2019.</span></span> <span data-ttu-id="68a98-106">所有用户都移动到 Skype 的业务服务器 2019年后，但在停用旧池或控制器之前，您必须在您的每个 SIP 域的内部 DNS 更新 DNS SRV 记录。</span><span class="sxs-lookup"><span data-stu-id="68a98-106">After all users have been moved to Skype for Business Server 2019, but before the legacy pool or Director is decommissioned, you must update the DNS SRV records in your internal DNS for every SIP domain.</span></span> <span data-ttu-id="68a98-107">此过程假定您的内部 DNS 具有用于您的 SIP 用户域的区域。</span><span class="sxs-lookup"><span data-stu-id="68a98-107">This procedure assumes that your internal DNS has zones for your SIP user domains.</span></span>
  
## <a name="to-configure-a-dns-srv-record"></a><span data-ttu-id="68a98-108">若要配置的 DNS SRV 记录</span><span class="sxs-lookup"><span data-stu-id="68a98-108">To configure a DNS SRV record</span></span>

1. <span data-ttu-id="68a98-109">在 DNS 服务器上，单击**开始**，单击**管理工具**，然后单击**DNS**。</span><span class="sxs-lookup"><span data-stu-id="68a98-109">On the DNS server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>
    
2. <span data-ttu-id="68a98-110">在您的 SIP 域的控制台树中，展开**正向查找区域**，展开 SIP 域中的 Skype 的业务服务器 2019年安装，并导航到 **_tcp**设置。</span><span class="sxs-lookup"><span data-stu-id="68a98-110">In the console tree for your SIP domain, expand **Forward Lookup Zones**, expand the SIP domain in which Skype for Business Server 2019 is installed, and navigate to the **_tcp** setting.</span></span> 
    
3. <span data-ttu-id="68a98-111">在右窗格中，右键单击 **_sipinternaltls**并选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="68a98-111">In the right pane, right-click **_sipinternaltls** and select **Properties**.</span></span>
    
4. <span data-ttu-id="68a98-112">在**主机提供此服务**，更新主机 FQDN 以指向业务服务器 2019年池 Skype。</span><span class="sxs-lookup"><span data-stu-id="68a98-112">In **Host offering this service**, update the host FQDN to point to the Skype for Business Server 2019 pool.</span></span>
    
5. <span data-ttu-id="68a98-113">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="68a98-113">Click **OK**.</span></span>
    
## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a><span data-ttu-id="68a98-114">若要验证可以解析前端池或 Standard Edition server 的 FQDN</span><span class="sxs-lookup"><span data-stu-id="68a98-114">To verify that the FQDN of the Front End pool or Standard Edition server can be resolved</span></span>

1. <span data-ttu-id="68a98-115">登录到域中的客户端计算机上。</span><span class="sxs-lookup"><span data-stu-id="68a98-115">Log on to a client computer in the domain.</span></span>
    
2. <span data-ttu-id="68a98-116">单击 **“开始”**，然后单击 **“运行”**。</span><span class="sxs-lookup"><span data-stu-id="68a98-116">Click **Start**, and then click **Run**.</span></span>
    
3. <span data-ttu-id="68a98-117">在**打开**框中，键入 cmd，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="68a98-117">In the **Open** box, type cmd, and then click **OK**.</span></span>
    
4. <span data-ttu-id="68a98-118">在命令提示符处键入 nslookup_\<的前端池的 FQDN\>_ 或_\<Standard Edition server 的 FQDN\>_，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="68a98-118">At the command prompt, type nslookup _\<FQDN of the Front End pool\>_ or  _\<FQDN of the Standard Edition server\>_, and then press ENTER.</span></span>
    
5. <span data-ttu-id="68a98-119">验证收到答复的 fqdn 解析为适当的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="68a98-119">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>
    

