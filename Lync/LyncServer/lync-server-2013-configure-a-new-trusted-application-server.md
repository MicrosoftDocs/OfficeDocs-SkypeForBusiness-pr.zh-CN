---
title: Lync Server 2013：配置新的受信任的应用程序服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a new trusted application server
ms:assetid: a7233db7-fac3-43ff-972e-3bc29a56adb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg617964(v=OCS.15)
ms:contentKeyID: 48185085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dae7e02d7642fed5fea60235283eaa0d7d7e1e35
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756356"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-new-trusted-application-server-in-lync-server-2013"></a><span data-ttu-id="b9ce5-102">在 Lync Server 2013 中配置新的受信任的应用程序服务器</span><span class="sxs-lookup"><span data-stu-id="b9ce5-102">Configure a new trusted application server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b9ce5-103">_**主题上次修改时间：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="b9ce5-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="b9ce5-104">受信任的应用程序是基于 Microsoft Lync Server 2013 信任的 Microsoft 统一通信托管 API （UCMA）3.0 核心 SDK 的应用程序。</span><span class="sxs-lookup"><span data-stu-id="b9ce5-104">A trusted application is an application based on Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK that is trusted by Microsoft Lync Server 2013.</span></span> <span data-ttu-id="b9ce5-105">有关 UCMA 应用程序的详细信息，请参阅 "统一通信托管 API 3.0 核心 SDK [http://go.microsoft.com/fwlink/p/?linkId=210320](http://go.microsoft.com/fwlink/p/?linkid=210320)文档"。</span><span class="sxs-lookup"><span data-stu-id="b9ce5-105">For details about UCMA applications, see “Unified Communications Managed API 3.0 Core SDK Documentation” at [http://go.microsoft.com/fwlink/p/?linkId=210320](http://go.microsoft.com/fwlink/p/?linkid=210320).</span></span>

<span data-ttu-id="b9ce5-106">有关配置 Microsoft Outlook Web Access （OWA）和 Lync Server 2013 的详细信息，请参阅 Microsoft Exchange Server 2013 文档中的 "配置 Outlook Web App 和 Lync Server 2010 集成"。</span><span class="sxs-lookup"><span data-stu-id="b9ce5-106">For information about configuring Microsoft Outlook Web Access (OWA) and Lync Server 2013, see “Configure Outlook Web App and Lync Server 2010 Integration” at the Microsoft Exchange Server 2013 documentation.</span></span>

<span data-ttu-id="b9ce5-107">若要在添加或删除服务器角色时成功发布、启用或禁用拓扑，您应以 RTCUniversalServerAdmins 和域管理员组成员的用户身份登录。</span><span class="sxs-lookup"><span data-stu-id="b9ce5-107">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged on as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="b9ce5-108">也可以委派正确的管理员权限和添加服务器角色的权限。</span><span class="sxs-lookup"><span data-stu-id="b9ce5-108">It is also possible to delegate the proper administrator permissions and rights for adding server roles.</span></span> <span data-ttu-id="b9ce5-109">有关详细信息，请参阅部署文档中[Lync Server 2013 中的委派设置权限](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="b9ce5-109">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in the Deployment documentation.</span></span> <span data-ttu-id="b9ce5-110">对于其他配置更改，仅需要 RTCUniversalServerAdmins 组中的成员身份。</span><span class="sxs-lookup"><span data-stu-id="b9ce5-110">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

<div>

## <a name="to-configure-a-trusted-application-server"></a><span data-ttu-id="b9ce5-111">配置受信任的应用程序服务器</span><span class="sxs-lookup"><span data-stu-id="b9ce5-111">To configure a trusted application server</span></span>

1.  <span data-ttu-id="b9ce5-112">以 Domain Admins 组和 RTCUniversalServerAdmins 组成员的身份登录安装了拓扑生成器的计算机。</span><span class="sxs-lookup"><span data-stu-id="b9ce5-112">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="b9ce5-113">启动拓扑生成器：单击 "**开始**"，单击 "**所有程序**"，单击 " **Microsoft Lync server 2013**"，然后单击 " **Lync server 拓扑生成器**"。</span><span class="sxs-lookup"><span data-stu-id="b9ce5-113">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

3.  <span data-ttu-id="b9ce5-114">选择 "**从现有部署下载拓扑**"，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="b9ce5-114">Select **Download topology from existing deployment**, and then click **OK**.</span></span>

4.  <span data-ttu-id="b9ce5-115">在 "**将拓扑另存为**" 对话框中，单击要使用的拓扑生成器文件，然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="b9ce5-115">In the **Save Topology As** dialog box, click the Topology Builder file you want to use, and then click **Save**.</span></span>

5.  <span data-ttu-id="b9ce5-116">在左窗格中，右键单击 "**受信任的应用程序服务器**"，然后单击 "**新建受信任的应用程序池**"。</span><span class="sxs-lookup"><span data-stu-id="b9ce5-116">In the left pane, right-click **Trusted application servers**, and then click **New Trusted Application Pool**.</span></span>

6.  <span data-ttu-id="b9ce5-117">输入受信任的应用程序池的**池 FQDN** ，选择它是单服务器还是多服务器，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="b9ce5-117">Enter the **Pool FQDN** of the trusted application pool, select whether it will be a single-server or multiple-server, and then click **Next**.</span></span>

7.  <span data-ttu-id="b9ce5-118">在 "**选择下一个跃点**" 页面上，从列表中选择 "Lync Server 2013 前端池"。</span><span class="sxs-lookup"><span data-stu-id="b9ce5-118">On the **Select the next hop** page, from the list, select the Lync Server 2013 Front End pool.</span></span>

8.  <span data-ttu-id="b9ce5-119">单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="b9ce5-119">Click **Finish**.</span></span>

9.  <span data-ttu-id="b9ce5-120">选择顶级节点**Lync Server 2013**，然后从 "**操作**" 菜单中单击 "**发布拓扑**"。</span><span class="sxs-lookup"><span data-stu-id="b9ce5-120">Select the top node **Lync Server 2013**, and then, from the **Actions** menu, click **Publish Topology**.</span></span>
    
    <span data-ttu-id="b9ce5-121">**受信任的应用程序池**应已成功创建并与正确的前端池关联。</span><span class="sxs-lookup"><span data-stu-id="b9ce5-121">The **Trusted Application Pool** should have been created successfully and associated with the correct Front End pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

