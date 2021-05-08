---
title: 在 Android Microsoft Teams 会议室部署应用
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
description: 阅读本文，了解如何在 Android Microsoft Teams 会议室部署。
ms.openlocfilehash: 3da0192ee3676f5ff7294ba719c778ea7b1cc7b2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120794"
---
# <a name="deploy-microsoft-teams-rooms-on-android"></a>在 Android Microsoft Teams 会议室部署应用

在 Android Microsoft Teams 会议室部署机器人可以分为以下阶段：

- **网站就绪性** 确认会议室中的 (位置) 满足部署要求。
- **服务就绪性** 创建资源帐户并将其分配给设备 (请参阅使用资源管理中心Microsoft 365 [资源) 。](resource-account-ui.md) 尽管我们建议使用专用聊天室许可证，但获得适当许可的最终用户帐户也可以登录到 android Teams 会议室帐户。
- **配置和部署** 设置Teams 会议室并连接所需的外围设备 (请参阅制造商的文档，了解) 。

若要Teams 会议室，需要是全局管理员、Teams管理员或Teams设备管理员。有关管理员角色详细信息，请参阅使用 Microsoft Teams[管理员角色管理Teams。](../using-admin-roles.md)

## <a name="site-readiness"></a>网站就绪

将订购的设备传送到组织时，请与网络、设施和音频视觉团队协作，确保满足部署要求，并且每个站点和会议室在电源、网络和显示方面已准备就绪。

我们针对协作栏网站的建议是：

- 大小最多 5 人的房间
- 专用资源帐户
- 支持触摸的显示器
- 以太网布线
- 为媒体 (网络上) QoS Microsoft Teams服务质量

有关物理安装注意事项，请参阅制造商的文档，如果有，在安装和装载屏幕并运行布线之前，请利用音频视觉团队的经验。

> [!TIP]
> 请务必查看准备网络Teams，以规划带宽并评估网络是否适合实时流量。 [](../prepare-network.md)
>
> 我们不建议在设备与Teams之间放置代理服务器。 有关代理服务器和客户端Teams，请查看[适用于 Teams](../proxy-servers-for-skype-for-business-online.md)的代理服务器。

|    |     |
|-----------|------------|
| ![描述决策点的图标](../media/audio_conferencing_image7.png) <br/>决策点|<ul><li>确认您的网站满足协作栏的网站就绪性要求，以便Microsoft Teams。</li><li>请确认为每个网站提供了足够的带宽。</li></ul>|
| ![描述下一步骤的图标](../media/audio_conferencing_image9.png)<br/>后续步骤|<ul><li>开始规划协作栏部署和配置。</li></ul>|

## <a name="service-readiness"></a>服务就绪

在部署Teams 会议室，需要确定它们是使用资源帐户Microsoft 365最终用户帐户，还是同时使用这两者。 Microsoft 365资源帐户是Teams资源（如会议室、投影仪等）的邮箱帐户和专用帐户。 这些资源帐户可以使用创建会议邀请时定义的规则自动响应会议邀请。 除非Teams 会议室专用于特定个人供其专用，否则建议Microsoft 365资源帐户。

### <a name="using-a-resource-account"></a>使用资源帐户

如果决定设置资源Microsoft 365帐户，则需要为它购买会议室许可证。 "会议室许可证"包括一个资源邮箱，使您的组织中的人员可以通过会议室或Outlook Teams。 该许可证还支持视频和音频会议以及会议参与者之间的屏幕共享。

如果需要接收或拨打外部电话号码，可能需要呼叫计划或Microsoft 365 商务语音[附加许可证](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md?tabs=small-business)。 如果组织中已启用直接路由，则只需会议室 SKU。

创建资源帐户时，可以选择是否允许帐户自动接受或拒绝会议请求、允许定期会议、指定用户可以提前预订资源多远，等等。

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

有关资源帐户Microsoft 365，请参阅使用管理中心创建Microsoft 365[帐户](resource-account-ui.md)。

|    |     |
|-----------|------------|
| ![描述决策点的图标](../media/audio_conferencing_image7.png) <br/>决策点|<ul><li>决定是拨打还是接听外部电话呼叫，并确定资源帐户的许可要求。</li></ul>|
| ![描述下一步骤的图标](../media/audio_conferencing_image9.png)<br/>后续步骤|<ul><li>准备资源帐户。</li></ul>|

## <a name="configuration-and-deployment"></a>配置和部署

配置和部署规划包括以下关键领域：

- 资源帐户预配
- 设备部署
- Teams 会议室应用程序和外围设备配置
- 测试
- 资产管理

### <a name="account-provisioning"></a>帐户设置

如果计划使用 Microsoft 365 资源帐户来允许用户预订协作栏，请按照使用[Microsoft 365](resource-account-ui.md)管理中心创建资源帐户中的说明为需要协作栏的每个协作栏创建 Microsoft 365 资源帐户。 这也是需要向资源帐户添加 会议室 许可证的地方，如果要拨打或接听来自外部电话号码的呼叫，请添加呼叫计划或商务语音许可证（如果组织没有使用直接路由）。

如果要将帐户Teams 会议室供个人用户使用，则不需要设置任何其他帐户。 用户可以使用个人帐户登录到协作栏。

> [!TIP]
> 使资源帐户的显示名称Microsoft 365描述性且易于理解。 这些是用户在搜索会议内容以及向会议添加Teams 会议室的名称。 您可以使用网站会议室名称 (最大会议室容量) 等约定，例如，伦敦 4 人会议室 Curie 可能拥有 - 显示名称 LON-CURIE (4) 。 

|    |     |
|-----------|------------|
| ![描述决策点的图标](../media/audio_conferencing_image7.png) <br/>决策点|<ul><li>确定专用资源帐户的命名约定。</li><li>决定是创建单个帐户还是使用批量预配脚本。</li></ul>|
| ![描述下一步骤的图标](../media/audio_conferencing_image9.png)<br/>后续步骤|<ul><li>开始计划设备部署。</li></ul>|

### <a name="device-deployment"></a>设备部署

接下来，需要创建计划，将设备及其分配的外围设备交付到会议室，然后继续进行安装和配置。

|    |     |
|-----------|------------|
| ![描述决策点的图标](../media/audio_conferencing_image7.png) <br/>决策点|<ul><li>决定管理站点到站点部署的人员。</li><li> 确定将现场安装Teams 会议室执行配置和测试的资源。</li></ul>|
| ![描述下一步骤的图标](../media/audio_conferencing_image9.png)<br/>后续步骤|<ul><li>开始设备测试.</li></ul>|

### <a name="testing"></a>测试

在部署Teams 会议室，应测试它们。 登录到 Teams 会议室检查预期功能是否正常工作。 强烈建议验证它们是否显示在管理中心的"设备"选项卡下的"协作Microsoft Teams部分。  还必须进行大量测试呼叫和会议，以检查质量和性能。

我们建议，作为常规 Microsoft Teams的一部分，请为呼叫质量仪表板 (CQD) 配置生成文件，监视质量趋势，并参与体验质量评审过程。 有关详细信息，请参阅 [体验质量评审指南](../quality-of-experience-review-guide.md)。

### <a name="asset-management"></a>资产管理

在部署中，需要使用聊天室名称、登录的资源帐户和分配的外围设备更新资产注册。

## <a name="related-topics"></a>相关主题

[使用管理Microsoft Teams 会议室配置Microsoft Teams帐户](resource-account-ui.md)

<!-- [Configure accounts for collaboration bars for Microsoft Teams using PowerShell](resource-account-ps.md) -->