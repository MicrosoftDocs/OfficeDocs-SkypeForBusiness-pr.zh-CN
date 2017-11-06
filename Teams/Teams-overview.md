---
title: "Microsoft Teams 概述 | Microsoft 支持"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "了解 Microsoft Teams、其基础结构以及如何配合使用 Teams 与 Office 365。"
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 10d4297f8b4cfcf3bf28a2a64177f078130166eb
ms.sourcegitcommit: 8cc7856bb7c305e0e96a4178535b1570cbfc3694
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/28/2017
---
<a name="overview-of-microsoft-teams"></a><span data-ttu-id="d2185-103">Microsoft Teams 概述</span><span class="sxs-lookup"><span data-stu-id="d2185-103">Overview of Microsoft Teams</span></span>
===========================

| | |
|---------|---------|
| <iframe src="//videoplayercdn.osi.office.net/hub/?csid=ux-cms-en-us-msoffice&uuid=ccf507a4-4ec4-4d61-9fb0-c86b5f1fc2a6&AutoPlayVideo=false&height=415&width=740" frameborder= "0" marginwidth= "0" marginheight= "0" scrolling= "no" allowfullscreen= "" style="width: 740px; height: 415px;"></iframe>   |         |


<span data-ttu-id="d2185-104">Microsoft Teams 结合了 Office 365 的完整宽度和深度，为团队合作提供了基于聊天的实际中心，让客户有机会创建更加开放、流动的数字化环境。</span><span class="sxs-lookup"><span data-stu-id="d2185-104">Microsoft Teams brings together the full breadth and depth of Office 365, to provide a true chat-based hub for teamwork and give customers the opportunity to create a more open, fluid, and digital environment.</span></span> <span data-ttu-id="d2185-105">Microsoft Teams 建立在由 Office 365 组联系在一起的现有 Microsoft 技术之上。</span><span class="sxs-lookup"><span data-stu-id="d2185-105">Microsoft Teams is built on existing Microsoft technologies woven together by Office 365 Groups.</span></span> 

<span data-ttu-id="d2185-106">Teams 属于开箱可用，它利用了 Azure Active Directory (Azure AD) 中存储的标识，并与 Office 365 中的其他服务集成在一起，可为创建的每个团队创建 SharePoint Online 网站和 Exchange Online 组邮箱。</span><span class="sxs-lookup"><span data-stu-id="d2185-106">Out of the box, Teams leverages identities stored in Azure Active Directory (Azure AD) and integrates with the other services within Office 365, to create a SharePoint online site and an Exchange Online group mailbox for each team created.</span></span>

<span data-ttu-id="d2185-107">与 Office 365 基底交互的聊天服务提供了 Teams 持久聊天功能，呈现了许多 Office 365 内置功能，例如，对 Teams 中交换的数据进行存档和电子数据展示。</span><span class="sxs-lookup"><span data-stu-id="d2185-107">The Teams persistent chat capability is provided by a chat service that interacts with the Office 365 substrate, surfacing many of the built-in Office 365 capabilities, such as archiving and eDiscovery to the data being exchanged in Teams.</span></span>

<span data-ttu-id="d2185-108">Teams 还提供通话和会议体验，这些体验建立在下一代基于云的基础结构之上，而 Skype 和 Skype for Business 也使用该基础结构。</span><span class="sxs-lookup"><span data-stu-id="d2185-108">Teams also provides a calling and meetings experience that is built on the next generation cloud-based infrastructure that is also used by Skype and Skype for Business.</span></span> <span data-ttu-id="d2185-109">这些技术投资包括用于媒体处理和信号发送的基于 Azure 的云服务、H.264 视频编解码器、SILK 和 Opus 音频编解码器、网络复原、遥测和质量诊断。</span><span class="sxs-lookup"><span data-stu-id="d2185-109">These technology investments include Azure-based cloud services for media processing and signaling, H.264 video codec, SILK and Opus audio codec, network resiliency, telemetry, and quality diagnostics.</span></span>

<span data-ttu-id="d2185-110">要扩展 Teams 功能，请使用连接器、选项卡和聊天机器人（以[应用](https://go.microsoft.com/fwlink/?linkid=854629)方式提供）以将外部信息、内容和聊天机器人交互传入 Teams。</span><span class="sxs-lookup"><span data-stu-id="d2185-110">To extend Teams capabilities, use Connectors, Tabs, and Bots - available as [Apps](https://go.microsoft.com/fwlink/?linkid=854629), to bring external information, content, and intelligent bot interactions to Teams.</span></span>

<a name="microsoft-teams-infrastructure"></a><span data-ttu-id="d2185-111">Microsoft Teams 基础结构</span><span class="sxs-lookup"><span data-stu-id="d2185-111">Microsoft Teams infrastructure</span></span>
------------------------------

<span data-ttu-id="d2185-112">Teams 建立在由 Office 365 组联系在一起的现有 Microsoft 技术之上。</span><span class="sxs-lookup"><span data-stu-id="d2185-112">Teams is built on existing Microsoft technologies, woven together by Office 365 Groups.</span></span> <span data-ttu-id="d2185-113">由 Microsoft 云提供技术支持，组织在其协作情景中利用 Teams 时，可以预见卓越性能和可靠性。</span><span class="sxs-lookup"><span data-stu-id="d2185-113">Powered by the Microsoft cloud, organizations can expect excellent performance and reliability when leveraging Teams as part of their collaboration story.</span></span>

<span data-ttu-id="d2185-114">Teams 中创建的团队立即可用，创建团队时会创建 Office 365 组、SharePoint Online 网站（附带文档库）、Exchange Online 组邮箱（将由 Teams 用于存储会议邀请等信息）。</span><span class="sxs-lookup"><span data-stu-id="d2185-114">Out of the box, a team created in Teams will create an Office 365 Group, a SharePoint Online site (complete with a document library), and an Exchange Online group mailbox, which will be used by Teams to store information such as meeting invites.</span></span> <span data-ttu-id="d2185-115">可以使用现有 Office 365 组创建团队，从而允许现有组成员身份以及 SharePoint Online 和 Exchange Online 中存储的内容转到 Teams。</span><span class="sxs-lookup"><span data-stu-id="d2185-115">A team can be created using existing Office 365 Groups, allowing existing group memberships, and contents stored in SharePoint Online and Exchange Online to be ported to Teams.</span></span>

<span data-ttu-id="d2185-116">与 Office 365 交互的聊天服务提供了 Teams 持久聊天功能，呈现了许多 Office 365 内置功能，例如，对 Teams 中交换的数据进行存档和电子数据展示。</span><span class="sxs-lookup"><span data-stu-id="d2185-116">Teams persistent chat is provided by a chat service that interacts with Office 365, surfacing many of the built-in Office 365 capabilities such as archiving and eDiscovery to the data being exchanged in Teams.</span></span>

<span data-ttu-id="d2185-117">为了补充作为持久聊天板的 Teams 功能（在此进行非正式的实时对话），Teams 还提供了建立在下一代基于云的基础结构（Skype 和 Skype for Business 也使用该基础结构）之上的会议体验。</span><span class="sxs-lookup"><span data-stu-id="d2185-117">To complement the Teams capability as a persistent chat board where informal, real-time conversations take place, Teams also provides a meeting experience built on the next generation cloud-based infrastructure that is also used by Skype and Skype for Business.</span></span> <span data-ttu-id="d2185-118">这些技术投资包括用于媒体处理和信号发送的基于 Azure 的云服务、H.264 视频编解码器、SILK 和 Opus 音频编解码器、网络复原、遥测和质量诊断。</span><span class="sxs-lookup"><span data-stu-id="d2185-118">These technology investments include Azure-based cloud services for media processing and signaling, H.264 video codec, SILK and Opus audio codec, network resiliency, telemetry, and quality diagnostics.</span></span>

<span data-ttu-id="d2185-119">Office 365 组利用 Azure Active Directory (Azure AD) 中存储的标识，因此，Teams 可以很容易地使用 Azure AD 中的所有身份验证和授权功能（例如，支持多重身份验证 (MFA)）。</span><span class="sxs-lookup"><span data-stu-id="d2185-119">Office 365 Groups leverage identities stored in Azure Active Directory (Azure AD) and as such, all authentication and authorization capabilities in Azure AD, such as support for multi-factor authentication (MFA), are readily available for use by Teams.</span></span>


<a name="microsoft-teams-and-office-365"></a><span data-ttu-id="d2185-120">Microsoft Teams 和 Office 365</span><span class="sxs-lookup"><span data-stu-id="d2185-120">Microsoft Teams and Office 365</span></span>
------------------------------

<span data-ttu-id="d2185-121">不同的组有自己的职能角色和工作方式，因此需求各不相同。</span><span class="sxs-lookup"><span data-stu-id="d2185-121">Different groups have various needs, based on their functional role and workstyle.</span></span> <span data-ttu-id="d2185-122">Office 365 适合每个组的独特工作方式，包含基于用途的集成应用，包括：</span><span class="sxs-lookup"><span data-stu-id="d2185-122">Office 365 is designed for the unique workstyle of every group and includes purpose-built, integrated applications, including:</span></span>

-   <span data-ttu-id="d2185-123">用于企业级电子邮件的 Outlook，现在具有组功能</span><span class="sxs-lookup"><span data-stu-id="d2185-123">Outlook for enterprise-grade email, now with groups functionality</span></span>

-   <span data-ttu-id="d2185-124">用于网站和门户、智能内容服务、业务流程自动化和企业搜索的 SharePoint</span><span class="sxs-lookup"><span data-stu-id="d2185-124">SharePoint for sites and portals, intelligent content services, business process automation and enterprise search</span></span>

-   <span data-ttu-id="d2185-125">用于推动公司范围的连接的 Yammer</span><span class="sxs-lookup"><span data-stu-id="d2185-125">Yammer for driving company-wide connections</span></span>

-   <span data-ttu-id="d2185-126">作为企业语音和视频的主干网的 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="d2185-126">Skype for Business as the backbone for enterprise voice and video</span></span>

-   <span data-ttu-id="d2185-127">以及现在的 Microsoft Teams，这是 Office 365 中基于聊天的新型工作区</span><span class="sxs-lookup"><span data-stu-id="d2185-127">And now, Microsoft Teams, the new chat-based workspace in Office 365</span></span>

<span data-ttu-id="d2185-128">下面是 Office 365 中每个应用的常见用例。</span><span class="sxs-lookup"><span data-stu-id="d2185-128">Here are common use cases for each application in Office 365.</span></span> <span data-ttu-id="d2185-129">有关详细的使用指导，请访问 [FastTrack 生产力库](https://go.microsoft.com/fwlink/?linkid=854630)。</span><span class="sxs-lookup"><span data-stu-id="d2185-129">For detailed usage guidance, visit the [FastTrack Productivity Library](https://go.microsoft.com/fwlink/?linkid=854630).</span></span>

![Microsoft Teams 图标。](media/Overview_of_Microsoft_Teams_image1.png)

-   <span data-ttu-id="d2185-131">由希望与同一组用户实时协作的用户和团队利用。</span><span class="sxs-lookup"><span data-stu-id="d2185-131">Leveraged by users and teams who are looking to collaborate in real-time with the same group of people.</span></span>

-   <span data-ttu-id="d2185-132">对希望快速对项目进行重复操作同时共享文件并对共享交付物进行协作的团队提供帮助。</span><span class="sxs-lookup"><span data-stu-id="d2185-132">Helps teams looking to iterate quickly on a project while sharing files and collaborating on shared deliverables.</span></span>

-   <span data-ttu-id="d2185-133">让希望将各种工具连接到其工作区（例如 Planner、Power BI、GitHub 等）的用户达到目的。</span><span class="sxs-lookup"><span data-stu-id="d2185-133">Allows Users looking to connect a wide range of tools into their workspace (such as Planner, Power BI, GitHub, etc.).</span></span>

![Microsoft Outlook 图标。](media/Overview_of_Microsoft_Teams_image2.png)

-   <span data-ttu-id="d2185-135">由更希望以熟悉的电子邮件环境和/或更加正式的结构化方式协作的用户利用。</span><span class="sxs-lookup"><span data-stu-id="d2185-135">Leveraged by users who prefer to collaborate in the familiar environment of email and/or a more formal, structured manner.</span></span>

-   <span data-ttu-id="d2185-136">提供特定的业务流程，这些业务流程要求使用电子邮件在企业边界内部和外部传输文档和信息。</span><span class="sxs-lookup"><span data-stu-id="d2185-136">Provides specific business processes that require email usage to transmit documents and information inside and outside corporate boundaries.</span></span>

-   <span data-ttu-id="d2185-137">与直接工作组或组织外部的用户沟通和联系。</span><span class="sxs-lookup"><span data-stu-id="d2185-137">Communicates and connects with users who are outside of immediate workgroups or organizations.</span></span>

![Yammer 图标。](media/Overview_of_Microsoft_Teams_image3.png)

-   <span data-ttu-id="d2185-139">用于协助连接跨组织的用户以围绕实践社区进行组织以及共享最佳做法。</span><span class="sxs-lookup"><span data-stu-id="d2185-139">Leveraged to help connect users across the organization to organize around communities of practice and share best practices.</span></span>

-   <span data-ttu-id="d2185-140">通过基于供给的开放式透明平台改进跨职能的工作流</span><span class="sxs-lookup"><span data-stu-id="d2185-140">Improves cross-functional workflows through an open and transparent feed-based platform</span></span>

-   <span data-ttu-id="d2185-141">通过领导与较广泛的员工群体之间的双向对话，加强高层-员工交流。</span><span class="sxs-lookup"><span data-stu-id="d2185-141">Fosters executive-employee engagement with two-way conversations between leadership and the wider employee base</span></span>

-   <span data-ttu-id="d2185-142">激励你的一线员工分享和接收知识和专业技能</span><span class="sxs-lookup"><span data-stu-id="d2185-142">Ignites your frontline workforce to share and receive knowledge and expertise</span></span>

![Skype for Business 图标。](media/Overview_of_Microsoft_Teams_image4.png)

-   <span data-ttu-id="d2185-144">用于在内部和外部与客户/合作伙伴实时通信与协作。</span><span class="sxs-lookup"><span data-stu-id="d2185-144">Leveraged for real-time communication and collaboration both internally and externally with customers/partners.</span></span>

-   <span data-ttu-id="d2185-145">为小型或大型团队（包括最多有 10,000 位参与者的企业员工大会）提供包含音频、视频和内容的会议。</span><span class="sxs-lookup"><span data-stu-id="d2185-145">Provides meetings with audio, video and content with small or large teams (including Town Halls with up to 10,000 participants).</span></span>

-   <span data-ttu-id="d2185-146">提供企业电话服务功能。</span><span class="sxs-lookup"><span data-stu-id="d2185-146">Offers enterprise telephony functionality.</span></span>


![Microsoft SharePoint 图标。](media/Overview_of_Microsoft_Teams_image5.png)

-   <span data-ttu-id="d2185-148">用于网站和门户（例如，公司新闻和公告、搜索和文档协作）。</span><span class="sxs-lookup"><span data-stu-id="d2185-148">Leveraged for sites and portals (e.g. company news & announcements, search, and document collaboration).</span></span>

-   <span data-ttu-id="d2185-149">通过集成 Microsoft Flow 和 PowerApps 对文档库和信息列表实施业务流程自动化。</span><span class="sxs-lookup"><span data-stu-id="d2185-149">Implements business process automation on document libraries and lists of information by integrating Microsoft Flow and PowerApps.</span></span>

-   <span data-ttu-id="d2185-150">每个 Microsoft 团队都自动预配了功能完善的 SharePoint 团队网站，用于文件存储、团队新闻、页面以及列表等。</span><span class="sxs-lookup"><span data-stu-id="d2185-150">Full-powered SharePoint team site automatically provisioned for every Microsoft Team for file storage, team news, pages, lists and more.</span></span>

-   <span data-ttu-id="d2185-151">请参阅 [SharePoint Online 和 OneDrive for Business 与 Teams 如何交互](SharePoint-OneDrive-interact.md)</span><span class="sxs-lookup"><span data-stu-id="d2185-151">See [How SharePoint Online and OneDrive for Business interact with Teams](SharePoint-OneDrive-interact.md)</span></span>

## <a name="what-happened-to-the-teams-admin-faq"></a><span data-ttu-id="d2185-152">Teams 管理员 FAQ 发生了什么情况？</span><span class="sxs-lookup"><span data-stu-id="d2185-152">What happened to the Teams admin FAQ?</span></span>

<span data-ttu-id="d2185-153">虽然我们首次发布 Teams 时 Teams 管理员 FAQ 使用起来很方便，但它很快变成了“杂物抽屉”，使得很难找到特定内容。</span><span class="sxs-lookup"><span data-stu-id="d2185-153">While the Teams Admin FAQ was handy when we first released Teams, it quickly became a "junk drawer" that made it hard to find anything specific.</span></span> <span data-ttu-id="d2185-154">因此，我们将 FAQ 拆分开，并将其有用信息合并到你现在看到的 Teams 文档中。</span><span class="sxs-lookup"><span data-stu-id="d2185-154">So we busted apart the FAQ and incorporated its valuable information into the Teams documentation that you're looking at right now.</span></span> <span data-ttu-id="d2185-155">你将在此文档的上下文中找到以前属于 FAQ 中的所有信息。</span><span class="sxs-lookup"><span data-stu-id="d2185-155">You'll find all the information that was in the FAQ in this documentation, in context.</span></span>

<span data-ttu-id="d2185-156">如果你遇到在此找不到的信息，请在下面的“**评论**”部分中告诉我们。</span><span class="sxs-lookup"><span data-stu-id="d2185-156">If you're looking for something that you can't find here, please tell us about it in the **Comments** section below.</span></span> <span data-ttu-id="d2185-157">我们会尽力在 24 小时内回复你的评论。</span><span class="sxs-lookup"><span data-stu-id="d2185-157">We try to respond to your comments within 24 hours.</span></span>

<span data-ttu-id="d2185-158">顺便提一下，我们****仍提供了针对[从 Skype for Business 到 Microsoft Teams 的旅程](FAQ-journey.md)的 FAQ。</span><span class="sxs-lookup"><span data-stu-id="d2185-158">By the way, we **do** still have an FAQ for the [Journey from Skype for Business to Microsoft Teams](FAQ-journey.md).</span></span> 