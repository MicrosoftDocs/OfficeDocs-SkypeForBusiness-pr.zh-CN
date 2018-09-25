---
title: Microsoft 团队中的保留策略
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: article
ms.service: msteams
ms.reviewer: anach
description: 了解如何保留策略以及如何管理这些团队中。
localization_priority: Normal
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 453e6f161b62846143493d7a444b364e27f3885e
ms.sourcegitcommit: 5e8d04bbc3eb1a57fed893e5ff929674b4297851
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/24/2018
ms.locfileid: "25004591"
---
# <a name="retention-policies-in-microsoft-teams"></a><span data-ttu-id="ecff2-103">Microsoft 团队中的保留策略</span><span class="sxs-lookup"><span data-stu-id="ecff2-103">Retention policies in Microsoft Teams</span></span>

<span data-ttu-id="ecff2-104">团队对话是永久性的且保留默认情况下不限次数。</span><span class="sxs-lookup"><span data-stu-id="ecff2-104">Teams conversations are persistent and retained forever by default.</span></span> <span data-ttu-id="ecff2-105">保留策略的引入，管理员可以在安全性和合规性中心配置保留策略 （保留和删除），团队聊天和频道邮件。</span><span class="sxs-lookup"><span data-stu-id="ecff2-105">With the introduction of retention policies, admins can configure retention policies (both preservation and deletion) in the Security & Compliance Center for Teams chat and channel messages.</span></span> <span data-ttu-id="ecff2-106">这有助于组织保留特定时间段法规遵从性 （即保留策略） 的数据，或者如果认为是责任特定的一段时间后删除的数据 （即，删除策略）。</span><span class="sxs-lookup"><span data-stu-id="ecff2-106">This helps organizations either retain data for compliance (namely, preservation policy) for a specific period or get rid of data (namely, deletion policy) if it is considered a liability after a specific period.</span></span> <span data-ttu-id="ecff2-107">团队保留策略确保删除数据时，它从删除所有团队服务上的永久数据存储位置。</span><span class="sxs-lookup"><span data-stu-id="ecff2-107">Teams retention policies ensure that when you delete data, it is removed from all permanent data storage locations on the Teams service.</span></span> 

<span data-ttu-id="ecff2-108">若要管理团队保留策略，请使用的设置和 Office 365 安全性和合规性中心下**数据调控**中的 cmdlet > **保留**。</span><span class="sxs-lookup"><span data-stu-id="ecff2-108">To manage Teams retention policies, use the settings and cmdlets in the Office 365 Security & Compliance Center under **Data Governance** > **Retention**.</span></span>

<span data-ttu-id="ecff2-109">支持团队保留策略：</span><span class="sxs-lookup"><span data-stu-id="ecff2-109">Teams retention policies do support:</span></span> 
    
- <span data-ttu-id="ecff2-110">保留： 指定的持续时间保持团队数据并不执行任何操作</span><span class="sxs-lookup"><span data-stu-id="ecff2-110">Preservation: Keep Teams data for a specified duration and then do nothing</span></span>
- <span data-ttu-id="ecff2-111">保留和然后删除： 团队数据保留在指定时间段，然后删除</span><span class="sxs-lookup"><span data-stu-id="ecff2-111">Preservation and then delete: Keep Teams data for a specified duration and then delete</span></span>
- <span data-ttu-id="ecff2-112">删除： 指定的时间后删除团队数据</span><span class="sxs-lookup"><span data-stu-id="ecff2-112">Deletion: Delete Teams data after a specified duration</span></span>

<span data-ttu-id="ecff2-113">尚不支持团队保留策略：</span><span class="sxs-lookup"><span data-stu-id="ecff2-113">Teams retention policies do not yet support:</span></span>

- <span data-ttu-id="ecff2-114">高级的保留策略不适用于团队聊天和团队通道消息位置</span><span class="sxs-lookup"><span data-stu-id="ecff2-114">Advanced retention policies don't apply to Teams chat and Teams channel message locations</span></span>
- <span data-ttu-id="ecff2-115">少于 30 天的持续时间</span><span class="sxs-lookup"><span data-stu-id="ecff2-115">Duration of fewer than 30 days</span></span>

<span data-ttu-id="ecff2-116">管理员可以设置团队专用聊天 （1:1 或一对多聊天） 和团队通道消息的独立的保留策略。</span><span class="sxs-lookup"><span data-stu-id="ecff2-116">Admins can set up separate retention policies for Teams private chats (1:1 or 1:Many chats) and Teams channel messages.</span></span> <span data-ttu-id="ecff2-117">在许多情况下，组织考虑为多个比通道消息，通常是与项目相关的更多对话责任的私人聊天数据。</span><span class="sxs-lookup"><span data-stu-id="ecff2-117">In many cases, organizations consider private chat data as more of a liability than channel messages, which are usually more project-related conversations.</span></span> <span data-ttu-id="ecff2-118">安全性和合规性中心、**数据调控**中设置这些策略 > **保留**。</span><span class="sxs-lookup"><span data-stu-id="ecff2-118">Set up these policies in the Security & Compliance Center, **Data governance** > **Retention**.</span></span> <span data-ttu-id="ecff2-119">打开**团队通道消息**和**团队聊天**，然后定义 （还如下图中所示） 这些位置的保留策略。</span><span class="sxs-lookup"><span data-stu-id="ecff2-119">Turn on **Teams channel messages** and **Teams chats** and then define retention policies for these locations (also shown in the diagram below).</span></span> 

<span data-ttu-id="ecff2-120">当您打开**团队通道消息**时，您可以指定此策略将应用于哪个团队。</span><span class="sxs-lookup"><span data-stu-id="ecff2-120">When you turn on **Teams channel messages**, you can specify Teams to which this policy will apply.</span></span> <span data-ttu-id="ecff2-121">例如，团队 X、 Y、 和 Z，管理员可以 1 年后删除策略设置 （通过单独选择这些团队），并将 3 年删除策略应用于工作组的其余部分。</span><span class="sxs-lookup"><span data-stu-id="ecff2-121">For example, for teams X, Y, and Z, the admin can set the deletion policies for 1 year (by selecting those teams individually), and apply a 3-year deletion policy to the rest of the teams.</span></span> 

<span data-ttu-id="ecff2-122">您可以通过选择特定用户并应用唯一的保留策略的**团队聊天**执行相同的操作。</span><span class="sxs-lookup"><span data-stu-id="ecff2-122">You can do the same thing for **Teams chats** by selecting specific users and applying unique retention policies.</span></span> 

![Teams 数据到 Exchange 和 SharePoint 的工作流示意图。](media/Retention-Policies.png)


> [!IMPORTANT]
> <span data-ttu-id="ecff2-124">团队通道消息位置和团队聊天位置仅地址存储在 Exchange Online 邮箱 （用户和组邮箱） 的团队对话。</span><span class="sxs-lookup"><span data-stu-id="ecff2-124">The Teams channel message locations and Teams chats locations only address the Teams conversations stored in Exchange Online mailboxes (user and group mailboxes).</span></span> <span data-ttu-id="ecff2-125">从所有相关的存储位置，即邮箱、 基底和聊天服务中删除邮件。</span><span class="sxs-lookup"><span data-stu-id="ecff2-125">The messages are deleted from all relevant storage locations, namely the mailboxes, substrate, and chat service.</span></span> 
> 
> <span data-ttu-id="ecff2-126">若要管理保留策略的工作组文件，存储在 OneDrive for Business 和 SharePoint，使用它们的保留策略。</span><span class="sxs-lookup"><span data-stu-id="ecff2-126">To manage retention policies for Teams files, which are stored in OneDrive for Business and SharePoint, use their retention policies.</span></span>

<span data-ttu-id="ecff2-127">按照设计，为团队文件删除策略配置通过 SharePoint Online 和 OneDrive 业务位置。</span><span class="sxs-lookup"><span data-stu-id="ecff2-127">By design, deletion policies for Teams files are configured through SharePoint Online and OneDrive for Business locations.</span></span> <span data-ttu-id="ecff2-128">因此，很可能策略无法删除之前删除这些消息获取团队聊天或通道邮件中引用的文件。</span><span class="sxs-lookup"><span data-stu-id="ecff2-128">As a result, it's possible that a policy could delete a file referenced in a Teams chat or channel message before those messages get deleted.</span></span> <span data-ttu-id="ecff2-129">在这种情况下，该文件将仍显示在工作组邮件中，但如果您单击该文件，将出现"找不到文件"错误 （此种可能还出现不存在的策略，如果有人手动删除文件从 SharePoint Online 或 OneDrive for Business）。</span><span class="sxs-lookup"><span data-stu-id="ecff2-129">In this case, the file will still show up in the Teams message, but if you click the file, you'll get a "File not found" error (this could also happen in the absence of a policy, if someone manually deletes a file from SharePoint Online or OneDrive for Business).</span></span>

<span data-ttu-id="ecff2-130">有关为 Office 365 配置保留策略的详细信息，请阅读[的保留策略的概述](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423)。</span><span class="sxs-lookup"><span data-stu-id="ecff2-130">For detailed information about configuring retention policies for Office 365, read [Overview of retention policies](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423).</span></span>
 
