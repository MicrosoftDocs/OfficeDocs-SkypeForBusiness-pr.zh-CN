---
title: SharePoint Online 和 OneDrive for Business 与 Microsoft Teams 如何交互
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 11/12/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: snigdhav
search.appverid: MET150
description: 了解 SharePoint Online 和 OneDrive for Business 与 Microsoft Teams 如何交互，例如，如何存储私人聊天文件，以及团队、频道和文档库之间的关系。
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9aba8bba3f2b00e00bae2a38d4b1cc7954cffe06
ms.sourcegitcommit: 3014331fff89a0842c4db0b9adf0ef32f9728ade
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2019
ms.locfileid: "30640687"
---
<a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a><span data-ttu-id="f9380-103">SharePoint Online 和 OneDrive for Business 与 Microsoft Teams 如何交互</span><span class="sxs-lookup"><span data-stu-id="f9380-103">How SharePoint Online and OneDrive for Business interact with Microsoft Teams</span></span>
=============================================================================

> [!Tip]
> <span data-ttu-id="f9380-104">观看下面的会话，若要了解与 Azure Active Directory (AAD)、 Office 365 组、 Exchange、 SharePoint 和 OneDrive for Business 团队交互的方式：[基础的 Microsoft 团队](https://aka.ms/teams-foundations)</span><span class="sxs-lookup"><span data-stu-id="f9380-104">Watch the following session to learn how Teams interacts with Azure Active Directory (AAD), Office 365 Groups, Exchange, SharePoint and OneDrive for Business: [Foundations of Microsoft Teams](https://aka.ms/teams-foundations)</span></span>

<span data-ttu-id="f9380-105">Microsoft Teams 中的每个团队在 SharePoint Online 中都有一个团队网站，团队中的每个频道在默认团队网站文档库中都有一个文件夹。</span><span class="sxs-lookup"><span data-stu-id="f9380-105">Each team in Microsoft Teams has a team site in SharePoint Online, and each channel in a team gets a folder within the default team site document library.</span></span> <span data-ttu-id="f9380-106">对话中共享的文件会自动添加到文档库中，在 SharePoint 中设置的权限和文件安全选项会自动反映在 Teams 中。</span><span class="sxs-lookup"><span data-stu-id="f9380-106">Files shared within a conversation are automatically added to the document library, and permissions and file security options set in SharePoint are automatically reflected within Teams.</span></span>

<span data-ttu-id="f9380-107">私人聊天文件存储在发送方的 OneDrive for Business 文件夹中，在文件共享过程中，系统会自动向所有参与者授予权限。</span><span class="sxs-lookup"><span data-stu-id="f9380-107">Private chat files are stored in the sender’s OneDrive for Business folder, and permissions are automatically granted to all participants as part of the file sharing process.</span></span>

<span data-ttu-id="f9380-108">如果没有为用户分配和启用 SharePoint Online 许可证，则他们在 Office 365 中没有 OneDrive for Business 存储空间。</span><span class="sxs-lookup"><span data-stu-id="f9380-108">If users aren't assigned and enabled with SharePoint Online licenses, they don't have OneDrive for Business storage in Office 365.</span></span> <span data-ttu-id="f9380-109">文件共享将继续以在通道，但用户无法共享 Office 365 中的业务存储中没有 OneDrive 聊天文件。</span><span class="sxs-lookup"><span data-stu-id="f9380-109">File sharing will continue to work in channels, but users won't be able to share files in chats without OneDrive for Business storage in Office 365.</span></span>

<span data-ttu-id="f9380-110">通过在 SharePoint Online 文档库和 OneDrive for Business 中存储文件，在租户级别配置的所有合规性规则将得到遵循。</span><span class="sxs-lookup"><span data-stu-id="f9380-110">By storing the files in the SharePoint Online document library and OneDrive for Business, all compliance rules configured at the tenant level will be followed.</span></span> 

> [!NOTE]
> <span data-ttu-id="f9380-111">与 Sharepoint 内部部署集成不支持的 Microsoft 团队这一次。</span><span class="sxs-lookup"><span data-stu-id="f9380-111">Integration with Sharepoint On-premises is not supported for Microsoft Teams at this time.</span></span>

<span data-ttu-id="f9380-112">下面是团队、频道和文档库之间的关系示例。</span><span class="sxs-lookup"><span data-stu-id="f9380-112">The following is the example of relationships between team, channel, and document library.</span></span>

<span data-ttu-id="f9380-113">对于每个团队，创建 SharePoint 网站后，会为团队创建默认文件夹**共享文档**。</span><span class="sxs-lookup"><span data-stu-id="f9380-113">For every team, a SharePoint site is created, and the **Shared Documents** folder is the default folder created for the team.</span></span> <span data-ttu-id="f9380-114">包括每个团队的默认频道“**常规**”频道在内的每个频道在“**共享文档**”下都有一个文件夹。</span><span class="sxs-lookup"><span data-stu-id="f9380-114">Each channel, including the **General** channel (the default channel for each team) has a folder in **Shared Documents**.</span></span>

![某个团队的 SharePoint Online 中的“共享文档”文件夹及其在 Microsoft Teams 中的频道示意图。](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

> [!NOTE]
> <span data-ttu-id="f9380-116">当前无法替代默认 SharePoint 站点和文档库。</span><span class="sxs-lookup"><span data-stu-id="f9380-116">It's not currently possible to replace the default SharePoint site and document library with another one.</span></span> <span data-ttu-id="f9380-117">我们已经知道你的需求，我们正在考虑。</span><span class="sxs-lookup"><span data-stu-id="f9380-117">We've heard from you that you want it, and we're considering it.</span></span> <span data-ttu-id="f9380-118">查看 [Teams 路线图](https://aka.ms/teamsroadmap)或 [Teams UserVoice](https://aka.ms/TeamsUserVoice)，以随时了解即将推出的功能。</span><span class="sxs-lookup"><span data-stu-id="f9380-118">Check the [Teams Roadmap](https://aka.ms/teamsroadmap) or [Teams UserVoice](https://aka.ms/TeamsUserVoice) to stay on top of upcoming features.</span></span>

> [!TIP]
> <span data-ttu-id="f9380-119">向团队链接到现有 SharePoint 网站页或现有的 SharePoint 文档库中添加选项卡：</span><span class="sxs-lookup"><span data-stu-id="f9380-119">To add a tab to your team that links to an existing SharePoint site page or to your existing SharePoint document library:</span></span>
> 1. <span data-ttu-id="f9380-120">选择选项卡旁边的加号。</span><span class="sxs-lookup"><span data-stu-id="f9380-120">Select the  plus sign next to the tabs.</span></span>
> 2. <span data-ttu-id="f9380-121">选择**SharePoint**的现有 SharePoint 网站页或**文档库**的现有文档库。</span><span class="sxs-lookup"><span data-stu-id="f9380-121">Select either **SharePoint** for an existing SharePoint site page or **Document Library** for an existing document library.</span></span>
> 3. <span data-ttu-id="f9380-122">选择相应的页或文档库。</span><span class="sxs-lookup"><span data-stu-id="f9380-122">Select the appropriate page or document library.</span></span>

<span data-ttu-id="f9380-123">对于每个用户，OneDrive 文件夹 **Microsoft Teams 聊天文件**用于存储私人聊天中与其他用户共享（一对一或一对多）的所有文件，且自动配置权限以限制仅目标用户可以访问这些文件。</span><span class="sxs-lookup"><span data-stu-id="f9380-123">For every user, the OneDrive folder **Microsoft Teams Chat Files** is used to store all files shared within private chats with other users (1:1 or 1:many), with permissions configured automatically to restrict access to the intended user only.</span></span>

![用于每个用户聊天的 OneDrive 文件夹（名为 Microsoft Teams Chat Files）示意图。](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

<a name="more-information"></a><span data-ttu-id="f9380-125">更多信息</span><span class="sxs-lookup"><span data-stu-id="f9380-125">More information</span></span>
----------------

<span data-ttu-id="f9380-126">有关与团队的 SharePoint 工作原理的详细信息，请参阅[SharePoint 和团队： 携手共赢](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593)。</span><span class="sxs-lookup"><span data-stu-id="f9380-126">For more information about how SharePoint works with Teams, see [SharePoint and Teams: better together](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).</span></span>


