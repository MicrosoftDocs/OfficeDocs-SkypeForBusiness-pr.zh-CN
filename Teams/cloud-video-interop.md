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
# <a name="cloud-video-interop-for-microsoft-teams"></a>Microsoft Teams 的云视频互操作性

云视频互操作 (CVI) 是 Microsoft 符合条件的第三方解决方案，可让第三方会议室 (网真) 和个人视频设备 (VTC) 加入 Microsoft Teams 会议。
 
借助 Microsoft Teams，您可以在会议（包括音频、视频和内容共享）中实现丰富的联机内容协作。 这可以通过桌面和 Web 客户端以及与 Microsoft Teams 本机集成的许多合作伙伴设备来享受。 但是，许多客户已经投资了视频电话会议和个人视频通信设备，升级成本可能很高。 云视频互操作提供了一个简单的解决方案，让你能够一直使用现有解决方案，直到准备好升级。

借助云视频互操作，Microsoft Teams 为会议室内或 Teams 客户端内的所有参与者提供本机会议体验。

### <a name="is-cloud-video-interop-for-me"></a>云视频互操作是否适合我？

云视频互操作提供中间服务，同时使用 Teams 终结点过渡到完整的本机 Microsoft Teams 解决方案。 提供的服务应该是迁移路径的一部分。

云视频互操作适用于符合以下条件的客户：

- 在超过 50 (个没有资格与 Microsoft Teams 直接集成的) 设备上部署大量会议室设备和个人视频设备
- 我们的一个云视频互操作合作伙伴支持
- 想要在迁移到本机 Microsoft Teams 解决方案期间保留其当前会议室设备和个人视频设备投资的价值

尽管云视频互操作提供了很好的中间解决方案，但我们鼓励客户长期查看本机 Teams 会议解决方案，例如 Teams 会议室系统。 

### <a name="office-365-us-government-and-third-party-services"></a>Office 365 美国政府版和第三方服务

Office 365 提供将第三方应用程序集成到 SharePoint Online 网站、Skype for Business、Teams、Microsoft 365 企业版应用中包含的 Office 应用程序 (例如 Word、Excel、PowerPoint 和 Outlook) 和 Outlook Web App。 此外，Office 365 支持与第三方服务提供商集成。 这些第三方应用程序和服务可能涉及在 Office 365 基础结构外部的第三方系统上存储、传输和处理组织的客户数据，因此未包括在 Office 365 合规性和数据保护承诺中。 **建议在评估针对组织的这些服务的适当使用时，查看第三方提供的隐私和合规性声明。**



### <a name="partners-certified-for-microsoft-teams"></a>Microsoft Teams 认证的合作伙伴

以下合作伙伴为 Microsoft Teams 提供视频互操作解决方案。 公司可以选择与企业中这些合作伙伴的任意组合合作。 

|合作伙伴|合作伙伴解决方案|
|----|---|
|![表示 Poly RealConnect 的徽标](media/polycom.png) | <a href="https://aka.ms/PolycomRealConnect" target="_blank">Poly RealConnect 服务</a> |
|![表示 Pexip Infinity 的徽标](media/pexip.png)| <a href="https://aka.ms/PexipInfinity" target="_blank">Microsoft Teams 的 Pexip 无穷大</a> | 
|![表示 BlueJeans 网关的徽标](media/bluejeans.png)| <a href="https://aka.ms/BluejeansGateway" target="_blank">Microsoft Teams 的 BlueJeans 网关</a> |
|![表示 Cisco CVI 的徽标](media/cisco.png)|<a href="https://aka.ms/CiscoCVI" target="_blank">Microsoft Teams 的 Cisco Webex 视频集成</a>|

### <a name="cloud-video-interop-overview"></a>云视频互操作概述

云视频互操作是一项第三方服务，由我们的合作伙伴提供，用于提供本地现有视频会议和个人视频设备解决方案与 Microsoft Teams 之间的互操作性。

合作伙伴提供的解决方案包括可完全基于云或部分/完全在本地部署的组件。 
     
下图显示了合作伙伴解决方案高级体系结构。

![描述 Teams 云视频互操作合作伙伴解决方案的示意图](media/teams-cloud-video-interop-partner-solution.png)


## <a name="deploy-cloud-video-interop"></a>部署云视频互操作

部署云视频互操作解决方案时，必须了解正在部署合作伙伴解决方案。 下图列出了部署云视频互操作时应该执行的常规步骤。

![描述在组织中部署 CVI 的示意图](media/deploying-cvi.png)

### <a name="plan"></a>规划

在计划阶段，应确定不会替换为本机 Teams 设备的设备，并找到支持这些设备的云视频互操作合作伙伴。  

另一个必须了解的是，需要为要安排希望启用云视频互操作的设备加入会议的每个用户提供许可证。 请注意，可以从云视频互操作合作伙伴获取确切的许可要求。 在开始部署之前，请确保这一点清晰明了。

### <a name="configure"></a>配置

为 CVI 部署选择的合作伙伴将提供完整的部署文档，其中包括在组织中成功部署所需的所有步骤。 这包括防火墙端口和 IP 范围、设备的配置更改，以及需要更改的其他设置。

### <a name="provision"></a>预配  

在预配阶段，根据合作伙伴配置指南将许可证分配给相应的用户。 还需要完成 Azure 许可过程，向合作伙伴提供对 Teams 环境的访问权限。 有关 Azure [许可过程的信息，请参阅 Microsoft 标识平台终结点](/azure/active-directory/develop/v2-permissions-and-consent) 中的权限和许可。

### <a name="schedule"></a>计划

为用户启用云视频互操作后，使用适用于 Outlook 的 Teams 会议加载项或 Teams 客户端安排的任何会议将自动添加到 Teams 会议，以便云视频互操作兼容的设备可以加入这些会议。

### <a name="join"></a>Join

根据合作伙伴解决方案，有几种方法可以加入启用了云视频互操作的会议。 云视频互操作合作伙伴将提供确切的会议加入方案。 下面列出了一些示例：

- IVR (交互式语音响应)  
  - 可以使用设备拨入合作伙伴的 IVR tenantkey@domain。
  - 当你在合作伙伴 IVR 中时，系统会提示你输入 VTC conferenceId，然后它将你连接到 Teams 会议。
- 直接拨号 
  - 通过使用直接拨号功能，可以使用完整的 tenantkey 字符串直接拨入 Teams 会议，而无需与合作伙伴的 IVR 交互。VTC ConferenceId@domain。
- 一键式拨号 
  - 如果你有集成的 Teams 会议室，可以使用合作伙伴团队提供的一键式拨号功能 (无需键入任何拨号字符串) 。

## <a name="manage-cloud-video-interop"></a>管理云视频互操作

部署云视频互操作后，可以使用合作伙伴提供的解决方案管理设备。 每个合作伙伴都会提供一个管理界面，其中包括许可证和设备管理。 

也可直接从合作伙伴管理界面获得报告。 有关报告功能的信息，请与你选择的合作伙伴联系。 

### <a name="troubleshooting-cloud-video-interop"></a>云视频互操作故障排除

云视频互操作是合作伙伴提供的服务。 如果遇到问题，第一步是连接安装了 Teams 客户端的设备，并连接到与导致问题的云视频互操作设备相同的段。 

如果 Teams 在此段中正常运行，并且你已遵循合作伙伴提供的所有网络和配置指南，则需要联系合作伙伴进行进一步故障排除。 

## <a name="powershell-for-cloud-video-interop"></a>PowerShell for Cloud Video Interop

可以使用以下 PowerShell cmdlet 来 (部分) 云视频互操作部署。

- **Get-CsTeamsVideoInteropServicepolicy：Microsoft** 为每个支持的合作伙伴提供预构建的策略，允许你指定要用于云视频互操作的合作伙伴 () 。<br>使用此 cmdlet 可以标识可在组织中使用的预构建策略。 可以通过使用 Grant-CsTeamsVideoInteropServicePolicy cmdlet 将此策略分配给一个或多个用户。
- **Grant-CsTeamsVideoInteropServicePolicy：** 此 cmdlet 允许分配预构造的策略以在组织中使用，或将策略分配给特定用户。
- **New-CsVideoInteropServiceProvider：** 使用此 cmdlet 指定有关组织希望使用的受支持 CVI 合作伙伴的信息。
- **Set-CsVideoInteropServiceProvider：** 使用此 cmdlet 更新有关组织使用的受支持 CVI 合作伙伴的信息。
- **Get-CsVideoInteropServiceProvider：** 使用此 cmdlet 获取已配置为在组织中使用的所有提供程序。
- **Remove-CsVideoInteropServiceProvider：** 使用此 cmdlet 删除有关组织不再使用的提供程序的所有提供程序信息。