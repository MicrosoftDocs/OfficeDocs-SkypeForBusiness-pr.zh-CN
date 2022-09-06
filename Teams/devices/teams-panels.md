---
title: Microsoft Teams 面板
author: CarolynRowe
ms.author: crowe
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
- Teams_ITAdmin_Devices
search.appverid: MET150
ms.localizationpriority: medium
description: 本文概述了 Microsoft Teams 面板支持的功能。
ms.openlocfilehash: d31ac86be9ac00b7aa8a77e37a906b32a00a2095
ms.sourcegitcommit: 75dfc3cd9b59282d68e35e4d7185da572eb3795c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2022
ms.locfileid: "67606731"
---
# <a name="microsoft-teams-panels"></a>Microsoft Teams 面板

Microsoft Teams 面板是安装在会议空间外部的紧凑式触摸屏设备，通常位于入口旁边。 Teams 面板使你能够一目了然地查看位置和会议详细信息，并在现场保留可用的会议空间。 使用丰富的大文本和颜色编码指示器，可以从远处查看会议空间的可用性。

Teams 面板是专用的 Microsoft Teams 设备，显示通过 Teams 或 Outlook 365 日历应用程序安排的会议详细信息。 突出显示会议详细信息后，与会者可以确认他们在正确的会议空间、正确的时间和正确的会议。

本文概述了 Teams 面板，可帮助你规划、交付和管理组织中的 Teams 面板设备。

## <a name="features-supported-by-teams-panels"></a>Teams 面板支持的功能

Teams 面板支持以下功能：

- **专门显示会议空间和会议详细信息。** 可以一目了然地了解会议空间的详细信息，包括会议空间的位置和可用性。 对于预留会议空间，可以查看关键会议详细信息，例如会议标题、会议日程安排和会议组织者。
- **保留临时会议的可用会议空间。** 使用触摸屏面板，可以现场为临时会议保留可用会议空间，并从会议室Microsoft Teams 会议室或 Surface Hub 设备 _加入_ Teams 会议。
- **空间可用性状态的颜色编码指示器。** 可通过充满活力的 LED 和主屏幕指示器近距离查看会议空间可用性。 绿色指示会议空间可用，如有必要，可以直接从面板本身保留它。 红色或紫色表示会议空间是保留的。
- **自定义壁纸和保留状态指示器。** 管理员可以通过设置更改面板的默认外观。 例如，管理员可以更改后台壁纸，或更改忙碌状态指示器的颜色。
- **辅助功能。** Teams 面板具有多种辅助功能（如高对比度文本），使任何人都可以更轻松地使用它们。

若要详细了解这些功能以及如何使用这些功能，请参阅 [“使用 Microsoft Teams”面板](use-teams-panels.md)。

## <a name="partners-certified-for-teams-panels"></a>Teams 面板认证的合作伙伴

若要了解有关 Teams 面板认证的合作伙伴的详细信息，请参阅 [当前认证的 Teams 面板](teams-ip-phones.md#certified-teams-panels)。

## <a name="teams-panels-requirements"></a>Teams 面板要求

部署面板设备的硬件、软件和网络要求可能有所不同，具体取决于要部署的面板设备类型。 请参阅原始设备制造商 (OEM) 文档，了解一组设备所需的内容。

## <a name="license-requirement"></a>许可证要求

若要使用 Teams 面板，需要[Microsoft Teams 会议室许可证](../rooms/rooms-licensing.md)。

> [!Note]
> 如果已在安装 Teams 面板的会议空间中部署了Microsoft Teams 会议室，则无需额外的许可证即可使用 Teams 面板。

## <a name="deploy-teams-panels-devices"></a>部署 Teams 面板设备

如果参与规划、部署和管理 Teams 面板设备，则本部分适用于你。 本部分不适用于 Teams 面板的最终用户。

可以将 Teams 面板设备的部署细分为以下任务：

- [会议空间清单和功能规划](#inventory-sites-and-meeting-spaces)：创建用于部署 Teams 面板设备的组织网站和会议空间的清单。
- [采购](#procurement)：从所选设备合作伙伴采购设备。  
- [站点准备情况](#site-readiness)：确认部署位置 (会议空间) 满足部署要求。
- [配置和部署](#configuration-and-deployment)：创建资源帐户并将其分配给设备。

## <a name="inventory-sites-and-meeting-spaces"></a>清单网站和会议空间

清点组织中现有的可预订会议空间。 标识部署 Teams 面板范围内的网站和会议空间。 与设施和视听团队协作，确定安装 Teams 面板设备的位置和方式，以及装载面板是否需要任何其他硬件。

## <a name="procurement"></a>采购

根据部署 Teams 面板范围内的会议空间数目，从为 [Teams 面板认证的合作伙伴](#partners-certified-for-teams-panels)之一采购设备。 访问合作伙伴的网站，详细了解设备和采购选项。

组织中的会议空间可能对安装或装载设备有不同的硬件要求。 例如，将设备装载到玻璃、石膏、干墙或木板上所需的硬件可能不一样。 有关可用的装载选项，请参阅设备合作伙伴的文档。

## <a name="site-readiness"></a>网站就绪

在将有序设备交付给组织时，请与网络、设施和视听团队协作，确保满足部署要求，并在电源和网络方面准备好每个站点和会议空间。

我们对 Teams 面板网站的建议包括：

- 专用资源帐户
- 电源 (面板通常支持通过以太网供电，以及 (PoE+) 。 有关任何特定于设备的电源要求，请参阅 OEM 文档。) 


有关物理安装注意事项，请参阅 OEM 文档，如果有文档，请在安装和装载设备并运行布线之前使用你的视听团队的体验。

## <a name="configuration-and-deployment"></a>配置和部署

配置和部署规划包括以下关键领域：

- 资源帐户预配
- 测试

### <a name="resource-account-provisioning"></a>资源帐户预配

每个 Teams 面板设备都需要 Microsoft 365 会议室资源帐户。 使用资源帐户凭据登录到面板设备上的 Microsoft Teams 应用。

若要为 Teams 面板设置 Microsoft 365 资源帐户，需要购买[Microsoft Teams 会议室许可证](#license-requirement)。
有关如何创建资源帐户并向其分配许可证的信息，请参阅 [为会议室和共享 Teams 设备创建资源帐户](../rooms/with-office-365.md)。

> [!NOTE]
>
>- 如果已经为要安装面板的会议空间设置了会议室资源帐户，请使用相同的会议室资源帐户登录到面板设备。 但是，请确保会议室资源帐户具有分配给它的Microsoft Teams 会议室许可证，以便将其用作面板资源帐户。
>
>- 如果已在安装 Teams 面板的会议空间中部署了Microsoft Teams 会议室，则无需购买用于部署面板的单独许可证。 管理员使用与同一空间的Microsoft Teams 会议室相同的凭据登录到面板设备。
>
>- 对于具有多个入口的大型会议空间（如板房或会议室），可以在每个入口装载一个面板设备。 属于单个会议空间的多个面板共享相同的资源帐户，并使用相同的凭据登录。 无需为每个面板为同一空间创建单独的资源帐户。

> [!TIP]
> 建议在实际的 Teams 面板安装之前提前创建资源帐户。
> 考虑对 Teams 面板资源帐户使用命名约定。 使 Microsoft 365 资源帐户的显示名称具有描述性且易于理解。 这些是用户在 Outlook 或 Teams 日历中安排会议时搜索会议空间时将看到的名称。

### <a name="testing"></a>测试

部署面板后，应对其进行测试。 检查 [Teams 面板支持的功能](#features-supported-by-teams-panels) 是否在已部署的设备上工作。 尝试通过计算机上的 Teams 或 Outlook 365 为各种时间段创建多个会议。 检查面板是否正确显示计划的会议的会议详细信息和可用性。 尝试使用 **“保留** ”按钮检查是否可以直接从设备保留可用会议空间。

## <a name="manage-teams-panels-in-your-organization"></a>管理组织中的 Teams 面板

若要管理 Teams 面板设备，请在 Microsoft Teams 管理中心的左侧导航中转到 **Teams 设备** > **面板**。 在此处，可以更改设备配置文件、管理更新、重启设备、添加和删除设备标记等。 有关详细信息，请参阅 [在 Teams 中管理设备](device-management.md)。

## <a name="next-steps"></a>后续步骤

[如何使用 Microsoft Teams 面板设备](use-teams-panels.md)

## <a name="see-also"></a>另请参阅

[Teams 面板上的 Microsoft Teams 博客](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/manage-meeting-space-availability-with-microsoft-teams-panels/ba-p/2167734)

[Teams 面板入门](https://support.microsoft.com/office/get-started-with-teams-panels-fa5e85d1-7ff3-4f11-b0b0-277e2302c8be)

[Teams 面板市场](https://office.com/teamsdevices)

[通过 Microsoft Teams 面板认证计划认证的设备](teams-ip-phones.md#certified-teams-panels)
