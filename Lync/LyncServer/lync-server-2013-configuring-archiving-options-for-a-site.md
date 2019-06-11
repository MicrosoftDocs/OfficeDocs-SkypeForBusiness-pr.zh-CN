---
title: 'Lync Server 2013: 配置网站的存档选项'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Archiving options for a site
ms:assetid: 59b48fd9-d5fc-40b4-abae-e9cf89ee5573
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204930(v=OCS.15)
ms:contentKeyID: 48184247
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 14b0e29a2796c23c13a16bfb3e8a202a0a535aaa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837282"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-archiving-options-for-a-site-in-lync-server-2013"></a><span data-ttu-id="1ddc5-102">在 Lync Server 2013 中配置网站的存档选项</span><span class="sxs-lookup"><span data-stu-id="1ddc5-102">Configuring Archiving options for a site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ddc5-103">_**主题上次修改时间:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="1ddc5-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="1ddc5-104">你可以通过在每个网站的存档配置中创建和配置选项来指定要应用到特定网站的存档选项。</span><span class="sxs-lookup"><span data-stu-id="1ddc5-104">You can specify Archiving options to be applied to specific sites by creating and configuring options in an Archiving configuration for each of those sites.</span></span> <span data-ttu-id="1ddc5-105">站点配置可覆盖全局配置，但它仅适用于站点配置中指定的站点。</span><span class="sxs-lookup"><span data-stu-id="1ddc5-105">A site configuration overrides the global configuration, but only for the site specified in the site configuration.</span></span> <span data-ttu-id="1ddc5-106">池配置替代网站配置</span><span class="sxs-lookup"><span data-stu-id="1ddc5-106">Pool configurations override site configurations</span></span>

<span data-ttu-id="1ddc5-107">有关存档配置的工作原理的详细信息 (包括全局、网站和池配置的层次结构), 请参阅规划文档、部署文档或操作文档中的[存档在 Lync Server 2013 中的工作原理](lync-server-2013-how-archiving-works.md).</span><span class="sxs-lookup"><span data-stu-id="1ddc5-107">For details about how Archiving configurations work, including the hierarchy for global, site, and pool configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1ddc5-108">在启用存档之前, 应在存档配置中指定所有适当的选项。</span><span class="sxs-lookup"><span data-stu-id="1ddc5-108">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1ddc5-109">若要启用存档，您必须指定存档策略以控制全局级别（适当情况下还包括站点和用户级别）的内部和外部通信的存档。</span><span class="sxs-lookup"><span data-stu-id="1ddc5-109">To enable archiving, you must specify archiving policies to control the archiving of internal and external communications at the global level and, if appropriate, at site and user levels.</span></span> <span data-ttu-id="1ddc5-110">如果配置用户级别策略，还必须向特定用户分配用户策略。</span><span class="sxs-lookup"><span data-stu-id="1ddc5-110">If you configure user-level policies, you must also assign the user policies to specific users.</span></span> <span data-ttu-id="1ddc5-111">有关创建和配置存档策略的详细信息, 请参阅在操作文档中<A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">管理 Lync Server 2013 中的内部和外部通信的存档</A>。</span><span class="sxs-lookup"><span data-stu-id="1ddc5-111">For details about creating and configuring archiving policies, see <A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">Managing the Archiving of internal and external communications in Lync Server 2013</A> in the Operations documentation.</span></span>



</div>

<div>

## <a name="to-configure-archiving-options-at-the-site-level"></a><span data-ttu-id="1ddc5-112">在网站级别配置存档选项</span><span class="sxs-lookup"><span data-stu-id="1ddc5-112">To configure archiving options at the site level</span></span>

1.  <span data-ttu-id="1ddc5-113">使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="1ddc5-113">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1ddc5-114">打开一个浏览器窗口, 然后输入管理员 URL 以打开 Lync Server 2013 控制面板。</span><span class="sxs-lookup"><span data-stu-id="1ddc5-114">Open a browser window, and then enter the Admin URL to open the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="1ddc5-115">有关可用于启动 Lync Server 2013 控制面板的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="1ddc5-115">For details about the different methods you can use to start Lync Server 2013 Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1ddc5-116">在左侧导航栏中，单击“监控和存档”\*\*\*\*，然后单击“存档配置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1ddc5-116">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="1ddc5-117">在“**存档配置**”页上，单击“**新建**”，然后单击“**站点配置**”。</span><span class="sxs-lookup"><span data-stu-id="1ddc5-117">On the **Archiving Configuration** page, click **New**, and then click **Site Configuration**.</span></span>

5.  <span data-ttu-id="1ddc5-118">在“**选择站点**”中，选择要为存档配置的站点。</span><span class="sxs-lookup"><span data-stu-id="1ddc5-118">In **Select a Site**, select the site to be configured for archiving.</span></span>

6.  <span data-ttu-id="1ddc5-119">在“**新建存档设置**”的“**存档设置**”下拉列表框中，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="1ddc5-119">In **New Archiving Setting**, in the **Archiving setting** drop-down list box, do one of the following:</span></span>
    
      - <span data-ttu-id="1ddc5-120">若要只为即时消息 (IM) 会话启用存档，请单击“**存档 IM 会话**”。</span><span class="sxs-lookup"><span data-stu-id="1ddc5-120">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
      - <span data-ttu-id="1ddc5-121">若要为 IM 会话和会议启用存档，请单击“**存档 IM 和 Web 会议会话**”。</span><span class="sxs-lookup"><span data-stu-id="1ddc5-121">To enable archiving for both IM sessions and conferences, click **Archive IM and web conferencing sessions**.</span></span>
    
      - <span data-ttu-id="1ddc5-122">若要为策略禁用存档，请单击“**禁用存档**”。</span><span class="sxs-lookup"><span data-stu-id="1ddc5-122">To disable archiving for the policy, click **Disable archiving**.</span></span>

7.  <span data-ttu-id="1ddc5-123">另请在“**新建存档设置**”中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="1ddc5-123">Also in **New Archiving Setting**, do the following:</span></span>
    
      - <span data-ttu-id="1ddc5-124">要在存档不可用时阻止活动，请选中“**存档失败时阻止即时消息 (IM) 或 Web 会议会话**”复选框。</span><span class="sxs-lookup"><span data-stu-id="1ddc5-124">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
      - <span data-ttu-id="1ddc5-125">若要使用 Microsoft Exchange Server 存储存档数据, 请单击 " **Microsoft exchange 集成**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="1ddc5-125">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
      - <span data-ttu-id="1ddc5-126">若要启用数据清除，请选中“**启用存档数据清除**”复选框，然后执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="1ddc5-126">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
        
          - <span data-ttu-id="1ddc5-127">要指定在特定的天数之后清除，请单击“**在最长期限（天）后清除导出的存档数据和存储的存档数据**”，然后指定天数。</span><span class="sxs-lookup"><span data-stu-id="1ddc5-127">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
        
          - <span data-ttu-id="1ddc5-128">要限制仅清除已导出的存档数据，请单击“**仅清除导出的存档数据**”。</span><span class="sxs-lookup"><span data-stu-id="1ddc5-128">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>

8.  <span data-ttu-id="1ddc5-129">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="1ddc5-129">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

