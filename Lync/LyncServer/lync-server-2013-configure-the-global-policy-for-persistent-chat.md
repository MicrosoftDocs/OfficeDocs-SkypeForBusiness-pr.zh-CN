---
title: Lync Server 2013：配置持久聊天的全局策略
description: Lync Server 2013：配置持久聊天的全局策略。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the global policy for Persistent Chat
ms:assetid: 6176eb5c-19de-4c07-bcc0-2e38f8965966
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204951(v=OCS.15)
ms:contentKeyID: 48184323
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 830074c31791ee8ff489d9a67af189be609c7f4c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544938"
---
# <a name="configure-the-global-policy-for-persistent-chat-in-lync-server-2013"></a><span data-ttu-id="b3230-103">在 Lync Server 2013 中配置持久聊天的全局策略</span><span class="sxs-lookup"><span data-stu-id="b3230-103">Configure the global policy for Persistent Chat in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b3230-104">_**上次修改的主题：** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="b3230-104">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="b3230-105">您可以使用默认全局策略来为部署中的所有用户启用持久聊天设置。</span><span class="sxs-lookup"><span data-stu-id="b3230-105">You can use the default global policy by itself to enable Persistent Chat settings for all users in your deployment.</span></span> <span data-ttu-id="b3230-106">您还可以为网站和用户指定其他策略，以控制是否为特定用户和网站启用或禁用持久聊天。</span><span class="sxs-lookup"><span data-stu-id="b3230-106">You can also specify additional policies for sites and users to control whether Persistent Chat is enabled or disabled for specific users and sites.</span></span>

<span data-ttu-id="b3230-107">无法删除全局策略。</span><span class="sxs-lookup"><span data-stu-id="b3230-107">You cannot delete the global policy.</span></span> <span data-ttu-id="b3230-108">如果试图删除全局策略，配置将重置为默认值。</span><span class="sxs-lookup"><span data-stu-id="b3230-108">If you attempt to delete it, the configuration resets to the default values.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b3230-109">若要配置和使用持久聊天服务器，必须首先使用拓扑生成器将持久聊天服务器支持添加到拓扑，然后发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="b3230-109">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="b3230-110">有关详细信息，请参阅部署文档中的在 <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Lync server 2013 中将持久聊天服务器添加到部署</A> 。</span><span class="sxs-lookup"><span data-stu-id="b3230-110">For details, see <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="b3230-111">若要配置持久聊天服务器配置设置，请参阅部署文档中的 " <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">全局或在 Lync server 2013 中为持久聊天服务器池配置持久聊天服务器选项</A> "。</span><span class="sxs-lookup"><span data-stu-id="b3230-111">To configure Persistent Chat Server configuration settings, see <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Configure Persistent Chat Server options globally or for Persistent Chat Server pool in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-configure-the-global-policy-for-persistent-chat"></a><span data-ttu-id="b3230-112">配置持久聊天的全局策略</span><span class="sxs-lookup"><span data-stu-id="b3230-112">To configure the Global Policy for Persistent Chat</span></span>

1.  <span data-ttu-id="b3230-113">使用分配给 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="b3230-113">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b3230-114">从 " **开始** " 菜单中，选择 "Lync Server 控制面板" 或打开一个浏览器窗口，然后输入管理 URL。</span><span class="sxs-lookup"><span data-stu-id="b3230-114">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="b3230-115">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅操作文档中的 [Open Lync Server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md) 。</span><span class="sxs-lookup"><span data-stu-id="b3230-115">For details about the different methods that you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md) in the Operations documentation.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="b3230-116">您还可以使用 Windows PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b3230-116">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="b3230-117">有关详细信息，请参阅部署文档中的 <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">使用 Windows PowerShell Cmdlet 配置持久聊天服务器</A> 。</span><span class="sxs-lookup"><span data-stu-id="b3230-117">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="b3230-118">在 "Lync Server 控制面板" 中，单击 " **持久聊天**"，然后单击 " **持久聊天策略**"。</span><span class="sxs-lookup"><span data-stu-id="b3230-118">In Lync Server Control Panel, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>

4.  <span data-ttu-id="b3230-119">单击策略列表中的“全局”\*\*\*\*，再单击“编辑”\*\*\*\*，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b3230-119">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="b3230-120">在“编辑持久聊天策略 - 全局”\*\*\*\* 中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="b3230-120">In **Edit Persistent Chat Policy - Global**, do the following:</span></span>
    
      - <span data-ttu-id="b3230-121">在“名称”\*\*\*\* 中，如果不想使用全局策略的默认名称 Global，可以为其指定新名称。</span><span class="sxs-lookup"><span data-stu-id="b3230-121">In **Name**, specify a new name for the global policy, if you do not want to use the default of Global.</span></span>
    
      - <span data-ttu-id="b3230-122">在 " **说明**" 中，提供有关 (用户策略的详细信息（例如，centralSiteName) 的全局策略）。</span><span class="sxs-lookup"><span data-stu-id="b3230-122">In **Description**, provide details about what the user policy is (for example, Global policy for centralSiteName).</span></span>
    
      - <span data-ttu-id="b3230-123">若要控制未通过站点策略或用户策略明确控制的所有站点和用户的持久聊天，请选中或清除 " **启用持久聊天** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="b3230-123">To control Persistent Chat for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Enable Persistent Chat** check box.</span></span>

6.  <span data-ttu-id="b3230-124">单击“提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b3230-124">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

