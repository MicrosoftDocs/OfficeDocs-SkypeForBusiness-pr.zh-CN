---
title: Microsoft Teams 面板
ms.author: v-mdhiman
author: ManikaDhiman
manager: serdars
ms.reviewer: weizxue
ms.topic: reference
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
search.appverid: MET150
localization_priority: Normal
description: 本文概述了 Microsoft Teams 面板支持的功能。
ms.openlocfilehash: 913924e62483c1a8d44bfade29e5bc700f92b646
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2021
ms.locfileid: "50568918"
---
# <a name="microsoft-teams-panels"></a>Microsoft Teams 面板

Microsoft Teams 面板是安装在会议空间外（通常位于入口旁）的紧凑触摸屏设备。 Teams 面板让你一目了然地查看位置和会议详细信息，并保留现场可用的会议空间。 使用丰富的大文本和颜色编码指示器，你可以从远方查看会议空间的可用性。

Teams 面板是专用的 Microsoft Teams 设备，用于显示通过 Teams 或 Outlook 365 日历应用程序安排的会议详细信息。 在会议详细信息以醒目方式显示后，与会者可以确认他们在正确的会议空间中、在正确的时间以及正确的会议。

本文概述了 Teams 面板，可帮助你规划、交付和管理组织中 Teams 面板设备。

## <a name="features-supported-by-teams-panels"></a>Teams 面板支持的功能

Teams 面板支持以下功能：

- **专门显示会议空间和会议详细信息。** 您可以一目了然地了解会议空间的详细信息，包括其位置和可用性。 对于保留的会议空间，可以看到关键会议详细信息，例如会议标题、会议日程安排和会议组织者。
- **为临时会议保留可用的会议空间。** 使用触摸屏面板，你可以就地为临时会议保留可用的会议空间，然后从房间中的 Microsoft Teams会议室或 Surface Hub 设备加入该 Teams 会议。
- **空间可用性状态的颜色编码指示器。** 通过生动的 LED 和主屏幕指示器，可远近查看会议空间可用性。 绿色表示会议空间可用，如有必要，你可以从面板本身保留它。 红色或紫色表示会议空间已保留。
- **自定义壁纸和保留状态指示器。** 管理员可以通过设置更改面板的默认外观。 例如，管理员可以更改背景壁纸或更改忙碌状态指示器的颜色。
- **辅助功能。** Teams 面板具有多种辅助功能，如高对比度文本，方便任何人使用。

若要详细了解这些功能及其使用方法，请参阅"使用 Microsoft [Teams"面板](use-teams-panels.md)。

## <a name="partners-certified-for-teams-panels"></a>通过 Teams 面板认证的合作伙伴

可以从以下合作伙伴之一获取 Teams 面板设备：

- Crestron
-  (Yealink) 即将推出

## <a name="teams-panels-requirements"></a>Teams 面板要求

部署面板设备的硬件、软件和网络要求可能会有所不同，具体取决于要部署的面板设备类型。 请参阅原始设备制造商 (OEM) 文档，了解设备集的要求。

## <a name="license-requirement"></a>许可证要求

若要使用 Teams 面板，需要 [Microsoft Teams 会议室标准版许可证](https://docs.microsoft.com/MicrosoftTeams/rooms/rooms-licensing)。

> [!Note]
>
> - 如果已在要安装 Teams 面板的会议空间中部署了 Microsoft Teams 会议室，则不需要额外的许可证来使用 Teams 面板。
> - 需要 Microsoft Teams 会议室高级版许可证才能使用即将推出的其他高级 Teams 面板功能。

## <a name="deploy-teams-panels-devices"></a>部署 Teams 面板设备

如果你参与规划、部署和管理 Teams 面板设备，则本部分适合你。 本部分不面向 Teams 面板的最终用户。

Teams 面板设备的部署可以细分为以下任务：

- [会议空间清单和容量规划](#inventory-sites-and-meeting-spaces)：创建组织网站和会议空间的清单，用于部署 Teams 面板设备。
- [采购](#procurement)：从所选设备合作伙伴采购设备。  
- [站点就绪](#site-readiness)性：确认部署 (空间) 满足部署要求。
- [配置和部署](#configuration-and-deployment)：创建资源帐户并将其分配给设备。

## <a name="inventory-sites-and-meeting-spaces"></a>库存网站和会议空间

记录组织中现有可预订会议空间的清单。 标识部署 Teams 面板范围内的网站和会议空间。 与设备和音频视觉团队协作，确定安装 Teams 面板设备的位置和方式，以及安装面板所需的任何其他硬件。

## <a name="procurement"></a>采购

根据部署 Teams 面板的范围中的会议空间数，从一个通过 Teams 面板认证的合作伙伴采购 [设备](#partners-certified-for-teams-panels)。 请访问合作伙伴的网站，了解有关设备和采购选项的详细信息。

您的组织中的会议空间在安装或装载设备时可能有不同的硬件要求。 例如，将设备装载到玻璃、玻璃窗、干墙或森林面板上所需的硬件可能不同。 有关可用的装载选项，请参阅设备合作伙伴的文档。

## <a name="site-readiness"></a>网站就绪

当订购的设备传送到组织时，请与网络、设备和音频视觉团队协作，确保满足部署要求，并且每个站点和会议空间在电源和网络方面已准备就绪。

对于 Teams 面板网站，我们的建议是：

- 专用资源帐户
- 电源 (面板通常支持以太网电源 (PoE+) 电源。 有关设备特定的电源要求，请参阅 OEM 文档。) 
- 网络上为 Microsoft Teams (QoS) 服务质量

有关物理安装注意事项，请参阅 OEM 文档，如果有，在安装和装载设备以及运行布线之前，请使用音频视觉团队的经验。

## <a name="configuration-and-deployment"></a>配置和部署

配置和部署规划包括以下关键领域：

- 资源帐户预配
- 测试

### <a name="resource-account-provisioning"></a>资源帐户预配

每个 Teams 面板设备都需要 Microsoft 365 会议室资源帐户。 使用资源帐户凭据登录到面板设备上 Microsoft Teams 应用。

若要为 Teams 面板设置 Microsoft 365 资源帐户，需要购买 Microsoft [Teams 会议室标准版许可证](#license-requirement)。 此许可证包括一个资源邮箱，使组织中的人员可以通过 Outlook 或 Teams 预订会议空间。

若要了解如何创建资源帐户并为其分配许可证，请参阅"使用 [Microsoft 365](resource-account-ui.md)管理中心创建资源帐户"。

> [!NOTE]
>
>- 如果已针对要安装面板的会议空间设置了会议室资源帐户，请使用同一会议室资源帐户登录到面板设备。 但是，请确保会议室资源帐户分配有 Microsoft Teams Room Standard 许可证，以便将其用作面板资源帐户。
>
>- 如果已在要安装 Teams 面板的会议空间中部署了 Microsoft Teams 会议室，则资源帐户已具有 [Microsoft Teams 会议室许可证](../rooms/rooms-licensing.md)。 在这种情况下，无需购买单独的 Microsoft Teams 会议室标准版许可证来部署面板。 管理员使用与 Microsoft Teams 会议室相同的凭据登录面板设备，但空间相同。
>
>- 对于具有多个入口的大型会议室（如会议室或会议室），您可以在每个进入处装载一个面板设备。 属于单个会议空间的多个面板共享同一资源帐户，并使用相同的凭据登录。 无需为同一空间的每个面板创建单独的资源帐户。

> [!TIP]
> 建议在实际 Teams 面板安装之前创建资源帐户。
> 请考虑对 Teams 面板资源帐户使用命名约定。 使 Microsoft 365 资源帐户的显示名称具有描述性且易于理解。 这些是用户在 Outlook 或 Teams 日历中安排会议时搜索会议空间时会看到的名称。

### <a name="testing"></a>测试

部署面板后，应测试它们。 检查 Teams [面板支持的功能在](#features-supported-by-teams-panels) 已部署设备上是否正常工作。 尝试在计算机上通过 Teams 或 Outlook 365 为不同时间段创建多个会议。 检查面板是否正确显示会议详细信息和已计划会议的可用性。 尝试使用" **保留"** 按钮检查是否可直接从设备保留可用的会议空间。

## <a name="manage-teams-panels-in-your-organization"></a>在组织中管理 Teams 面板

若要管理 Teams 面板设备，在 Microsoft Teams 管理中心的左侧导航栏中，转到 **"设备**  >  **团队"面板**。 可在此处更改设备配置文件、管理更新、重启设备、添加和删除设备标记等。 有关详细信息，请参阅["在 Teams 中管理设备"。](device-management.md)

## <a name="next-steps"></a>后续步骤

[如何使用 Microsoft Teams 面板设备](use-teams-panels.md)

## <a name="see-also"></a>另请参阅

[Teams 面板上的 Microsoft Teams 博客](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/manage-meeting-space-availability-with-microsoft-teams-panels/ba-p/2167734)

[Teams 面板入门](https://support.microsoft.com/office/get-started-with-teams-panels-fa5e85d1-7ff3-4f11-b0b0-277e2302c8be)

[在 Microsoft Teams 面板认证计划下认证的设备](teams-ip-phones.md#currently-certified-teams-panels)