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
description: 将云视频互操作用作中间解决方案，以允许第三方会议室设备加入 Microsoft 团队会议。
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
ms.custom:
- seo-marvel-apr2020
- seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: c17768f5d8c67db81f7457122632a6b205827cb5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523419"
---
# <a name="cloud-video-interop-for-microsoft-teams"></a>Microsoft Teams 的云视频互操作性

云视频互操作 (CVI) 是 Microsoft 合格的第三方解决方案，支持第三方会议室 (telepresence) 和个人视频设备 (VTCs) 来加入 Microsoft 团队会议。
 
有了 Microsoft 团队，您就可以在会议中获得丰富的在线内容协作，包括音频、视频和内容共享。 通过桌面和 web 客户端，以及通过与 Microsoft 团队本身集成的许多合作伙伴设备，可以享受此操作。 但是，许多客户已经购买了视频 teleconferencing 和个人视频通信设备，这些设备的升级成本可能会很高。 云视频互操作提供了一个简单的解决方案，使你可以继续使用现有解决方案，直到准备好升级。

借助云视频互操作，Microsoft 团队可为所有参与者（在会议室或团队客户内）提供本机会议体验。

### <a name="is-cloud-video-interop-for-me"></a>云视频互操作是否适合我？

在使用团队终结点切换到完整的本地 Microsoft 团队解决方案时，云视频互操作提供了一个中间服务。 提供的服务应该是你的迁移路径的一部分。

云视频互操作适用于满足以下条件的客户：

- 大型部署会议室设备和个人视频设备部署 (50 个以上的设备) 没有资格与 Microsoft 团队直接集成
- 由我们的一个云视频互操作合作伙伴支持
- 希望在迁移到本机 Microsoft 团队解决方案的过程中保留其在当前会议室设备和个人视频设备中的投资值

虽然云视频互操作提供出色的中间解决方案，但我们鼓励我们的客户查看我们的本机团队会议解决方案，例如团队房间系统。 

### <a name="office-365-us-government-and-third-party-services"></a>Office 365 美国政府和第三方服务

Office 365 提供了将第三方应用程序集成到 SharePoint Online 网站、Skype for Business、团队和 Office 应用程序中的 Microsoft 365 (应用（如 Word、Excel、PowerPoint 和 Outlook) 以及 Outlook Web App）。 此外，Office 365 支持与第三方服务提供商的集成。 这些第三方应用程序和服务可能涉及在 Office 365 基础结构之外的第三方系统上存储、传输和处理你的组织的客户数据，因此不受 Office 365 合规性和数据保护承诺的覆盖。 **建议你查看由第三方提供的隐私和合规声明，以便在评估你的组织的相应服务时使用。**



### <a name="partners-certified-for-microsoft-teams"></a>面向 Microsoft 团队认证的合作伙伴

以下合作伙伴具有适用于 Microsoft 团队的视频互操作解决方案。 您的公司可以选择与您的企业内的这些合作伙伴的任意组合配合使用。 

|配偶|合作伙伴解决方案|
|----|---|
|![代表 Polycom RealConnect 的徽标](media/polycom.png) | <a href="https://aka.ms/PolycomRealConnect" target="_blank">Polycom RealConnect 服务</a> |
|![表示 Pexip 无穷大的徽标](media/pexip.png)| <a href="https://aka.ms/PexipInfinity" target="_blank">Microsoft 团队的 Pexip 无穷大</a> | 
|![表示 BlueJeans 网关的徽标](media/bluejeans.png)| <a href="https://aka.ms/BluejeansGateway" target="_blank">Microsoft 团队的 BlueJeans 网关</a> |
|![表示 Cisco CVI 的徽标](media/cisco.png)|<a href="https://aka.ms/CiscoCVI" target="_blank">适用于 Microsoft 团队的 Cisco Webex 视频集成</a>|

### <a name="cloud-video-interop-overview"></a>云视频互操作概述

云视频互操作是由合作伙伴提供的第三方服务，可提供现有视频会议和个人视频设备解决方案在本地和 Microsoft 团队之间的互操作性。

合作伙伴提供的解决方案由可在内部部署完全基于云或部分/完全部署的组件组成。 
     
下图显示了合作伙伴解决方案的高级体系结构。

![描述团队云视频互操作合作伙伴解决方案的图表](media/teams-cloud-video-interop-partner-solution.png)


## <a name="deploy-cloud-video-interop"></a>部署云视频互操作

部署云视频互操作解决方案时，了解你正在部署合作伙伴解决方案非常重要。 下图列出了部署云视频互操作应执行的常规步骤。

![介绍如何在组织中部署 CVI 的图表](media/deploying-cvi.png)

### <a name="plan"></a>规划

在计划阶段，你应确定不会替换为本机团队设备的设备，并查找可支持这些设备的云视频互操作合作伙伴。  

还需要了解的是，你将需要每位用户都有一个许可证，这些用户将安排你希望启用云视频互操作的设备加入的会议。 请注意，可以从云视频互操作合作伙伴获得确切的许可要求。 在开始部署之前，请确保此操作已清除。

### <a name="configure"></a>配置

你为 CVI 部署选择的合作伙伴将向你提供完整的部署文档，该文档包含在你的组织内成功部署所需的所有步骤。 这将包括防火墙端口和 IP 范围、你的设备的配置更改以及需要更改的其他设置。

### <a name="provision"></a>提供  

在设置阶段，你将根据合作伙伴配置指南将许可证分配给相应的用户。 您还需要通过 Azure 同意流程来向您的团队环境提供合作伙伴访问权限。 有关 Azure 同意流程的详细信息，请参阅 [Microsoft 标识平台终结点中的权限和同意](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent) 。

### <a name="schedule"></a>安排

为用户启用云视频互操作后，使用 Outlook 或团队客户端的团队会议加载项安排的任何会议都将自动添加到团队会议中，以便与云视频互操作兼容的设备可以加入这些会议。

### <a name="join"></a>Join

根据合作伙伴解决方案，有多种方法可以加入启用云视频互操作的会议。 确切的会议加入方案将由你的云视频互操作合作伙伴提供。 我们已在下面列出了一些示例：

- IVR (交互式语音回复)  
  - 您可以使用 tenantkey@domain 拨入合作伙伴的 IVR。
  - 当您在合作伙伴 IVR 中时，系统将提示您输入 VTC conferenceId，然后该会将您连接到团队会议。
- 直接拨号 
  - 您可以通过直接拨号功能使用 tenantkey 的完整字符串，直接拨入团队会议，而无需使用直接拨号功能与合作伙伴的 IVR 进行交互。VTC ConferenceId@domain。
- 单点触控拨号 
  - 如果您有一个集成的团队聊天室，则可以使用合作伙伴 (提供的一种触摸式拨号功能，而无需键入任何拨号字符串) 。

## <a name="manage-cloud-video-interop"></a>管理云视频互操作

部署云视频互操作后，你可以使用合作伙伴提供的解决方案管理设备。 每个合作伙伴将为您提供一个管理界面，该界面将同时包含许可证和设备管理。 

也可以直接从合作伙伴管理界面获取报告。 有关报告功能的详细信息，请联系你选择的合作伙伴。 

### <a name="troubleshooting-cloud-video-interop"></a>云视频互操作疑难解答

云视频互操作是合作伙伴提供的服务。 如果遇到问题，第一步是连接已安装团队客户端的设备，并将其连接到与导致问题的云视频互操作设备相同的网段。 

如果团队在此段上正常运行，并且你还遵守了合作伙伴提供的所有网络和配置指南，则需要联系合作伙伴以进行进一步的故障排除。 

## <a name="powershell-for-cloud-video-interop"></a>云视频互操作的 PowerShell

你可以使用以下 PowerShell cmdlet (部分) 自动执行云视频互操作部署。

- **CsTeamsVideoInteropServicepolicy**： Microsoft 为每个受支持的合作伙伴提供预构建的策略，以便你可以指定哪个合作伙伴 (s) 用于云视频互操作。<br>此 cmdlet 允许你标识可在你的组织中使用的预构建的策略。 你可以利用 Grant-CsTeamsVideoInteropServicePolicy cmdlet 将此策略分配给一个或多个用户。
- **Grant-CsTeamsVideoInteropServicePolicy**：此 cmdlet 允许你分配用于组织的预构建策略或将策略分配给特定用户。
- **CsVideoInteropServiceProvider**：使用此 cmdlet 指定有关你的组织希望使用的受支持的 CVI 合作伙伴的信息。
- **Set-CsVideoInteropServiceProvider**：使用此 cmdlet 更新有关你的组织使用的受支持的 CVI 合作伙伴的信息。
- **CsVideoInteropServiceProvider**：使用此 cmdlet 获取已配置为在组织内使用的所有提供商。
- **Remove-CsVideoInteropServiceProvider**：使用此 cmdlet 删除有关你的组织不再使用的提供程序的所有提供程序信息。
