---
title: Microsoft Teams 的云视频互操作性
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: naforer
f1.keywords:
- NOCSH
description: 使用云视频互操作作为中间解决方案，允许第三方会议室设备加入 Microsoft Teams 会议。
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
ms.custom:
- seo-marvel-apr2020
- seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3a8d657e2cbc12695453e26ef0e4bf9ad55070bf
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122356"
---
# <a name="cloud-video-interop-for-microsoft-teams"></a><span data-ttu-id="edf2d-103">Microsoft Teams 的云视频互操作性</span><span class="sxs-lookup"><span data-stu-id="edf2d-103">Cloud Video Interop for Microsoft Teams</span></span>

<span data-ttu-id="edf2d-104">云视频互操作 (CVI) 是 Microsoft 符合条件的第三方解决方案，可让第三方会议室 (网真) 和个人视频设备 (VTC) 加入 Microsoft Teams 会议。</span><span class="sxs-lookup"><span data-stu-id="edf2d-104">Cloud Video Interop (CVI) is a Microsoft Qualified third-party solution that enables third-party meeting rooms (telepresence) and personal video devices (VTCs) to join Microsoft Teams meetings.</span></span>
 
<span data-ttu-id="edf2d-105">借助 Microsoft Teams，您可以在会议（包括音频、视频和内容共享）中实现丰富的联机内容协作。</span><span class="sxs-lookup"><span data-stu-id="edf2d-105">With Microsoft Teams, you get rich online content collaboration in meetings that include audio, video, and content sharing.</span></span> <span data-ttu-id="edf2d-106">这可以通过桌面和 Web 客户端以及与 Microsoft Teams 本机集成的许多合作伙伴设备来享受。</span><span class="sxs-lookup"><span data-stu-id="edf2d-106">This can be enjoyed through the desktop and web client, as well as through many partner devices that integrate natively with Microsoft Teams.</span></span> <span data-ttu-id="edf2d-107">但是，许多客户已经投资了视频电话会议和个人视频通信设备，升级成本可能很高。</span><span class="sxs-lookup"><span data-stu-id="edf2d-107">However, many customers have already invested in video teleconferencing and personal video communication devices, which can be expensive to upgrade.</span></span> <span data-ttu-id="edf2d-108">云视频互操作提供了一个简单的解决方案，让你能够一直使用现有解决方案，直到准备好升级。</span><span class="sxs-lookup"><span data-stu-id="edf2d-108">Cloud Video Interop provides an easy solution, allowing you to keep using your existing solutions until you are ready to upgrade.</span></span>

<span data-ttu-id="edf2d-109">借助云视频互操作，Microsoft Teams 为会议室内或 Teams 客户端内的所有参与者提供本机会议体验。</span><span class="sxs-lookup"><span data-stu-id="edf2d-109">With Cloud Video Interop, Microsoft Teams delivers a native meeting experience for all participants – in meeting rooms or inside of Teams clients.</span></span>

### <a name="is-cloud-video-interop-for-me"></a><span data-ttu-id="edf2d-110">云视频互操作是否适合我？</span><span class="sxs-lookup"><span data-stu-id="edf2d-110">Is Cloud Video Interop for me?</span></span>

<span data-ttu-id="edf2d-111">云视频互操作提供中间服务，同时使用 Teams 终结点过渡到完整的本机 Microsoft Teams 解决方案。</span><span class="sxs-lookup"><span data-stu-id="edf2d-111">Cloud Video Interop provides an intermediate service while you transition to a full native Microsoft Teams Solution, using Teams endpoints.</span></span> <span data-ttu-id="edf2d-112">提供的服务应该是迁移路径的一部分。</span><span class="sxs-lookup"><span data-stu-id="edf2d-112">The service provided should be part of your migration path.</span></span>

<span data-ttu-id="edf2d-113">云视频互操作适用于符合以下条件的客户：</span><span class="sxs-lookup"><span data-stu-id="edf2d-113">Cloud Video Interop is intended for customers who meet the following criteria:</span></span>

- <span data-ttu-id="edf2d-114">在超过 50 (个没有资格与 Microsoft Teams 直接集成的) 设备上部署大量会议室设备和个人视频设备</span><span class="sxs-lookup"><span data-stu-id="edf2d-114">Have a large deployment of meeting room devices and personal video devices deployment (50+ devices) that are not qualified for direct integration with Microsoft Teams</span></span>
- <span data-ttu-id="edf2d-115">我们的一个云视频互操作合作伙伴支持</span><span class="sxs-lookup"><span data-stu-id="edf2d-115">Are supported by one of our Cloud Video Interop partners</span></span>
- <span data-ttu-id="edf2d-116">想要在迁移到本机 Microsoft Teams 解决方案期间保留其当前会议室设备和个人视频设备投资的价值</span><span class="sxs-lookup"><span data-stu-id="edf2d-116">Want to retain the value of their investment in their current meeting room devices and personal video devices during the migration to a native Microsoft Teams solution</span></span>

<span data-ttu-id="edf2d-117">尽管云视频互操作提供了很好的中间解决方案，但我们鼓励客户长期查看本机 Teams 会议解决方案，例如 Teams 会议室系统。</span><span class="sxs-lookup"><span data-stu-id="edf2d-117">While Cloud Video Interop provides a great intermediate solution, we encourage our customers to look into our native Teams Meeting solutions, such as Teams Room Systems, for the long term.</span></span> 

### <a name="office-365-us-government-and-third-party-services"></a><span data-ttu-id="edf2d-118">Office 365 美国政府版和第三方服务</span><span class="sxs-lookup"><span data-stu-id="edf2d-118">Office 365 US Government and third-party services</span></span>

<span data-ttu-id="edf2d-119">Office 365 提供将第三方应用程序集成到 SharePoint Online 网站、Skype for Business、Teams、Microsoft 365 企业版应用中包含的 Office 应用程序 (例如 Word、Excel、PowerPoint 和 Outlook) 和 Outlook Web App。</span><span class="sxs-lookup"><span data-stu-id="edf2d-119">Office 365 provides the ability to integrate third-party applications into SharePoint Online sites, Skype for Business, Teams, Office applications included in Microsoft 365 Apps for enterprise (such as Word, Excel, PowerPoint, and Outlook), and Outlook Web App.</span></span> <span data-ttu-id="edf2d-120">此外，Office 365 支持与第三方服务提供商集成。</span><span class="sxs-lookup"><span data-stu-id="edf2d-120">In addition, Office 365 supports integration with third-party service providers.</span></span> <span data-ttu-id="edf2d-121">这些第三方应用程序和服务可能涉及在 Office 365 基础结构外部的第三方系统上存储、传输和处理组织的客户数据，因此未包括在 Office 365 合规性和数据保护承诺中。</span><span class="sxs-lookup"><span data-stu-id="edf2d-121">These third-party applications and services might involve storing, transmitting, and processing your organization's customer data on third-party systems that are outside of the Office 365 infrastructure and therefore are not covered by the Office 365 compliance and data protection commitments.</span></span> <span data-ttu-id="edf2d-122">**建议在评估针对组织的这些服务的适当使用时，查看第三方提供的隐私和合规性声明。**</span><span class="sxs-lookup"><span data-stu-id="edf2d-122">**It is recommended that you review the privacy and compliance statements provided by the third parties when assessing the appropriate use of these services for your organization.**</span></span>



### <a name="partners-certified-for-microsoft-teams"></a><span data-ttu-id="edf2d-123">Microsoft Teams 认证的合作伙伴</span><span class="sxs-lookup"><span data-stu-id="edf2d-123">Partners Certified for Microsoft Teams</span></span>

<span data-ttu-id="edf2d-124">以下合作伙伴为 Microsoft Teams 提供视频互操作解决方案。</span><span class="sxs-lookup"><span data-stu-id="edf2d-124">The following partners have video interop solutions for Microsoft Teams.</span></span> <span data-ttu-id="edf2d-125">公司可以选择与企业中这些合作伙伴的任意组合合作。</span><span class="sxs-lookup"><span data-stu-id="edf2d-125">Your company may choose to work with any combination of these partners within your enterprise.</span></span> 

|<span data-ttu-id="edf2d-126">合作伙伴</span><span class="sxs-lookup"><span data-stu-id="edf2d-126">Partner</span></span>|<span data-ttu-id="edf2d-127">合作伙伴解决方案</span><span class="sxs-lookup"><span data-stu-id="edf2d-127">Partner solution</span></span>|
|----|---|
|![表示 Poly RealConnect 的徽标](media/polycom.png) | <span data-ttu-id="edf2d-129"><a href="https://aka.ms/PolycomRealConnect" target="_blank">Poly RealConnect 服务</a></span><span class="sxs-lookup"><span data-stu-id="edf2d-129"><a href="https://aka.ms/PolycomRealConnect" target="_blank">Poly RealConnect Service</a></span></span> |
|![表示 Pexip Infinity 的徽标](media/pexip.png)| <span data-ttu-id="edf2d-131"><a href="https://aka.ms/PexipInfinity" target="_blank">Microsoft Teams 的 Pexip 无穷大</a></span><span class="sxs-lookup"><span data-stu-id="edf2d-131"><a href="https://aka.ms/PexipInfinity" target="_blank">Pexip Infinity for Microsoft Teams</a></span></span> | 
|![表示 BlueJeans 网关的徽标](media/bluejeans.png)| <span data-ttu-id="edf2d-133"><a href="https://aka.ms/BluejeansGateway" target="_blank">Microsoft Teams 的 BlueJeans 网关</a></span><span class="sxs-lookup"><span data-stu-id="edf2d-133"><a href="https://aka.ms/BluejeansGateway" target="_blank">BlueJeans Gateway for Microsoft Teams</a></span></span> |
|![表示 Cisco CVI 的徽标](media/cisco.png)|<span data-ttu-id="edf2d-135"><a href="https://aka.ms/CiscoCVI" target="_blank">Microsoft Teams 的 Cisco Webex 视频集成</a></span><span class="sxs-lookup"><span data-stu-id="edf2d-135"><a href="https://aka.ms/CiscoCVI" target="_blank">Cisco Webex Video Integration for Microsoft Teams</a></span></span>|

### <a name="cloud-video-interop-overview"></a><span data-ttu-id="edf2d-136">云视频互操作概述</span><span class="sxs-lookup"><span data-stu-id="edf2d-136">Cloud Video Interop overview</span></span>

<span data-ttu-id="edf2d-137">云视频互操作是一项第三方服务，由我们的合作伙伴提供，用于提供本地现有视频会议和个人视频设备解决方案与 Microsoft Teams 之间的互操作性。</span><span class="sxs-lookup"><span data-stu-id="edf2d-137">Cloud Video Interop is a third-party service that is offered by our partners to provide interoperability between existing video conferencing and personal video device solutions on premises, and Microsoft Teams.</span></span>

<span data-ttu-id="edf2d-138">合作伙伴提供的解决方案包括可完全基于云或部分/完全在本地部署的组件。</span><span class="sxs-lookup"><span data-stu-id="edf2d-138">The solutions offered by our partners consist of components that can be deployed either fully cloud based or partially/fully on premises.</span></span> 
     
<span data-ttu-id="edf2d-139">下图显示了合作伙伴解决方案高级体系结构。</span><span class="sxs-lookup"><span data-stu-id="edf2d-139">The following diagram shows the high-level architecture of our partner solutions.</span></span>

![描述 Teams 云视频互操作合作伙伴解决方案的示意图](media/teams-cloud-video-interop-partner-solution.png)


## <a name="deploy-cloud-video-interop"></a><span data-ttu-id="edf2d-141">部署云视频互操作</span><span class="sxs-lookup"><span data-stu-id="edf2d-141">Deploy Cloud Video Interop</span></span>

<span data-ttu-id="edf2d-142">部署云视频互操作解决方案时，必须了解正在部署合作伙伴解决方案。</span><span class="sxs-lookup"><span data-stu-id="edf2d-142">When deploying a Cloud Video Interop solution, it's important to understand that you are deploying a partner solution.</span></span> <span data-ttu-id="edf2d-143">下图列出了部署云视频互操作时应该执行的常规步骤。</span><span class="sxs-lookup"><span data-stu-id="edf2d-143">The general steps you should take to deploy Cloud Video Interop are listed in the following diagram.</span></span>

![描述在组织中部署 CVI 的示意图](media/deploying-cvi.png)

### <a name="plan"></a><span data-ttu-id="edf2d-145">规划</span><span class="sxs-lookup"><span data-stu-id="edf2d-145">Plan</span></span>

<span data-ttu-id="edf2d-146">在计划阶段，应确定不会替换为本机 Teams 设备的设备，并找到支持这些设备的云视频互操作合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="edf2d-146">During the plan phase, you should identify the devices that you will not replace with a native Teams device, and find a Cloud Video Interop partner that can support these devices.</span></span>  

<span data-ttu-id="edf2d-147">另一个必须了解的是，需要为要安排希望启用云视频互操作的设备加入会议的每个用户提供许可证。</span><span class="sxs-lookup"><span data-stu-id="edf2d-147">It's also important to understand that you will need a license for each user who will schedule meetings in which you want a Cloud Video Interop-enabled device to join.</span></span> <span data-ttu-id="edf2d-148">请注意，可以从云视频互操作合作伙伴获取确切的许可要求。</span><span class="sxs-lookup"><span data-stu-id="edf2d-148">Note that exact licensing requirements can be obtained from the Cloud Video Interop partner.</span></span> <span data-ttu-id="edf2d-149">在开始部署之前，请确保这一点清晰明了。</span><span class="sxs-lookup"><span data-stu-id="edf2d-149">Ensure that this is clear before you start your deployment.</span></span>

### <a name="configure"></a><span data-ttu-id="edf2d-150">配置</span><span class="sxs-lookup"><span data-stu-id="edf2d-150">Configure</span></span>

<span data-ttu-id="edf2d-151">为 CVI 部署选择的合作伙伴将提供完整的部署文档，其中包括在组织中成功部署所需的所有步骤。</span><span class="sxs-lookup"><span data-stu-id="edf2d-151">The partner that you have chosen for your CVI deployment will provide you with a full deployment document that consists of all the steps needed to deploy successfully within your organization.</span></span> <span data-ttu-id="edf2d-152">这包括防火墙端口和 IP 范围、设备的配置更改，以及需要更改的其他设置。</span><span class="sxs-lookup"><span data-stu-id="edf2d-152">This will include firewall ports and IP ranges, configuration changes for your devices, and other settings that need to change.</span></span>

### <a name="provision"></a><span data-ttu-id="edf2d-153">预配</span><span class="sxs-lookup"><span data-stu-id="edf2d-153">Provision</span></span>  

<span data-ttu-id="edf2d-154">在预配阶段，根据合作伙伴配置指南将许可证分配给相应的用户。</span><span class="sxs-lookup"><span data-stu-id="edf2d-154">During the provision phase, you will assign licenses to the appropriate users according to the partner configuration guide.</span></span> <span data-ttu-id="edf2d-155">还需要完成 Azure 许可过程，向合作伙伴提供对 Teams 环境的访问权限。</span><span class="sxs-lookup"><span data-stu-id="edf2d-155">You will also need to go through the Azure Consent process to provide the partner access to your Teams environment.</span></span> <span data-ttu-id="edf2d-156">有关 Azure [许可过程的信息，请参阅 Microsoft 标识平台终结点](/azure/active-directory/develop/v2-permissions-and-consent) 中的权限和许可。</span><span class="sxs-lookup"><span data-stu-id="edf2d-156">See [Permissions and consent in the Microsoft identity platform endpoint](/azure/active-directory/develop/v2-permissions-and-consent) for more information about the Azure consent process.</span></span>

### <a name="schedule"></a><span data-ttu-id="edf2d-157">计划</span><span class="sxs-lookup"><span data-stu-id="edf2d-157">Schedule</span></span>

<span data-ttu-id="edf2d-158">为用户启用云视频互操作后，使用适用于 Outlook 的 Teams 会议加载项或 Teams 客户端安排的任何会议将自动添加到 Teams 会议，以便云视频互操作兼容的设备可以加入这些会议。</span><span class="sxs-lookup"><span data-stu-id="edf2d-158">After a user is enabled for Cloud Video Interop, any meeting scheduled using either the Teams Meeting Add-in for Outlook or the Teams Client will have the appropriate additional information automatically added into the Teams meeting so that Cloud Video Interop-compatible devices can join these meetings.</span></span>

### <a name="join"></a><span data-ttu-id="edf2d-159">Join</span><span class="sxs-lookup"><span data-stu-id="edf2d-159">Join</span></span>

<span data-ttu-id="edf2d-160">根据合作伙伴解决方案，有几种方法可以加入启用了云视频互操作的会议。</span><span class="sxs-lookup"><span data-stu-id="edf2d-160">Depending on the partner solution, there are several ways to join a Cloud Video Interop-enabled meeting.</span></span> <span data-ttu-id="edf2d-161">云视频互操作合作伙伴将提供确切的会议加入方案。</span><span class="sxs-lookup"><span data-stu-id="edf2d-161">Exact meeting join scenarios will be provided by your Cloud Video Interop partner.</span></span> <span data-ttu-id="edf2d-162">下面列出了一些示例：</span><span class="sxs-lookup"><span data-stu-id="edf2d-162">We've listed some examples below:</span></span>

- <span data-ttu-id="edf2d-163">IVR (交互式语音响应) </span><span class="sxs-lookup"><span data-stu-id="edf2d-163">IVR (Interactive Voice Response)</span></span> 
  - <span data-ttu-id="edf2d-164">可以使用设备拨入合作伙伴的 IVR tenantkey@domain。</span><span class="sxs-lookup"><span data-stu-id="edf2d-164">You can dial in to the partner's IVR using the tenantkey@domain.</span></span>
  - <span data-ttu-id="edf2d-165">当你在合作伙伴 IVR 中时，系统会提示你输入 VTC conferenceId，然后它将你连接到 Teams 会议。</span><span class="sxs-lookup"><span data-stu-id="edf2d-165">When you are in the partner IVR, you will be prompted to enter the VTC conferenceId, which will then connect you to the Teams meeting.</span></span>
- <span data-ttu-id="edf2d-166">直接拨号</span><span class="sxs-lookup"><span data-stu-id="edf2d-166">Direct dial</span></span> 
  - <span data-ttu-id="edf2d-167">通过使用直接拨号功能，可以使用完整的 tenantkey 字符串直接拨入 Teams 会议，而无需与合作伙伴的 IVR 交互。VTC ConferenceId@domain。</span><span class="sxs-lookup"><span data-stu-id="edf2d-167">You can directly dial in to the Teams meeting without interacting with the partner's IVR by using the direct dial feature, using the full string of tenantkey.VTC ConferenceId@domain.</span></span>
- <span data-ttu-id="edf2d-168">一键式拨号</span><span class="sxs-lookup"><span data-stu-id="edf2d-168">One-touch dial</span></span> 
  - <span data-ttu-id="edf2d-169">如果你有集成的 Teams 会议室，可以使用合作伙伴团队提供的一键式拨号功能 (无需键入任何拨号字符串) 。</span><span class="sxs-lookup"><span data-stu-id="edf2d-169">If you have an integrated Teams room, you can use the one-touch dial capabilities offered by your partner (without needing to type any dial string).</span></span>

## <a name="manage-cloud-video-interop"></a><span data-ttu-id="edf2d-170">管理云视频互操作</span><span class="sxs-lookup"><span data-stu-id="edf2d-170">Manage Cloud Video Interop</span></span>

<span data-ttu-id="edf2d-171">部署云视频互操作后，可以使用合作伙伴提供的解决方案管理设备。</span><span class="sxs-lookup"><span data-stu-id="edf2d-171">After Cloud Video Interop is deployed, you can manage the devices using the solutions provided by our partners.</span></span> <span data-ttu-id="edf2d-172">每个合作伙伴都会提供一个管理界面，其中包括许可证和设备管理。</span><span class="sxs-lookup"><span data-stu-id="edf2d-172">Each partner will provide you with an administrative interface that will include both license and device management.</span></span> 

<span data-ttu-id="edf2d-173">也可直接从合作伙伴管理界面获得报告。</span><span class="sxs-lookup"><span data-stu-id="edf2d-173">Reporting is also available directly from the partner administrative interface.</span></span> <span data-ttu-id="edf2d-174">有关报告功能的信息，请与你选择的合作伙伴联系。</span><span class="sxs-lookup"><span data-stu-id="edf2d-174">For more information on reporting capabilities, contact the partner of your choice.</span></span> 

### <a name="troubleshooting-cloud-video-interop"></a><span data-ttu-id="edf2d-175">云视频互操作故障排除</span><span class="sxs-lookup"><span data-stu-id="edf2d-175">Troubleshooting Cloud Video Interop</span></span>

<span data-ttu-id="edf2d-176">云视频互操作是合作伙伴提供的服务。</span><span class="sxs-lookup"><span data-stu-id="edf2d-176">Cloud Video Interop is a partner-provided service.</span></span> <span data-ttu-id="edf2d-177">如果遇到问题，第一步是连接安装了 Teams 客户端的设备，并连接到与导致问题的云视频互操作设备相同的段。</span><span class="sxs-lookup"><span data-stu-id="edf2d-177">If you are experiencing issues, the first step is to connect a device that has the Teams Client installed and connect it to the same segment as the Cloud Video Interop device that is causing problems.</span></span> 

<span data-ttu-id="edf2d-178">如果 Teams 在此段中正常运行，并且你已遵循合作伙伴提供的所有网络和配置指南，则需要联系合作伙伴进行进一步故障排除。</span><span class="sxs-lookup"><span data-stu-id="edf2d-178">If Teams functions correctly on this segment, and you have also followed all the networking and configuration guidelines the partner has provided, you will need to contact the partner for further troubleshooting.</span></span> 

## <a name="powershell-for-cloud-video-interop"></a><span data-ttu-id="edf2d-179">PowerShell for Cloud Video Interop</span><span class="sxs-lookup"><span data-stu-id="edf2d-179">PowerShell for Cloud Video Interop</span></span>

<span data-ttu-id="edf2d-180">可以使用以下 PowerShell cmdlet 来 (部分) 云视频互操作部署。</span><span class="sxs-lookup"><span data-stu-id="edf2d-180">The following PowerShell cmdlets are available for you to (partially) automate the Cloud Video Interop deployment.</span></span>

- <span data-ttu-id="edf2d-181">**Get-CsTeamsVideoInteropServicepolicy：Microsoft** 为每个支持的合作伙伴提供预构建的策略，允许你指定要用于云视频互操作的合作伙伴 () 。</span><span class="sxs-lookup"><span data-stu-id="edf2d-181">**Get-CsTeamsVideoInteropServicepolicy**: Microsoft provides pre-constructed policies for each of our supported partners that allow you to designate which partner(s) to use for Cloud Video Interop.</span></span><br><span data-ttu-id="edf2d-182">使用此 cmdlet 可以标识可在组织中使用的预构建策略。</span><span class="sxs-lookup"><span data-stu-id="edf2d-182">This cmdlet allows you to identify the pre-constructed policies that you can use in your organization.</span></span> <span data-ttu-id="edf2d-183">可以通过使用 Grant-CsTeamsVideoInteropServicePolicy cmdlet 将此策略分配给一个或多个用户。</span><span class="sxs-lookup"><span data-stu-id="edf2d-183">You can assign this policy to one or more of your users by leveraging the Grant-CsTeamsVideoInteropServicePolicy cmdlet.</span></span>
- <span data-ttu-id="edf2d-184">**Grant-CsTeamsVideoInteropServicePolicy：** 此 cmdlet 允许分配预构造的策略以在组织中使用，或将策略分配给特定用户。</span><span class="sxs-lookup"><span data-stu-id="edf2d-184">**Grant-CsTeamsVideoInteropServicePolicy**: This cmdlet allows you to assign a pre-constructed policy for use in your organization or assign the policy to specific users.</span></span>
- <span data-ttu-id="edf2d-185">**New-CsVideoInteropServiceProvider：** 使用此 cmdlet 指定有关组织希望使用的受支持 CVI 合作伙伴的信息。</span><span class="sxs-lookup"><span data-stu-id="edf2d-185">**New-CsVideoInteropServiceProvider**: Use this cmdlet to specify information about a supported CVI partner that your organization would like to use.</span></span>
- <span data-ttu-id="edf2d-186">**Set-CsVideoInteropServiceProvider：** 使用此 cmdlet 更新有关组织使用的受支持 CVI 合作伙伴的信息。</span><span class="sxs-lookup"><span data-stu-id="edf2d-186">**Set-CsVideoInteropServiceProvider**: Use this cmdlet to update information about a supported CVI partner that your organization uses.</span></span>
- <span data-ttu-id="edf2d-187">**Get-CsVideoInteropServiceProvider：** 使用此 cmdlet 获取已配置为在组织中使用的所有提供程序。</span><span class="sxs-lookup"><span data-stu-id="edf2d-187">**Get-CsVideoInteropServiceProvider**: Use this cmdlet to get all of the providers that have been configured for use within the organization.</span></span>
- <span data-ttu-id="edf2d-188">**Remove-CsVideoInteropServiceProvider：** 使用此 cmdlet 删除有关组织不再使用的提供程序的所有提供程序信息。</span><span class="sxs-lookup"><span data-stu-id="edf2d-188">**Remove-CsVideoInteropServiceProvider**: Use this cmdlet to remove all provider information about a provider that your organization no longer uses.</span></span>