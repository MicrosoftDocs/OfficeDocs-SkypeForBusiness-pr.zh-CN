---
title: Microsoft 团队中的 Walkie Talkie 应用程序
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: 如何从 ITAdmin 角度配置 Microsoft 团队中的 Walkie Talkie 应用。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9369cf56a32142d6527fcb86271d8d0fa56718ec
ms.sourcegitcommit: 2467ece95e100a3a3cc2be3538d8eb7d878b3663
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/06/2020
ms.locfileid: "45043005"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a>Microsoft 团队中的 Walkie Talkie 应用

[!INCLUDE [preview-feature](includes/preview-feature.md)]

团队中的 Walkie Talkie 应用为你的团队提供即时推送通话（PTT）通信，不久将在 Android 上的公共预览版中提供。 Walkie Talkie 允许用户使用与其成员相同的基础频道连接其团队。 仅在频道中连接到 Walkie Talkie 的用户成为参与者，并且可以使用 "按下" 与他人进行通信，每次一个通话。

通过 Walkie Talkie，一线的工作人员现在可以安全地与熟悉的 PTT 体验进行通信，而无需携带有容量的无线收发器，并且使用 WiFi 或手机互联网连接，Walkie Talkie 可以工作。

## <a name="getting-started"></a>入门

### <a name="deploying-walkie-talkie"></a>部署 Walkie Talkie

在公共预览版期间，Walkie Talkie 尚未预安装。 若要为你的组织中的用户启用此功能，你需要将 Walkie Talkie [App Setup Policy](teams-app-setup-policies.md)添加到   分配给[团队管理中心](https://admin.teams.microsoft.com/)中的用户的应用设置策略。

启用后，Walkie Talkie 将在48小时内的 Android 应用中可用。

### <a name="adding-walkie-talkie-to-your-app-list"></a>将 Walkie Talkie 添加到你的应用列表

在 Microsoft 团队管理中心的 "**团队应用**  >  **设置策略**" 下，应将 "**允许用户固定**" 设置为 **"打开"**。 然后，在 "固定应用" 部分下，单击 " **+ 添加应用**"。

:::image type="content" source="media/deploy-walkie-talkie-1.png" alt-text="显示 "固定应用" 部分和要选择的 "添加应用" 按钮。":::

在右侧显示的 "**添加固定应用**" 面板上，使用 "**搜索**" 文本框查找 Walkie Talkie。 当您将其作为搜索结果时，请单击名称右侧的 "**添加**" 按钮，将其添加到您的列表。

:::image type="content" source="media/deploy-walkie-talkie-2.png" alt-text="显示 "添加已固定的应用" 边栏，其中 Walkie 输入到搜索窗格中，在搜索结果中显示 Walkie Talkie 应用，旁边显示 "添加" 按钮。":::

Walkie Talkie 应用现在应显示在 "已附加的应用" 列表中，并且在你单击 "**保存**" 按钮后才可使用。

:::image type="content" source="media/deploy-walkie-talkie-3.png" alt-text="显示添加了 Walkie Talkie 应用的固定应用列表，以及列表下方的 "保存" 按钮。":::

### <a name="network-documentation"></a>网络文档

团队中的 Walkie Talkie 需要 Internet 连接，并且必须满足网络条件才能获得最佳体验。

延迟（RTT） < 300ms |抖动 < 30ms |数据包丢失 < 1%

如上所述，通过 IP 网络的实时媒体质量很大程度上受到网络连接质量的影响，但特别是：

- **延迟**-这是将 IP 数据包从点 A 转到网络上的点 B 所需的时间。 此网络传播延迟实质上与两个点之间的物理距离和光之间的距离保持联系，包括不同路由器所用的额外开销。 延迟按往返时间（RTT）测量。
- **数据包丢失**-这通常定义为在给定时间段内丢失的数据包的百分比。 数据包丢失直接影响音频质量—从少量的单个丢失的数据包几乎没有影响，到导致完整的音频切出的后端到后爆发损失。
- **抖动**-这是连续数据包之间的延迟的平均变化。

在发送或接收音频时，Walkie Talkie 的预期数据使用量在 20KB/s 周围。 当空闲时，Walkie Talkie 中的预期数据使用量可以忽略。

### <a name="walkie-talkie-devices"></a>Walkie Talkie 设备

即使在手机处于锁定状态时，一线工作人员也经常需要说和接听 Walkie Talkie 通话。 通过具有专用 PTT 按钮的专用设备，可实现此体验。

- 现有手机
  - 有线耳机（[Klein 电子设备](https://www.kleinelectronics.com/)）
  - 无线耳机（[Jabra evolve BlueParrott](https://www.blueparrott.com/)）
- 坚固的手机
  - Samsung Galaxy XCover Pro
    - [详细信息](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/)。
    - [设置指南](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm)。

> [!NOTE]
> 这些设备不是团队认证的设备。 他们已经过验证，可与 Walkie Talkie 的团队协作。

### <a name="license-requirements"></a>许可证要求

Walkie Talkie 应用均包含在[Office 365 订阅](https://docs.microsoft.com/MicrosoftTeams/office-365-licensing)中的所有已收费许可证团队中。 有关获取团队的详细信息，请查看 [如何获取 Microsoft 团队的访问权限](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)？

> [!NOTE]
> 某些高级功能可能需要额外的许可。 例如，与 Samsung Galaxy XCover Pro 的集成需要安装 Knox 许可证。

## <a name="further-information"></a>详细信息

- ITAdmins 可以通过应用策略保持控制哪些人正在使用 Walkie Talkie。
- 如果你的一线工作者使用移动数据通过团队进行通信，Walkie Talkie 将使用相同的方法。
- Walkie Talkie 应在低带宽情况下运行，或者智能手机已连接并正常工作的情况。 如果根本没有连接，Walkie Talkie 将不起作用。

有关最终用户体验的进一步阅读，请参阅：

- [团队 Walkie Talkie 入门](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [通过 Walkie Talkie 与你的团队进行通信](https://support.microsoft.com/office/communicate-with-your-team-in-walkie-talkie-e4342550-5516-4451-b9ec-93166b60f8a4)
