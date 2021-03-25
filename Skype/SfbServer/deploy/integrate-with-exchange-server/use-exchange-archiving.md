---
title: 配置 Skype for Business Server 以使用Exchange Server存档
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 260346d1-edc8-4a0c-8ad2-6c2401c3c377
description: 摘要：配置 Exchange Server 2016 或 Exchange Server 2013 和 Skype for Business Server 的 IM 脚本。
ms.openlocfilehash: 43a57fc227f7fc0dbcb33b2ecb4808f3e9762ad6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120311"
---
# <a name="configure-skype-for-business-server-to-use-exchange-server-archiving"></a><span data-ttu-id="1acc1-103">配置 Skype for Business Server 以使用Exchange Server存档</span><span class="sxs-lookup"><span data-stu-id="1acc1-103">Configure Skype for Business Server to use Exchange Server archiving</span></span>

<span data-ttu-id="1acc1-104">**摘要：** 为 2016 Exchange Server 2013 Exchange Server Skype for Business Server 配置 IM 脚本。</span><span class="sxs-lookup"><span data-stu-id="1acc1-104">**Summary:** Configure IM transcripts for Exchange Server 2016 or Exchange Server 2013 and Skype for Business Server.</span></span>

<span data-ttu-id="1acc1-105">Skype for Business Server 使管理员可以选择将即时消息和 Web 会议脚本存档到用户的 Exchange Server 2016 或 Exchange Server 2013 邮箱，而不是 SQL Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="1acc1-105">Skype for Business Server gives administrators the option of having instant messaging and Web conferencing transcripts archived to a user's Exchange Server 2016 or Exchange Server 2013 mailbox rather than a SQL Server database.</span></span> <span data-ttu-id="1acc1-106">如果启用此选项，则会将脚本写入用户邮箱中的“清除”文件夹。</span><span class="sxs-lookup"><span data-stu-id="1acc1-106">If you enable this option, transcripts are written to the Purges folder in the user's mailbox.</span></span> <span data-ttu-id="1acc1-107">“清除”文件夹是“可恢复邮件”文件夹下的一个隐藏文件夹。</span><span class="sxs-lookup"><span data-stu-id="1acc1-107">The Purges folder is a hidden folder found in the Recoverable Items folder.</span></span> <span data-ttu-id="1acc1-108">尽管此文件夹对最终用户不可见，但该文件夹由 Exchange 搜索引擎编制索引，并且可以使用 Exchange 邮箱搜索和/或 Microsoft SharePoint Server 2013 来发现。</span><span class="sxs-lookup"><span data-stu-id="1acc1-108">Although this folder is not visible to end users, the folder is indexed by the Exchange search engine and can be discovered by using Exchange mailbox search and/or Microsoft SharePoint Server 2013.</span></span> <span data-ttu-id="1acc1-109">由于信息存储在 Exchange In-Place 保留功能 (负责存档电子邮件和其他 Exchange 通信) 所使用的同一文件夹中，因此管理员可以使用单个工具来搜索为用户存档的所有电子通信。</span><span class="sxs-lookup"><span data-stu-id="1acc1-109">Because information is stored in the same folder used by the Exchange In-Place Hold feature (responsible for archiving email and other Exchange communications), administrators can use a single tool to search for all the electronic communications archived for a user.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1acc1-110">若要完全禁用对话存档，还必须禁用对话历史记录。</span><span class="sxs-lookup"><span data-stu-id="1acc1-110">To completely disable conversation archiving, you must also disable conversation history.</span></span> <span data-ttu-id="1acc1-111">有关详细信息，请参阅以下主题 [：Managing the Archiving of internal and external communications in Skype for Business Server、](/previous-versions/office/lync-server-2013/lync-server-2013-managing-the-archiving-of-internal-and-external-communications) [New-CsClientPolicy](/powershell/module/skype/new-csclientpolicy?view=skype-ps)和 [Set-CsClientPolicy](/powershell/module/skype/set-csclientpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="1acc1-111">For more information, see the following topics: [Managing the Archiving of internal and external communications in Skype for Business Server](/previous-versions/office/lync-server-2013/lync-server-2013-managing-the-archiving-of-internal-and-external-communications), [New-CsClientPolicy](/powershell/module/skype/new-csclientpolicy?view=skype-ps), and [Set-CsClientPolicy](/powershell/module/skype/set-csclientpolicy?view=skype-ps).</span></span>

<span data-ttu-id="1acc1-112">为了将脚本存档到Exchange Server必须先在 Skype for Business Server 和 Skype for Business Server 之间配置服务器到服务器Exchange Server。</span><span class="sxs-lookup"><span data-stu-id="1acc1-112">In order to archive transcripts to Exchange Server you must begin by configuring server-to-server authentication between Skype for Business Server and Exchange Server.</span></span> <span data-ttu-id="1acc1-113">在服务器到服务器身份验证就位后，可以在 Skype for Business Server (中执行以下任务，请注意，根据你的设置和配置，你可能不需要完成所有这些任务) ：</span><span class="sxs-lookup"><span data-stu-id="1acc1-113">After server-to-server authentication is in place, you can then carry out the following tasks in Skype for Business Server (note that, depending on your setup and configuration, you might not need to complete all of these tasks):</span></span>

1. <span data-ttu-id="1acc1-114">通过修改 Skype for Business Server 存档配置设置启用 Exchange 存档。</span><span class="sxs-lookup"><span data-stu-id="1acc1-114">Enable Exchange archiving by modifying your Skype for Business Server archiving configuration settings.</span></span> <span data-ttu-id="1acc1-115">此步骤是所有部署必需的。</span><span class="sxs-lookup"><span data-stu-id="1acc1-115">This step is required for all deployments.</span></span>

2. <span data-ttu-id="1acc1-116">为用户的内部和/或外部通信启用存档。</span><span class="sxs-lookup"><span data-stu-id="1acc1-116">Enable archiving for internal and/or external communications for your users.</span></span> <span data-ttu-id="1acc1-117">此步骤是所有部署必需的。</span><span class="sxs-lookup"><span data-stu-id="1acc1-117">This step is required for all deployments.</span></span>

3. <span data-ttu-id="1acc1-118">为每个用户配置 ExchangeArchivingPolicy 属性。</span><span class="sxs-lookup"><span data-stu-id="1acc1-118">Configure the ExchangeArchivingPolicy property for each user.</span></span> <span data-ttu-id="1acc1-119">只有当 Skype for Business Server 和 Exchange Server位于不同的林时，才需要执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="1acc1-119">This step is only required if Skype for Business Server and Exchange Server are located in different forests.</span></span>

## <a name="step-1-enabling-exchange-archiving"></a><span data-ttu-id="1acc1-120">步骤 1：启用 Exchange 存档</span><span class="sxs-lookup"><span data-stu-id="1acc1-120">Step 1: Enabling Exchange Archiving</span></span>

<span data-ttu-id="1acc1-121">Skype for Business Server 中的存档主要是通过使用存档配置设置进行管理的。</span><span class="sxs-lookup"><span data-stu-id="1acc1-121">Archiving in Skype for Business Server is primarily managed by using the archiving configuration settings.</span></span> <span data-ttu-id="1acc1-122">安装 Skype for Business Server 时，系统会自动提供这些设置的单个全局集合。</span><span class="sxs-lookup"><span data-stu-id="1acc1-122">When you install Skype for Business Server you are automatically given a single, global collection of these settings.</span></span> <span data-ttu-id="1acc1-123"> (管理员可以选择在站点范围创建新的存档设置集合。) 默认情况下，不会在全局设置中启用存档，也不会在这些设置中启用 Exchange 存档。</span><span class="sxs-lookup"><span data-stu-id="1acc1-123">(Administrators can optionally create new collections of archiving settings at the site scope.) By default, archiving is not enabled in the global settings, nor is Exchange archiving enabled in these settings.</span></span> <span data-ttu-id="1acc1-124">为了使用 Exchange 存档，管理员必须在这些配置设置中同时配置 EnableArchiving 和 EnableExchangeArchiving 属性。</span><span class="sxs-lookup"><span data-stu-id="1acc1-124">In order to use Exchange archiving, administrators must configure both the EnableArchiving and the EnableExchangeArchiving properties in these configuration settings.</span></span> <span data-ttu-id="1acc1-125">EnableArchiving 属性可以设置为以下三个可能的值之一：</span><span class="sxs-lookup"><span data-stu-id="1acc1-125">The EnableArchiving property can be set to one of three possible values:</span></span>

- <span data-ttu-id="1acc1-126">**无**。</span><span class="sxs-lookup"><span data-stu-id="1acc1-126">**None**.</span></span> <span data-ttu-id="1acc1-127">禁用存档。</span><span class="sxs-lookup"><span data-stu-id="1acc1-127">Archiving is disabled.</span></span> <span data-ttu-id="1acc1-128">这是默认值。</span><span class="sxs-lookup"><span data-stu-id="1acc1-128">This is the default value.</span></span> <span data-ttu-id="1acc1-129">如果 EnableArchiving 设置为 None，则 Skype for Business Server 存档数据库或存档数据库中不会存档任何Exchange Server。</span><span class="sxs-lookup"><span data-stu-id="1acc1-129">If EnableArchiving is set to None then nothing will be archived in either your Skype for Business Server archiving database or in Exchange Server.</span></span>

- <span data-ttu-id="1acc1-130">**ImOnly**。</span><span class="sxs-lookup"><span data-stu-id="1acc1-130">**ImOnly**.</span></span> <span data-ttu-id="1acc1-131">仅存档即时消息脚本。</span><span class="sxs-lookup"><span data-stu-id="1acc1-131">Only instant message transcripts are archived.</span></span> <span data-ttu-id="1acc1-132">如果启用 Exchange 存档，这些脚本将存档在Exchange Server。</span><span class="sxs-lookup"><span data-stu-id="1acc1-132">If Exchange archiving is enabled, these transcripts will be archived in Exchange Server.</span></span> <span data-ttu-id="1acc1-133">如果禁用 Exchange 存档，这些脚本将存档到 Skype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="1acc1-133">If Exchange archiving is disabled then these transcripts will be archived to Skype for Business Server.</span></span>

- <span data-ttu-id="1acc1-134">**ImAndWebConf**。</span><span class="sxs-lookup"><span data-stu-id="1acc1-134">**ImAndWebConf**.</span></span> <span data-ttu-id="1acc1-135">将存档即时消息脚本和 Web 会议脚本。</span><span class="sxs-lookup"><span data-stu-id="1acc1-135">Both instant message transcripts and Web conferencing transcripts are archived.</span></span> <span data-ttu-id="1acc1-136">如果启用 Exchange 存档，这些脚本将存档在Exchange Server。</span><span class="sxs-lookup"><span data-stu-id="1acc1-136">If Exchange archiving is enabled these transcripts will be archived in Exchange Server.</span></span> <span data-ttu-id="1acc1-137">如果禁用 Exchange 存档，这些脚本将存档到 Skype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="1acc1-137">If Exchange archiving is disabled then these transcripts will be archived to Skype for Business Server.</span></span>

<span data-ttu-id="1acc1-138">EnableExchangeArchiving 属性是一个布尔值：将 EnableExchangeArchiving 设置为 True ($True) 以启用 Exchange 存档，或将 EnableExchangeArchiving 设置为 False ($False) 禁用 Exchange 存档。</span><span class="sxs-lookup"><span data-stu-id="1acc1-138">The EnableExchangeArchiving property is a Boolean value: set EnableExchangeArchiving to True ($True) to enable Exchange archiving or set EnableExchangeArchiving to False ($False) to disable Exchange archiving.</span></span> <span data-ttu-id="1acc1-139">例如，此命令可启用即时消息脚本的存档，还启用 Exchange 存档：</span><span class="sxs-lookup"><span data-stu-id="1acc1-139">For example, this command enables the archiving of instant messaging transcripts and also enables Exchange archiving:</span></span>

```powershell
Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $True
```

<span data-ttu-id="1acc1-140">若要禁用 Exchange 存档，请使用类似如下的命令，该命令可启用即时消息存档，但禁用 Exchange (换句话说，脚本将存档到 Skype for Business Server) ：</span><span class="sxs-lookup"><span data-stu-id="1acc1-140">To disable Exchange archiving, use a command similar to the following, which enables instant messaging archiving but disables archiving to Exchange (in other words, transcripts will be archived to Skype for Business Server):</span></span>

```powershell
Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $False
```

> [!NOTE]
> <span data-ttu-id="1acc1-141">如果 EnableArchiving 属性设置为 None，则 Skype for Business Server 将完全不存档即时消息和 Web 会议脚本。</span><span class="sxs-lookup"><span data-stu-id="1acc1-141">If the EnableArchiving property is set to None, then Skype for Business Server will not archive instant messaging and Web conferencing transcripts at all.</span></span> <span data-ttu-id="1acc1-142">在本例中，服务器只会忽略为 EnableExchangeArchiving 配置的值。</span><span class="sxs-lookup"><span data-stu-id="1acc1-142">In that case, the server will simply ignore the value configured for EnableExchangeArchiving.</span></span>

<span data-ttu-id="1acc1-143">通过使用 Skype for Business Server， (Exchange 存档) 或禁用 Exchange 存档。</span><span class="sxs-lookup"><span data-stu-id="1acc1-143">Exchange archiving can also be enabled (or disabled) by using the Skype for Business Server.</span></span> <span data-ttu-id="1acc1-144">为此，请完成以下过程：</span><span class="sxs-lookup"><span data-stu-id="1acc1-144">To do that, complete the following procedure:</span></span>

1. <span data-ttu-id="1acc1-145">在控制面板中，单击“监控和存档”，然后单击“存档配置”。</span><span class="sxs-lookup"><span data-stu-id="1acc1-145">In Control Panel, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

2. <span data-ttu-id="1acc1-146">在“存档配置”选项卡上，双击要修改的存档设置集合（例如“全局”集合）。</span><span class="sxs-lookup"><span data-stu-id="1acc1-146">On the **Archiving Configuration** tab, double-click the collection of archiving settings to be modified (for example, the **Global** collection).</span></span>

3. <span data-ttu-id="1acc1-147">在“编辑存档设置”窗格中，单击“存档设置”下拉列表并选择“存档 IM 会话”（仅存档即时消息会话）或“存档 IM 和 Web 会议会话”（存档即时消息和 Web 会议会话）。</span><span class="sxs-lookup"><span data-stu-id="1acc1-147">In the **Edit Archiving Setting** pane, click the **Archiving setting** dropdown list and select either **Archive IM sessions** (to archive just instant messaging sessions) or **Archive IM and web conferencing sessions** (to archive both instant messaging and Web conferencing sessions).</span></span>

4. <span data-ttu-id="1acc1-148">选择要存档的项目后，选中"Exchange Server **集成"复选框** 以启用 Exchange 存档。</span><span class="sxs-lookup"><span data-stu-id="1acc1-148">After choosing the items to be archived, select the **Exchange Server integration** checkbox to enable Exchange archiving.</span></span> <span data-ttu-id="1acc1-149">若要禁用 Exchange 存档，请清除此复选框。</span><span class="sxs-lookup"><span data-stu-id="1acc1-149">To disable Exchange archiving, clear this checkbox.</span></span>

> [!NOTE]
> <span data-ttu-id="1acc1-150">如果“存档设置”设置为“禁用存档”，则“Exchange Server 集成”复选框不可用。</span><span class="sxs-lookup"><span data-stu-id="1acc1-150">The **Exchange Server integration** checkbox will not be available if the **Archiving setting** is set to **Disable archiving**.</span></span> <span data-ttu-id="1acc1-151">必须先启用存档，然后再启用 Exchange 存档。</span><span class="sxs-lookup"><span data-stu-id="1acc1-151">You must enable archiving first and then enable Exchange archiving.</span></span>

<span data-ttu-id="1acc1-152">如果 Skype for Business Server 和 Exchange Server 位于同一个林中，则使用 Exchange In-Place 保留策略管理单个用户的存档 (或至少在 Exchange Server) 上拥有电子邮件帐户的用户的存档。</span><span class="sxs-lookup"><span data-stu-id="1acc1-152">If Skype for Business Server and Exchange Server are located in the same forest, then archiving for individual users (or at least for users who have email accounts on Exchange Server) is managed by using Exchange In-Place Hold policies.</span></span> <span data-ttu-id="1acc1-153">如果你有用户托管在以前版本的 Exchange 上，则这些用户的存档将通过使用 Skype for Business Server 存档策略进行管理。</span><span class="sxs-lookup"><span data-stu-id="1acc1-153">If you have users who are homed on a previous version of Exchange then archiving for those users will be managed by using Skype for Business Server archiving policies.</span></span> <span data-ttu-id="1acc1-154">请注意，只有拥有 2016 Exchange Server 2013 Exchange Server帐户的用户才能将其 Skype for Business 脚本存档到 Exchange。</span><span class="sxs-lookup"><span data-stu-id="1acc1-154">Note that only users with accounts on Exchange Server 2016 or Exchange Server 2013 can have their Skype for Business transcripts archived to Exchange.</span></span>

<span data-ttu-id="1acc1-155">如果 Skype for Business Server Exchange Server位于不同的林中，则通过为各个用户帐户配置 ExchangeArchivingPolicy 属性管理单个用户的存档。</span><span class="sxs-lookup"><span data-stu-id="1acc1-155">If Skype for Business Server and Exchange Server are located in different forests then archiving for individual users is managed by configuring the ExchangeArchivingPolicy property for each individual user account.</span></span> <span data-ttu-id="1acc1-156">请参阅步骤 3 以了解更多信息。</span><span class="sxs-lookup"><span data-stu-id="1acc1-156">See Step 3 for more information.</span></span>

## <a name="step-2-enabling-the-archiving-of-internal-andor-external-communications"></a><span data-ttu-id="1acc1-157">步骤 2：启用内部和/或外部通信的存档</span><span class="sxs-lookup"><span data-stu-id="1acc1-157">Step 2: Enabling the Archiving of Internal and/or External Communications</span></span>

<span data-ttu-id="1acc1-158">在启用存档策略 (Exchange 存档) 您必须修改相应的存档策略以确保实际存档用户会话。</span><span class="sxs-lookup"><span data-stu-id="1acc1-158">After you have enabled archiving (and Exchange archiving) you must then modify the appropriate archiving policies to ensure that user sessions are actually archived.</span></span> <span data-ttu-id="1acc1-159">请注意，仅启用 (步骤 1) 不会导致 Skype for Business Server 开始存档即时消息和 Web 会议脚本。</span><span class="sxs-lookup"><span data-stu-id="1acc1-159">Note that simply enabling archiving (Step 1) does not cause Skype for Business Server to begin archiving instant messaging and Web conferencing transcripts.</span></span> <span data-ttu-id="1acc1-160">相反，您必须使用存档策略启用内部和/或外部存档。</span><span class="sxs-lookup"><span data-stu-id="1acc1-160">Instead, you must use archiving policies to enable internal and/or external archiving.</span></span> <span data-ttu-id="1acc1-161">安装 Skype for Business Server 时，还会安装一个包含两个属性的全局存档策略：</span><span class="sxs-lookup"><span data-stu-id="1acc1-161">When you install Skype for Business Server you also install a single, global archiving policy that contains two properties:</span></span>

- <span data-ttu-id="1acc1-p119">**ArchiveInternal**。当设置为 True ($True) 时，指示将存档仅涉及在贵组织中有 Active Directory 帐户的用户的内部通信会话。</span><span class="sxs-lookup"><span data-stu-id="1acc1-p119">**ArchiveInternal**. When set to True ($True) indicates that internal communication sessions involving only users who have Active Directory accounts in your organization) will be archived.</span></span>

- <span data-ttu-id="1acc1-p120">**ArchiveExternal**。当设置为 True ($True) 时，指示将存档内部通信会话（涉及至少一个在贵组织中没有 Active Directory 帐户的用户的会话）。</span><span class="sxs-lookup"><span data-stu-id="1acc1-p120">**ArchiveExternal**. When set to True ($True) indicates that internal communication sessions (sessions involving at least one user who does not have an Active Directory account in your organization) will be archived.</span></span>

<span data-ttu-id="1acc1-166">默认情况下，这两个属性的值都设置为 False，意味着既不存档内部通信会话也不存档外部通信会话。</span><span class="sxs-lookup"><span data-stu-id="1acc1-166">By default, both of these property values are set to False, meaning that neither internal nor external communication sessions are archived.</span></span> <span data-ttu-id="1acc1-167">若要修改全局策略，可以使用 Skype for Business Server 命令行管理程序和 Set-CsArchivingPolicy cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1acc1-167">To modify the global policy, you can use the Skype for Business Server Management Shell and the Set-CsArchivingPolicy cmdlet.</span></span> <span data-ttu-id="1acc1-168">此命令可对内部和外部通信会话进行存档：</span><span class="sxs-lookup"><span data-stu-id="1acc1-168">This command enables the archiving of both internal and external communication sessions:</span></span>

```powershell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True
```

<span data-ttu-id="1acc1-p122">您也可以使用 New-CsArchivingPolicy 在站点范围或每用户范围创建一个新策略。例如，此命令可新建一个名为 RedmondArchivingPolicy 的每用户存档策略：</span><span class="sxs-lookup"><span data-stu-id="1acc1-p122">Alternatively, you can use the New-CsArchivingPolicy to create a new policy at either the site scope or the per-user scope. For example, this command creates a new per-user archiving policy named RedmondArchivingPolicy:</span></span>

```powershell
New-CsArchivingPolicy -Identity "RedmondArchivingPolicy" -ArchiveInternal $True -ArchiveExternal $True
```

<span data-ttu-id="1acc1-p123">如果您创建每用户策略，您将需要将该策略分配给相应的用户。例如：</span><span class="sxs-lookup"><span data-stu-id="1acc1-p123">If you create a per-user policy you will then need to assign that policy to the appropriate users. For example:</span></span>

```powershell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName  "RedmondArchivingPolicy"
```

<span data-ttu-id="1acc1-173">存档策略也可使用 Skype for Business Server 控制面板进行管理。</span><span class="sxs-lookup"><span data-stu-id="1acc1-173">Archiving policies can also be managed by using the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="1acc1-174">在控制面板中，单击“监控和存档”，然后单击“存档策略”。</span><span class="sxs-lookup"><span data-stu-id="1acc1-174">Within the Control Panel, click **Monitoring and Archiving** and then click **Archiving Policy**.</span></span> <span data-ttu-id="1acc1-175">若要修改现有策略，请双击该策略（例如“全局”），然后在“编辑存档策略”窗格中，根据需要选中或清除“存档内部通信”和“存档外部通信”复选框。</span><span class="sxs-lookup"><span data-stu-id="1acc1-175">To modify an existing policy, double-click the policy (e.g., Global) and then, in the **Edit Archiving Policy** pane, select or clear the **Archive internal communications** and the **Archive external communications** checkboxes as needed.</span></span> <span data-ttu-id="1acc1-176">若要创建新的存档策略，请单击"**新建**"，然后选择"站点策略"**或**"**用户策略"。**</span><span class="sxs-lookup"><span data-stu-id="1acc1-176">To create a new archiving policy, click **New** and then select either **Site policy** or **User policy**.</span></span> <span data-ttu-id="1acc1-177">如果您新建用户策略，则必须访问相应的用户帐户（从“用户”选项卡中）并为这些用户分配新策略。</span><span class="sxs-lookup"><span data-stu-id="1acc1-177">If you create a new user policy then you must access the appropriate user accounts (from the **Users** tab) and assign those users the new policy.</span></span>

## <a name="step-3-configuring-the-exchangearchivingpolicy-property"></a><span data-ttu-id="1acc1-178">步骤 3：配置 ExchangeArchivingPolicy 属性</span><span class="sxs-lookup"><span data-stu-id="1acc1-178">Step 3: Configuring the ExchangeArchivingPolicy Property</span></span>

<span data-ttu-id="1acc1-179">如果 Skype for Business Server Exchange Server位于不同的林中，则只需在存档配置设置中启用 Exchange 存档是不够的;这不会在 Exchange 中存档即时消息和 Web 会议脚本。</span><span class="sxs-lookup"><span data-stu-id="1acc1-179">If Skype for Business Server and Exchange Server are located in different forests, then it is not enough to simply enable Exchange archiving in the archiving configuration settings; that will not result in instant messaging and Web conferencing transcripts being archived in Exchange.</span></span> <span data-ttu-id="1acc1-180">相反，还必须在每个相关的 Skype for Business Server 用户帐户上配置 ExchangeArchivingPolicy 属性。</span><span class="sxs-lookup"><span data-stu-id="1acc1-180">Instead, you must also configure the ExchangeArchivingPolicy property on each of the relevant Skype for Business Server user accounts.</span></span> <span data-ttu-id="1acc1-181">此属性可设置为以下四个可能的值之一：</span><span class="sxs-lookup"><span data-stu-id="1acc1-181">This property can be set to one of four possible values:</span></span>

1. <span data-ttu-id="1acc1-182">**未初始化**。</span><span class="sxs-lookup"><span data-stu-id="1acc1-182">**Uninitialized**.</span></span> <span data-ttu-id="1acc1-183">指示存档将基于为In-Place Exchange 邮箱配置的"保留"设置;如果In-Place邮箱上未启用"保留"功能，则用户将在 Skype for Business Server 中存档其消息和 Web 会议脚本。</span><span class="sxs-lookup"><span data-stu-id="1acc1-183">Indicates that archiving will be based on the In-Place Hold settings configured for the user's Exchange mailbox; if In-Place Hold has not been enabled on the user's mailbox then the user will have his or her messaging and Web conferencing transcripts archived in Skype for Business Server.</span></span>

2. <span data-ttu-id="1acc1-184">**UseLyncArchivingPolicy**。</span><span class="sxs-lookup"><span data-stu-id="1acc1-184">**UseLyncArchivingPolicy**.</span></span> <span data-ttu-id="1acc1-185">指示应在 Skype for Business Server 而非 Exchange 中存档用户的即时消息和 Web 会议脚本。</span><span class="sxs-lookup"><span data-stu-id="1acc1-185">Indicates that the user's instant messaging and Web conferencing transcripts should be archived in Skype for Business Server rather than in Exchange.</span></span>

3. <span data-ttu-id="1acc1-186">**NoArchiving**。</span><span class="sxs-lookup"><span data-stu-id="1acc1-186">**NoArchiving**.</span></span> <span data-ttu-id="1acc1-187">指示根本不应存档用户的即时消息和 Web 会议脚本。</span><span class="sxs-lookup"><span data-stu-id="1acc1-187">Indicates that the user's instant messaging and Web conferencing transcripts should not be archived at all.</span></span> <span data-ttu-id="1acc1-188">请注意，此设置会覆盖分配给用户的任何 Skype for Business Server 存档策略。</span><span class="sxs-lookup"><span data-stu-id="1acc1-188">Note that this setting overrides any Skype for Business Server archiving policies assigned to the user.</span></span>

4. <span data-ttu-id="1acc1-189">**ArchivingToExchange**。</span><span class="sxs-lookup"><span data-stu-id="1acc1-189">**ArchivingToExchange**.</span></span> <span data-ttu-id="1acc1-190">指示用户即时消息和 Web 会议脚本应存档到 Exchange，而不考虑 (或) 分配给用户邮箱的 In-Place 保留设置。</span><span class="sxs-lookup"><span data-stu-id="1acc1-190">Indicates that the user's instant messaging and Web conferencing transcripts should be archived to Exchange regardless of the In-Place Hold settings that have (or have not) been assigned to the user's mailbox.</span></span>

<span data-ttu-id="1acc1-191">例如，若要配置用户帐户以便始终将即时消息和 Web 会议脚本存档到 Exchange，可以从 Skype for Business Server 命令行管理程序使用类似以下的命令：</span><span class="sxs-lookup"><span data-stu-id="1acc1-191">For example, to configure a user account so that instant messaging and Web conferencing transcripts are always archived to Exchange you can use a command similar to this from the Skype for Business Server Management Shell:</span></span>

```powershell
Set-CsUser -Identity "Ken Myer" -ExchangeArchivingPolicy ArchivingToExchange
```

<span data-ttu-id="1acc1-192">如果要为一组用户（例如驻留在指定注册器池中的所有用户）设置同一存档策略，可以使用如下命令：</span><span class="sxs-lookup"><span data-stu-id="1acc1-192">If you want to set the same archiving policy for a group of users (for example, all the users homed on a specified Registrar pool) you can use a command similar to this:</span></span>

```powershell
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Set-CsUser -ExchangeArchivingPolicy ArchivingToExchange
```

<span data-ttu-id="1acc1-193">请注意，必须使用 Skype for Business Server 命令行管理程序 (Windows PowerShell) 才能配置 ExchangeArchivingPolicy 属性的值。</span><span class="sxs-lookup"><span data-stu-id="1acc1-193">Note that you must use the Skype for Business Server Management Shell (and Windows PowerShell) in order to configure value of the ExchangeArchivingPolicy property.</span></span> <span data-ttu-id="1acc1-194">此属性不会向 Skype for Business Server 中的管理员公开。</span><span class="sxs-lookup"><span data-stu-id="1acc1-194">This property is not exposed to administrators in the Skype for Business Server.</span></span>

<span data-ttu-id="1acc1-195">如果您要查看已向其分配了特定存档策略的所有用户的列表，则可以使用如下命令，此命令返回已将 ExchangeArchivingPolicy 属性设置为“未初始化”的所有用户的 Active Directory 显示名称：</span><span class="sxs-lookup"><span data-stu-id="1acc1-195">If you would like to view a list of all the users who have been assigned a specific archiving policy then you can use a command similar to the following, which returns the Active Directory display name of all the users who have had the ExchangeArchivingPolicy property set to Uninitialized:</span></span>

```powershell
Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -eq "Uninitialized"} | Select-Object DisplayName
```

<span data-ttu-id="1acc1-196">同样，此命令也返回尚未将 ExchangeArchivingPolicy 属性设置为 UseLyncArchivingPolicy 的用户的显示名称：</span><span class="sxs-lookup"><span data-stu-id="1acc1-196">Likewise, this command returns the display name of the users who have not have the ExchangeArchivingPolicy property set to UseLyncArchivingPolicy:</span></span>

```powershell
Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -ne "UseLyncArchivingPolicy"} | Select-Object DisplayName
```