---
title: Microsoft Teams 概述
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: ''
description: 了解 Microsoft Teams、其基础结构以及如何配合使用 Teams 与 Office 365。
localization_priority: Normal
search.appverid: MET150
ms.custom:
- NewAdminCenter_Update
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4fb74faf3acb0b3df7960ba4429c88e1383204f8
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2018
ms.locfileid: "26295202"
---
<a name="overview-of-microsoft-teams"></a><span data-ttu-id="3d08c-103">Microsoft Teams 概述</span><span class="sxs-lookup"><span data-stu-id="3d08c-103">Overview of Microsoft Teams</span></span>
===========================

> [!VIDEO https://videoplayercdn.osi.office.net/hub/?csid=ux-cms-en-us-msoffice&uuid=ccf507a4-4ec4-4d61-9fb0-c86b5f1fc2a6&AutoPlayVideo=false] 


<span data-ttu-id="3d08c-104">Microsoft Teams 结合了 Office 365 的完整宽度和深度，为团队合作提供了基于聊天的实际中心，让客户有机会创建更加开放、流动的数字化环境。</span><span class="sxs-lookup"><span data-stu-id="3d08c-104">Microsoft Teams brings together the full breadth and depth of Office 365, to provide a true chat-based hub for teamwork and give customers the opportunity to create a more open, fluid, and digital environment.</span></span> <span data-ttu-id="3d08c-105">Microsoft Teams 建立在由 Office 365 组联系在一起的现有 Microsoft 技术之上。</span><span class="sxs-lookup"><span data-stu-id="3d08c-105">Microsoft Teams is built on existing Microsoft technologies woven together by Office 365 Groups.</span></span> 

<span data-ttu-id="3d08c-106">Teams 属于开箱可用，它利用了 Azure Active Directory (Azure AD) 中存储的标识，并与 Office 365 中的其他服务集成在一起，可为创建的每个团队创建 SharePoint Online 网站和 Exchange Online 组邮箱。</span><span class="sxs-lookup"><span data-stu-id="3d08c-106">Out of the box, Teams leverages identities stored in Azure Active Directory (Azure AD) and integrates with the other services within Office 365, to create a SharePoint online site and an Exchange Online group mailbox for each team created.</span></span>

<span data-ttu-id="3d08c-107">具有业务或使用者的电子邮件帐户，如 Outlook、 Gmail，或其他任何人都可以作为来宾团队中参与。</span><span class="sxs-lookup"><span data-stu-id="3d08c-107">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams.</span></span> <span data-ttu-id="3d08c-108">团队中的所有来宾都涵盖的相同的遵从性和 Office 365 的其余部分的审核保护并来宾可以安全地管理 Azure AD 中。</span><span class="sxs-lookup"><span data-stu-id="3d08c-108">All guests in Teams are covered by the same compliance and auditing protection as the rest of Office 365, and guests can be managed securely within Azure AD.</span></span> <span data-ttu-id="3d08c-109">管理员可以集中管理来宾其 Office 365 环境中的参与如何和轻松地查看、 添加或取消对主机租户来宾访问权限。</span><span class="sxs-lookup"><span data-stu-id="3d08c-109">Admins can centrally manage how guests participate within their Office 365 environment and easily view, add, or revoke a guest’s access to the host tenant.</span></span>

<span data-ttu-id="3d08c-110">Teams 提供持久聊天功能、通话和会议、快速访问 Office 365 其他组件的功能以及强大的扩展功能。</span><span class="sxs-lookup"><span data-stu-id="3d08c-110">Teams provides a persistent chat capability, calling and meetings, easy access to other components of Office 365 as well as a robust extensibility story.</span></span>  <span data-ttu-id="3d08c-111">它提供了一个适用于大型公司、小型组织及其所有成员的团队合作中心。</span><span class="sxs-lookup"><span data-stu-id="3d08c-111">This provides a hub for teamwork that is appropriate for enterprise companies, small organizations and everyone in between.</span></span>  

<span data-ttu-id="3d08c-112">要扩展 Teams 功能，请使用连接器、选项卡和聊天机器人（以[应用](https://go.microsoft.com/fwlink/?linkid=854629)方式提供）以将外部信息、内容和聊天机器人交互传入 Teams。</span><span class="sxs-lookup"><span data-stu-id="3d08c-112">To extend Teams capabilities, use Connectors, Tabs, and Bots - available as [Apps](https://go.microsoft.com/fwlink/?linkid=854629), to bring external information, content, and intelligent bot interactions to Teams.</span></span>  

<a name="microsoft-teams-infrastructure"></a><span data-ttu-id="3d08c-113">Microsoft Teams 基础结构</span><span class="sxs-lookup"><span data-stu-id="3d08c-113">Microsoft Teams infrastructure</span></span>
------------------------------

<span data-ttu-id="3d08c-114">Teams 建立在由 Office 365 组联系在一起的现有 Microsoft 技术之上。</span><span class="sxs-lookup"><span data-stu-id="3d08c-114">Teams is built on existing Microsoft technologies, woven together by Office 365 Groups.</span></span> <span data-ttu-id="3d08c-115">由 Microsoft 云提供技术支持，组织在其协作情景中利用 Teams 时，可以预见卓越性能和可靠性。</span><span class="sxs-lookup"><span data-stu-id="3d08c-115">Powered by the Microsoft cloud, organizations can expect excellent performance and reliability when leveraging Teams as part of their collaboration story.</span></span>

<span data-ttu-id="3d08c-116">Teams 中创建的团队立即可用，创建团队时会创建 Office 365 组、SharePoint Online 网站（附带文档库）、Exchange Online 组邮箱（将由 Teams 用于存储会议邀请等信息）。</span><span class="sxs-lookup"><span data-stu-id="3d08c-116">Out of the box, a team created in Teams will create an Office 365 Group, a SharePoint Online site (complete with a document library), and an Exchange Online group mailbox, which will be used by Teams to store information such as meeting invites.</span></span> <span data-ttu-id="3d08c-117">可以使用现有 Office 365 组创建团队，从而允许现有组成员身份以及 SharePoint Online 和 Exchange Online 中存储的内容转到 Teams。</span><span class="sxs-lookup"><span data-stu-id="3d08c-117">A team can be created using existing Office 365 Groups, allowing existing group memberships, and contents stored in SharePoint Online and Exchange Online to be ported to Teams.</span></span>

<span data-ttu-id="3d08c-118">若要为多个持久聊天主板其中非正式、 实时对话进行，也团队补充团队功能提供呼叫和会议体验的下一个生成基于云的基础结构还使用 Skype 和 Skype 的构建业务。</span><span class="sxs-lookup"><span data-stu-id="3d08c-118">To complement the Teams capability as a persistent chat board where informal, real-time conversations take place, Teams also provides a calling and meeting experience built on the next generation cloud-based infrastructure that is also used by Skype and Skype for Business.</span></span> <span data-ttu-id="3d08c-119">这些技术投资包括用于媒体处理和信号发送的基于 Azure 的云服务、H.264 视频编解码器、SILK 和 Opus 音频编解码器、网络复原、遥测和质量诊断。</span><span class="sxs-lookup"><span data-stu-id="3d08c-119">These technology investments include Azure-based cloud services for media processing and signaling, H.264 video codec, SILK and Opus audio codec, network resiliency, telemetry, and quality diagnostics.</span></span>

<span data-ttu-id="3d08c-120">Office 365 组利用 Azure Active Directory (Azure AD) 中存储的标识，因此，Teams 可以很容易地使用 Azure AD 中的所有身份验证和授权功能（例如，支持多重身份验证 (MFA)）。</span><span class="sxs-lookup"><span data-stu-id="3d08c-120">Office 365 Groups leverage identities stored in Azure Active Directory (Azure AD) and as such, all authentication and authorization capabilities in Azure AD, such as support for multi-factor authentication (MFA), are readily available for use by Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="3d08c-121">根据客户反馈，由于 Microsoft 团队在创建团队生成的新 Office 365 组将不再显示在 Outlook 中默认情况下。</span><span class="sxs-lookup"><span data-stu-id="3d08c-121">Based on customer feedback, new Office 365 Groups generated as a result of creating a team in Microsoft Teams will no longer show in Outlook by default.</span></span> <span data-ttu-id="3d08c-122">对于要继续在 Outlook 中显示这些组的现有行为的客户，将其可以启用 Outlook 体验的组提供 Exchange Online PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3d08c-122">For customers that want to continue with the existing behavior of showing these groups in Outlook, an Exchange Online PowerShell cmdlet will be provided which can enable the group for the Outlook experience.</span></span> <span data-ttu-id="3d08c-123">组创建通过 Outlook 和更高版本启用团队将继续要显示在 Outlook 和团队。</span><span class="sxs-lookup"><span data-stu-id="3d08c-123">Groups created through Outlook and then later enabled for Teams will continue to show in both Outlook and Teams.</span></span> <span data-ttu-id="3d08c-124">此更新将逐步执行跨 Outlook 和团队滚月。</span><span class="sxs-lookup"><span data-stu-id="3d08c-124">This update will gradually roll out across Outlook and Teams in the coming months.</span></span>


<a name="microsoft-teams-and-office-365"></a><span data-ttu-id="3d08c-125">Microsoft Teams 和 Office 365</span><span class="sxs-lookup"><span data-stu-id="3d08c-125">Microsoft Teams and Office 365</span></span>
------------------------------

<span data-ttu-id="3d08c-126">不同的组有自己的职能角色和工作方式，因此需求各不相同。</span><span class="sxs-lookup"><span data-stu-id="3d08c-126">Different groups have various needs, based on their functional role and workstyle.</span></span> <span data-ttu-id="3d08c-127">Office 365 适合每个组的独特工作方式，包含基于用途的集成应用，包括：</span><span class="sxs-lookup"><span data-stu-id="3d08c-127">Office 365 is designed for the unique workstyle of every group and includes purpose-built, integrated applications, including:</span></span>

-   <span data-ttu-id="3d08c-128">用于企业级电子邮件的 Outlook，现在具有组功能</span><span class="sxs-lookup"><span data-stu-id="3d08c-128">Outlook for enterprise-grade email, now with groups functionality</span></span>

-   <span data-ttu-id="3d08c-129">用于网站和门户、智能内容服务、业务流程自动化和企业搜索的 SharePoint</span><span class="sxs-lookup"><span data-stu-id="3d08c-129">SharePoint for sites and portals, intelligent content services, business process automation and enterprise search</span></span>

-   <span data-ttu-id="3d08c-130">用于推动公司范围的连接的 Yammer</span><span class="sxs-lookup"><span data-stu-id="3d08c-130">Yammer for driving company-wide connections</span></span>

-   <span data-ttu-id="3d08c-131">作为企业语音和视频的主干网的 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="3d08c-131">Skype for Business as the backbone for enterprise voice and video</span></span>

-   <span data-ttu-id="3d08c-132">以及现在的 Microsoft Teams，这是 Office 365 中基于聊天的新型工作区</span><span class="sxs-lookup"><span data-stu-id="3d08c-132">And now, Microsoft Teams, the new chat-based workspace in Office 365</span></span>

<span data-ttu-id="3d08c-133">下面是 Office 365 中每个应用的常见用例。</span><span class="sxs-lookup"><span data-stu-id="3d08c-133">Here are common use cases for each application in Office 365.</span></span> <span data-ttu-id="3d08c-134">有关详细的使用指导，请访问 [FastTrack 生产力库](https://go.microsoft.com/fwlink/?linkid=854630)。</span><span class="sxs-lookup"><span data-stu-id="3d08c-134">For detailed usage guidance, visit the [FastTrack Productivity Library](https://go.microsoft.com/fwlink/?linkid=854630).</span></span>

![Microsoft Teams 图标。](media/Overview_of_Microsoft_Teams_image1.png)

-   <span data-ttu-id="3d08c-136">由希望与同一组用户实时协作的用户和团队利用。</span><span class="sxs-lookup"><span data-stu-id="3d08c-136">Leveraged by users and teams who are looking to collaborate in real-time with the same group of people.</span></span>

-   <span data-ttu-id="3d08c-137">对希望快速对项目进行重复操作同时共享文件并对共享交付物进行协作的团队提供帮助。</span><span class="sxs-lookup"><span data-stu-id="3d08c-137">Helps teams looking to iterate quickly on a project while sharing files and collaborating on shared deliverables.</span></span>

-   <span data-ttu-id="3d08c-138">允许用户连接到其工作区 （如规划器、 Power BI、 GitHub 等） 的各种工具。</span><span class="sxs-lookup"><span data-stu-id="3d08c-138">Allows users to connect a wide range of tools into their workspace (such as Planner, Power BI, GitHub, etc.).</span></span>

![Microsoft Outlook 图标。](media/Overview_of_Microsoft_Teams_image2.png)

-   <span data-ttu-id="3d08c-140">由更希望以熟悉的电子邮件环境和/或更加正式的结构化方式协作的用户利用。</span><span class="sxs-lookup"><span data-stu-id="3d08c-140">Leveraged by users who prefer to collaborate in the familiar environment of email and/or a more formal, structured manner.</span></span>

-   <span data-ttu-id="3d08c-141">提供特定的业务流程，这些业务流程要求使用电子邮件在企业边界内部和外部传输文档和信息。</span><span class="sxs-lookup"><span data-stu-id="3d08c-141">Provides specific business processes that require email usage to transmit documents and information inside and outside corporate boundaries.</span></span>

-   <span data-ttu-id="3d08c-142">与直接工作组或组织外部的用户沟通和联系。</span><span class="sxs-lookup"><span data-stu-id="3d08c-142">Communicates and connects with users who are outside of immediate workgroups or organizations.</span></span>

![Yammer 图标。](media/Overview_of_Microsoft_Teams_image3.png)

-   <span data-ttu-id="3d08c-144">用于协助连接跨组织的用户以围绕实践社区进行组织以及共享最佳做法。</span><span class="sxs-lookup"><span data-stu-id="3d08c-144">Leveraged to help connect users across the organization to organize around communities of practice and share best practices.</span></span>

-   <span data-ttu-id="3d08c-145">通过基于供给的开放式透明平台改进跨职能的工作流</span><span class="sxs-lookup"><span data-stu-id="3d08c-145">Improves cross-functional workflows through an open and transparent feed-based platform</span></span>

-   <span data-ttu-id="3d08c-146">通过领导与较广泛的员工群体之间的双向对话，加强高层-员工交流。</span><span class="sxs-lookup"><span data-stu-id="3d08c-146">Fosters executive-employee engagement with two-way conversations between leadership and the wider employee base</span></span>

-   <span data-ttu-id="3d08c-147">激励你的一线员工分享和接收知识和专业技能</span><span class="sxs-lookup"><span data-stu-id="3d08c-147">Ignites your frontline workforce to share and receive knowledge and expertise</span></span>

![Skype for Business 图标。](media/Overview_of_Microsoft_Teams_image4.png)

-   <span data-ttu-id="3d08c-149">用于在内部和外部与客户/合作伙伴实时通信与协作。</span><span class="sxs-lookup"><span data-stu-id="3d08c-149">Leveraged for real-time communication and collaboration both internally and externally with customers/partners.</span></span>

-   <span data-ttu-id="3d08c-150">为小型或大型团队（包括最多有 10,000 位参与者的企业员工大会）提供包含音频、视频和内容的会议。</span><span class="sxs-lookup"><span data-stu-id="3d08c-150">Provides meetings with audio, video and content with small or large teams (including Town Halls with up to 10,000 participants).</span></span>

-   <span data-ttu-id="3d08c-151">提供企业电话服务功能。</span><span class="sxs-lookup"><span data-stu-id="3d08c-151">Offers enterprise telephony functionality.</span></span>


![Microsoft SharePoint 图标。](media/Overview_of_Microsoft_Teams_image5.png)

-   <span data-ttu-id="3d08c-153">用于网站和门户（例如，公司新闻和公告、搜索和文档协作）。</span><span class="sxs-lookup"><span data-stu-id="3d08c-153">Leveraged for sites and portals (e.g. company news & announcements, search, and document collaboration).</span></span>

-   <span data-ttu-id="3d08c-154">通过集成 Microsoft Flow 和 PowerApps 对文档库和信息列表实施业务流程自动化。</span><span class="sxs-lookup"><span data-stu-id="3d08c-154">Implements business process automation on document libraries and lists of information by integrating Microsoft Flow and PowerApps.</span></span>

-   <span data-ttu-id="3d08c-155">每个 Microsoft 团队都自动预配了功能完善的 SharePoint 团队网站，用于文件存储、团队新闻、页面以及列表等。</span><span class="sxs-lookup"><span data-stu-id="3d08c-155">Full-powered SharePoint team site automatically provisioned for every Microsoft Team for file storage, team news, pages, lists and more.</span></span>

-   <span data-ttu-id="3d08c-156">请参阅 [SharePoint Online 和 OneDrive for Business 与 Teams 如何交互](SharePoint-OneDrive-interact.md)</span><span class="sxs-lookup"><span data-stu-id="3d08c-156">See [How SharePoint Online and OneDrive for Business interact with Teams](SharePoint-OneDrive-interact.md)</span></span>

## <a name="teams-known-issuesknown-issuesmd"></a>[<span data-ttu-id="3d08c-157">Teams 已知问题</span><span class="sxs-lookup"><span data-stu-id="3d08c-157">Teams known issues</span></span>](Known-issues.md)

## <a name="teams-client-release-noteshttpssupportofficecomarticlerelease-notes-for-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de"></a>[<span data-ttu-id="3d08c-158">Teams 客户端发行说明</span><span class="sxs-lookup"><span data-stu-id="3d08c-158">Teams client release notes</span></span>](https://support.office.com/article/Release-notes-for-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)


