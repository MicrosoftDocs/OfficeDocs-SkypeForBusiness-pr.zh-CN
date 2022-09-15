---
title: Microsoft Teams 的云视频互操作性
ms.author: mabond
author: mkbond007
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: naforer
f1.keywords:
- NOCSH
description: 使用云视频互操作作为中间解决方案，允许第三方会议室设备加入 Microsoft Teams 会议。
ms.localizationpriority: medium
ms.collection:
- M365-voice
- M365-collaboration
ms.custom:
- seo-marvel-apr2020
- seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3c732cc01a525a4895fafe45c954c965fe960853
ms.sourcegitcommit: 424b14534aa269bb408c97c368102a193b481656
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/14/2022
ms.locfileid: "67706449"
---
# <a name="cloud-video-interop-for-microsoft-teams"></a>Microsoft Teams 的云视频互操作性

云视频互操作 (CVI) 是一种 Microsoft 合格的第三方解决方案，可让第三方会议室 (远程) 和个人视频设备 (VTC) 加入 Microsoft Teams 会议。
 
借助 Microsoft Teams，可以在包括音频、视频和内容共享的会议中获得丰富的在线内容协作。 可以通过桌面和 Web 客户端以及许多与 Microsoft Teams 本机集成的合作伙伴设备来享受此功能。 但是，许多客户已经投资了视频电话会议和个人视频通信设备，升级成本可能很高。 云视频互操作提供了一种简单的解决方案，允许你继续使用现有解决方案，直到准备升级为止。

借助云视频互操作，Microsoft Teams 为所有参与者提供本机会议体验 - 在会议室或 Teams 客户端内部。

### <a name="is-cloud-video-interop-for-me"></a>云视频互操作是否适合我？

使用 Teams 终结点过渡到完整的本机 Microsoft Teams 解决方案时，云视频互操作提供中间服务。 提供的服务应是迁移路径的一部分。

云视频互操作适用于满足以下条件的客户：

- 大量部署会议室设备和个人视频设备 (50 多台设备) 不符合与 Microsoft Teams 直接集成的资格
- 我们的云视频互操作合作伙伴之一支持
- 希望在迁移到本机 Microsoft Teams 解决方案期间保留其当前会议室设备和个人视频设备的投资价值

虽然云视频互操作提供了很好的中间解决方案，但我们鼓励客户长期研究本机 Teams 会议解决方案，如 Teams 会议室系统。 

### <a name="office-365-us-government-and-third-party-services"></a>Office 365美国政府和第三方服务

Office 365提供了将第三方应用程序集成到 SharePoint Online 网站、Skype for Business、Teams、Microsoft 365 企业应用版 (中包括的 Office 应用程序（如 Word、Excel、PowerPoint 和 Outlook) ）和 Outlook Web App 的功能。 此外，Office 365支持与第三方服务提供商集成。 这些第三方应用程序和服务可能涉及在Office 365基础结构之外的第三方系统上存储、传输和处理组织的客户数据，因此Office 365合规性和数据保护承诺不涵盖这些数据。 **建议在评估组织适当使用这些服务时，查看第三方提供的隐私和合规性声明。**



### <a name="partners-certified-for-microsoft-teams"></a>Microsoft Teams 认证的合作伙伴

以下合作伙伴为 Microsoft Teams 提供视频互操作解决方案。 你的公司可以选择与企业中这些合作伙伴的任何组合合作。 

|伙伴|合作伙伴解决方案|
|----|---|
|![表示 Poly RealConnect 的徽标。](media/polycom.png) | <a href="https://aka.ms/PolycomRealConnect" target="_blank">Poly RealConnect 服务</a> |
|![表示 Pexip 无穷大的徽标。](media/pexip.png)| <a href="https://aka.ms/PexipInfinity" target="_blank">Microsoft Teams 的 Pexip 无穷大</a> | 
|![表示 BlueJeans 网关的徽标。](media/bluejeans.png)| <a href="https://aka.ms/BluejeansGateway" target="_blank">Microsoft Teams 的 BlueJeans 网关</a> |
|![表示 Cisco CVI 的徽标。](media/cisco.png)|<a href="https://aka.ms/CiscoCVI" target="_blank">适用于 Microsoft Teams 的 Cisco Webex 视频集成</a>|

### <a name="cloud-video-interop-overview"></a>云视频互操作概述

云视频互操作是合作伙伴提供的第三方服务，可在本地现有视频会议和个人视频设备解决方案与 Microsoft Teams 之间提供互操作性。

合作伙伴提供的解决方案包括可完全基于云部署或部分/完全部署在本地的组件。 
     
下图显示了合作伙伴解决方案的高级体系结构。

![描述 Teams 云视频互操作合作伙伴解决方案的示意图。](media/teams-cloud-video-interop-partner-solution.png)


## <a name="deploy-cloud-video-interop"></a>部署云视频互操作

部署云视频互操作解决方案时，请务必了解要部署合作伙伴解决方案。 下图列出了部署云视频互操作时应执行的常规步骤。

![描述在组织中部署 CVI 的示意图。](media/deploying-cvi.png)

### <a name="plan"></a>规划

在计划阶段，应标识不会替换为本机 Teams 设备的设备，并找到可支持这些设备的云视频互操作合作伙伴。  

同样重要的是要了解，你需要为每个计划会议的用户提供许可证，你希望启用云视频互操作的设备加入会议。 请注意，可以从云视频互操作合作伙伴获取确切的许可要求。 在开始部署之前，请确保这是清楚的。

### <a name="configure"></a>配置

为 CVI 部署选择的合作伙伴将为你提供完整的部署文档，其中包含在组织内成功部署所需的所有步骤。 这将包括防火墙端口和 IP 范围、设备的配置更改，以及需要更改的其他设置。

### <a name="provision"></a>提供  

在预配阶段，你将根据合作伙伴配置指南向相应的用户分配许可证。 还需要通过 Azure 许可过程来提供合作伙伴对 Teams 环境的访问权限。 有关 Azure 许可过程的详细信息，请参阅[Microsoft 标识平台终结点中的](/azure/active-directory/develop/v2-permissions-and-consent)权限和许可。

### <a name="schedule"></a>附表

为用户启用云视频互操作后，使用适用于 Outlook 的 Teams 会议外接程序或 Teams 客户端安排的任何会议都将自动将相应的附加信息添加到 Teams 会议中，以便与云视频互操作兼容的设备可以加入这些会议。

### <a name="join"></a>Join

根据合作伙伴解决方案，可通过多种方式加入已启用云视频互操作的会议。 确切的会议加入方案将由云视频互操作合作伙伴提供。 我们列出了以下一些示例：

- IVR (交互式语音响应)  
  - 可以使用tenantkey@domain拨入合作伙伴的 IVR。
  - 在合作伙伴 IVR 中时，系统会提示输入 VTC conferenceId，然后将你连接到 Teams 会议。
- 直拨 
  - 可以使用租户密钥的完整字符串使用直接拨号功能直接拨入 Teams 会议，而无需与合作伙伴的 IVR 进行交互。VTC ConferenceId@domain。
- 单击拨号 
  - 如果你有一个集成的 Teams 会议室，则可以使用合作伙伴 (提供的一触式拨号功能，而无需键入任何拨号字符串) 。

## <a name="manage-cloud-video-interop"></a>管理云视频互操作

部署云视频互操作后，可以使用合作伙伴提供的解决方案管理设备。 每个合作伙伴将为你提供包含许可证和设备管理的管理接口。 

报告也可直接从合作伙伴管理界面获取。 有关报告功能的详细信息，请联系所选合作伙伴。 

### <a name="troubleshooting-cloud-video-interop"></a>云视频互操作疑难解答

云视频互操作是合作伙伴提供的服务。 如果遇到问题，第一步是连接安装了 Teams 客户端的设备，并将其连接到与导致问题的云视频互操作设备相同的段。 

如果 Teams 在此段上正常运行，并且你也遵循了合作伙伴提供的所有网络和配置准则，则需要与合作伙伴联系以进行进一步的故障排除。 

## <a name="powershell-for-cloud-video-interop"></a>PowerShell for Cloud Video Interop

以下 PowerShell cmdlet 可用于 (部分) 自动执行云视频互操作部署。

- **Get-CsTeamsVideoInteropServicepolicy**：Microsoft 为每个受支持的合作伙伴提供预先构造的策略，让你能够指定用于云视频互操作的合作伙伴 () 。<br>使用此 cmdlet 可以标识可在组织中使用的预构造策略。 可以利用Grant-CsTeamsVideoInteropServicePolicy cmdlet 将此策略分配给一个或多个用户。
- **Grant-CsTeamsVideoInteropServicePolicy**：此 cmdlet 允许分配预构造策略以供组织使用，或将策略分配给特定用户。
- **New-CsVideoInteropServiceProvider**：使用此 cmdlet 指定有关组织想要使用的受支持的 CVI 合作伙伴的信息。
- **Set-CsVideoInteropServiceProvider**：使用此 cmdlet 更新有关组织使用的受支持的 CVI 合作伙伴的信息。
- **Get-CsVideoInteropServiceProvider**：使用此 cmdlet 获取已配置为在组织内使用的所有提供程序。
- **Remove-CsVideoInteropServiceProvider**：使用此 cmdlet 删除有关组织不再使用的提供程序的所有提供程序信息。