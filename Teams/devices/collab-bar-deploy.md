---
title: 为 Microsoft 团队部署协作栏
ms.author: mitressl
author: flinchbot
manager: serdars
audience: ITPro
ms.reviewer: payurevi
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: 阅读本文，了解如何为 Microsoft 团队部署协作栏。
ms.openlocfilehash: 71f9482dd5f42ddeb56b32c1a92db033d1f179f7
ms.sourcegitcommit: 86b0956680b867b8bedb2e969220b8006829ee53
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/28/2020
ms.locfileid: "44410447"
---
# <a name="deploy-collaboration-bars-for-microsoft-teams"></a>为 Microsoft 团队部署协作栏

可将 Microsoft 团队的协作栏部署分为以下阶段：

- **网站准备情况**确认部署位置（会议室）满足部署要求。
- **服务准备情况**创建资源帐户并将其分配给设备（[请参阅使用 Microsoft 365 管理中心创建资源帐户](resource-account-ui.md)）。 尽管我们建议使用专用的会议室许可证，但经正确授权的最终用户帐户也可以登录协作栏。
- **配置和部署**在会议室中设置协作栏并连接所需的外围设备（请参阅协作栏的制造商文档）。

## <a name="site-readiness"></a>网站准备情况

当已订购的设备正在发送给你的组织时，请与你的网络、设施和音频视觉团队协作，以确保满足部署要求，并且每个网站和聊天室均可在 power、网络和显示器方面随时准备就绪。

我们针对协作栏网站的建议如下：

- 大小最多为4人的会议室
- 专用资源帐户
- 支持触摸的显示器
- 以太网缆线
- 在网络上启用的适用于 Microsoft 团队媒体的服务质量（QoS）

有关物理安装的注意事项，请参阅制造商的文档，如果有，请在安装和装入屏幕并运行缆线之前，充分利用您的音频视觉团队的体验。

> [!TIP]
> 请务必查看针对团队进行带宽规划和评估网络对实时流量的适用性的[准备好网络](../prepare-network.md)。
>
> 我们不建议在团队设备和 Internet 之间放置代理服务器。 有关代理服务器和团队的详细信息，请查看[团队的代理服务器](../proxy-servers-for-skype-for-business-online.md)。

|    |     |
|-----------|------------|
| ![描述决策点的图标](../media/audio_conferencing_image7.png) <br/>决策点|<ul><li>确认您的网站满足 Microsoft 团队协作栏的网站准备情况要求。</li><li>确认您是否为每个网站都提供了足够的带宽。</li></ul>|
| ![描述后续步骤的图标](../media/audio_conferencing_image9.png)<br/>后续步骤|<ul><li>开始规划协作栏部署和配置。</li></ul>|

## <a name="service-readiness"></a>服务就绪

在部署协作栏之前，您需要确定他们是使用 Microsoft 365 资源帐户、最终用户帐户还是同时使用这两者。 Microsoft 365 资源帐户是指专用于特定资源（如房间、投影仪等）的邮箱和团队帐户。 这些资源帐户可以使用在创建规则时定义的规则自动答复会议邀请。 除非协作栏专用于特定个人供其私人使用，否则我们建议为其设置 Microsoft 365 资源帐户。

### <a name="using-a-resource-account"></a>使用资源帐户

如果您决定设置 Microsoft 365 资源帐户，您需要为其购买会议室许可证。 会议室许可证包括一个资源邮箱，使组织中的人员可以通过 Outlook 或团队预订会议室。 许可证还支持会议参与者之间的视频和音频会议以及屏幕共享。

如果您需要接收或拨出外部电话号码，您可能需要一个呼叫计划或 Microsoft 365 Business Voice[附加设备许可证](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing?tabs=small-business)。 如果您的组织中已启用直接路由，则只需要会议室 SKU。

创建资源帐户时，可以选择是让帐户自动接受或拒绝会议请求、允许定期会议、指定提前的人员可以预订资源的进度，等等。

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

有关 Microsoft 365 资源帐户的协作栏的详细信息，请参阅[使用 microsoft 365 管理中心创建资源帐户](resource-account-ui.md)。

|    |     |
|-----------|------------|
| ![描述决策点的图标](../media/audio_conferencing_image7.png) <br/>决策点|<ul><li>确定您是否要拨打或接听外部电话，并确定您的资源帐户的授权要求。</li></ul>|
| ![描述后续步骤的图标](../media/audio_conferencing_image9.png)<br/>后续步骤|<ul><li>准备资源帐户。</li></ul>|

## <a name="configuration-and-deployment"></a>配置和部署

规划配置和部署涵盖以下主要方面：

- 资源帐户预配
- 设备部署
- Microsoft 团队应用程序和外围设备配置的协作栏
-  测试
- 资产管理

### <a name="account-provisioning"></a>帐户预配

如果您计划使用 Microsoft 365 资源帐户让用户预订协作栏，请按照[使用 microsoft 365 管理中心创建资源帐户](resource-account-ui.md)中的说明为需要其中一个的每个协作栏创建 Microsoft 365 资源帐户。 这也是你需要向资源帐户添加会议室许可证的地方，如果你想要在你的组织未使用直接路由的情况下拨打或接听外部电话号码、呼叫计划或商业语音许可证，请使用呼叫计划或商业语音许可证。

如果要为单个用户分配协作栏以供其私人使用，则无需设置任何其他帐户。 用户可以使用其个人帐户登录到协作栏。

> [!TIP]
> 使您的 Microsoft 365 资源帐户的显示名称易于理解。 这些是用户在搜索并将 Microsoft 团队的协作栏添加到会议时将看到的名称。 你可以使用类似于*网站* - *聊天室名称*（*最大会议室容量*）的约定，因此例如 Curie 在伦敦的4人会议室，可能会有显示名称 LON-Curie （4）。

|    |     |
|-----------|------------|
| ![描述决策点的图标](../media/audio_conferencing_image7.png) <br/>决策点|<ul><li>确定专用资源帐户的命名约定。</li><li>确定是创建单个帐户还是使用批量预配脚本。</li></ul>|
| ![描述后续步骤的图标](../media/audio_conferencing_image9.png)<br/>后续步骤|<ul><li>开始规划设备部署。</li></ul>|

### <a name="device-deployment"></a>设备部署

接下来，你需要创建你的计划，以便将设备和分配的外围设备交付到你的聊天室，然后继续安装和配置。

|    |     |
|-----------|------------|
| ![描述决策点的图标](../media/audio_conferencing_image7.png) <br/>决策点|<ul><li>确定由谁来管理网站的网站部署。</li><li> 确定将为 Microsoft 团队网站安装协作栏并执行配置和测试的资源。</li></ul>|
| ![描述后续步骤的图标](../media/audio_conferencing_image9.png)<br/>后续步骤|<ul><li>开始设备测试。</li></ul>|

### <a name="testing"></a> 测试

部署 Microsoft 团队的协作栏后，应进行测试。 登录设备，检查所需的功能是否在已部署的设备上工作。 强烈建议你验证设备是否显示在 Microsoft 团队管理中心的 "**设备**" 选项卡的 "**协作栏**" 部分中。 还必须进行大量测试通话和会议才能检查质量和性能。

我们建议作为常规 Microsoft 团队推出的一部分，为通话质量仪表板（CQD）配置构建文件，监控质量趋势并参与体验审核流程。 有关详细信息，请参阅[体验质量检查指南](https://aka.ms/qerguide)。

### <a name="asset-management"></a>资产管理

作为部署的一部分，您将需要用房间名称、登录资源帐户和分配的外围设备更新您的资产注册。

## <a name="related-topics"></a>相关主题

[使用 Microsoft 团队管理中心为 Microsoft 团队配置协作栏的帐户](resource-account-ui.md)

<!-- [Configure accounts for collaboration bars for Microsoft Teams using PowerShell](resource-account-ps.md) -->
