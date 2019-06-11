---
title: 'Lync Server 2013: 安装 Lync 会议室系统管理 Web 门户'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Installing the Lync Room System Administrative Web Portal
ms:assetid: dd19e368-c338-4e21-a40d-6439d46a9748
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn436326(v=OCS.15)
ms:contentKeyID: 56737622
ms.date: 04/09/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d1c69231c6f07d2e57c0fe8be31d18ed6da109fc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829979"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a><span data-ttu-id="ac0f0-102">Installing the Lync Room System Administrative Web Portal in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ac0f0-102">Installing the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ac0f0-103">_**主题上次修改时间:** 2015-04-09_</span><span class="sxs-lookup"><span data-stu-id="ac0f0-103">_**Topic Last Modified:** 2015-04-09_</span></span>

<span data-ttu-id="ac0f0-104">您可以从 Microsoft 下载中心下载 Microsoft Lync 会议室系统管理 Web 门户[http://go.microsoft.com/fwlink/p/?LinkId=324044](http://go.microsoft.com/fwlink/p/?linkid=324044)。</span><span class="sxs-lookup"><span data-stu-id="ac0f0-104">You can download the Microsoft Lync Room System Administrative Web Portal from the Microsoft Download Center at [http://go.microsoft.com/fwlink/p/?LinkId=324044](http://go.microsoft.com/fwlink/p/?linkid=324044).</span></span>

<span data-ttu-id="ac0f0-105">若要安装 Lync 会议室系统管理 Web 门户, 请使用以下步骤。</span><span class="sxs-lookup"><span data-stu-id="ac0f0-105">To install the Lync Room System Administrative Web Portal, use the following steps.</span></span>

1.  <span data-ttu-id="ac0f0-106">通过在 Lync Server 命令行管理程序中运行以下 cmdlet 来配置受信任的应用程序端口:</span><span class="sxs-lookup"><span data-stu-id="ac0f0-106">Configure the Trusted Application Port by running the following cmdlet in Lync Server Management Shell:</span></span>
    
        Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457

2.  <span data-ttu-id="ac0f0-107">若要安装会议室门户, 请下载**LyncRoomAdminPortal** , 然后以管理员身份运行。</span><span class="sxs-lookup"><span data-stu-id="ac0f0-107">To install the Meeting Room Portal, download **LyncRoomAdminPortal.exe** and then run it as an administrator.</span></span>

3.  <span data-ttu-id="ac0f0-108">打开以下位置中的 Web.config 文件：</span><span class="sxs-lookup"><span data-stu-id="ac0f0-108">Open the Web.config file from the following location:</span></span>
    
    <span data-ttu-id="ac0f0-109">% 程序文件%\\Microsoft Lync Server 2013\\Web Components\\会议室门户\\程序 Int\\处理程序</span><span class="sxs-lookup"><span data-stu-id="ac0f0-109">%Program Files%\\Microsoft Lync Server 2013\\Web Components\\Meeting Room Portal\\Int\\Handler</span></span>\\

4.  <span data-ttu-id="ac0f0-110">在 web.config 文件中, 将 PortalUserName 更改为在步骤2中创建的用户名, 在 "配置 Lync 会议室系统管理员的先决条件" 部分下创建的用户名 (步骤中推荐的名称为 LRSApp):</span><span class="sxs-lookup"><span data-stu-id="ac0f0-110">In the Web.Config file, change the PortalUserName to the username created in Step 2 under the section “Configuring Prerequisites for Lync Room System Admin Portal” (the recommended name in the step is LRSApp):</span></span>
    
        <add key="PortalUserName" value="sip:LRSApp@domain.com" />

5.  <span data-ttu-id="ac0f0-111">由于 LRS 管理门户是一个受信任的应用程序, 因此无需在门户配置中提供密码。</span><span class="sxs-lookup"><span data-stu-id="ac0f0-111">Because the LRS Admin Portal is a trusted application, you do not need to provide the password in the portal configuration.</span></span> <span data-ttu-id="ac0f0-112">如果此用户使用的是非本地注册器，你需要通过在 Web.Config 文件中添加以下行来为其指定注册器：</span><span class="sxs-lookup"><span data-stu-id="ac0f0-112">If this user is using a different registrar than local registrar, you need to specify the registrar for it by adding the following line in the Web.Config file:</span></span>
    
        <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />

6.  <span data-ttu-id="ac0f0-113">如果使用的端口不是 5061，则需要在 Web.Config 文件中添加以下行：</span><span class="sxs-lookup"><span data-stu-id="ac0f0-113">If the port used is other than 5061, add the following line in the Web.Config file:</span></span>
    
        <add key="PortalUserRegistrarPort" value="5061" />

<div>

## <a name="verifying-installation-of-the-lync-room-system-administrative-web-portal"></a><span data-ttu-id="ac0f0-114">验证 Lync 会议室系统管理 Web 门户的安装</span><span class="sxs-lookup"><span data-stu-id="ac0f0-114">Verifying Installation of the Lync Room System Administrative Web Portal</span></span>

<span data-ttu-id="ac0f0-115">若要验证 Lync 会议室系统管理 Web 门户的安装, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="ac0f0-115">To verify installation of the Lync Room System Administrative Web Portal, do the following:</span></span>


1.  <span data-ttu-id="ac0f0-116">在前端服务器上，浏览至以下 URL：</span><span class="sxs-lookup"><span data-stu-id="ac0f0-116">On a Front End server, browse to the following URL:</span></span>
    
    <span data-ttu-id="ac0f0-117">https://\<fe-服务器\>/lrs</span><span class="sxs-lookup"><span data-stu-id="ac0f0-117">https://\<fe-server\>/lrs</span></span>
    
    <span data-ttu-id="ac0f0-118">你不应该看到任何错误，如下图所示：</span><span class="sxs-lookup"><span data-stu-id="ac0f0-118">You should not see any errors, as shown in the following image:</span></span>
    
    <span data-ttu-id="ac0f0-119">![Lync 会议室系统管理门户登录屏幕](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Lync 会议室系统管理门户登录屏幕")</span><span class="sxs-lookup"><span data-stu-id="ac0f0-119">![Lync Room System Admin Portal Sign In screen](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Lync Room System Admin Portal Sign In screen")</span></span>

2.  <span data-ttu-id="ac0f0-120">如果你未看到任何错误，请尝试从拓扑中的任何其他计算机访问以下 URL：</span><span class="sxs-lookup"><span data-stu-id="ac0f0-120">If you do not see any errors, try accessing the following URL from any other computer in the topology:</span></span>
    
    <span data-ttu-id="ac0f0-121">https://\<fe-服务器\>/lrs</span><span class="sxs-lookup"><span data-stu-id="ac0f0-121">https://\<fe-server\>/lrs</span></span>
    
    <span data-ttu-id="ac0f0-122">若要访问页面, 你需要添加 DNS 记录, 如 "自动客户登录所需的 DNS 记录" 中所述[http://go.microsoft.com/fwlink/p/?LinkId=318056](http://go.microsoft.com/fwlink/p/?linkid=318056)。</span><span class="sxs-lookup"><span data-stu-id="ac0f0-122">To access the page, you will need to add the DNS records as described in “Required DNS Records for Automatic Client Sign-In” at [http://go.microsoft.com/fwlink/p/?LinkId=318056](http://go.microsoft.com/fwlink/p/?linkid=318056).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

