---
title: Lync Server 2013：为 Lync 会议室系统管理 Web 门户配置你的环境
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring your environment for the Lync Room System Administrative Web Portal
ms:assetid: 1bf3cc55-cfa8-46ee-a8bc-6dab3bff76b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn436325(v=OCS.15)
ms:contentKeyID: 56737623
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 739e440765feb07d70b7f5a8d1490a85a938701d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154064"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-your-lync-server-2013-environment-for-the-lync-room-system-administrative-web-portal"></a><span data-ttu-id="9bfa1-102">为 Lync 会议室系统管理 Web 门户配置 Lync Server 2013 环境</span><span class="sxs-lookup"><span data-stu-id="9bfa1-102">Configuring your Lync Server 2013 environment for the Lync Room System Administrative Web Portal</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9bfa1-103">_**上次修改的主题：** 2014-05-22_</span><span class="sxs-lookup"><span data-stu-id="9bfa1-103">_**Topic Last Modified:** 2014-05-22_</span></span>

<span data-ttu-id="9bfa1-104">若要使用 Lync 会议室系统（LRS）管理 Web 门户，您将需要安装或配置以下必备组件。</span><span class="sxs-lookup"><span data-stu-id="9bfa1-104">To use the Lync Room System (LRS) Administrative Web Portal, you will need to install or configure the following prerequisites.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="9bfa1-105">如果服务器配置了 Kerberos 和 NTLM 身份验证，并且 LRS 在未加入域的计算机上运行，则 Kerberos 身份验证将失败，并且用户将不会在管理门户中看到 LRS 的状态。</span><span class="sxs-lookup"><span data-stu-id="9bfa1-105">If the server is configured with both Kerberos and NTLM authentication, and LRS is running on a computer that is not joined to the domain, Kerberos authentication will fail and the user will not see the status of LRS in the administrative portal.</span></span> <span data-ttu-id="9bfa1-106">若要解决此问题，请将服务器配置为使用 NTLM 身份验证或 NTLM 和 TLS DSK 身份验证（不使用 Kerberos），或将 LRS 计算机加入域。</span><span class="sxs-lookup"><span data-stu-id="9bfa1-106">To resolve this issue, configure the server with NTLM authentication or both NTLM and TLS-DSK authentication (without Kerberos), or join the LRS computer to the domain.</span></span>



</div>

1.  <span data-ttu-id="9bfa1-107">Install Lync Server 2013 累积更新： Lync Server 拓扑中的7月2013。</span><span class="sxs-lookup"><span data-stu-id="9bfa1-107">Install Lync Server 2013 Cumulative Updates: July 2013 in the Lync Server topology.</span></span>
    
    <span data-ttu-id="9bfa1-108">若要获取更新或查看它所包含的内容，请参阅[Lync Server 2013 更新](https://go.microsoft.com/fwlink/p/?linkid=323959)。</span><span class="sxs-lookup"><span data-stu-id="9bfa1-108">To get the update or see what’s included with it, see [Updates for Lync Server 2013](https://go.microsoft.com/fwlink/p/?linkid=323959).</span></span>

2.  <span data-ttu-id="9bfa1-109">创建启用了 SIP 的 Active Directory 用户。</span><span class="sxs-lookup"><span data-stu-id="9bfa1-109">Create a SIP-enabled Active Directory user.</span></span>
    
    <span data-ttu-id="9bfa1-110">LRS 管理 Web 门户使用这些凭据来查询 Lync Server 中的信息。</span><span class="sxs-lookup"><span data-stu-id="9bfa1-110">The LRS Administrative Web Portal uses these credentials to query information from Lync Server.</span></span> <span data-ttu-id="9bfa1-111">建议的用户名为 LRSApp。</span><span class="sxs-lookup"><span data-stu-id="9bfa1-111">The recommended username is LRSApp.</span></span>

3.  <span data-ttu-id="9bfa1-112">创建名称为 LRSSupportAdminGroup 的 Active Directory 安全组。</span><span class="sxs-lookup"><span data-stu-id="9bfa1-112">Create an Active Directory security group with name LRSSupportAdminGroup.</span></span>
    
    <span data-ttu-id="9bfa1-113">创建组作用域为 "全局" 和 "组类型" 作为 "安全" 的组。</span><span class="sxs-lookup"><span data-stu-id="9bfa1-113">Create the group with Group Scope as Global and Group Type as Security.</span></span> <span data-ttu-id="9bfa1-114">添加到此组的启用 SIP 的用户将被授权查看聊天室列表并执行某些命令，如收集日志。</span><span class="sxs-lookup"><span data-stu-id="9bfa1-114">SIP enabled users who are added to this group will be authorized to see the list of rooms and execute certain commands, such as collecting logs.</span></span>

4.  <span data-ttu-id="9bfa1-115">创建名称为 LRSFullAccessAdminGroup 的 Active Directory 安全组。</span><span class="sxs-lookup"><span data-stu-id="9bfa1-115">Create an Active Directory security group with name LRSFullAccessAdminGroup.</span></span>
    
    <span data-ttu-id="9bfa1-116">创建组作用域为 "全局" 和 "组类型" 的组作为安全性。添加到此组的启用 SIP 的用户已被授权使用所有管理门户功能。</span><span class="sxs-lookup"><span data-stu-id="9bfa1-116">Create the group with Group Scope as Global and Group Type as Security.SIP enabled users who are added to this group are authorized to use all admin portal functionality.</span></span>
    
     
    
    <span data-ttu-id="9bfa1-117">![具有安全组角色的管理员组的列表](images/Dn436325.5d432819-a2e2-452c-bc2a-5d4ee79d8c33(OCS.15).png "具有安全组角色的管理员组的列表")</span><span class="sxs-lookup"><span data-stu-id="9bfa1-117">![List of Admin Groups with security group role](images/Dn436325.5d432819-a2e2-452c-bc2a-5d4ee79d8c33(OCS.15).png "List of Admin Groups with security group role")</span></span>  
    
     

5.  <span data-ttu-id="9bfa1-118">将 LRSFullAccessAdminGroup 添加为 LRSSupportAdminGroup 的成员。</span><span class="sxs-lookup"><span data-stu-id="9bfa1-118">Add LRSFullAccessAdminGroup as a member of LRSSupportAdminGroup.</span></span>
    
    <span data-ttu-id="9bfa1-119">![LRSSupportAdminGroup 属性 "成员" 页](images/Dn436325.91a4a28a-cacf-4ef6-aac1-915ec41c9648(OCS.15).png "LRSSupportAdminGroup 属性 "成员" 页")</span><span class="sxs-lookup"><span data-stu-id="9bfa1-119">![LRSSupportAdminGroup Properties Members page](images/Dn436325.91a4a28a-cacf-4ef6-aac1-915ec41c9648(OCS.15).png "LRSSupportAdminGroup Properties Members page")</span></span>  
    
     

6.  <span data-ttu-id="9bfa1-120">创建具有名称 LRSSupport 的启用 SIP 的 Active Directory 用户。</span><span class="sxs-lookup"><span data-stu-id="9bfa1-120">Create a SIP enabled Active Directory user with name LRSSupport.</span></span> <span data-ttu-id="9bfa1-121">将此用户添加到 LRSSupportAdminGroup。</span><span class="sxs-lookup"><span data-stu-id="9bfa1-121">Add this user to LRSSupportAdminGroup.</span></span>
    
    <span data-ttu-id="9bfa1-122">![LRSSupportAdminGroup 属性 "成员" 页](images/Dn436325.7638055d-22ac-4909-914d-1966f5623909(OCS.15).png "LRSSupportAdminGroup 属性 "成员" 页")</span><span class="sxs-lookup"><span data-stu-id="9bfa1-122">![LRSSupportAdminGroup Properties Members page](images/Dn436325.7638055d-22ac-4909-914d-1966f5623909(OCS.15).png "LRSSupportAdminGroup Properties Members page")</span></span>  
    
     

7.  <span data-ttu-id="9bfa1-123">安装 ASP.NET MVC 4 for Visual Studio 2010 SP1 和 Visual Web Developer 2010 SP1 （可从 Microsoft 下载中心处[https://go.microsoft.com/fwlink/p/?LinkId=323967](https://go.microsoft.com/fwlink/p/?linkid=323967)获取）。</span><span class="sxs-lookup"><span data-stu-id="9bfa1-123">Install ASP.NET MVC 4 for Visual Studio 2010 SP1 and Visual Web Developer 2010 SP1, available in the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=323967](https://go.microsoft.com/fwlink/p/?linkid=323967).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

