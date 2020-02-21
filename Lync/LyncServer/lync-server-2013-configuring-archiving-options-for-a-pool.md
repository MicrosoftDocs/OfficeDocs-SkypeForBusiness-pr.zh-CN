---
title: Lync Server 2013：配置池的存档选项
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Archiving options for a pool
ms:assetid: b7cb0fd8-3d31-4858-a75c-c66a7742556e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205200(v=OCS.15)
ms:contentKeyID: 48185230
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e82c44a157b33de36495699e15cf7a48b8dd61f4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188545"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-archiving-options-for-a-pool-in-lync-server-2013"></a><span data-ttu-id="69553-102">在 Lync Server 2013 中配置池的存档选项</span><span class="sxs-lookup"><span data-stu-id="69553-102">Configuring Archiving options for a pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="69553-103">_**上次修改的主题：** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="69553-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="69553-p101">可以通过在每个特定池的存档配置中创建并配置选项来指定要应用于这些池的存档选项。池配置可重写全局配置和站点配置，但它仅适用于池配置中指定的池。</span><span class="sxs-lookup"><span data-stu-id="69553-p101">You can specify Archiving options to be applied to specific pools by creating and configuring options in an Archiving configuration for each of those pools. A pool configuration overrides the global configuration and site configuration, but only for the pool specified in the pool configuration.</span></span>

<span data-ttu-id="69553-106">有关存档配置的工作原理（包括全局、站点和池配置的层次结构）的详细信息，请参阅规划文档、部署文档或操作文档中的[存档在 Lync Server 2013 中的工作原理](lync-server-2013-how-archiving-works.md)。</span><span class="sxs-lookup"><span data-stu-id="69553-106">For details about how Archiving configurations work, including the hierarchy for global, site, and pool configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="69553-107">在启用存档之前，应在存档配置中指定所有适当选项。</span><span class="sxs-lookup"><span data-stu-id="69553-107">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span> <span data-ttu-id="69553-108">有关详细信息，请参阅部署文档中的在<A href="lync-server-2013-configuring-archiving-options.md">Lync Server 2013 中配置存档选项</A>。</span><span class="sxs-lookup"><span data-stu-id="69553-108">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-configure-archiving-options-at-the-pool-level"></a><span data-ttu-id="69553-109">在池级别配置存档选项</span><span class="sxs-lookup"><span data-stu-id="69553-109">To configure archiving options at the pool level</span></span>

1.  <span data-ttu-id="69553-110">使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="69553-110">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="69553-111">打开浏览器窗口，然后输入管理员 URL 以打开 Lync Server 2013 控制面板。</span><span class="sxs-lookup"><span data-stu-id="69553-111">Open a browser window, and then enter the Admin URL to open the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="69553-112">有关可用于启动 Lync Server 2013 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="69553-112">For details about the different methods that you can use to start Lync Server 2013 Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="69553-113">在左侧导航栏中，单击 **“监控和存档”**，然后单击 **“存档配置”**。</span><span class="sxs-lookup"><span data-stu-id="69553-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="69553-114">在“存档配置”\*\*\*\* 页上，单击“新建”\*\*\*\*，然后单击“池配置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="69553-114">On the **Archiving Configuration** page, click **New**, and then click **Pool Configuration**.</span></span>

5.  <span data-ttu-id="69553-115">在“选择服务”\*\*\*\* 中，选择要为存档配置的池。</span><span class="sxs-lookup"><span data-stu-id="69553-115">In **Select a Service**, select the pool to be configured for archiving.</span></span>

6.  <span data-ttu-id="69553-116">在“新建存档设置”\*\*\*\* 的“存档设置”\*\*\*\* 下拉列表中，选择下列存档选项之一：</span><span class="sxs-lookup"><span data-stu-id="69553-116">In **New Archiving Setting**, in the **Archiving setting** drop-down list, select one of the following archiving options:</span></span>
    
      - <span data-ttu-id="69553-117">**禁用存档**</span><span class="sxs-lookup"><span data-stu-id="69553-117">**Disable archiving**</span></span>
    
      - <span data-ttu-id="69553-118">**存档 IM 会话**</span><span class="sxs-lookup"><span data-stu-id="69553-118">**Archive IM sessions**</span></span>
    
      - <span data-ttu-id="69553-119">**存档 IM 和 Web 会议会话**</span><span class="sxs-lookup"><span data-stu-id="69553-119">**Archive IM and web conferencing sessions**</span></span>

7.  <span data-ttu-id="69553-120">另请在“新建存档设置”\*\*\*\* 页中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="69553-120">Also in **New Archiving Setting** page, do the following:</span></span>
    
      - <span data-ttu-id="69553-121">要在存档不可用时阻止活动，请选中“存档失败时阻止即时消息(IM)或 Web 会议会话”\*\*\*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="69553-121">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
      - <span data-ttu-id="69553-122">若要使用 Microsoft Exchange Server 存储存档数据，请单击 " **Microsoft exchange 集成**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="69553-122">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
      - <span data-ttu-id="69553-123">若要启用数据清除，请选中“启用存档数据清除”\*\*\*\* 复选框，然后执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="69553-123">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
        
          - <span data-ttu-id="69553-124">要指定在特定的天数之后清除，请单击“在最长期限(天)后清除导出的存档数据和存储的存档数据”\*\*\*\*，然后指定天数。</span><span class="sxs-lookup"><span data-stu-id="69553-124">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
        
          - <span data-ttu-id="69553-125">要限制仅清除已导出的存档数据，请单击“仅清除导出的存档数据”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="69553-125">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>

8.  <span data-ttu-id="69553-126">单击“提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="69553-126">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

