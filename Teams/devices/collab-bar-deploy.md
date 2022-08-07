---
title: 在 Android 上部署Microsoft Teams 会议室
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: payurevi
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Devices
ms.custom: ''
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: 阅读本文，了解如何在 Android 上部署Microsoft Teams 会议室。
ms.openlocfilehash: f5f49a7e461153d24837d28d7160a475e4992eba
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2022
ms.locfileid: "67267807"
---
# <a name="deploy-microsoft-teams-rooms-on-android"></a>在 Android 上部署Microsoft Teams 会议室

在 Android 上部署Microsoft Teams 会议室可分为以下阶段：

- **站点就绪情况** 确认部署位置 (会议室) 满足部署要求。
- **服务就绪情况** 创建资源帐户并将其分配到设备 ([请参阅使用Microsoft 365 管理中心) 创建资源帐户](resource-account-ui.md)。 虽然我们建议使用专用会议室许可证，但获得适当许可的最终用户帐户也可以登录到 Android 上的Teams 会议室。
- **配置和部署** 设置Teams 会议室并连接所需的外围设备 (请参阅制造商的文档，了解详细信息) 。

若要管理Teams 会议室，需要全局管理员、Teams 服务管理员或 Teams 设备管理员。有关管理员角色的详细信息，请参阅[使用 Microsoft Teams 管理员角色来管理 Teams](../using-admin-roles.md)。

## <a name="site-readiness"></a>网站就绪

在将订购的设备交付给组织时，请与网络、设施和视听团队协作，确保满足部署要求，并在电源、网络和显示方面准备好每个站点和房间。

我们对协作栏网站的建议包括：

- 最多 5 人大小的会议室
- 专用资源帐户
- 启用触摸的显示器
- 以太网布线
- 为 Microsoft Teams 媒体在网络上启用服务质量 (QoS) 

有关物理安装注意事项，请参阅制造商的文档，如果你有文档，请在安装和装载屏幕并运行布线之前利用你的视听团队的体验。

> [!TIP]
> 请务必查看为 [Teams 准备网络以](../prepare-network.md) 进行带宽规划，并评估网络是否适合实时流量。
>
> 我们不建议在 Teams 设备和 Internet 之间放置代理服务器。 有关代理服务器和 Teams 的详细信息，请查看 [Teams 的代理服务器](../proxy-servers-for-skype-for-business-online.md)。

|&nbsp;|&nbsp;|
|-----------|------------|
| ![描述决策点的图标。](../media/audio_conferencing_image7.png) <br/>决策点|<ul><li>确认您的网站符合 Microsoft Teams 协作栏的站点就绪性要求。</li><li>请确认为每个网站提供了足够的带宽。</li></ul>|
| ![描述后续步骤的图标。](../media/audio_conferencing_image9.png)<br/>后续步骤|<ul><li>开始规划协作栏部署和配置。</li></ul>|

## <a name="service-readiness"></a>服务就绪

在部署Teams 会议室之前，需要确定它们是使用 Microsoft 365 资源帐户、最终用户帐户还是这两者的混合。 Microsoft 365 资源帐户是专用于特定资源（如会议室、投影机等）的邮箱和 Teams 帐户。 这些资源帐户可以使用创建时定义的规则自动响应会议邀请。 除非Teams 会议室专用于特定个人供其私用，否则建议为其设置 Microsoft 365 资源帐户。

### <a name="using-a-resource-account"></a>使用资源帐户

如果决定设置 Microsoft 365 资源帐户，则需要为其购买会议室许可证。 会议室许可证包含一个资源邮箱，使组织中的人员能够通过 Outlook 或 Teams 预订会议室。 许可证还允许会议参与者之间进行视频和音频会议和屏幕共享。

如果需要接收或拨打外部电话号码或从外部电话号码拨打电话，可能需要通话套餐或Microsoft 365 商务语音[加载项许可证](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md?tabs=small-business)。 如果在组织中启用了直接路由，则只需会议室 SKU。

创建资源帐户时，可以选择是让帐户自动接受还是拒绝会议请求，允许定期会议，指定用户可以提前预订资源的程度，等等。

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

有关 Microsoft 365 资源帐户的详细信息，请参阅[使用Microsoft 365 管理中心创建资源帐户](resource-account-ui.md)。

|&nbsp;|&nbsp;|
|-----------|------------|
| ![描述决策点的图标。](../media/audio_conferencing_image7.png) <br/>决策点|<ul><li>确定是要拨打还是接听外部电话，并确定资源帐户的许可要求。</li></ul>|
| ![描述后续步骤的图标。](../media/audio_conferencing_image9.png)<br/>后续步骤|<ul><li>准备资源帐户。</li></ul>|

## <a name="configuration-and-deployment"></a>配置和部署

配置和部署规划包括以下关键领域：

- 资源帐户预配
- 设备部署
- Teams 会议室应用程序和外围设备配置
- 测试
- 资产管理

### <a name="account-provisioning"></a>帐户设置

如果计划使用 Microsoft 365 资源帐户让用户预订协作栏，请按照[使用Microsoft 365 管理中心创建资源帐户](resource-account-ui.md)中的说明为每个需要一个协作栏创建 Microsoft 365 资源帐户。 此外，还需要将会议室许可证添加到资源帐户，如果要拨打或接听外部电话号码或从外部电话号码拨打或接听呼叫，则如果你的组织未使用直接路由，则需要使用呼叫计划或商务语音许可证。

如果要将Teams 会议室分配给单个用户以供其专用使用，则无需设置任何其他帐户。 用户可以使用其个人帐户登录到协作栏。

> [!TIP]
> 使 Microsoft 365 资源帐户的显示名称具有描述性且易于理解。 这些是用户在搜索和向会议添加Teams 会议室时将看到的名称。 可以使用 *网站*-*会议室名称* (*最大会议室容量*) 等约定，例如，伦敦 4 人会议室 Curie 的显示名称 LON-CURIE (4) 。

|&nbsp;|&nbsp;|
|-----------|------------|
| ![描述决策点的图标。](../media/audio_conferencing_image7.png) <br/>决策点|<ul><li>确定专用资源帐户的命名约定。</li><li>确定是创建单个帐户还是使用批量预配脚本。</li></ul>|
| ![描述后续步骤的图标。](../media/audio_conferencing_image9.png)<br/>后续步骤|<ul><li>开始计划设备部署。</li></ul>|

### <a name="device-deployment"></a>设备部署

接下来，需要创建计划，将设备及其分配的外围设备交付到会议室，然后继续安装和配置。

|&nbsp;|&nbsp;|
|-----------|------------|
| ![描述决策点的图标。](../media/audio_conferencing_image7.png) <br/>决策点|<ul><li>决定管理站点到站点部署的人员。</li><li> 确定将在现场安装Teams 会议室并进行配置和测试的资源。</li></ul>|
| ![描述后续步骤的图标。](../media/audio_conferencing_image9.png)<br/>后续步骤|<ul><li>开始设备测试.</li></ul>|

### <a name="testing"></a>测试

部署Teams 会议室后，应对其进行测试。 登录Teams 会议室并检查预期功能是否正常工作。 强烈建议验证它们是否出现在 Microsoft Teams 管理中心的“**Teams 设备”** 选项卡下的 **“协作栏**”部分。 还必须进行多次测试电话和会议来检查质量和性能。

建议在常规 Microsoft Teams 推出过程中，为呼叫质量仪表板配置生成文件 (CQD) ，监视质量趋势，并参与体验质量评审过程。 有关详细信息，请参阅 [体验质量评审指南](../quality-of-experience-review-guide.md)。

### <a name="asset-management"></a>资产管理

在部署过程中，需要使用会议室名称、登录资源帐户和分配的外围设备更新资产注册表。

## <a name="related-topics"></a>相关主题

[为会议室和共享 Teams 设备创建资源帐户](../rooms/with-office-365.md)