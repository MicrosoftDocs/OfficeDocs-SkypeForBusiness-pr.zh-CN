---
title: Lync Server 2013：针对 Lync Room System 管理 Web 门户配置您的环境
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring your environment for the Lync Room System Administrative Web Portal
ms:assetid: 1bf3cc55-cfa8-46ee-a8bc-6dab3bff76b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn436325(v=OCS.15)
ms:contentKeyID: 56737623
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ef7596e65c44f871da8c26a0526a389dde72a45
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837143"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-your-lync-server-2013-environment-for-the-lync-room-system-administrative-web-portal"></a><span data-ttu-id="10b64-102">Configuring your Lync Server 2013 environment for the Lync Room System Administrative Web Portal</span><span class="sxs-lookup"><span data-stu-id="10b64-102">Configuring your Lync Server 2013 environment for the Lync Room System Administrative Web Portal</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="10b64-103">_**主题上次修改时间:** 2014-05-22_</span><span class="sxs-lookup"><span data-stu-id="10b64-103">_**Topic Last Modified:** 2014-05-22_</span></span>

<span data-ttu-id="10b64-104">若要使用 Lync 会议室系统 (LRS) 管理 Web 门户, 你需要安装或配置以下先决条件。</span><span class="sxs-lookup"><span data-stu-id="10b64-104">To use the Lync Room System (LRS) Administrative Web Portal, you will need to install or configure the following prerequisites.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="10b64-105">如果服务器配置了 Kerberos 和 NTLM 身份验证, 并且 LRS 在未加入域的计算机上运行, 则 Kerberos 身份验证将失败, 并且用户在管理门户中将看不到 LRS 的状态。</span><span class="sxs-lookup"><span data-stu-id="10b64-105">If the server is configured with both Kerberos and NTLM authentication, and LRS is running on a computer that is not joined to the domain, Kerberos authentication will fail and the user will not see the status of LRS in the administrative portal.</span></span> <span data-ttu-id="10b64-106">若要解决此问题, 请将服务器配置为 NTLM 身份验证或 NTLM 和 TLS DSK 身份验证 (没有 Kerberos), 或者将 LRS 计算机加入域。</span><span class="sxs-lookup"><span data-stu-id="10b64-106">To resolve this issue, configure the server with NTLM authentication or both NTLM and TLS-DSK authentication (without Kerberos), or join the LRS computer to the domain.</span></span>



</div>

1.  <span data-ttu-id="10b64-107">安装 Lync Server 2013 累积更新: Lync Server 拓扑中的2013至7月。</span><span class="sxs-lookup"><span data-stu-id="10b64-107">Install Lync Server 2013 Cumulative Updates: July 2013 in the Lync Server topology.</span></span>
    
    <span data-ttu-id="10b64-108">若要获取更新或查看其中包含的内容, 请参阅[Lync Server 2013 更新](http://go.microsoft.com/fwlink/p/?linkid=323959)。</span><span class="sxs-lookup"><span data-stu-id="10b64-108">To get the update or see what’s included with it, see [Updates for Lync Server 2013](http://go.microsoft.com/fwlink/p/?linkid=323959).</span></span>

2.  <span data-ttu-id="10b64-109">创建启用了 SIP 的 Active Directory 用户。</span><span class="sxs-lookup"><span data-stu-id="10b64-109">Create a SIP-enabled Active Directory user.</span></span>
    
    <span data-ttu-id="10b64-110">LRS 管理 Web 门户使用这些凭据从 Lync Server 查询信息。</span><span class="sxs-lookup"><span data-stu-id="10b64-110">The LRS Administrative Web Portal uses these credentials to query information from Lync Server.</span></span> <span data-ttu-id="10b64-111">建议的用户名为 LRSApp。</span><span class="sxs-lookup"><span data-stu-id="10b64-111">The recommended username is LRSApp.</span></span>

3.  <span data-ttu-id="10b64-112">创建名称为 LRSSupportAdminGroup 的 Active Directory 安全组。</span><span class="sxs-lookup"><span data-stu-id="10b64-112">Create an Active Directory security group with name LRSSupportAdminGroup.</span></span>
    
    <span data-ttu-id="10b64-p103">创建“组作用域”为“全局”、“组类型”为“安全”的组。添加到此组启用了 SIP 的用户将被授权查看聊天室列表并执行特定命令（例如收集日志）。</span><span class="sxs-lookup"><span data-stu-id="10b64-p103">Create the group with Group Scope as Global and Group Type as Security. SIP enabled users who are added to this group will be authorized to see the list of rooms and execute certain commands, such as collecting logs.</span></span>

4.  <span data-ttu-id="10b64-115">创建名称为 LRSFullAccessAdminGroup 的 Active Directory 安全组。</span><span class="sxs-lookup"><span data-stu-id="10b64-115">Create an Active Directory security group with name LRSFullAccessAdminGroup.</span></span>
    
    <span data-ttu-id="10b64-116">创建组范围为 "全局" 和 "组" 类型的组作为安全性。添加到该组的已启用 SIP 用户已获得使用所有管理员门户功能的授权。</span><span class="sxs-lookup"><span data-stu-id="10b64-116">Create the group with Group Scope as Global and Group Type as Security.SIP enabled users who are added to this group are authorized to use all admin portal functionality.</span></span>
    
     
    
    <span data-ttu-id="10b64-117">![具有安全组角色的管理员组的列表](images/Dn436325.5d432819-a2e2-452c-bc2a-5d4ee79d8c33(OCS.15).png "具有安全组角色的管理员组的列表")</span><span class="sxs-lookup"><span data-stu-id="10b64-117">![List of Admin Groups with security group role](images/Dn436325.5d432819-a2e2-452c-bc2a-5d4ee79d8c33(OCS.15).png "List of Admin Groups with security group role")</span></span>  
    
     

5.  <span data-ttu-id="10b64-118">将 LRSFullAccessAdminGroup 添加为 LRSSupportAdminGroup 的成员。</span><span class="sxs-lookup"><span data-stu-id="10b64-118">Add LRSFullAccessAdminGroup as a member of LRSSupportAdminGroup.</span></span>
    
    <span data-ttu-id="10b64-119">![LRSSupportAdminGroup 属性 "成员" 页面](images/Dn436325.91a4a28a-cacf-4ef6-aac1-915ec41c9648(OCS.15).png "LRSSupportAdminGroup 属性 \"成员\" 页面")</span><span class="sxs-lookup"><span data-stu-id="10b64-119">![LRSSupportAdminGroup Properties Members page](images/Dn436325.91a4a28a-cacf-4ef6-aac1-915ec41c9648(OCS.15).png "LRSSupportAdminGroup Properties Members page")</span></span>  
    
     

6.  <span data-ttu-id="10b64-120">创建名称为 LRSSupport 的启用了 SIP 的 Active Directory 用户。</span><span class="sxs-lookup"><span data-stu-id="10b64-120">Create a SIP enabled Active Directory user with name LRSSupport.</span></span> <span data-ttu-id="10b64-121">将此用户添加到 LRSSupportAdminGroup。</span><span class="sxs-lookup"><span data-stu-id="10b64-121">Add this user to LRSSupportAdminGroup.</span></span>
    
    <span data-ttu-id="10b64-122">![LRSSupportAdminGroup 属性 "成员" 页面](images/Dn436325.7638055d-22ac-4909-914d-1966f5623909(OCS.15).png "LRSSupportAdminGroup 属性 \"成员\" 页面")</span><span class="sxs-lookup"><span data-stu-id="10b64-122">![LRSSupportAdminGroup Properties Members page](images/Dn436325.7638055d-22ac-4909-914d-1966f5623909(OCS.15).png "LRSSupportAdminGroup Properties Members page")</span></span>  
    
     

7.  <span data-ttu-id="10b64-123">安装 Visual Studio 2010 SP1 和 Visual Web Developer 2010 SP1 的 ASP.NET MVC 4, 可在 Microsoft 下载中心查看[http://go.microsoft.com/fwlink/p/?LinkId=323967](http://go.microsoft.com/fwlink/p/?linkid=323967)。</span><span class="sxs-lookup"><span data-stu-id="10b64-123">Install ASP.NET MVC 4 for Visual Studio 2010 SP1 and Visual Web Developer 2010 SP1, available in the Microsoft Download Center at [http://go.microsoft.com/fwlink/p/?LinkId=323967](http://go.microsoft.com/fwlink/p/?linkid=323967).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

