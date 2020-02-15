---
title: 在共存方案中使用 Lync Server 2010 管理包
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Lync Server 2010 management packs in a coexistence scenario
ms:assetid: 8b792503-bd88-47fe-9d97-b071e8d429a5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205078(v=OCS.15)
ms:contentKeyID: 48184772
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8014f947a669b7b636061f17e40dee0fef287345
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007491"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-lync-server-2010-management-packs-in-a-coexistence-scenario"></a><span data-ttu-id="c0e5d-102">在共存方案中使用 Lync Server 2010 管理包</span><span class="sxs-lookup"><span data-stu-id="c0e5d-102">Using the Lync Server 2010 management packs in a coexistence scenario</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c0e5d-103">_**上次修改的主题：** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="c0e5d-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="c0e5d-104">许多客户在其企业内采用了推出计划，在该计划中，用户从 Microsoft Lync Server 2010 逐渐迁移到 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="c0e5d-104">Many customers adopt a rollout program inside of their enterprises in which users are progressively migrated from Microsoft Lync Server 2010 to Lync Server 2013.</span></span> <span data-ttu-id="c0e5d-105">这些公司的管理员将负责监视两个版本的 Lync Server，以帮助确保所有最终用户都能获得最佳的通信体验。</span><span class="sxs-lookup"><span data-stu-id="c0e5d-105">The administrators at these companies will care about monitoring both versions of Lync Server to help ensure that all of their end users are getting the best possible communication experience.</span></span> <span data-ttu-id="c0e5d-106">在这种情况下，Lync Server 2013 管理包支持与 Lync Server 2010 管理包的并行迁移路径。</span><span class="sxs-lookup"><span data-stu-id="c0e5d-106">For this scenario, the Lync Server 2013 Management Pack supports a side-by-side migration path with the Lync Server 2010 Management Pack.</span></span>

<span data-ttu-id="c0e5d-107">在 Lync Server 2010 中，通过与中央管理存储一起存储的拓扑文档发现了 Lync Server 计算机。</span><span class="sxs-lookup"><span data-stu-id="c0e5d-107">In the Lync Server 2010, Lync Server computers were discovered through the topology document stored with the Central Management store.</span></span> <span data-ttu-id="c0e5d-108">在此配置中，一台计算机将报告所有其他 Lync Server 计算机是否存在。</span><span class="sxs-lookup"><span data-stu-id="c0e5d-108">In this configuration, a single computer would report the existence of all the other Lync Server computers.</span></span>

<span data-ttu-id="c0e5d-109">Lync Server 2013 的管理包现在使用计算机级发现，而不是在 Lync Server 2010 中使用的中央发现机制。</span><span class="sxs-lookup"><span data-stu-id="c0e5d-109">The management packs for Lync Server 2013 now use machine-level discovery instead of the central discovery mechanism that was used in Lync Server 2010.</span></span> <span data-ttu-id="c0e5d-110">这意味着每个 System Center 代理实质上都会发现自己，并报告它是否存在于 System Center Operations Manager 中。</span><span class="sxs-lookup"><span data-stu-id="c0e5d-110">This means that each System Center agent essentially discovers itself and reports its existence to System Center Operations Manager.</span></span> <span data-ttu-id="c0e5d-111">使用计算机级别发现可简化对 System Center 基础结构的管理，还会启用不同版本的 Lync Server 管理包（例如，lync server 2010 的管理包和 Lync Server 2013 的管理包）能够更轻松地共存。</span><span class="sxs-lookup"><span data-stu-id="c0e5d-111">Using machine-level discovery simplifies administration of your System Center infrastructure and also enables different versions of the Lync Server management packs (for example, management packs for Lync Server 2010 and management packs for Lync Server 2013) to coexist more easily.</span></span>

<span data-ttu-id="c0e5d-112">若要支持此迁移，首先需要升级现有的 Lync Server 2010 监控，以避免覆盖范围的差距。</span><span class="sxs-lookup"><span data-stu-id="c0e5d-112">To support this migration, you will first need to upgrade your existing Lync Server 2010 monitoring to avoid gaps in coverage.</span></span> <span data-ttu-id="c0e5d-113">为此，请在将中央管理存储升级到 Lync Server 2013 之前，选择现有的 Lync Server 2010 计算机为 Lync Server 2010 服务的中央发现脚本。</span><span class="sxs-lookup"><span data-stu-id="c0e5d-113">To do this, elect an existing Lync Server 2010 computer to service the Central Discovery script for the Lync Server 2010 before upgrading your Central Management store to Lync Server 2013.</span></span> <span data-ttu-id="c0e5d-114">这是四个步骤的过程：</span><span class="sxs-lookup"><span data-stu-id="c0e5d-114">This is a four-step process:</span></span>

1.  <span data-ttu-id="c0e5d-115">将 Lync Server 2010 管理包升级到累积更新7。</span><span class="sxs-lookup"><span data-stu-id="c0e5d-115">Upgrade the Lync Server 2010 Management Packs to Cumulative Update 7.</span></span>

2.  <span data-ttu-id="c0e5d-116">指示 Lync Server 2010 计算机运行中央发现脚本。</span><span class="sxs-lookup"><span data-stu-id="c0e5d-116">Instruct a Lync Server 2010 computer to run the Central Discovery script.</span></span>

3.  <span data-ttu-id="c0e5d-117">替代 Microsoft Lync Server 2010 管理包中的中央发现候选项。</span><span class="sxs-lookup"><span data-stu-id="c0e5d-117">Override the Central Discovery Candidate in the Microsoft Lync Server 2010 Management Pack.</span></span>

4.  <span data-ttu-id="c0e5d-118">验证是否已发现新的中央发现候选项。</span><span class="sxs-lookup"><span data-stu-id="c0e5d-118">Verify that the new Central Discovery Candidate has been discovered.</span></span>

<div>

## <a name="instructing-a-lync-server-2010-computer-to-run-the-central-discovery-script"></a><span data-ttu-id="c0e5d-119">指示 Lync Server 2010 计算机运行中央发现脚本</span><span class="sxs-lookup"><span data-stu-id="c0e5d-119">Instructing a Lync Server 2010 Computer to Run the Central Discovery script</span></span>

<span data-ttu-id="c0e5d-120">若要提名非中央管理存储计算机（例如，Lync Server 前端）服务器来处理中央发现，您需要在非中心管理存储服务器上创建以下注册表项：</span><span class="sxs-lookup"><span data-stu-id="c0e5d-120">To nominate a non-Central Management store computer (for example, a Lync Server Front End) server to handle central discovery, you will need to create the following registry key on the non-Central Management store server:</span></span>

<span data-ttu-id="c0e5d-121">HKLM\\软件\\Microsoft\\实时通信\\运行状况\\CentralDiscoveryCandidate</span><span class="sxs-lookup"><span data-stu-id="c0e5d-121">HKLM\\Software\\Microsoft\\Real-Time Communications\\Health\\CentralDiscoveryCandidate</span></span>

<span data-ttu-id="c0e5d-122">您可以通过完成以下过程来创建此注册表项：</span><span class="sxs-lookup"><span data-stu-id="c0e5d-122">You can create this registry key by completing the following procedure:</span></span>

1.  <span data-ttu-id="c0e5d-123">单击“开始”\*\*\*\*，再单击“运行”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c0e5d-123">Click **Start** and then click **Run**.</span></span>

2.  <span data-ttu-id="c0e5d-124">在“运行”\*\*\*\* 对话框中，键入“regedit”\*\*\*\*，然后按 Enter 键。</span><span class="sxs-lookup"><span data-stu-id="c0e5d-124">In the **Run** dialog box, type **regedit** and then press ENTER.</span></span>

3.  <span data-ttu-id="c0e5d-125">在注册表编辑器中，**展开\_"\_HKEY 本地计算机**"，展开 "**软件**"，再展开 " **Microsoft**"，然后展开 "**实时通信**"。</span><span class="sxs-lookup"><span data-stu-id="c0e5d-125">In Registry Editor, expand **HKEY\_LOCAL\_MACHINE**, expand **SOFTWARE**, expand **Microsoft**, and then expand **Real-Time Communications**.</span></span>

4.  <span data-ttu-id="c0e5d-126">右键单击 "**运行状况**"，单击 "**新建**"，然后单击 "**项**"。</span><span class="sxs-lookup"><span data-stu-id="c0e5d-126">Right-click **Health**, click **New**, and then click **Key**.</span></span> <span data-ttu-id="c0e5d-127">如果**运行状况**项不存在，则右键单击 "**实时通信**"，指向 "**新建**"，然后单击 "**项**"。</span><span class="sxs-lookup"><span data-stu-id="c0e5d-127">If the **Health** key does not exist, then right-click **Real-Time Communications**, point to **New**, and then click **Key**.</span></span> <span data-ttu-id="c0e5d-128">创建新密钥时，键入 Health，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="c0e5d-128">When the new key is created, type Health, and then press ENTER.</span></span>
    
    <span data-ttu-id="c0e5d-129">创建新密钥后，键入**CentralDiscoveryCandidate** ，然后按 enter 重命名该项。</span><span class="sxs-lookup"><span data-stu-id="c0e5d-129">After the new key has been created, type **CentralDiscoveryCandidate** and then press ENTER to rename the key.</span></span>

<span data-ttu-id="c0e5d-130">可能需要几个小时才能获取此更改。</span><span class="sxs-lookup"><span data-stu-id="c0e5d-130">It may take the computer several hours to pick up this change.</span></span> <span data-ttu-id="c0e5d-131">若要使更改立即生效，请停止运行状况代理服务，然后再重新启动它。</span><span class="sxs-lookup"><span data-stu-id="c0e5d-131">To make the change take effect immediately, stop and then restart the Health Agent service.</span></span> <span data-ttu-id="c0e5d-132">若要重新启动运行状况代理服务，请在 Lync Server 2010 计算机上完成以下过程：</span><span class="sxs-lookup"><span data-stu-id="c0e5d-132">To restart the Health Agent service, complete the following procedure on the Lync Server 2010 computer:</span></span>

1.  <span data-ttu-id="c0e5d-133">单击 "**开始**"，单击 "**所有程序**"，单击 "**附件**"，右键单击 "**命令提示符**"，然后单击 "以**管理员身份运行**"。</span><span class="sxs-lookup"><span data-stu-id="c0e5d-133">Click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="c0e5d-134">在控制台窗口中键入以下命令，然后按 Enter：</span><span class="sxs-lookup"><span data-stu-id="c0e5d-134">In the console window, type the following command and then press ENTER:</span></span>
    
        Net stop HealthService

3.  <span data-ttu-id="c0e5d-135">您将看到一条消息，指出 "System Center Management service 正在停止"，后跟第二条消息，告诉您服务已停止。</span><span class="sxs-lookup"><span data-stu-id="c0e5d-135">You will see a message that states "The System Center Management service is stopping," followed by a second message that tells you that the service has been stopped.</span></span> <span data-ttu-id="c0e5d-136">停止服务后，您可以通过键入以下命令并按 ENTER 来重新启动它：</span><span class="sxs-lookup"><span data-stu-id="c0e5d-136">After the service has stopped, you can restart it by typing the following command and pressing ENTER:</span></span>
    
        Net start HealthService

</div>

<div>

## <a name="overriding-the-central-discovery-candidate-in-the-lync-server-2010-management-pack"></a><span data-ttu-id="c0e5d-137">替代 Lync Server 2010 管理包中的中央发现候选项</span><span class="sxs-lookup"><span data-stu-id="c0e5d-137">Overriding the Central Discovery Candidate in the Lync Server 2010 Management Pack</span></span>

<span data-ttu-id="c0e5d-138">指示 Lync Server 2010 计算机在 Lync Server 2010 计算机上报告之后，您还需要通知 Lync Server 2010 管理包有关此更改。</span><span class="sxs-lookup"><span data-stu-id="c0e5d-138">After instructing a Lync Server 2010 computer to report on Lync Server 2010 computers, you will need to inform the Lync Server 2010 Management Pack about this change as well.</span></span> <span data-ttu-id="c0e5d-139">若要执行此操作，您将需要在管理包中创建替代。</span><span class="sxs-lookup"><span data-stu-id="c0e5d-139">To do this, you will need to create an override in the Management Pack.</span></span> <span data-ttu-id="c0e5d-140">这可通过执行下列过程来完成：</span><span class="sxs-lookup"><span data-stu-id="c0e5d-140">That can be done by completing the following procedure:</span></span>

1.  <span data-ttu-id="c0e5d-141">在 Operations Manager 控制台中，单击 "**创作**"。</span><span class="sxs-lookup"><span data-stu-id="c0e5d-141">In the Operations Manager console, click **Authoring**.</span></span>

2.  <span data-ttu-id="c0e5d-142">在 "创作" 选项卡上，展开 "**管理包对象**"，单击 "**对象发现**"，然后单击 "**范围**"。</span><span class="sxs-lookup"><span data-stu-id="c0e5d-142">On the Authoring tab, expand **Management Pack Objects**, click **Object Discoveries**, and then click **Scope**.</span></span>

3.  <span data-ttu-id="c0e5d-143">在 "**作用域管理包对象**" 对话框中，选择带有目标**LS "发现候选**项" 的项目，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="c0e5d-143">In the **Scope Management Pack Objects** dialog box, select the item with the Target **LS Discovery Candidate** and then click **OK**.</span></span> <span data-ttu-id="c0e5d-144">请注意，只有在安装了 Lync Server 2010 管理包的情况下，才会显示 "发现候选项"。</span><span class="sxs-lookup"><span data-stu-id="c0e5d-144">Note that LS Discovery Candidate will appear only if you have installed the Lync Server 2010 Management Pack.</span></span>

4.  <span data-ttu-id="c0e5d-145">在 Operations Manager 控制台中，右键单击 " **LS 发现候选人**"，指向 "**替代**"，指向 "**替代对象发现**"，然后单击 "**类的所有对象"： LS "发现候选**"。</span><span class="sxs-lookup"><span data-stu-id="c0e5d-145">In the Operations Manager console, right-click **LS Discovery Candidate**, point to **Overrides**, point to **Override the Object Discovery**, and then click **For all objects of class: LS Discovery Candidate**.</span></span>

5.  <span data-ttu-id="c0e5d-146">在 "**替代属性**" 对话框中，选中参数**中心发现 watchernode.msi Fqdn**旁边的 "**替代**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="c0e5d-146">In the **Override Properties** dialog box, select the **Override** check box next to the parameter **Central Discovery WatcherNode Fqdn**.</span></span> <span data-ttu-id="c0e5d-147">在 "**替代值**和**有效值**" 框中键入 Lync Server 2010 计算机的完全限定域名。</span><span class="sxs-lookup"><span data-stu-id="c0e5d-147">Type the fully qualified domain name of the Lync Server 2010 computer in the **Override Value** and **Effective Value** boxes.</span></span> <span data-ttu-id="c0e5d-148">选中 "**强制**" 复选框，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="c0e5d-148">Select the **Enforced** check box and click **OK**.</span></span>

<span data-ttu-id="c0e5d-149">创建替代后，需要在根管理服务器上重新启动运行状况服务。</span><span class="sxs-lookup"><span data-stu-id="c0e5d-149">After you have created the override, you need to restart the health service on the Root Management Server.</span></span> <span data-ttu-id="c0e5d-150">若要重新启动运行状况服务，请在根管理服务器上完成以下过程：</span><span class="sxs-lookup"><span data-stu-id="c0e5d-150">To restart the health service, complete the following procedure on the Root Management Server:</span></span>

1.  <span data-ttu-id="c0e5d-151">单击 "**开始**"，单击 "**所有程序**"，单击 "**附件**"，右键单击 "**命令提示符**"，然后单击 "以**管理员身份运行**"。</span><span class="sxs-lookup"><span data-stu-id="c0e5d-151">Click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="c0e5d-152">在控制台窗口中，键入以下命令，然后按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="c0e5d-152">In the console window, type the following command, and then press ENTER:</span></span>
    
        Net stop HealthService

3.  <span data-ttu-id="c0e5d-153">你将看到一条消息，表明 "System Center Management service 正在停止"，然后再出现第二条消息，告诉你服务已停止。</span><span class="sxs-lookup"><span data-stu-id="c0e5d-153">You will see a message stating that "The System Center Management service is stopping," followed by a second message that tells you that the service has been stopped.</span></span> <span data-ttu-id="c0e5d-154">停止服务后，您可以通过键入以下命令并按 ENTER 来重新启动它：</span><span class="sxs-lookup"><span data-stu-id="c0e5d-154">After the service has stopped, you can then restart it by typing the following command and pressing ENTER:</span></span>
    
        Net start HealthService

</div>

<div>

## <a name="verifying-that-the-new-central-discovery-candidate-was-discovered"></a><span data-ttu-id="c0e5d-155">验证是否已发现新的中央发现候选项</span><span class="sxs-lookup"><span data-stu-id="c0e5d-155">Verifying that the New Central Discovery Candidate Was Discovered</span></span>

<span data-ttu-id="c0e5d-156">升级中央管理存储之前的最后一步是确保 Lync Server 2010 管理包发现了新的中央发现候选项。</span><span class="sxs-lookup"><span data-stu-id="c0e5d-156">The final step before upgrading Central Management store is to make sure that the new central discovery candidate was discovered by the Lync Server 2010 Management Pack.</span></span> <span data-ttu-id="c0e5d-157">为此，请打开 Operations Manager 控制台，然后单击 "监视"。</span><span class="sxs-lookup"><span data-stu-id="c0e5d-157">To do this, open the Operations Manager console and then click Monitoring.</span></span> <span data-ttu-id="c0e5d-158">在 "监视" 选项卡上，展开 " **Microsoft Lync Server 2010 运行状况**"，展开 "**拓扑发现**"，然后单击 "**发现状态视图**"。</span><span class="sxs-lookup"><span data-stu-id="c0e5d-158">On the Monitoring tab, expand **Microsoft Lync Server 2010 Health**, expand **Topology Discovery**, and then click **Discovery State View**.</span></span> <span data-ttu-id="c0e5d-159">验证显示的行是否有列出了中央发现候选项的完全限定域名的**路径**。</span><span class="sxs-lookup"><span data-stu-id="c0e5d-159">Verify that a row in the display has a **Path** that lists the fully qualified domain name of the central discovery candidate.</span></span> <span data-ttu-id="c0e5d-160">您还应验证计算机状态是否报告为**正常**。</span><span class="sxs-lookup"><span data-stu-id="c0e5d-160">You should also verify that the computer state is reported as **Healthy**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

