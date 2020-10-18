---
title: Lync Server 2013：安装 Lync 会议室系统管理 Web 门户
description: Lync Server 2013：安装 Lync 会议室系统管理 Web 门户。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing the Lync Room System Administrative Web Portal
ms:assetid: dd19e368-c338-4e21-a40d-6439d46a9748
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn436326(v=OCS.15)
ms:contentKeyID: 56737622
ms.date: 04/09/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0fba239346d75142bb4009c58e0ac67e8e1f3bcb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573868"
---
# <a name="installing-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a><span data-ttu-id="e0fe6-103">在 Lync Server 2013 中安装 Lync 会议室系统管理 Web 门户</span><span class="sxs-lookup"><span data-stu-id="e0fe6-103">Installing the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e0fe6-104">_**上次修改的主题：** 2015-04-09_</span><span class="sxs-lookup"><span data-stu-id="e0fe6-104">_**Topic Last Modified:** 2015-04-09_</span></span>

<span data-ttu-id="e0fe6-105">您可以从 Microsoft 下载中心下载 Microsoft Lync 会议室系统管理 Web 门户 [https://go.microsoft.com/fwlink/p/?LinkId=324044](https://go.microsoft.com/fwlink/p/?linkid=324044) 。</span><span class="sxs-lookup"><span data-stu-id="e0fe6-105">You can download the Microsoft Lync Room System Administrative Web Portal from the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=324044](https://go.microsoft.com/fwlink/p/?linkid=324044).</span></span>

<span data-ttu-id="e0fe6-106">若要安装 Lync 会议室系统管理 Web 门户，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="e0fe6-106">To install the Lync Room System Administrative Web Portal, use the following steps.</span></span>

1.  <span data-ttu-id="e0fe6-107">在 Lync Server 命令行管理程序中运行以下 cmdlet，以配置受信任的应用程序端口：</span><span class="sxs-lookup"><span data-stu-id="e0fe6-107">Configure the Trusted Application Port by running the following cmdlet in Lync Server Management Shell:</span></span>
    
        Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457

2.  <span data-ttu-id="e0fe6-108">若要安装会议室门户，请下载 **LyncRoomAdminPortal.exe** ，然后以管理员身份运行。</span><span class="sxs-lookup"><span data-stu-id="e0fe6-108">To install the Meeting Room Portal, download **LyncRoomAdminPortal.exe** and then run it as an administrator.</span></span>

3.  <span data-ttu-id="e0fe6-109">从以下位置打开 "Web.config" 文件：</span><span class="sxs-lookup"><span data-stu-id="e0fe6-109">Open the Web.config file from the following location:</span></span>
    
    <span data-ttu-id="e0fe6-110">% Program Files% \\ Microsoft Lync Server 2013 \\ Web 组件会议室 \\ 门户 \\ Int \\ 处理程序</span><span class="sxs-lookup"><span data-stu-id="e0fe6-110">%Program Files%\\Microsoft Lync Server 2013\\Web Components\\Meeting Room Portal\\Int\\Handler</span></span>\\

4.  <span data-ttu-id="e0fe6-111">在 "Web.Config" 文件中，将 PortalUserName 更改为 "配置 Lync 会议室系统管理门户的必备组件" 一节中的步骤2中创建的用户名 (步骤中的建议名称是 LRSApp) ：</span><span class="sxs-lookup"><span data-stu-id="e0fe6-111">In the Web.Config file, change the PortalUserName to the username created in Step 2 under the section “Configuring Prerequisites for Lync Room System Admin Portal” (the recommended name in the step is LRSApp):</span></span>
    
        <add key="PortalUserName" value="sip:LRSApp@domain.com" />

5.  <span data-ttu-id="e0fe6-112">由于 LRS 管理门户是一个受信任的应用程序，因此您无需在门户配置中提供密码。</span><span class="sxs-lookup"><span data-stu-id="e0fe6-112">Because the LRS Admin Portal is a trusted application, you do not need to provide the password in the portal configuration.</span></span> <span data-ttu-id="e0fe6-113">如果此用户使用的是与本地注册器不同的注册器，则需要通过在 Web.Config 文件中添加以下行来为其指定注册器：</span><span class="sxs-lookup"><span data-stu-id="e0fe6-113">If this user is using a different registrar than local registrar, you need to specify the registrar for it by adding the following line in the Web.Config file:</span></span>
    
        <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />

6.  <span data-ttu-id="e0fe6-114">如果使用的端口不是5061，则在 Web.Config 文件中添加以下行：</span><span class="sxs-lookup"><span data-stu-id="e0fe6-114">If the port used is other than 5061, add the following line in the Web.Config file:</span></span>
    
        <add key="PortalUserRegistrarPort" value="5061" />

<div>

## <a name="verifying-installation-of-the-lync-room-system-administrative-web-portal"></a><span data-ttu-id="e0fe6-115">验证 Lync 会议室系统管理 Web 门户的安装</span><span class="sxs-lookup"><span data-stu-id="e0fe6-115">Verifying Installation of the Lync Room System Administrative Web Portal</span></span>

<span data-ttu-id="e0fe6-116">若要验证 Lync 会议室系统管理 Web 门户的安装，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e0fe6-116">To verify installation of the Lync Room System Administrative Web Portal, do the following:</span></span>


1.  <span data-ttu-id="e0fe6-117">在前端服务器上，浏览到以下 URL：</span><span class="sxs-lookup"><span data-stu-id="e0fe6-117">On a Front End server, browse to the following URL:</span></span>
    
    <span data-ttu-id="e0fe6-118">https:// \<fe-server\> /lrs</span><span class="sxs-lookup"><span data-stu-id="e0fe6-118">https://\<fe-server\>/lrs</span></span>
    
    <span data-ttu-id="e0fe6-119">您不应看到任何错误，如下图所示：</span><span class="sxs-lookup"><span data-stu-id="e0fe6-119">You should not see any errors, as shown in the following image:</span></span>
    
    <span data-ttu-id="e0fe6-120">![Lync 会议室系统管理门户登录屏幕](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Lync 会议室系统管理门户登录屏幕")</span><span class="sxs-lookup"><span data-stu-id="e0fe6-120">![Lync Room System Admin Portal Sign In screen](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Lync Room System Admin Portal Sign In screen")</span></span>

2.  <span data-ttu-id="e0fe6-121">如果没有看到任何错误，请尝试从拓扑中的任何其他计算机访问以下 URL：</span><span class="sxs-lookup"><span data-stu-id="e0fe6-121">If you do not see any errors, try accessing the following URL from any other computer in the topology:</span></span>
    
    <span data-ttu-id="e0fe6-122">https:// \<fe-server\> /lrs</span><span class="sxs-lookup"><span data-stu-id="e0fe6-122">https://\<fe-server\>/lrs</span></span>
    
    <span data-ttu-id="e0fe6-123">若要访问该页面，你将需要添加 DNS 记录，如中的 "自动客户端登录所需的 DNS 记录" 中所述 [https://go.microsoft.com/fwlink/p/?LinkId=318056](https://go.microsoft.com/fwlink/p/?linkid=318056) 。</span><span class="sxs-lookup"><span data-stu-id="e0fe6-123">To access the page, you will need to add the DNS records as described in “Required DNS Records for Automatic Client Sign-In” at [https://go.microsoft.com/fwlink/p/?LinkId=318056](https://go.microsoft.com/fwlink/p/?linkid=318056).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

