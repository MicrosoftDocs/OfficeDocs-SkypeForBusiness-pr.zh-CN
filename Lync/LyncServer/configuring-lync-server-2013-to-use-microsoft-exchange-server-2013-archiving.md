---
title: 将 Lync Server 2013 配置为使用 Microsoft Exchange Server 2013 存档
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server 2013 to use Exchange Server 2013 archiving
ms:assetid: 260346d1-edc8-4a0c-8ad2-6c2401c3c377
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ679896(v=OCS.15)
ms:contentKeyID: 49557731
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b163b0ce3324455f8a80eca7be5c1423b302a3d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723182"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving"></a><span data-ttu-id="13367-102">将 Microsoft Lync Server 2013 配置为使用 Microsoft Exchange Server 2013 存档</span><span class="sxs-lookup"><span data-stu-id="13367-102">Configuring Microsoft Lync Server 2013 to use Microsoft Exchange Server 2013 archiving</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="13367-103">_**主题上次修改时间：** 2014-06-24_</span><span class="sxs-lookup"><span data-stu-id="13367-103">_**Topic Last Modified:** 2014-06-24_</span></span>

<span data-ttu-id="13367-104">Microsoft Lync Server 2013 让管理员可以选择将即时消息和 Web 会议脚本存档到用户的 Microsoft Exchange Server 2013 邮箱，而不是 SQL Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="13367-104">Microsoft Lync Server 2013 gives administrators the option of having instant messaging and Web conferencing transcripts archived to a user's Microsoft Exchange Server 2013 mailbox rather than a SQL Server database.</span></span> <span data-ttu-id="13367-105">如果启用此选项，则会将脚本写入用户邮箱中的“清除”文件夹。</span><span class="sxs-lookup"><span data-stu-id="13367-105">If you enable this option, transcripts are written to the Purges folder in the user's mailbox.</span></span> <span data-ttu-id="13367-106">“清除”文件夹是“可恢复邮件”文件夹下的一个隐藏文件夹。</span><span class="sxs-lookup"><span data-stu-id="13367-106">The Purges folder is a hidden folder found in the Recoverable Items folder.</span></span> <span data-ttu-id="13367-107">虽然此文件夹对最终用户不可见，但文件夹由 Exchange 搜索引擎进行索引，并且可以使用 Exchange 邮箱搜索和/或 Microsoft SharePoint Server 2013 进行发现。</span><span class="sxs-lookup"><span data-stu-id="13367-107">Although this folder is not visible to end-users, the folder is indexed by the Exchange search engine and can be discovered by using Exchange mailbox search and/or Microsoft SharePoint Server 2013.</span></span> <span data-ttu-id="13367-108">由于信息存储在 Exchange 就地保留功能所使用的同一个文件夹中（负责存档电子邮件和其他 Exchange 通信），因此管理员可以使用单个工具搜索已存档的所有电子通信user.</span><span class="sxs-lookup"><span data-stu-id="13367-108">Because information is stored in the same folder used by the Exchange In-Place Hold feature (responsible for archiving email and other Exchange communications), administrators can use a single tool to search for all the electronic communications archived for a user.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="13367-109">若要完全禁用 Lync 对话的存档，还必须禁用 Lync 对话历史记录。</span><span class="sxs-lookup"><span data-stu-id="13367-109">To completely disable archiving of Lync conversation, you must also disable Lync conversation history.</span></span> <span data-ttu-id="13367-110">有关详细信息，请参阅以下主题：<A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">在 Lync Server 2013、set-csclientpolicy 和 set-csclientpolicy 中管理内部和外部通信的存档</A>。 <A href="https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy"></A> <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy"></A></span><span class="sxs-lookup"><span data-stu-id="13367-110">For more information, see the following topics: <A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">Managing the Archiving of internal and external communications in Lync Server 2013</A>, <A href="https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy">New-CsClientPolicy</A>, and <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">Set-CsClientPolicy</A>.</span></span>



</div>

<span data-ttu-id="13367-111">为了将脚本存档到 Exchange 2013，必须首先在两台服务器之间配置服务器到服务器的身份验证。</span><span class="sxs-lookup"><span data-stu-id="13367-111">In order to archive transcripts to Exchange 2013 you must begin by configuring server-to-server authentication between the two servers.</span></span> <span data-ttu-id="13367-112">在实施服务器到服务器身份验证之后，你可以在 Microsoft Lync Server 2013 中执行以下任务（请注意，根据你的设置和配置，你可能不需要完成所有这些任务）：</span><span class="sxs-lookup"><span data-stu-id="13367-112">After server-to-server authentication is in place you can then carry out the following tasks in Microsoft Lync Server 2013 (note that, depending on your setup and configuration, you might not need to complete all of these tasks):</span></span>

1.  <span data-ttu-id="13367-113">通过修改 Lync 服务器存档配置设置启用 Exchange 存档。</span><span class="sxs-lookup"><span data-stu-id="13367-113">Enable Exchange archiving by modifying your Lync Server archiving configuration settings.</span></span> <span data-ttu-id="13367-114">此步骤是所有部署必需的。</span><span class="sxs-lookup"><span data-stu-id="13367-114">This step is required for all deployments.</span></span>

2.  <span data-ttu-id="13367-115">为用户的内部和/或外部通信启用存档。</span><span class="sxs-lookup"><span data-stu-id="13367-115">Enable archiving for internal and/or external communications for your users.</span></span> <span data-ttu-id="13367-116">此步骤是所有部署必需的。</span><span class="sxs-lookup"><span data-stu-id="13367-116">This step is required for all deployments.</span></span>

3.  <span data-ttu-id="13367-117">为每个用户配置 ExchangeArchivingPolicy 属性。</span><span class="sxs-lookup"><span data-stu-id="13367-117">Configure the ExchangeArchivingPolicy property for each user.</span></span> <span data-ttu-id="13367-118">此步骤仅在 Lync Server 中需要，Exchange 位于不同的林中。</span><span class="sxs-lookup"><span data-stu-id="13367-118">This step is only required in Lync Server and Exchange are located in different forests.</span></span>

<div>

## <a name="step-1-enabling-exchange-archiving"></a><span data-ttu-id="13367-119">步骤1：启用 Exchange 存档</span><span class="sxs-lookup"><span data-stu-id="13367-119">Step 1: Enabling Exchange Archiving</span></span>

<span data-ttu-id="13367-120">Lync Server 中的存档主要通过使用存档配置设置进行管理。</span><span class="sxs-lookup"><span data-stu-id="13367-120">Archiving in Lync Server is primarily managed by using the archiving configuration settings.</span></span> <span data-ttu-id="13367-121">安装 Lync Server 2013 时，系统会自动为您提供这些设置的单个全局集合。</span><span class="sxs-lookup"><span data-stu-id="13367-121">When you install Lync Server 2013 you are automatically given a single, global collection of these settings.</span></span> <span data-ttu-id="13367-122">（管理员可以选择在网站范围内创建新的存档设置集合。）默认情况下，不会在全局设置中启用存档，也不会在这些设置中启用 Exchange 存档。</span><span class="sxs-lookup"><span data-stu-id="13367-122">(Administrators can optionally create new collections of archiving settings at the site scope.) By default, archiving is not enabled in the global settings, nor is Exchange archiving enabled in these settings.</span></span> <span data-ttu-id="13367-123">为了使用 Exchange 存档管理员，必须在这些配置设置中同时配置 EnableArchiving 和 EnableExchangeArchiving 属性。</span><span class="sxs-lookup"><span data-stu-id="13367-123">In order to use Exchange archiving administrators must configure both the EnableArchiving and the EnableExchangeArchiving properties in these configuration settings.</span></span> <span data-ttu-id="13367-124">EnableArchiving 属性可以设置为以下三个可能的值之一：</span><span class="sxs-lookup"><span data-stu-id="13367-124">The EnableArchiving property can be set to one of three possible values:</span></span>

  - <span data-ttu-id="13367-125">**无**。</span><span class="sxs-lookup"><span data-stu-id="13367-125">**None**.</span></span> <span data-ttu-id="13367-126">禁用存档。</span><span class="sxs-lookup"><span data-stu-id="13367-126">Archiving is disabled.</span></span> <span data-ttu-id="13367-127">这是默认值。</span><span class="sxs-lookup"><span data-stu-id="13367-127">This is the default value.</span></span> <span data-ttu-id="13367-128">如果 EnableArchiving 设置为 "无"，则不会在 Lync Server 存档数据库或 Exchange 2013 中存档任何内容。</span><span class="sxs-lookup"><span data-stu-id="13367-128">If EnableArchiving is set to None then nothing will be archived in either your Lync Server archiving database or in Exchange 2013.</span></span>

  - <span data-ttu-id="13367-129">**ImOnly**。</span><span class="sxs-lookup"><span data-stu-id="13367-129">**ImOnly**.</span></span> <span data-ttu-id="13367-130">仅存档即时消息脚本。</span><span class="sxs-lookup"><span data-stu-id="13367-130">Only instant message transcripts are archived.</span></span> <span data-ttu-id="13367-131">如果启用 Exchange 存档，这些脚本将在 Exchange 2013 中存档。</span><span class="sxs-lookup"><span data-stu-id="13367-131">If Exchange archiving is enabled these transcripts will be archived in Exchange 2013.</span></span> <span data-ttu-id="13367-132">如果禁用 Exchange 存档，则会将这些脚本存档到 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="13367-132">If Exchange archiving is disabled then these transcripts will be archived to Lync Server.</span></span>

  - <span data-ttu-id="13367-133">**ImAndWebConf**。</span><span class="sxs-lookup"><span data-stu-id="13367-133">**ImAndWebConf**.</span></span> <span data-ttu-id="13367-134">将存档即时消息脚本和 Web 会议脚本。</span><span class="sxs-lookup"><span data-stu-id="13367-134">Both instant message transcripts and Web conferencing transcripts are archived.</span></span> <span data-ttu-id="13367-135">如果启用 Exchange 存档，这些脚本将在 Exchange 2013 中存档。</span><span class="sxs-lookup"><span data-stu-id="13367-135">If Exchange archiving is enabled these transcripts will be archived in Exchange 2013.</span></span> <span data-ttu-id="13367-136">如果禁用 Exchange 存档，则会将这些脚本存档到 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="13367-136">If Exchange archiving is disabled then these transcripts will be archived to Lync Server.</span></span>

<span data-ttu-id="13367-137">EnableExchangeArchiving 属性是一个布尔值：将 EnableExchangeArchiving 设置为 True （$True）以启用 Exchange 存档，或将 EnableExchangeArchiving 设置为 False （$False）以禁用 Exchange 存档。</span><span class="sxs-lookup"><span data-stu-id="13367-137">The EnableExchangeArchiving property is a Boolean value: set EnableExchangeArchiving to True ($True) to enable Exchange archiving or set EnableExchangeArchiving to False ($False) to disable Exchange archiving.</span></span> <span data-ttu-id="13367-138">例如，此命令启用即时消息脚本的存档，同时启用 Exchange 存档：</span><span class="sxs-lookup"><span data-stu-id="13367-138">For example, this command enables the archiving of instant messaging transcripts and also enables Exchange archiving:</span></span>

    Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $True

<span data-ttu-id="13367-139">若要禁用 Exchange 存档，请使用类似于以下内容的命令，这将启用即时消息存档，但禁用对 Exchange 的存档（换句话说，脚本将存档到 Lync 服务器）：</span><span class="sxs-lookup"><span data-stu-id="13367-139">To disable Exchange archiving, use a command similar to the following, which enables instant messaging archiving but disables archiving to Exchange (in other words, transcripts will be archived to Lync Server):</span></span>

    Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $False

<div>


> [!NOTE]  
> <span data-ttu-id="13367-140">如果 EnableArchiving 属性设置为 "无"，则 Lync Server 将根本不存档即时消息和 Web 会议脚本。</span><span class="sxs-lookup"><span data-stu-id="13367-140">If the EnableArchiving property is set to None then Lync Server will not archive instant messaging and Web conferencing transcripts at all.</span></span> <span data-ttu-id="13367-141">在本例中，服务器只会忽略为 EnableExchangeArchiving 配置的值。</span><span class="sxs-lookup"><span data-stu-id="13367-141">In that case, the server will simply ignore the value configured for EnableExchangeArchiving.</span></span>



</div>

<span data-ttu-id="13367-142">也可以使用 Lync Server 控制面板启用（或禁用） Exchange 存档。</span><span class="sxs-lookup"><span data-stu-id="13367-142">Exchange archiving can also be enabled (or disabled) by using the Lync Server Control Panel.</span></span> <span data-ttu-id="13367-143">为此，请完成以下过程：</span><span class="sxs-lookup"><span data-stu-id="13367-143">To do that, complete the following procedure:</span></span>

1.  <span data-ttu-id="13367-144">在控制面板中，单击“**监控和存档**”，然后单击“**存档配置**”。</span><span class="sxs-lookup"><span data-stu-id="13367-144">In Control Panel, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

2.  <span data-ttu-id="13367-145">在“**存档配置**”选项卡上，双击要修改的存档设置集合（例如“**全局**”集合）。</span><span class="sxs-lookup"><span data-stu-id="13367-145">On the **Archiving Configuration** tab, double-click the collection of archiving settings to be modified (for example, the **Global** collection).</span></span>

3.  <span data-ttu-id="13367-146">在“**编辑存档设置**”窗格中，单击“**存档设置**”下拉列表并选择“**存档 IM 会话**”（仅存档即时消息会话）或“**存档 IM 和 Web 会议会话**”（存档即时消息和 Web 会议会话）。</span><span class="sxs-lookup"><span data-stu-id="13367-146">In the **Edit Archiving Setting** pane, click the **Archiving setting** dropdown list and select either **Archive IM sessions** (to archive just instant messaging sessions) or **Archive IM and web conferencing sessions** (to archive both instant messaging and Web conferencing sessions).</span></span>

4.  <span data-ttu-id="13367-147">选择要存档的项目后，选中 " **Exchange 服务器集成**" 复选框以启用 exchange 存档。</span><span class="sxs-lookup"><span data-stu-id="13367-147">After choosing the items to be archived, select the **Exchange Server integration** checkbox to enable Exchange archiving.</span></span> <span data-ttu-id="13367-148">若要禁用 Exchange 存档，请清除此复选框。</span><span class="sxs-lookup"><span data-stu-id="13367-148">To disable Exchange archiving, clear this checkbox.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="13367-149">如果“<STRONG>存档设置</STRONG>”设置为“<STRONG>禁用存档</STRONG>”，则“<STRONG>Exchange Server 集成</STRONG>”复选框不可用。</span><span class="sxs-lookup"><span data-stu-id="13367-149">The <STRONG>Exchange Server integration</STRONG> checkbox will not be available if the <STRONG>Archiving setting</STRONG> is set to <STRONG>Disable archiving</STRONG>.</span></span> <span data-ttu-id="13367-150">必须先启用存档，然后启用 Exchange 存档。</span><span class="sxs-lookup"><span data-stu-id="13367-150">You must enable archiving first and then enable Exchange archiving.</span></span>



</div>

<span data-ttu-id="13367-151">如果 Lync Server 2013 和 Exchange 2013 位于同一林中，则为单个用户存档（或至少对于在 Exchange 2013 上具有电子邮件帐户的用户）通过使用 "Exchange 就地保留策略" 进行管理。</span><span class="sxs-lookup"><span data-stu-id="13367-151">If Lync Server 2013 and Exchange 2013 are located in the same forest then archiving for individual users (or at least for users who have email accounts on Exchange 2013) is managed by using Exchange In-Place Hold policies.</span></span> <span data-ttu-id="13367-152">如果你的用户是托管以前版本的 Exchange 的用户，则将使用 Lync Server 存档策略管理这些用户的存档。</span><span class="sxs-lookup"><span data-stu-id="13367-152">If you have users who are homed on a previous version of Exchange then archiving for those users will be managed by using Lync Server archiving policies.</span></span> <span data-ttu-id="13367-153">请注意，只有 Exchange 2013 帐户的用户才能将其 Lync 脚本存档到 Exchange。</span><span class="sxs-lookup"><span data-stu-id="13367-153">Note that only users with accounts on Exchange 2013 can have their Lync transcripts archived to Exchange.</span></span>

<span data-ttu-id="13367-154">如果 Lync Server 2013 和 Exchange 2013 位于不同的林中，则通过为每个单独的用户帐户配置 ExchangeArchivingPolicy 属性来管理对单个用户的存档。</span><span class="sxs-lookup"><span data-stu-id="13367-154">If Lync Server 2013 and Exchange 2013 are located in different forests then archiving for individual users is managed by configuring the ExchangeArchivingPolicy property for each individual user account.</span></span> <span data-ttu-id="13367-155">请参阅步骤 3 以了解更多信息。</span><span class="sxs-lookup"><span data-stu-id="13367-155">See Step 3 for more information.</span></span>

</div>

<div>

## <a name="step-2-enabling-the-archiving-of-internal-andor-external-communications"></a><span data-ttu-id="13367-156">步骤 2：启用内部和/或外部通信的存档</span><span class="sxs-lookup"><span data-stu-id="13367-156">Step 2: Enabling the Archiving of Internal and/or External Communications</span></span>

<span data-ttu-id="13367-157">启用存档（和 Exchange 存档）后，必须修改相应的存档策略，以确保实际存档用户会话。</span><span class="sxs-lookup"><span data-stu-id="13367-157">After you have enabled archiving (and Exchange archiving) you must then modify the appropriate archiving policies to ensure that user sessions are actually archived.</span></span> <span data-ttu-id="13367-158">请注意，仅启用存档（步骤1）不会导致 Lync Server 开始存档即时消息和网络会议脚本。</span><span class="sxs-lookup"><span data-stu-id="13367-158">Note that simply enabling archiving (Step 1) does not cause Lync Server to begin archiving instant messaging and Web conferencing transcripts.</span></span> <span data-ttu-id="13367-159">相反，您必须使用存档策略启用内部和/或外部存档。</span><span class="sxs-lookup"><span data-stu-id="13367-159">Instead, you must use archiving policies to enable internal and/or external archiving.</span></span> <span data-ttu-id="13367-160">安装 Lync Server 2013 时，还会安装单个全局存档策略，其中包含两个属性：</span><span class="sxs-lookup"><span data-stu-id="13367-160">When you install Lync Server 2013 you also install a single, global archiving policy that contains two properties:</span></span>

  - <span data-ttu-id="13367-p119">**ArchiveInternal**。当设置为 True ($True) 时，指示将存档仅涉及在贵组织中有 Active Directory 帐户的用户的内部通信会话。</span><span class="sxs-lookup"><span data-stu-id="13367-p119">**ArchiveInternal**. When set to True ($True) indicates that internal communication sessions involving only users who have Active Directory accounts in your organization) will be archived.</span></span>

  - <span data-ttu-id="13367-p120">**ArchiveExternal**。当设置为 True ($True) 时，指示将存档内部通信会话（涉及至少一个在贵组织中没有 Active Directory 帐户的用户的会话）。</span><span class="sxs-lookup"><span data-stu-id="13367-p120">**ArchiveExternal**. When set to True ($True) indicates that internal communication sessions (sessions involving at least one user who does not have an Active Directory account in your organization) will be archived.</span></span>

<span data-ttu-id="13367-165">默认情况下，这两个属性的值都设置为 False，意味着既不存档内部通信会话也不存档外部通信会话。</span><span class="sxs-lookup"><span data-stu-id="13367-165">By default, both of these property values are set to False, meaning that neither internal nor external communication sessions are archived.</span></span> <span data-ttu-id="13367-166">若要修改全局策略，可以使用 Lync Server 命令行管理程序和 CsArchivingPolicy cmdlet。</span><span class="sxs-lookup"><span data-stu-id="13367-166">To modify the global policy, you can use the Lync Server Management Shell and the Set-CsArchivingPolicy cmdlet.</span></span> <span data-ttu-id="13367-167">此命令可对内部和外部通信会话进行存档：</span><span class="sxs-lookup"><span data-stu-id="13367-167">This command enables the archiving of both internal and external communication sessions:</span></span>

    Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True

<span data-ttu-id="13367-p122">您也可以使用 New-CsArchivingPolicy 在站点范围或每用户范围创建一个新策略。例如，此命令可新建一个名为 RedmondArchivingPolicy 的每用户存档策略：</span><span class="sxs-lookup"><span data-stu-id="13367-p122">Alternatively, you can use the New-CsArchivingPolicy to create a new policy at either the site scope or the per-user scope. For example, this command creates a new per-user archiving policy named RedmondArchivingPolicy:</span></span>

    New-CsArchivingPolicy -Identity "RedmondArchivingPolicy" -ArchiveInternal $True -ArchiveExternal $True

<span data-ttu-id="13367-p123">如果您创建每用户策略，您将需要将该策略分配给相应的用户。例如：</span><span class="sxs-lookup"><span data-stu-id="13367-p123">If you create a per-user policy you will then need to assign that policy to the appropriate users. For example:</span></span>

    Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName  "RedmondArchivingPolicy"

<span data-ttu-id="13367-172">还可以使用 Lync Server 控制面板管理存档策略。</span><span class="sxs-lookup"><span data-stu-id="13367-172">Archiving policies can also be managed by using the Lync Server Control Panel.</span></span> <span data-ttu-id="13367-173">在控制面板中，单击“**监控和存档**”，然后单击“**存档策略**”。</span><span class="sxs-lookup"><span data-stu-id="13367-173">Within the Control Panel, click **Monitoring and Archiving** and then click **Archiving Policy**.</span></span> <span data-ttu-id="13367-174">若要修改现有策略，请双击该策略（例如“全局”），然后在“**编辑存档策略**”窗格中，根据需要选中或清除“**存档内部通信**”和“**存档外部通信**”复选框。</span><span class="sxs-lookup"><span data-stu-id="13367-174">To modify an existing policy, double-click the policy (e.g., Global) and then, in the **Edit Archiving Policy** pane, select or clear the **Archive internal communications** and the **Archive external communications** checkboxes as needed.</span></span> <span data-ttu-id="13367-175">若要创建新的存档策略，请单击 "**新建**"，然后选择 "**网站策略**" 或 "**用户策略**"。</span><span class="sxs-lookup"><span data-stu-id="13367-175">To create a new archiving policy, click **New** and then select either **Site policy** or **User policy**.</span></span> <span data-ttu-id="13367-176">如果您新建用户策略，则必须访问相应的用户帐户（从“**用户**”选项卡中）并为这些用户分配新策略。</span><span class="sxs-lookup"><span data-stu-id="13367-176">If you create a new user policy then you must access the appropriate user accounts (from the **Users** tab) and assign those users the new policy.</span></span>

</div>

<div>

## <a name="step-3-configuring-the-exchangearchivingpolicy-property"></a><span data-ttu-id="13367-177">步骤 3：配置 ExchangeArchivingPolicy 属性</span><span class="sxs-lookup"><span data-stu-id="13367-177">Step 3: Configuring the ExchangeArchivingPolicy Property</span></span>

<span data-ttu-id="13367-178">如果 Lync Server 2013 和 Exchange 2013 位于不同的林中，则只需在存档配置设置中启用 Exchange 存档就够了。这不会导致即时消息和网络会议脚本在 Exchange 中存档。</span><span class="sxs-lookup"><span data-stu-id="13367-178">If Lync Server 2013 and Exchange 2013 are located in different forests then it is not enough to simply enable Exchange archiving in the archiving configuration settings; that will not result in instant messaging and Web conferencing transcripts being archived in Exchange.</span></span> <span data-ttu-id="13367-179">因此，你还必须在每个相关 Lync 服务器用户帐户上配置 ExchangeArchivingPolicy 属性。</span><span class="sxs-lookup"><span data-stu-id="13367-179">Instead, you must also configure the ExchangeArchivingPolicy property on each of the relevant Lync Server user accounts.</span></span> <span data-ttu-id="13367-180">此属性可设置为以下四个可能的值之一：</span><span class="sxs-lookup"><span data-stu-id="13367-180">This property can be set to one of four possible values:</span></span>

1.  <span data-ttu-id="13367-181">未初始化。</span><span class="sxs-lookup"><span data-stu-id="13367-181">Uninitialized.</span></span> <span data-ttu-id="13367-182">指示存档将基于为用户的 Exchange 邮箱配置的就地保留设置;如果用户的邮箱尚未启用就地保留，则用户将在 Lync Server 中存档他或她的邮件和网络会议脚本。</span><span class="sxs-lookup"><span data-stu-id="13367-182">Indicates that archiving will be based on the In-Place Hold settings configured for the user's Exchange mailbox; if In-Place Hold has not been enabled on the user's mailbox then the user will have his or her messaging and Web conferencing transcripts archived in Lync Server.</span></span>

2.  <span data-ttu-id="13367-183">**UseLyncArchivingPolicy**。</span><span class="sxs-lookup"><span data-stu-id="13367-183">**UseLyncArchivingPolicy**.</span></span> <span data-ttu-id="13367-184">指示用户的即时消息和 Web 会议脚本应存档在 Lync Server 中，而不是在 Exchange 中。</span><span class="sxs-lookup"><span data-stu-id="13367-184">Indicates that the user's instant messaging and Web conferencing transcripts should be archived in Lync Server rather than in Exchange.</span></span>

3.  <span data-ttu-id="13367-185">**NoArchiving**。</span><span class="sxs-lookup"><span data-stu-id="13367-185">**NoArchiving**.</span></span> <span data-ttu-id="13367-186">指示根本不应存档用户的即时消息和 Web 会议脚本。</span><span class="sxs-lookup"><span data-stu-id="13367-186">Indicates that the user's instant messaging and Web conferencing transcripts should not be archived at all.</span></span> <span data-ttu-id="13367-187">请注意，此设置将替代分配给用户的任何 Lync Server 存档策略。</span><span class="sxs-lookup"><span data-stu-id="13367-187">Note that this setting overrides any Lync Server archiving policies assigned to the user.</span></span>

4.  <span data-ttu-id="13367-188">**ArchivingToExchange**。</span><span class="sxs-lookup"><span data-stu-id="13367-188">**ArchivingToExchange**.</span></span> <span data-ttu-id="13367-189">指示无论已将（或尚未）分配给用户的邮箱的就地保留设置如何，用户的即时消息和 Web 会议脚本都应存档到 Exchange。</span><span class="sxs-lookup"><span data-stu-id="13367-189">Indicates that the user's instant messaging and Web conferencing transcripts should be archived to Exchange regardless of the In-Place Hold settings that have (or have not) been assigned to the user's mailbox.</span></span>

<span data-ttu-id="13367-190">例如，若要配置用户帐户以使即时消息和 Web 会议脚本始终存档到 Exchange，您可以使用 Lync Server Management Shell 中类似的命令：</span><span class="sxs-lookup"><span data-stu-id="13367-190">For example, to configure a user account so that instant messaging and Web conferencing transcripts are always archived to Exchange you can use a command similar to this from the Lync Server Management Shell:</span></span>

    Set-CsUser -Identity "Ken Myer" -ExchangeArchivingPolicy ArchivingToExchange

<span data-ttu-id="13367-191">如果要为一组用户（例如驻留在指定注册器池中的所有用户）设置同一存档策略，可以使用如下命令：</span><span class="sxs-lookup"><span data-stu-id="13367-191">If you want to set the same archiving policy for a group of users (for example, all the users homed on a specified Registrar pool) you can use a command similar to this:</span></span>

    Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Set-CsUser -ExchangeArchivingPolicy ArchivingToExchange

<span data-ttu-id="13367-192">请注意，你必须使用 Lync Server Management Shell （和 Windows PowerShell）才能配置 ExchangeArchivingPolicy 属性的值。</span><span class="sxs-lookup"><span data-stu-id="13367-192">Note that you must use the Lync Server Management Shell (and Windows PowerShell) in order to configure value of the ExchangeArchivingPolicy property.</span></span> <span data-ttu-id="13367-193">此属性不会向 Lync Server "控制面板" 中的管理员公开。</span><span class="sxs-lookup"><span data-stu-id="13367-193">This property is not exposed to administrators in the Lync Server Control Panel.</span></span>

<span data-ttu-id="13367-194">如果您要查看已向其分配了特定存档策略的所有用户的列表，则可以使用如下命令，此命令返回已将 ExchangeArchivingPolicy 属性设置为“未初始化”的所有用户的 Active Directory 显示名称：</span><span class="sxs-lookup"><span data-stu-id="13367-194">If you would like to view a list of all the users who have been assigned a specific archiving policy then you can use a command similar to the following, which returns the Active Directory display name of all the users who have had the ExchangeArchivingPolicy property set to Uninitialized:</span></span>

    Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -eq "Uninitialized"} | Select-Object DisplayName

<span data-ttu-id="13367-195">同样，此命令也返回尚未将 ExchangeArchivingPolicy 属性设置为 UseLyncArchivingPolicy 的用户的显示名称：</span><span class="sxs-lookup"><span data-stu-id="13367-195">Likewise, this command returns the display name of the users who have not have the ExchangeArchivingPolicy property set to UseLyncArchivingPolicy:</span></span>

    Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -ne "UseLyncArchivingPolicy"} | Select-Object DisplayName

</div>

</div>

<span> </span>

</div>

</div>

</div>

