---
title: Microsoft Teams 概述
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: ninadara
description: 了解 Microsoft Teams、其基础结构以及如何配合使用 Teams 与 Office 365。
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: cbbd2cad0b84ccdcc887d5bcdf272c1556c9c546
ms.sourcegitcommit: 39228142658557890b2173c41db9661eb502b946
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
<a name="overview-of-microsoft-teams"></a><span data-ttu-id="0308a-103">Microsoft Teams 概述</span><span class="sxs-lookup"><span data-stu-id="0308a-103">Overview of Microsoft Teams</span></span>
===========================

> [!VIDEO https://videoplayercdn.osi.office.net/hub/?csid=ux-cms-en-us-msoffice&uuid=ccf507a4-4ec4-4d61-9fb0-c86b5f1fc2a6&AutoPlayVideo=false] 


<span data-ttu-id="0308a-104">Microsoft Teams 结合了 Office 365 的完整宽度和深度，为团队合作提供了基于聊天的实际中心，让客户有机会创建更加开放、流动的数字化环境。</span><span class="sxs-lookup"><span data-stu-id="0308a-104">Microsoft Teams brings together the full breadth and depth of Office 365, to provide a true chat-based hub for teamwork and give customers the opportunity to create a more open, fluid, and digital environment.</span></span> <span data-ttu-id="0308a-105">Microsoft Teams 建立在由 Office 365 组联系在一起的现有 Microsoft 技术之上。</span><span class="sxs-lookup"><span data-stu-id="0308a-105">Microsoft Teams is built on existing Microsoft technologies woven together by Office 365 Groups.</span></span> 

<span data-ttu-id="0308a-106">Teams 属于开箱可用，它利用了 Azure Active Directory (Azure AD) 中存储的标识，并与 Office 365 中的其他服务集成在一起，可为创建的每个团队创建 SharePoint Online 网站和 Exchange Online 组邮箱。</span><span class="sxs-lookup"><span data-stu-id="0308a-106">Out of the box, Teams leverages identities stored in Azure Active Directory (Azure AD) and integrates with the other services within Office 365, to create a SharePoint online site and an Exchange Online group mailbox for each team created.</span></span>

<span data-ttu-id="0308a-107">具有业务或使用者的电子邮件帐户，如 Outlook、 Gmail，或其他人，任何人都可以参与以访客身份在团队中。</span><span class="sxs-lookup"><span data-stu-id="0308a-107">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams.</span></span> <span data-ttu-id="0308a-108">相同的法规遵从性和审核保护 Office 365 的其余部分被覆盖在团队中的所有客人，客人可以在 Azure 广告内安全地管理。</span><span class="sxs-lookup"><span data-stu-id="0308a-108">All guests in Teams are covered by the same compliance and auditing protection as the rest of Office 365, and guests can be managed securely within Azure AD.</span></span> <span data-ttu-id="0308a-109">管理员可以集中管理客人在其 Office 365 提供环境中的参与方式和方便地查看、 添加或撤销对主机租户的来宾访问权限。</span><span class="sxs-lookup"><span data-stu-id="0308a-109">Admins can centrally manage how guests participate within their Office 365 environment and easily view, add, or revoke a guest’s access to the host tenant.</span></span>

<span data-ttu-id="0308a-110">Teams 提供持久聊天功能、通话和会议、快速访问 Office 365 其他组件的功能以及强大的扩展功能。</span><span class="sxs-lookup"><span data-stu-id="0308a-110">Teams provides a persistent chat capability, calling and meetings, easy access to other components of Office 365 as well as a robust extensibility story.</span></span>  <span data-ttu-id="0308a-111">它提供了一个适用于大型公司、小型组织及其所有成员的团队合作中心。</span><span class="sxs-lookup"><span data-stu-id="0308a-111">This provides a hub for teamwork that is appropriate for enterprise companies, small organizations and everyone in between.</span></span>  

<span data-ttu-id="0308a-112">要扩展 Teams 功能，请使用连接器、选项卡和聊天机器人（以[应用](https://go.microsoft.com/fwlink/?linkid=854629)方式提供）以将外部信息、内容和聊天机器人交互传入 Teams。</span><span class="sxs-lookup"><span data-stu-id="0308a-112">To extend Teams capabilities, use Connectors, Tabs, and Bots - available as [Apps](https://go.microsoft.com/fwlink/?linkid=854629), to bring external information, content, and intelligent bot interactions to Teams.</span></span>  

<a name="microsoft-teams-infrastructure"></a><span data-ttu-id="0308a-113">Microsoft Teams 基础结构</span><span class="sxs-lookup"><span data-stu-id="0308a-113">Microsoft Teams infrastructure</span></span>
------------------------------

<span data-ttu-id="0308a-114">Teams 建立在由 Office 365 组联系在一起的现有 Microsoft 技术之上。</span><span class="sxs-lookup"><span data-stu-id="0308a-114">Teams is built on existing Microsoft technologies, woven together by Office 365 Groups.</span></span> <span data-ttu-id="0308a-115">由 Microsoft 云提供技术支持，组织在其协作情景中利用 Teams 时，可以预见卓越性能和可靠性。</span><span class="sxs-lookup"><span data-stu-id="0308a-115">Powered by the Microsoft cloud, organizations can expect excellent performance and reliability when leveraging Teams as part of their collaboration story.</span></span>

<span data-ttu-id="0308a-116">Teams 中创建的团队立即可用，创建团队时会创建 Office 365 组、SharePoint Online 网站（附带文档库）、Exchange Online 组邮箱（将由 Teams 用于存储会议邀请等信息）。</span><span class="sxs-lookup"><span data-stu-id="0308a-116">Out of the box, a team created in Teams will create an Office 365 Group, a SharePoint Online site (complete with a document library), and an Exchange Online group mailbox, which will be used by Teams to store information such as meeting invites.</span></span> <span data-ttu-id="0308a-117">可以使用现有 Office 365 组创建团队，从而允许现有组成员身份以及 SharePoint Online 和 Exchange Online 中存储的内容转到 Teams。</span><span class="sxs-lookup"><span data-stu-id="0308a-117">A team can be created using existing Office 365 Groups, allowing existing group memberships, and contents stored in SharePoint Online and Exchange Online to be ported to Teams.</span></span>

<span data-ttu-id="0308a-118">为了补充作为持久聊天板的 Teams 功能（在此进行非正式的实时对话），Teams 还提供了建立在下一代基于云的基础结构（Skype 和 Skype for Business 也使用该基础结构）之上的会议体验。</span><span class="sxs-lookup"><span data-stu-id="0308a-118">To complement the Teams capability as a persistent chat board where informal, real-time conversations take place, Teams also provides a meeting experience built on the next generation cloud-based infrastructure that is also used by Skype and Skype for Business.</span></span> <span data-ttu-id="0308a-119">这些技术投资包括用于媒体处理和信号发送的基于 Azure 的云服务、H.264 视频编解码器、SILK 和 Opus 音频编解码器、网络复原、遥测和质量诊断。</span><span class="sxs-lookup"><span data-stu-id="0308a-119">These technology investments include Azure-based cloud services for media processing and signaling, H.264 video codec, SILK and Opus audio codec, network resiliency, telemetry, and quality diagnostics.</span></span>

<span data-ttu-id="0308a-120">Office 365 组利用 Azure Active Directory (Azure AD) 中存储的标识，因此，Teams 可以很容易地使用 Azure AD 中的所有身份验证和授权功能（例如，支持多重身份验证 (MFA)）。</span><span class="sxs-lookup"><span data-stu-id="0308a-120">Office 365 Groups leverage identities stored in Azure Active Directory (Azure AD) and as such, all authentication and authorization capabilities in Azure AD, such as support for multi-factor authentication (MFA), are readily available for use by Teams.</span></span>

<span data-ttu-id="0308a-121">Teams 还提供通话和会议体验，这些体验建立在下一代基于云的基础结构之上，而 Skype 和 Skype for Business 也使用该基础结构。</span><span class="sxs-lookup"><span data-stu-id="0308a-121">Teams also provides a calling and meetings experience that is built on the next generation cloud-based infrastructure that is also used by Skype and Skype for Business.</span></span> <span data-ttu-id="0308a-122">这些技术投资包括用于媒体处理和信号发送的基于 Azure 的云服务、H.264 视频编解码器、SILK 和 Opus 音频编解码器、网络复原、遥测和质量诊断。</span><span class="sxs-lookup"><span data-stu-id="0308a-122">These technology investments include Azure-based cloud services for media processing and signaling, H.264 video codec, SILK and Opus audio codec, network resiliency, telemetry, and quality diagnostics.</span></span>

> [!NOTE]
> <span data-ttu-id="0308a-123">根据客户的反馈，导致在 Microsoft 小组创建团队生成的新 Office 365 组将不再显示在 Outlook 中，默认情况。</span><span class="sxs-lookup"><span data-stu-id="0308a-123">Based on customer feedback, new Office 365 Groups generated as a result of creating a team in Microsoft Teams will no longer show in Outlook by default.</span></span> <span data-ttu-id="0308a-124">对于想要继续使用现有的 Outlook 中显示这些组行为的客户，将可以使 Outlook 体验组提供 Exchange 联机 PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0308a-124">For customers that want to continue with the existing behavior of showing these groups in Outlook, an Exchange Online PowerShell cmdlet will be provided which can enable the group for the Outlook experience.</span></span> <span data-ttu-id="0308a-125">通过 Outlook 创建和稍后启用团队组将继续显示在 Outlook 和团队。</span><span class="sxs-lookup"><span data-stu-id="0308a-125">Groups created through Outlook and then later enabled for Teams will continue to show in both Outlook and Teams.</span></span> <span data-ttu-id="0308a-126">此更新将逐渐滚动出跨 Outlook 和团队在几个月。</span><span class="sxs-lookup"><span data-stu-id="0308a-126">This update will gradually roll out across Outlook and Teams in the coming months.</span></span>


<a name="microsoft-teams-and-office-365"></a><span data-ttu-id="0308a-127">Microsoft Teams 和 Office 365</span><span class="sxs-lookup"><span data-stu-id="0308a-127">Microsoft Teams and Office 365</span></span>
------------------------------

<span data-ttu-id="0308a-128">不同的组有自己的职能角色和工作方式，因此需求各不相同。</span><span class="sxs-lookup"><span data-stu-id="0308a-128">Different groups have various needs, based on their functional role and workstyle.</span></span> <span data-ttu-id="0308a-129">Office 365 适合每个组的独特工作方式，包含基于用途的集成应用，包括：</span><span class="sxs-lookup"><span data-stu-id="0308a-129">Office 365 is designed for the unique workstyle of every group and includes purpose-built, integrated applications, including:</span></span>

-   <span data-ttu-id="0308a-130">用于企业级电子邮件的 Outlook，现在具有组功能</span><span class="sxs-lookup"><span data-stu-id="0308a-130">Outlook for enterprise-grade email, now with groups functionality</span></span>

-   <span data-ttu-id="0308a-131">用于网站和门户、智能内容服务、业务流程自动化和企业搜索的 SharePoint</span><span class="sxs-lookup"><span data-stu-id="0308a-131">SharePoint for sites and portals, intelligent content services, business process automation and enterprise search</span></span>

-   <span data-ttu-id="0308a-132">用于推动公司范围的连接的 Yammer</span><span class="sxs-lookup"><span data-stu-id="0308a-132">Yammer for driving company-wide connections</span></span>

-   <span data-ttu-id="0308a-133">作为企业语音和视频的主干网的 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="0308a-133">Skype for Business as the backbone for enterprise voice and video</span></span>

-   <span data-ttu-id="0308a-134">以及现在的 Microsoft Teams，这是 Office 365 中基于聊天的新型工作区</span><span class="sxs-lookup"><span data-stu-id="0308a-134">And now, Microsoft Teams, the new chat-based workspace in Office 365</span></span>

<span data-ttu-id="0308a-135">下面是 Office 365 中每个应用的常见用例。</span><span class="sxs-lookup"><span data-stu-id="0308a-135">Here are common use cases for each application in Office 365.</span></span> <span data-ttu-id="0308a-136">有关详细的使用指导，请访问 [FastTrack 生产力库](https://go.microsoft.com/fwlink/?linkid=854630)。</span><span class="sxs-lookup"><span data-stu-id="0308a-136">For detailed usage guidance, visit the [FastTrack Productivity Library](https://go.microsoft.com/fwlink/?linkid=854630).</span></span>

![Microsoft Teams 图标。](media/Overview_of_Microsoft_Teams_image1.png)

-   <span data-ttu-id="0308a-138">由希望与同一组用户实时协作的用户和团队利用。</span><span class="sxs-lookup"><span data-stu-id="0308a-138">Leveraged by users and teams who are looking to collaborate in real-time with the same group of people.</span></span>

-   <span data-ttu-id="0308a-139">对希望快速对项目进行重复操作同时共享文件并对共享交付物进行协作的团队提供帮助。</span><span class="sxs-lookup"><span data-stu-id="0308a-139">Helps teams looking to iterate quickly on a project while sharing files and collaborating on shared deliverables.</span></span>

-   <span data-ttu-id="0308a-140">允许用户连接到其工作区 （如计划、 电源 BI，GitHub 等） 的各种工具。</span><span class="sxs-lookup"><span data-stu-id="0308a-140">Allows users to connect a wide range of tools into their workspace (such as Planner, Power BI, GitHub, etc.).</span></span>

![Microsoft Outlook 图标。](media/Overview_of_Microsoft_Teams_image2.png)

-   <span data-ttu-id="0308a-142">由更希望以熟悉的电子邮件环境和/或更加正式的结构化方式协作的用户利用。</span><span class="sxs-lookup"><span data-stu-id="0308a-142">Leveraged by users who prefer to collaborate in the familiar environment of email and/or a more formal, structured manner.</span></span>

-   <span data-ttu-id="0308a-143">提供特定的业务流程，这些业务流程要求使用电子邮件在企业边界内部和外部传输文档和信息。</span><span class="sxs-lookup"><span data-stu-id="0308a-143">Provides specific business processes that require email usage to transmit documents and information inside and outside corporate boundaries.</span></span>

-   <span data-ttu-id="0308a-144">与直接工作组或组织外部的用户沟通和联系。</span><span class="sxs-lookup"><span data-stu-id="0308a-144">Communicates and connects with users who are outside of immediate workgroups or organizations.</span></span>

![Yammer 图标。](media/Overview_of_Microsoft_Teams_image3.png)

-   <span data-ttu-id="0308a-146">用于协助连接跨组织的用户以围绕实践社区进行组织以及共享最佳做法。</span><span class="sxs-lookup"><span data-stu-id="0308a-146">Leveraged to help connect users across the organization to organize around communities of practice and share best practices.</span></span>

-   <span data-ttu-id="0308a-147">通过基于供给的开放式透明平台改进跨职能的工作流</span><span class="sxs-lookup"><span data-stu-id="0308a-147">Improves cross-functional workflows through an open and transparent feed-based platform</span></span>

-   <span data-ttu-id="0308a-148">通过领导与较广泛的员工群体之间的双向对话，加强高层-员工交流。</span><span class="sxs-lookup"><span data-stu-id="0308a-148">Fosters executive-employee engagement with two-way conversations between leadership and the wider employee base</span></span>

-   <span data-ttu-id="0308a-149">激励你的一线员工分享和接收知识和专业技能</span><span class="sxs-lookup"><span data-stu-id="0308a-149">Ignites your frontline workforce to share and receive knowledge and expertise</span></span>

![Skype for Business 图标。](media/Overview_of_Microsoft_Teams_image4.png)

-   <span data-ttu-id="0308a-151">用于在内部和外部与客户/合作伙伴实时通信与协作。</span><span class="sxs-lookup"><span data-stu-id="0308a-151">Leveraged for real-time communication and collaboration both internally and externally with customers/partners.</span></span>

-   <span data-ttu-id="0308a-152">为小型或大型团队（包括最多有 10,000 位参与者的企业员工大会）提供包含音频、视频和内容的会议。</span><span class="sxs-lookup"><span data-stu-id="0308a-152">Provides meetings with audio, video and content with small or large teams (including Town Halls with up to 10,000 participants).</span></span>

-   <span data-ttu-id="0308a-153">提供企业电话服务功能。</span><span class="sxs-lookup"><span data-stu-id="0308a-153">Offers enterprise telephony functionality.</span></span>


![Microsoft SharePoint 图标。](media/Overview_of_Microsoft_Teams_image5.png)

-   <span data-ttu-id="0308a-155">用于网站和门户（例如，公司新闻和公告、搜索和文档协作）。</span><span class="sxs-lookup"><span data-stu-id="0308a-155">Leveraged for sites and portals (e.g. company news & announcements, search, and document collaboration).</span></span>

-   <span data-ttu-id="0308a-156">通过集成 Microsoft Flow 和 PowerApps 对文档库和信息列表实施业务流程自动化。</span><span class="sxs-lookup"><span data-stu-id="0308a-156">Implements business process automation on document libraries and lists of information by integrating Microsoft Flow and PowerApps.</span></span>

-   <span data-ttu-id="0308a-157">每个 Microsoft 团队都自动预配了功能完善的 SharePoint 团队网站，用于文件存储、团队新闻、页面以及列表等。</span><span class="sxs-lookup"><span data-stu-id="0308a-157">Full-powered SharePoint team site automatically provisioned for every Microsoft Team for file storage, team news, pages, lists and more.</span></span>

-   <span data-ttu-id="0308a-158">请参阅 [SharePoint Online 和 OneDrive for Business 与 Teams 如何交互](SharePoint-OneDrive-interact.md)</span><span class="sxs-lookup"><span data-stu-id="0308a-158">See [How SharePoint Online and OneDrive for Business interact with Teams](SharePoint-OneDrive-interact.md)</span></span>

## <a name="teams-known-issuesknown-issuesmd"></a>[<span data-ttu-id="0308a-159">Teams 已知问题</span><span class="sxs-lookup"><span data-stu-id="0308a-159">Teams known issues</span></span>](Known-issues.md)

## <a name="teams-client-release-noteshttpssupportofficecomarticlerelease-notes-for-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de"></a>[<span data-ttu-id="0308a-160">Teams 客户端发行说明</span><span class="sxs-lookup"><span data-stu-id="0308a-160">Teams client release notes</span></span>](https://support.office.com/article/Release-notes-for-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)

## <a name="what-happened-to-the-teams-admin-faq"></a><span data-ttu-id="0308a-161">Teams 管理员 FAQ 发生了什么情况？</span><span class="sxs-lookup"><span data-stu-id="0308a-161">What happened to the Teams admin FAQ?</span></span>

<span data-ttu-id="0308a-162">虽然我们首次发布 Teams 时 Teams 管理员 FAQ 使用起来很方便，但它很快变成了“杂物抽屉”，使得很难找到特定内容。</span><span class="sxs-lookup"><span data-stu-id="0308a-162">While the Teams Admin FAQ was handy when we first released Teams, it quickly became a "junk drawer" that made it hard to find anything specific.</span></span> <span data-ttu-id="0308a-163">因此，我们将 FAQ 拆分开，并将其有用信息合并到你现在看到的 Teams 文档中。</span><span class="sxs-lookup"><span data-stu-id="0308a-163">So we busted apart the FAQ and incorporated its valuable information into the Teams documentation that you're looking at right now.</span></span> <span data-ttu-id="0308a-164">你将在此文档的上下文中找到以前属于 FAQ 中的所有信息。</span><span class="sxs-lookup"><span data-stu-id="0308a-164">You'll find all the information that was in the FAQ in this documentation, in context.</span></span>

<span data-ttu-id="0308a-165">如果您正在寻找在此处找不到的东西，请告诉我们有关它下面的**反馈**部分中。</span><span class="sxs-lookup"><span data-stu-id="0308a-165">If you're looking for something that you can't find here, please tell us about it in the **Feedback** section below.</span></span> <span data-ttu-id="0308a-166">我们尝试在 24 小时内答复您的反馈意见。</span><span class="sxs-lookup"><span data-stu-id="0308a-166">We try to respond to your feedback within 24 hours.</span></span>

<span data-ttu-id="0308a-167">顺便提一下，我们仍**提供**了针对[从 Skype for Business 到 Microsoft Teams 的旅程](FAQ-journey.md)的 FAQ。</span><span class="sxs-lookup"><span data-stu-id="0308a-167">By the way, we **do** still have an FAQ for the [Journey from Skype for Business to Microsoft Teams](FAQ-journey.md).</span></span> 
