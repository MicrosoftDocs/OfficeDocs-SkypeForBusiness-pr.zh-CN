---
title: Microsoft Teams 的云视频互操作性
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: srividhc
f1.keywords:
- NOCSH
description: 将云视频互操作用作中间解决方案，以允许第三方会议室设备加入 Microsoft 团队会议。
localization_priority: Normal
ms.custom:
- seo-marvel-apr2020
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 08dbe4e3ad6f527545fbf691905ce5d70c5b7dbe
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2020
ms.locfileid: "46581813"
---
# <a name="cloud-video-interop-for-microsoft-teams"></a><span data-ttu-id="01398-103">Microsoft Teams 的云视频互操作性</span><span class="sxs-lookup"><span data-stu-id="01398-103">Cloud Video Interop for Microsoft Teams</span></span>

<span data-ttu-id="01398-104">云视频互操作 (CVI) 是 Microsoft 合格的第三方解决方案，支持第三方会议室 (telepresence) 和个人视频设备 (VTCs) 来加入 Microsoft 团队会议。</span><span class="sxs-lookup"><span data-stu-id="01398-104">Cloud Video Interop (CVI) is a Microsoft Qualified third-party solution that enables third-party meeting rooms (telepresence) and personal video devices (VTCs) to join Microsoft Teams meetings.</span></span>
 
<span data-ttu-id="01398-105">有了 Microsoft 团队，您就可以在会议中获得丰富的在线内容协作，包括音频、视频和内容共享。</span><span class="sxs-lookup"><span data-stu-id="01398-105">With Microsoft Teams, you get rich online content collaboration in meetings that include audio, video, and content sharing.</span></span> <span data-ttu-id="01398-106">通过桌面和 web 客户端，以及通过与 Microsoft 团队本身集成的许多合作伙伴设备，可以享受此操作。</span><span class="sxs-lookup"><span data-stu-id="01398-106">This can be enjoyed through the desktop and web client, as well as through many partner devices that integrate natively with Microsoft Teams.</span></span> <span data-ttu-id="01398-107">但是，许多客户已经购买了视频 teleconferencing 和个人视频通信设备，这些设备的升级成本可能会很高。</span><span class="sxs-lookup"><span data-stu-id="01398-107">However, many customers have already invested in video teleconferencing and personal video communication devices, which can be expensive to upgrade.</span></span> <span data-ttu-id="01398-108">云视频互操作提供了一个简单的解决方案，使你可以继续使用现有解决方案，直到准备好升级。</span><span class="sxs-lookup"><span data-stu-id="01398-108">Cloud Video Interop provides an easy solution, allowing you to keep using your existing solutions until you are ready to upgrade.</span></span>

<span data-ttu-id="01398-109">借助云视频互操作，Microsoft 团队可为所有参与者（在会议室或团队客户内）提供本机会议体验。</span><span class="sxs-lookup"><span data-stu-id="01398-109">With Cloud Video Interop, Microsoft Teams delivers a native meeting experience for all participants – in meeting rooms or inside of Teams clients.</span></span>

### <a name="is-cloud-video-interop-for-me"></a><span data-ttu-id="01398-110">云视频互操作是否适合我？</span><span class="sxs-lookup"><span data-stu-id="01398-110">Is Cloud Video Interop for me?</span></span>

<span data-ttu-id="01398-111">在使用团队终结点切换到完整的本地 Microsoft 团队解决方案时，云视频互操作提供了一个中间服务。</span><span class="sxs-lookup"><span data-stu-id="01398-111">Cloud Video Interop provides an intermediate service while you transition to a full native Microsoft Teams Solution, using Teams endpoints.</span></span> <span data-ttu-id="01398-112">提供的服务应该是你的迁移路径的一部分。</span><span class="sxs-lookup"><span data-stu-id="01398-112">The service provided should be part of your migration path.</span></span>

<span data-ttu-id="01398-113">云视频互操作适用于满足以下条件的客户：</span><span class="sxs-lookup"><span data-stu-id="01398-113">Cloud Video Interop is intended for customers who meet the following criteria:</span></span>

- <span data-ttu-id="01398-114">大型部署会议室设备和个人视频设备部署 (50 个以上的设备) 没有资格与 Microsoft 团队直接集成</span><span class="sxs-lookup"><span data-stu-id="01398-114">Have a large deployment of meeting room devices and personal video devices deployment (50+ devices) that are not qualified for direct integration with Microsoft Teams</span></span>
- <span data-ttu-id="01398-115">由我们的一个云视频互操作合作伙伴支持</span><span class="sxs-lookup"><span data-stu-id="01398-115">Are supported by one of our Cloud Video Interop partners</span></span>
- <span data-ttu-id="01398-116">希望在迁移到本机 Microsoft 团队解决方案的过程中保留其在当前会议室设备和个人视频设备中的投资值</span><span class="sxs-lookup"><span data-stu-id="01398-116">Want to retain the value of their investment in their current meeting room devices and personal video devices during the migration to a native Microsoft Teams solution</span></span>

<span data-ttu-id="01398-117">虽然云视频互操作提供出色的中间解决方案，但我们鼓励我们的客户查看我们的本机团队会议解决方案，例如团队房间系统。</span><span class="sxs-lookup"><span data-stu-id="01398-117">While Cloud Video Interop provides a great intermediate solution, we encourage our customers to look into our native Teams Meeting solutions, such as Teams Room Systems, for the long term.</span></span> 

### <a name="office-365-us-government-and-third-party-services"></a><span data-ttu-id="01398-118">Office 365 美国政府和第三方服务</span><span class="sxs-lookup"><span data-stu-id="01398-118">Office 365 US Government and third-party services</span></span>

<span data-ttu-id="01398-119">Office 365 提供了将第三方应用程序集成到 SharePoint Online 网站、Skype for Business、团队和 Office 应用程序中的 Microsoft 365 (应用（如 Word、Excel、PowerPoint 和 Outlook) 以及 Outlook Web App）。</span><span class="sxs-lookup"><span data-stu-id="01398-119">Office 365 provides the ability to integrate third-party applications into SharePoint Online sites, Skype for Business, Teams, Office applications included in Microsoft 365 Apps for enterprise (such as Word, Excel, PowerPoint, and Outlook), and Outlook Web App.</span></span> <span data-ttu-id="01398-120">此外，Office 365 支持与第三方服务提供商的集成。</span><span class="sxs-lookup"><span data-stu-id="01398-120">In addition, Office 365 supports integration with third-party service providers.</span></span> <span data-ttu-id="01398-121">这些第三方应用程序和服务可能涉及在 Office 365 基础结构之外的第三方系统上存储、传输和处理你的组织的客户数据，因此不受 Office 365 合规性和数据保护承诺的覆盖。</span><span class="sxs-lookup"><span data-stu-id="01398-121">These third-party applications and services might involve storing, transmitting, and processing your organization's customer data on third-party systems that are outside of the Office 365 infrastructure and therefore are not covered by the Office 365 compliance and data protection commitments.</span></span> <span data-ttu-id="01398-122">**建议你查看由第三方提供的隐私和合规声明，以便在评估你的组织的相应服务时使用。**</span><span class="sxs-lookup"><span data-stu-id="01398-122">**It is recommended that you review the privacy and compliance statements provided by the third parties when assessing the appropriate use of these services for your organization.**</span></span>



### <a name="partners-certified-for-microsoft-teams"></a><span data-ttu-id="01398-123">面向 Microsoft 团队认证的合作伙伴</span><span class="sxs-lookup"><span data-stu-id="01398-123">Partners Certified for Microsoft Teams</span></span>

<span data-ttu-id="01398-124">以下合作伙伴具有适用于 Microsoft 团队的视频互操作解决方案。</span><span class="sxs-lookup"><span data-stu-id="01398-124">The following partners have video interop solutions for Microsoft Teams.</span></span> <span data-ttu-id="01398-125">您的公司可以选择与您的企业内的这些合作伙伴的任意组合配合使用。</span><span class="sxs-lookup"><span data-stu-id="01398-125">Your company may choose to work with any combination of these partners within your enterprise.</span></span> 

|<span data-ttu-id="01398-126">配偶</span><span class="sxs-lookup"><span data-stu-id="01398-126">Partner</span></span>|<span data-ttu-id="01398-127">合作伙伴解决方案</span><span class="sxs-lookup"><span data-stu-id="01398-127">Partner solution</span></span>|
|----|---|
|![代表 Polycom RealConnect 的徽标](media/polycom.png) | <span data-ttu-id="01398-129"><a href="https://aka.ms/PolycomRealConnect" target="_blank">Polycom RealConnect 服务</a></span><span class="sxs-lookup"><span data-stu-id="01398-129"><a href="https://aka.ms/PolycomRealConnect" target="_blank">Polycom RealConnect Service</a></span></span> |
|![表示 Pexip 无穷大的徽标](media/pexip.png)| <span data-ttu-id="01398-131"><a href="https://aka.ms/PexipInfinity" target="_blank">Microsoft 团队的 Pexip 无穷大</a></span><span class="sxs-lookup"><span data-stu-id="01398-131"><a href="https://aka.ms/PexipInfinity" target="_blank">Pexip Infinity for Microsoft Teams</a></span></span> | 
|![表示 BlueJeans 网关的徽标](media/bluejeans.png)| <span data-ttu-id="01398-133"><a href="https://aka.ms/BluejeansGateway" target="_blank">Microsoft 团队的 BlueJeans 网关</a></span><span class="sxs-lookup"><span data-stu-id="01398-133"><a href="https://aka.ms/BluejeansGateway" target="_blank">BlueJeans Gateway for Microsoft Teams</a></span></span> |

### <a name="cloud-video-interop-overview"></a><span data-ttu-id="01398-134">云视频互操作概述</span><span class="sxs-lookup"><span data-stu-id="01398-134">Cloud Video Interop overview</span></span>

<span data-ttu-id="01398-135">云视频互操作是由合作伙伴提供的第三方服务，可提供现有视频会议和个人视频设备解决方案在本地和 Microsoft 团队之间的互操作性。</span><span class="sxs-lookup"><span data-stu-id="01398-135">Cloud Video Interop is a third-party service that is offered by our partners to provide interoperability between existing video conferencing and personal video device solutions on premises, and Microsoft Teams.</span></span>

<span data-ttu-id="01398-136">合作伙伴提供的解决方案由可在内部部署完全基于云或部分/完全部署的组件组成。</span><span class="sxs-lookup"><span data-stu-id="01398-136">The solutions offered by our partners consist of components that can be deployed either fully cloud based or partially/fully on premises.</span></span> 
     
<span data-ttu-id="01398-137">下图显示了合作伙伴解决方案的高级体系结构。</span><span class="sxs-lookup"><span data-stu-id="01398-137">The following diagram shows the high-level architecture of our partner solutions.</span></span>

![描述团队云视频互操作合作伙伴解决方案的图表](media/teams-cloud-video-interop-partner-solution.png)


## <a name="deploy-cloud-video-interop"></a><span data-ttu-id="01398-139">部署云视频互操作</span><span class="sxs-lookup"><span data-stu-id="01398-139">Deploy Cloud Video Interop</span></span>

<span data-ttu-id="01398-140">部署云视频互操作解决方案时，了解你正在部署合作伙伴解决方案非常重要。</span><span class="sxs-lookup"><span data-stu-id="01398-140">When deploying a Cloud Video Interop solution, it's important to understand that you are deploying a partner solution.</span></span> <span data-ttu-id="01398-141">下图列出了部署云视频互操作应执行的常规步骤。</span><span class="sxs-lookup"><span data-stu-id="01398-141">The general steps you should take to deploy Cloud Video Interop are listed in the following diagram.</span></span>

![介绍如何在组织中部署 CVI 的图表](media/deploying-cvi.png)

### <a name="plan"></a><span data-ttu-id="01398-143">规划</span><span class="sxs-lookup"><span data-stu-id="01398-143">Plan</span></span>

<span data-ttu-id="01398-144">在计划阶段，你应确定不会替换为本机团队设备的设备，并查找可支持这些设备的云视频互操作合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="01398-144">During the plan phase, you should identify the devices that you will not replace with a native Teams device, and find a Cloud Video Interop partner that can support these devices.</span></span>  

<span data-ttu-id="01398-145">还需要了解的是，你将需要每位用户都有一个许可证，这些用户将安排你希望启用云视频互操作的设备加入的会议。</span><span class="sxs-lookup"><span data-stu-id="01398-145">It's also important to understand that you will need a license for each user who will schedule meetings in which you want a Cloud Video Interop-enabled device to join.</span></span> <span data-ttu-id="01398-146">请注意，可以从云视频互操作合作伙伴获得确切的许可要求。</span><span class="sxs-lookup"><span data-stu-id="01398-146">Note that exact licensing requirements can be obtained from the Cloud Video Interop partner.</span></span> <span data-ttu-id="01398-147">在开始部署之前，请确保此操作已清除。</span><span class="sxs-lookup"><span data-stu-id="01398-147">Ensure that this is clear before you start your deployment.</span></span>

### <a name="configure"></a><span data-ttu-id="01398-148">配置</span><span class="sxs-lookup"><span data-stu-id="01398-148">Configure</span></span>

<span data-ttu-id="01398-149">你为 CVI 部署选择的合作伙伴将向你提供完整的部署文档，该文档包含在你的组织内成功部署所需的所有步骤。</span><span class="sxs-lookup"><span data-stu-id="01398-149">The partner that you have chosen for your CVI deployment will provide you with a full deployment document that consists of all the steps needed to deploy successfully within your organization.</span></span> <span data-ttu-id="01398-150">这将包括防火墙端口和 IP 范围、你的设备的配置更改以及需要更改的其他设置。</span><span class="sxs-lookup"><span data-stu-id="01398-150">This will include firewall ports and IP ranges, configuration changes for your devices, and other settings that need to change.</span></span>

### <a name="provision"></a><span data-ttu-id="01398-151">提供</span><span class="sxs-lookup"><span data-stu-id="01398-151">Provision</span></span>  

<span data-ttu-id="01398-152">在设置阶段，你将根据合作伙伴配置指南将许可证分配给相应的用户。</span><span class="sxs-lookup"><span data-stu-id="01398-152">During the provision phase, you will assign licenses to the appropriate users according to the partner configuration guide.</span></span> <span data-ttu-id="01398-153">您还需要通过 Azure 同意流程来向您的团队环境提供合作伙伴访问权限。</span><span class="sxs-lookup"><span data-stu-id="01398-153">You will also need to go through the Azure Consent process to provide the partner access to your Teams environment.</span></span> <span data-ttu-id="01398-154">有关 Azure 同意流程的详细信息，请参阅[Microsoft 标识平台终结点中的权限和同意](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent)。</span><span class="sxs-lookup"><span data-stu-id="01398-154">See [Permissions and consent in the Microsoft identity platform endpoint](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent) for more information about the Azure consent process.</span></span>

### <a name="schedule"></a><span data-ttu-id="01398-155">安排</span><span class="sxs-lookup"><span data-stu-id="01398-155">Schedule</span></span>

<span data-ttu-id="01398-156">为用户启用云视频互操作后，使用 Outlook 或团队客户端的团队会议加载项安排的任何会议都将自动添加到团队会议中，以便与云视频互操作兼容的设备可以加入这些会议。</span><span class="sxs-lookup"><span data-stu-id="01398-156">After a user is enabled for Cloud Video Interop, any meeting scheduled using either the Teams Meeting Add-in for Outlook or the Teams Client will have the appropriate additional information automatically added into the Teams meeting so that Cloud Video Interop-compatible devices can join these meetings.</span></span>

### <a name="join"></a><span data-ttu-id="01398-157">Join</span><span class="sxs-lookup"><span data-stu-id="01398-157">Join</span></span>

<span data-ttu-id="01398-158">根据合作伙伴解决方案，有多种方法可以加入启用云视频互操作的会议。</span><span class="sxs-lookup"><span data-stu-id="01398-158">Depending on the partner solution, there are several ways to join a Cloud Video Interop-enabled meeting.</span></span> <span data-ttu-id="01398-159">确切的会议加入方案将由你的云视频互操作合作伙伴提供。</span><span class="sxs-lookup"><span data-stu-id="01398-159">Exact meeting join scenarios will be provided by your Cloud Video Interop partner.</span></span> <span data-ttu-id="01398-160">我们已在下面列出了一些示例：</span><span class="sxs-lookup"><span data-stu-id="01398-160">We've listed some examples below:</span></span>

- <span data-ttu-id="01398-161">IVR (交互式语音回复) </span><span class="sxs-lookup"><span data-stu-id="01398-161">IVR (Interactive Voice Response)</span></span> 
  - <span data-ttu-id="01398-162">您可以使用 tenantkey@domain 拨入合作伙伴的 IVR。</span><span class="sxs-lookup"><span data-stu-id="01398-162">You can dial in to the partner's IVR using the tenantkey@domain.</span></span>
  - <span data-ttu-id="01398-163">当您在合作伙伴 IVR 中时，系统将提示您输入 VTC conferenceId，然后该会将您连接到团队会议。</span><span class="sxs-lookup"><span data-stu-id="01398-163">When you are in the partner IVR, you will be prompted to enter the VTC conferenceId, which will then connect you to the Teams meeting.</span></span>
- <span data-ttu-id="01398-164">直接拨号</span><span class="sxs-lookup"><span data-stu-id="01398-164">Direct dial</span></span> 
  - <span data-ttu-id="01398-165">您可以通过直接拨号功能使用 tenantkey 的完整字符串，直接拨入团队会议，而无需使用直接拨号功能与合作伙伴的 IVR 进行交互。VTC ConferenceId@domain。</span><span class="sxs-lookup"><span data-stu-id="01398-165">You can directly dial in to the Teams meeting without interacting with the partner's IVR by using the direct dial feature, using the full string of tenantkey.VTC ConferenceId@domain.</span></span>
- <span data-ttu-id="01398-166">单点触控拨号</span><span class="sxs-lookup"><span data-stu-id="01398-166">One-touch dial</span></span> 
  - <span data-ttu-id="01398-167">如果您有一个集成的团队聊天室，则可以使用合作伙伴 (提供的一种触摸式拨号功能，而无需键入任何拨号字符串) 。</span><span class="sxs-lookup"><span data-stu-id="01398-167">If you have an integrated Teams room, you can use the one-touch dial capabilities offered by your partner (without needing to type any dial string).</span></span>

## <a name="manage-cloud-video-interop"></a><span data-ttu-id="01398-168">管理云视频互操作</span><span class="sxs-lookup"><span data-stu-id="01398-168">Manage Cloud Video Interop</span></span>

<span data-ttu-id="01398-169">部署云视频互操作后，你可以使用合作伙伴提供的解决方案管理设备。</span><span class="sxs-lookup"><span data-stu-id="01398-169">After Cloud Video Interop is deployed, you can manage the devices using the solutions provided by our partners.</span></span> <span data-ttu-id="01398-170">每个合作伙伴将为您提供一个管理界面，该界面将同时包含许可证和设备管理。</span><span class="sxs-lookup"><span data-stu-id="01398-170">Each partner will provide you with an administrative interface that will include both license and device management.</span></span> 

<span data-ttu-id="01398-171">也可以直接从合作伙伴管理界面获取报告。</span><span class="sxs-lookup"><span data-stu-id="01398-171">Reporting is also available directly from the partner administrative interface.</span></span> <span data-ttu-id="01398-172">有关报告功能的详细信息，请联系你选择的合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="01398-172">For more information on reporting capabilities, contact the partner of your choice.</span></span> 

### <a name="troubleshooting-cloud-video-interop"></a><span data-ttu-id="01398-173">云视频互操作疑难解答</span><span class="sxs-lookup"><span data-stu-id="01398-173">Troubleshooting Cloud Video Interop</span></span>

<span data-ttu-id="01398-174">云视频互操作是合作伙伴提供的服务。</span><span class="sxs-lookup"><span data-stu-id="01398-174">Cloud Video Interop is a partner-provided service.</span></span> <span data-ttu-id="01398-175">如果遇到问题，第一步是连接已安装团队客户端的设备，并将其连接到与导致问题的云视频互操作设备相同的网段。</span><span class="sxs-lookup"><span data-stu-id="01398-175">If you are experiencing issues, the first step is to connect a device that has the Teams Client installed and connect it to the same segment as the Cloud Video Interop device that is causing problems.</span></span> 

<span data-ttu-id="01398-176">如果团队在此段上正常运行，并且你还遵守了合作伙伴提供的所有网络和配置指南，则需要联系合作伙伴以进行进一步的故障排除。</span><span class="sxs-lookup"><span data-stu-id="01398-176">If Teams functions correctly on this segment, and you have also followed all the networking and configuration guidelines the partner has provided, you will need to contact the partner for further troubleshooting.</span></span> 

## <a name="powershell-for-cloud-video-interop"></a><span data-ttu-id="01398-177">云视频互操作的 PowerShell</span><span class="sxs-lookup"><span data-stu-id="01398-177">PowerShell for Cloud Video Interop</span></span>

<span data-ttu-id="01398-178">你可以使用以下 PowerShell cmdlet (部分) 自动执行云视频互操作部署。</span><span class="sxs-lookup"><span data-stu-id="01398-178">The following PowerShell cmdlets are available for you to (partially) automate the Cloud Video Interop deployment.</span></span>

- <span data-ttu-id="01398-179">**CsTeamsVideoInteropServicepolicy**： Microsoft 为每个受支持的合作伙伴提供预构建的策略，以便你可以指定哪个合作伙伴 (s) 用于云视频互操作。</span><span class="sxs-lookup"><span data-stu-id="01398-179">**Get-CsTeamsVideoInteropServicepolicy**: Microsoft provides pre-constructed policies for each of our supported partners that allow you to designate which partner(s) to use for Cloud Video Interop.</span></span><br><span data-ttu-id="01398-180">此 cmdlet 允许你标识可在你的组织中使用的预构建的策略。</span><span class="sxs-lookup"><span data-stu-id="01398-180">This cmdlet allows you to identify the pre-constructed policies that you can use in your organization.</span></span> <span data-ttu-id="01398-181">你可以利用 CsTeamsVideoInteropServicePolicy cmdlet 将此策略分配给一个或多个用户。</span><span class="sxs-lookup"><span data-stu-id="01398-181">You can assign this policy to one or more of your users by leveraging the Grant-CsTeamsVideoInteropServicePolicy cmdlet.</span></span>
- <span data-ttu-id="01398-182">**Grant-CsTeamsVideoInteropServicePolicy**：此 cmdlet 允许你分配用于组织的预构建策略或将策略分配给特定用户。</span><span class="sxs-lookup"><span data-stu-id="01398-182">**Grant-CsTeamsVideoInteropServicePolicy**: This cmdlet allows you to assign a pre-constructed policy for use in your organization or assign the policy to specific users.</span></span>
- <span data-ttu-id="01398-183">**CsVideoInteropServiceProvider**：使用此 cmdlet 指定有关你的组织希望使用的受支持的 CVI 合作伙伴的信息。</span><span class="sxs-lookup"><span data-stu-id="01398-183">**New-CsVideoInteropServiceProvider**: Use this cmdlet to specify information about a supported CVI partner that your organization would like to use.</span></span>
- <span data-ttu-id="01398-184">**Set-CsVideoInteropServiceProvider**：使用此 cmdlet 更新有关你的组织使用的受支持的 CVI 合作伙伴的信息。</span><span class="sxs-lookup"><span data-stu-id="01398-184">**Set-CsVideoInteropServiceProvider**: Use this cmdlet to update information about a supported CVI partner that your organization uses.</span></span>
- <span data-ttu-id="01398-185">**CsVideoInteropServiceProvider**：使用此 cmdlet 获取已配置为在组织内使用的所有提供商。</span><span class="sxs-lookup"><span data-stu-id="01398-185">**Get-CsVideoInteropServiceProvider**: Use this cmdlet to get all of the providers that have been configured for use within the organization.</span></span>
- <span data-ttu-id="01398-186">**Remove-CsVideoInteropServiceProvider**：使用此 cmdlet 删除有关你的组织不再使用的提供程序的所有提供程序信息。</span><span class="sxs-lookup"><span data-stu-id="01398-186">**Remove-CsVideoInteropServiceProvider**: Use this cmdlet to remove all provider information about a provider that your organization no longer uses.</span></span>
