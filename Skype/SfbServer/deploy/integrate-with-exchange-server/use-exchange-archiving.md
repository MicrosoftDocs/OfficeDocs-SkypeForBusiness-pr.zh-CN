---
title: 配置 Business Server 使用 Exchange Server 存档的 Skype
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 260346d1-edc8-4a0c-8ad2-6c2401c3c377
description: 摘要： 配置 IM 脚本 Exchange Server 2016 或 Exchange Server 2013 和 Skype 业务服务器。
ms.openlocfilehash: 63d533091426fe609932de18e3d37bd75004ce4c
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/28/2018
ms.locfileid: "23258023"
---
# <a name="configure-skype-for-business-server-to-use-exchange-server-archiving"></a><span data-ttu-id="9a8c6-103">配置 Business Server 使用 Exchange Server 存档的 Skype</span><span class="sxs-lookup"><span data-stu-id="9a8c6-103">Configure Skype for Business Server to use Exchange Server archiving</span></span>

<span data-ttu-id="9a8c6-104">**摘要：** 配置 Exchange Server 2016 或 Exchange Server 2013 和 Skype 业务服务器 IM 脚本。</span><span class="sxs-lookup"><span data-stu-id="9a8c6-104">**Summary:** Configure IM transcripts for Exchange Server 2016 or Exchange Server 2013 and Skype for Business Server.</span></span>

<span data-ttu-id="9a8c6-105">Skype 业务服务器为管理员提供了无即时消息和 Web 会议脚本存档到用户的 Exchange Server 2016 或 Exchange Server 2013 的邮箱，而不是 SQL Server 数据库的选项。</span><span class="sxs-lookup"><span data-stu-id="9a8c6-105">Skype for Business Server gives administrators the option of having instant messaging and Web conferencing transcripts archived to a user's Exchange Server 2016 or Exchange Server 2013 mailbox rather than a SQL Server database.</span></span> <span data-ttu-id="9a8c6-106">如果启用此选项，则会将脚本写入用户邮箱中的“清除”文件夹。</span><span class="sxs-lookup"><span data-stu-id="9a8c6-106">If you enable this option, transcripts are written to the Purges folder in the user's mailbox.</span></span> <span data-ttu-id="9a8c6-107">“清除”文件夹是“可恢复邮件”文件夹下的一个隐藏文件夹。</span><span class="sxs-lookup"><span data-stu-id="9a8c6-107">The Purges folder is a hidden folder found in the Recoverable Items folder.</span></span> <span data-ttu-id="9a8c6-108">尽管此文件夹不是最终用户可见的文件夹由 Exchange 搜索引擎编制索引，并可以发现使用 Exchange 邮箱搜索和/或 Microsoft SharePoint Server 2013。</span><span class="sxs-lookup"><span data-stu-id="9a8c6-108">Although this folder is not visible to end users, the folder is indexed by the Exchange search engine and can be discovered by using Exchange mailbox search and/or Microsoft SharePoint Server 2013.</span></span> <span data-ttu-id="9a8c6-109">因为由 Exchange 就地保留功能 (存档电子邮件和其他 Exchange 通信 responsible) 的同一文件夹中存储的信息，管理员可以使用单一的工具可以搜索所有电子通信的存档用户。</span><span class="sxs-lookup"><span data-stu-id="9a8c6-109">Because information is stored in the same folder used by the Exchange In-Place Hold feature (responsible for archiving email and other Exchange communications), administrators can use a single tool to search for all the electronic communications archived for a user.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9a8c6-110">要完全禁用对话存档，您还必须禁用对话历史记录。</span><span class="sxs-lookup"><span data-stu-id="9a8c6-110">To completely disable conversation archiving, you must also disable conversation history.</span></span> <span data-ttu-id="9a8c6-111">有关详细信息，请参阅以下主题：[管理 Skype 业务服务器中的内部和外部通信的存档](https://technet.microsoft.com/library/6c2cf941-3204-4f1a-a7e0-416c828056d9.aspx)、 [New-csclientpolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps)和[Set-csclientpolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="9a8c6-111">For more information, see the following topics: [Managing the Archiving of internal and external communications in Skype for Business Server](https://technet.microsoft.com/library/6c2cf941-3204-4f1a-a7e0-416c828056d9.aspx), [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps), and [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps).</span></span>

<span data-ttu-id="9a8c6-112">若要存档到 Exchange 服务器，必须首先 Skype 业务 server 和 Exchange 服务器之间配置服务器到服务器身份验证的脚本。</span><span class="sxs-lookup"><span data-stu-id="9a8c6-112">In order to archive transcripts to Exchange Server you must begin by configuring server-to-server authentication between Skype for Business Server and Exchange Server.</span></span> <span data-ttu-id="9a8c6-113">服务器到服务器身份验证后，您可以再执行 Skype 中的以下任务的业务服务器 （请注意，具体取决于您的安装和配置，您可能不需要完成这些任务的所有）：</span><span class="sxs-lookup"><span data-stu-id="9a8c6-113">After server-to-server authentication is in place, you can then carry out the following tasks in Skype for Business Server (note that, depending on your setup and configuration, you might not need to complete all of these tasks):</span></span>

1. <span data-ttu-id="9a8c6-114">启用 Exchange 存档通过修改您 Skype 业务服务器存档配置设置。</span><span class="sxs-lookup"><span data-stu-id="9a8c6-114">Enable Exchange archiving by modifying your Skype for Business Server archiving configuration settings.</span></span> <span data-ttu-id="9a8c6-115">此步骤是所有部署必需的。</span><span class="sxs-lookup"><span data-stu-id="9a8c6-115">This step is required for all deployments.</span></span>

2. <span data-ttu-id="9a8c6-p105">为用户的内部和/或外部通信启用存档。此步骤是所有部署必需的。</span><span class="sxs-lookup"><span data-stu-id="9a8c6-p105">Enable archiving for internal and/or external communications for your users. This step is required for all deployments.</span></span>

3. <span data-ttu-id="9a8c6-118">为每个用户配置 ExchangeArchivingPolicy 属性。</span><span class="sxs-lookup"><span data-stu-id="9a8c6-118">Configure the ExchangeArchivingPolicy property for each user.</span></span> <span data-ttu-id="9a8c6-119">此步骤即告仅所需的业务 Server 和 Exchange Server 的 Skype 都位于不同的林中。</span><span class="sxs-lookup"><span data-stu-id="9a8c6-119">This step is only required if Skype for Business Server and Exchange Server are located in different forests.</span></span>

## <a name="step-1-enabling-exchange-archiving"></a><span data-ttu-id="9a8c6-120">步骤 1： 启用 Exchange 存档</span><span class="sxs-lookup"><span data-stu-id="9a8c6-120">Step 1: Enabling Exchange Archiving</span></span>

<span data-ttu-id="9a8c6-121">适用于业务 Server archiving Skype 中主要使用存档配置设置进行管理。</span><span class="sxs-lookup"><span data-stu-id="9a8c6-121">Archiving in Skype for Business Server is primarily managed by using the archiving configuration settings.</span></span> <span data-ttu-id="9a8c6-122">为业务服务器安装 Skype 时将自动授予这些设置的单个、 全局集合。</span><span class="sxs-lookup"><span data-stu-id="9a8c6-122">When you install Skype for Business Server you are automatically given a single, global collection of these settings.</span></span> <span data-ttu-id="9a8c6-123">（管理员可以选择创建新的存档设置集在站点范围。）默认情况下，存档的全局设置中未启用也不 Exchange 存档启用这些设置中。</span><span class="sxs-lookup"><span data-stu-id="9a8c6-123">(Administrators can optionally create new collections of archiving settings at the site scope.) By default, archiving is not enabled in the global settings, nor is Exchange archiving enabled in these settings.</span></span> <span data-ttu-id="9a8c6-124">若要使用 Exchange 存档，管理员必须在这些配置设置中配置 EnableArchiving 和 EnableExchangeArchiving 属性。</span><span class="sxs-lookup"><span data-stu-id="9a8c6-124">In order to use Exchange archiving, administrators must configure both the EnableArchiving and the EnableExchangeArchiving properties in these configuration settings.</span></span> <span data-ttu-id="9a8c6-125">EnableArchiving 属性可以设置为以下三个可能的值之一：</span><span class="sxs-lookup"><span data-stu-id="9a8c6-125">The EnableArchiving property can be set to one of three possible values:</span></span>

- <span data-ttu-id="9a8c6-126">**无**。</span><span class="sxs-lookup"><span data-stu-id="9a8c6-126">**None**.</span></span> <span data-ttu-id="9a8c6-127">禁用存档。</span><span class="sxs-lookup"><span data-stu-id="9a8c6-127">Archiving is disabled.</span></span> <span data-ttu-id="9a8c6-128">这是默认值。</span><span class="sxs-lookup"><span data-stu-id="9a8c6-128">This is the default value.</span></span> <span data-ttu-id="9a8c6-129">如果 EnableArchiving 设置为 None，则执行任何操作将在存档您 Skype，存档数据库的业务服务器或 Exchange 服务器中。</span><span class="sxs-lookup"><span data-stu-id="9a8c6-129">If EnableArchiving is set to None then nothing will be archived in either your Skype for Business Server archiving database or in Exchange Server.</span></span>

- <span data-ttu-id="9a8c6-130">**ImOnly**。</span><span class="sxs-lookup"><span data-stu-id="9a8c6-130">**ImOnly**.</span></span> <span data-ttu-id="9a8c6-131">仅存档即时消息脚本。</span><span class="sxs-lookup"><span data-stu-id="9a8c6-131">Only instant message transcripts are archived.</span></span> <span data-ttu-id="9a8c6-132">如果启用 Exchange 存档，则这些脚本将存档在 Exchange 服务器中。</span><span class="sxs-lookup"><span data-stu-id="9a8c6-132">If Exchange archiving is enabled, these transcripts will be archived in Exchange Server.</span></span> <span data-ttu-id="9a8c6-133">如果禁用 Exchange 存档然后这些脚本将存档到 Skype 业务服务器。</span><span class="sxs-lookup"><span data-stu-id="9a8c6-133">If Exchange archiving is disabled then these transcripts will be archived to Skype for Business Server.</span></span>

- <span data-ttu-id="9a8c6-134">**ImAndWebConf**。</span><span class="sxs-lookup"><span data-stu-id="9a8c6-134">**ImAndWebConf**.</span></span> <span data-ttu-id="9a8c6-135">将存档即时消息脚本和 Web 会议脚本。</span><span class="sxs-lookup"><span data-stu-id="9a8c6-135">Both instant message transcripts and Web conferencing transcripts are archived.</span></span> <span data-ttu-id="9a8c6-136">如果启用 Exchange 存档，则这些脚本将存档在 Exchange 服务器中。</span><span class="sxs-lookup"><span data-stu-id="9a8c6-136">If Exchange archiving is enabled these transcripts will be archived in Exchange Server.</span></span> <span data-ttu-id="9a8c6-137">如果禁用 Exchange 存档然后这些脚本将存档到 Skype 业务服务器。</span><span class="sxs-lookup"><span data-stu-id="9a8c6-137">If Exchange archiving is disabled then these transcripts will be archived to Skype for Business Server.</span></span>

<span data-ttu-id="9a8c6-138">EnableExchangeArchiving 属性是一个布尔值： 为 False ($False) 若要禁用 Exchange 存档设置为 True ($True) 可启用 Exchange 存档设置 EnableExchangeArchiving EnableExchangeArchiving。</span><span class="sxs-lookup"><span data-stu-id="9a8c6-138">The EnableExchangeArchiving property is a Boolean value: set EnableExchangeArchiving to True ($True) to enable Exchange archiving or set EnableExchangeArchiving to False ($False) to disable Exchange archiving.</span></span> <span data-ttu-id="9a8c6-139">例如，此命令启用存档即时消息脚本，并还允许 Exchange 存档：</span><span class="sxs-lookup"><span data-stu-id="9a8c6-139">For example, this command enables the archiving of instant messaging transcripts and also enables Exchange archiving:</span></span>

```
Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $True
```

<span data-ttu-id="9a8c6-140">若要禁用 Exchange 存档，请使用类似于以下内容，它们启用即时消息存档但禁用 exchange 存档命令 （换言之，脚本将存档到 Skype 业务 server）：</span><span class="sxs-lookup"><span data-stu-id="9a8c6-140">To disable Exchange archiving, use a command similar to the following, which enables instant messaging archiving but disables archiving to Exchange (in other words, transcripts will be archived to Skype for Business Server):</span></span>

```
Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $False
```

> [!NOTE]
> <span data-ttu-id="9a8c6-141">如果 EnableArchiving 属性设置为无，然后 Skype 业务服务器将不存档即时消息和 Web 会议脚本根本。</span><span class="sxs-lookup"><span data-stu-id="9a8c6-141">If the EnableArchiving property is set to None, then Skype for Business Server will not archive instant messaging and Web conferencing transcripts at all.</span></span> <span data-ttu-id="9a8c6-142">在本例中，服务器只会忽略为 EnableExchangeArchiving 配置的值。</span><span class="sxs-lookup"><span data-stu-id="9a8c6-142">In that case, the server will simply ignore the value configured for EnableExchangeArchiving.</span></span>

<span data-ttu-id="9a8c6-143">Exchange 存档可以还启用 （或禁用） 使用 Skype 业务服务器。</span><span class="sxs-lookup"><span data-stu-id="9a8c6-143">Exchange archiving can also be enabled (or disabled) by using the Skype for Business Server.</span></span> <span data-ttu-id="9a8c6-144">为此，请完成以下过程：</span><span class="sxs-lookup"><span data-stu-id="9a8c6-144">To do that, complete the following procedure:</span></span>

1. <span data-ttu-id="9a8c6-145">在控制面板中，单击“**监控和存档**”，然后单击“**存档配置**”。</span><span class="sxs-lookup"><span data-stu-id="9a8c6-145">In Control Panel, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

2. <span data-ttu-id="9a8c6-146">在“**存档配置**”选项卡上，双击要修改的存档设置集合（例如“**全局**”集合）。</span><span class="sxs-lookup"><span data-stu-id="9a8c6-146">On the **Archiving Configuration** tab, double-click the collection of archiving settings to be modified (for example, the **Global** collection).</span></span>

3. <span data-ttu-id="9a8c6-147">在“**编辑存档设置**”窗格中，单击“**存档设置**”下拉列表并选择“**存档 IM 会话**”（仅存档即时消息会话）或“**存档 IM 和 Web 会议会话**”（存档即时消息和 Web 会议会话）。</span><span class="sxs-lookup"><span data-stu-id="9a8c6-147">In the **Edit Archiving Setting** pane, click the **Archiving setting** dropdown list and select either **Archive IM sessions** (to archive just instant messaging sessions) or **Archive IM and web conferencing sessions** (to archive both instant messaging and Web conferencing sessions).</span></span>

4. <span data-ttu-id="9a8c6-148">选择后要存档的项目，选择**Exchange Server 集成**复选框以启用 Exchange 存档。</span><span class="sxs-lookup"><span data-stu-id="9a8c6-148">After choosing the items to be archived, select the **Exchange Server integration** checkbox to enable Exchange archiving.</span></span> <span data-ttu-id="9a8c6-149">若要禁用 Exchange 存档，请清除此复选框。</span><span class="sxs-lookup"><span data-stu-id="9a8c6-149">To disable Exchange archiving, clear this checkbox.</span></span>

> [!NOTE]
> <span data-ttu-id="9a8c6-150">如果“**存档设置**”设置为“**禁用存档**”，则“**Exchange Server 集成**”复选框不可用。</span><span class="sxs-lookup"><span data-stu-id="9a8c6-150">The **Exchange Server integration** checkbox will not be available if the **Archiving setting** is set to **Disable archiving**.</span></span> <span data-ttu-id="9a8c6-151">您必须启用存档的第一，并启用 Exchange 存档。</span><span class="sxs-lookup"><span data-stu-id="9a8c6-151">You must enable archiving first and then enable Exchange archiving.</span></span>

<span data-ttu-id="9a8c6-152">通过使用 Exchange 就地保留策略管理如果 Business Server 和 Exchange Server 的 Skype 位于同一个林中，然后为各个用户存档 （或至少具有电子邮件的用户帐户的 Exchange 服务器上）。</span><span class="sxs-lookup"><span data-stu-id="9a8c6-152">If Skype for Business Server and Exchange Server are located in the same forest, then archiving for individual users (or at least for users who have email accounts on Exchange Server) is managed by using Exchange In-Place Hold policies.</span></span> <span data-ttu-id="9a8c6-153">如果您有用户驻留在以前版本的 Exchange 然后存档这些用户将使用 Skype Business Server 存档策略管理。</span><span class="sxs-lookup"><span data-stu-id="9a8c6-153">If you have users who are homed on a previous version of Exchange then archiving for those users will be managed by using Skype for Business Server archiving policies.</span></span> <span data-ttu-id="9a8c6-154">请注意，仅使用 Exchange Server 2016 或 Exchange Server 2013 上的帐户的用户可以具有业务脚本存档到 Exchange 其 Skype。</span><span class="sxs-lookup"><span data-stu-id="9a8c6-154">Note that only users with accounts on Exchange Server 2016 or Exchange Server 2013 can have their Skype for Business transcripts archived to Exchange.</span></span>

<span data-ttu-id="9a8c6-155">如果业务 Server 和 Exchange Server 的 Skype 位于在不同的林中，然后为各个用户存档所管理的配置 ExchangeArchivingPolicy 属性的每个用户帐户。</span><span class="sxs-lookup"><span data-stu-id="9a8c6-155">If Skype for Business Server and Exchange Server are located in different forests then archiving for individual users is managed by configuring the ExchangeArchivingPolicy property for each individual user account.</span></span> <span data-ttu-id="9a8c6-156">请参阅步骤 3 以了解更多信息。</span><span class="sxs-lookup"><span data-stu-id="9a8c6-156">See Step 3 for more information.</span></span>

## <a name="step-2-enabling-the-archiving-of-internal-andor-external-communications"></a><span data-ttu-id="9a8c6-157">步骤 2：启用内部和/或外部通信的存档</span><span class="sxs-lookup"><span data-stu-id="9a8c6-157">Step 2: Enabling the Archiving of Internal and/or External Communications</span></span>

<span data-ttu-id="9a8c6-158">在启用了存档 （和 Exchange 存档后） 然后必须修改相应的存档策略以确保用户会话实际已存档。</span><span class="sxs-lookup"><span data-stu-id="9a8c6-158">After you have enabled archiving (and Exchange archiving) you must then modify the appropriate archiving policies to ensure that user sessions are actually archived.</span></span> <span data-ttu-id="9a8c6-159">请注意只启用存档 (第 1 步) 不会导致 Skype 业务服务器开始存档即时消息和 Web 会议脚本。</span><span class="sxs-lookup"><span data-stu-id="9a8c6-159">Note that simply enabling archiving (Step 1) does not cause Skype for Business Server to begin archiving instant messaging and Web conferencing transcripts.</span></span> <span data-ttu-id="9a8c6-160">相反，您必须使用存档策略启用内部和/或外部存档。</span><span class="sxs-lookup"><span data-stu-id="9a8c6-160">Instead, you must use archiving policies to enable internal and/or external archiving.</span></span> <span data-ttu-id="9a8c6-161">为业务服务器安装 Skype 时还会安装包含两个属性的单个、 全局存档策略：</span><span class="sxs-lookup"><span data-stu-id="9a8c6-161">When you install Skype for Business Server you also install a single, global archiving policy that contains two properties:</span></span>

- <span data-ttu-id="9a8c6-p119">**ArchiveInternal**。当设置为 True ($True) 时，指示将存档仅涉及在贵组织中有 Active Directory 帐户的用户的内部通信会话。</span><span class="sxs-lookup"><span data-stu-id="9a8c6-p119">**ArchiveInternal**. When set to True ($True) indicates that internal communication sessions involving only users who have Active Directory accounts in your organization) will be archived.</span></span>

- <span data-ttu-id="9a8c6-p120">**ArchiveExternal**。当设置为 True ($True) 时，指示将存档内部通信会话（涉及至少一个在贵组织中没有 Active Directory 帐户的用户的会话）。</span><span class="sxs-lookup"><span data-stu-id="9a8c6-p120">**ArchiveExternal**. When set to True ($True) indicates that internal communication sessions (sessions involving at least one user who does not have an Active Directory account in your organization) will be archived.</span></span>

<span data-ttu-id="9a8c6-166">默认情况下，这两个属性的值都设置为 False，意味着既不存档内部通信会话也不存档外部通信会话。</span><span class="sxs-lookup"><span data-stu-id="9a8c6-166">By default, both of these property values are set to False, meaning that neither internal nor external communication sessions are archived.</span></span> <span data-ttu-id="9a8c6-167">若要修改全局策略，您可用于 Skype 业务 Server 命令行管理程序和 Set-csarchivingpolicy cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9a8c6-167">To modify the global policy, you can use the Skype for Business Server Management Shell and the Set-CsArchivingPolicy cmdlet.</span></span> <span data-ttu-id="9a8c6-168">此命令可对内部和外部通信会话进行存档：</span><span class="sxs-lookup"><span data-stu-id="9a8c6-168">This command enables the archiving of both internal and external communication sessions:</span></span>

```
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True
```

<span data-ttu-id="9a8c6-p122">您也可以使用 New-CsArchivingPolicy 在站点范围或每用户范围创建一个新策略。例如，此命令可新建一个名为 RedmondArchivingPolicy 的每用户存档策略：</span><span class="sxs-lookup"><span data-stu-id="9a8c6-p122">Alternatively, you can use the New-CsArchivingPolicy to create a new policy at either the site scope or the per-user scope. For example, this command creates a new per-user archiving policy named RedmondArchivingPolicy:</span></span>

```
New-CsArchivingPolicy -Identity "RedmondArchivingPolicy" -ArchiveInternal $True -ArchiveExternal $True
```

<span data-ttu-id="9a8c6-p123">如果您创建每用户策略，您将需要将该策略分配给相应的用户。例如：</span><span class="sxs-lookup"><span data-stu-id="9a8c6-p123">If you create a per-user policy you will then need to assign that policy to the appropriate users. For example:</span></span>

```
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName  "RedmondArchivingPolicy"
```

<span data-ttu-id="9a8c6-173">也可以使用适用于业务 Server Control Panel Skype 管理存档策略。</span><span class="sxs-lookup"><span data-stu-id="9a8c6-173">Archiving policies can also be managed by using the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="9a8c6-174">在控制面板中，单击“**监控和存档**”，然后单击“**存档策略**”。</span><span class="sxs-lookup"><span data-stu-id="9a8c6-174">Within the Control Panel, click **Monitoring and Archiving** and then click **Archiving Policy**.</span></span> <span data-ttu-id="9a8c6-175">若要修改现有策略，请双击该策略（例如“全局”），然后在“**编辑存档策略**”窗格中，根据需要选中或清除“**存档内部通信**”和“**存档外部通信**”复选框。</span><span class="sxs-lookup"><span data-stu-id="9a8c6-175">To modify an existing policy, double-click the policy (e.g., Global) and then, in the **Edit Archiving Policy** pane, select or clear the **Archive internal communications** and the **Archive external communications** checkboxes as needed.</span></span> <span data-ttu-id="9a8c6-176">若要创建新的存档策略，单击**新建**，然后选择**站点策略**或**用户策略**。</span><span class="sxs-lookup"><span data-stu-id="9a8c6-176">To create a new archiving policy, click **New** and then select either **Site policy** or **User policy**.</span></span> <span data-ttu-id="9a8c6-177">如果您新建用户策略，则必须访问相应的用户帐户（从“**用户**”选项卡中）并为这些用户分配新策略。</span><span class="sxs-lookup"><span data-stu-id="9a8c6-177">If you create a new user policy then you must access the appropriate user accounts (from the **Users** tab) and assign those users the new policy.</span></span>

## <a name="step-3-configuring-the-exchangearchivingpolicy-property"></a><span data-ttu-id="9a8c6-178">步骤 3：配置 ExchangeArchivingPolicy 属性</span><span class="sxs-lookup"><span data-stu-id="9a8c6-178">Step 3: Configuring the ExchangeArchivingPolicy Property</span></span>

<span data-ttu-id="9a8c6-179">如果业务 Server 和 Exchange Server 的 Skype 位于不同的林中，则它不是足够只启用 Exchange 存档的存档配置设置;不会导致即时消息和 Web 会议脚本在 Exchange 存档。</span><span class="sxs-lookup"><span data-stu-id="9a8c6-179">If Skype for Business Server and Exchange Server are located in different forests, then it is not enough to simply enable Exchange archiving in the archiving configuration settings; that will not result in instant messaging and Web conferencing transcripts being archived in Exchange.</span></span> <span data-ttu-id="9a8c6-180">相反，您还必须在每个企业服务器用户帐户相关的 Skype 配置 ExchangeArchivingPolicy 属性。</span><span class="sxs-lookup"><span data-stu-id="9a8c6-180">Instead, you must also configure the ExchangeArchivingPolicy property on each of the relevant Skype for Business Server user accounts.</span></span> <span data-ttu-id="9a8c6-181">此属性可设置为以下四个可能的值之一：</span><span class="sxs-lookup"><span data-stu-id="9a8c6-181">This property can be set to one of four possible values:</span></span>

1. <span data-ttu-id="9a8c6-182">**未初始化**。</span><span class="sxs-lookup"><span data-stu-id="9a8c6-182">**Uninitialized**.</span></span> <span data-ttu-id="9a8c6-183">指示将用户的 Exchange 邮箱; 配置的就地保留设置基于存档如果就地保留未然后用户将具有他/她消息和 Web 会议脚本存档中 Skype 业务服务器已启用对用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="9a8c6-183">Indicates that archiving will be based on the In-Place Hold settings configured for the user's Exchange mailbox; if In-Place Hold has not been enabled on the user's mailbox then the user will have his or her messaging and Web conferencing transcripts archived in Skype for Business Server.</span></span>

2. <span data-ttu-id="9a8c6-184">**UseLyncArchivingPolicy**。</span><span class="sxs-lookup"><span data-stu-id="9a8c6-184">**UseLyncArchivingPolicy**.</span></span> <span data-ttu-id="9a8c6-185">指示应存档用户的即时消息和 Web 会议脚本，Skype 业务服务器而不是 Exchange 中。</span><span class="sxs-lookup"><span data-stu-id="9a8c6-185">Indicates that the user's instant messaging and Web conferencing transcripts should be archived in Skype for Business Server rather than in Exchange.</span></span>

3. <span data-ttu-id="9a8c6-186">**NoArchiving**。</span><span class="sxs-lookup"><span data-stu-id="9a8c6-186">**NoArchiving**.</span></span> <span data-ttu-id="9a8c6-187">指示根本不应存档用户的即时消息和 Web 会议脚本。</span><span class="sxs-lookup"><span data-stu-id="9a8c6-187">Indicates that the user's instant messaging and Web conferencing transcripts should not be archived at all.</span></span> <span data-ttu-id="9a8c6-188">请注意，此设置将覆盖的任何 Skype 业务服务器存档策略分配给用户。</span><span class="sxs-lookup"><span data-stu-id="9a8c6-188">Note that this setting overrides any Skype for Business Server archiving policies assigned to the user.</span></span>

4. <span data-ttu-id="9a8c6-189">**ArchivingToExchange**。</span><span class="sxs-lookup"><span data-stu-id="9a8c6-189">**ArchivingToExchange**.</span></span> <span data-ttu-id="9a8c6-190">指示用户的即时消息和 Web 会议脚本应无论就地保留设置存档到 Exchange （或不具有） 已分配给用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="9a8c6-190">Indicates that the user's instant messaging and Web conferencing transcripts should be archived to Exchange regardless of the In-Place Hold settings that have (or have not) been assigned to the user's mailbox.</span></span>

<span data-ttu-id="9a8c6-191">例如，配置的用户帐户，使即时消息和 Web 会议脚本总是存档到 Exchange 可以为业务 Server 命令行管理程序使用从 Skype 类似于以下命令：</span><span class="sxs-lookup"><span data-stu-id="9a8c6-191">For example, to configure a user account so that instant messaging and Web conferencing transcripts are always archived to Exchange you can use a command similar to this from the Skype for Business Server Management Shell:</span></span>

```
Set-CsUser -Identity "Ken Myer" -ExchangeArchivingPolicy ArchivingToExchange
```

<span data-ttu-id="9a8c6-192">如果要为一组用户（例如驻留在指定注册器池中的所有用户）设置同一存档策略，可以使用如下命令：</span><span class="sxs-lookup"><span data-stu-id="9a8c6-192">If you want to set the same archiving policy for a group of users (for example, all the users homed on a specified Registrar pool) you can use a command similar to this:</span></span>

```
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Set-CsUser -ExchangeArchivingPolicy ArchivingToExchange
```

<span data-ttu-id="9a8c6-193">请注意，您必须使用 Skype 业务 Server Management Shell （和 Windows PowerShell），才能配置 ExchangeArchivingPolicy 属性的值。</span><span class="sxs-lookup"><span data-stu-id="9a8c6-193">Note that you must use the Skype for Business Server Management Shell (and Windows PowerShell) in order to configure value of the ExchangeArchivingPolicy property.</span></span> <span data-ttu-id="9a8c6-194">此属性不向管理员 Skype 公开业务服务器。</span><span class="sxs-lookup"><span data-stu-id="9a8c6-194">This property is not exposed to administrators in the Skype for Business Server.</span></span>

<span data-ttu-id="9a8c6-195">如果您要查看已向其分配了特定存档策略的所有用户的列表，则可以使用如下命令，此命令返回已将 ExchangeArchivingPolicy 属性设置为“未初始化”的所有用户的 Active Directory 显示名称：</span><span class="sxs-lookup"><span data-stu-id="9a8c6-195">If you would like to view a list of all the users who have been assigned a specific archiving policy then you can use a command similar to the following, which returns the Active Directory display name of all the users who have had the ExchangeArchivingPolicy property set to Uninitialized:</span></span>

```
Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -eq "Uninitialized"} | Select-Object DisplayName
```

<span data-ttu-id="9a8c6-196">同样，此命令也返回尚未将 ExchangeArchivingPolicy 属性设置为 UseLyncArchivingPolicy 的用户的显示名称：</span><span class="sxs-lookup"><span data-stu-id="9a8c6-196">Likewise, this command returns the display name of the users who have not have the ExchangeArchivingPolicy property set to UseLyncArchivingPolicy:</span></span>

```
Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -ne "UseLyncArchivingPolicy"} | Select-Object DisplayName
```


