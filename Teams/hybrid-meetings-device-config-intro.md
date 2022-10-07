---
title: 步骤 5 - 概述
ms.author: dstrome
author: dstrome
f1.keywords:
- Teams hybrid
- remote work
- Teams meetings
manager: serdars
audience: ITPro
description: 逐步完成在组织中设置新Teams 会议室设备的完整过程。
ms.topic: article
ms.service: msteams
ms.localizationpriority: high
ms.collection:
- m365solution-teamshybrid
- m365solution-scenario
ms.custom: ''
keywords: ''
ms.openlocfilehash: 2255aa52ec04354799761c7785cfc5f761a1e962
ms.sourcegitcommit: 957502f999512a32794a9f99e292588d66ed8a33
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2022
ms.locfileid: "67885540"
---
# <a name="step-5---overview"></a>步骤 5 - 概述

:::image type="content" source="media/hybrid-audience-itpro-small.png" alt-text="IT Pro 受众" border="false":::

安装并连接所有设备后，就可以配置Teams 会议室控制台了。

若要Teams 会议室与组织合作，需要完成几个步骤。 这些步骤为 Teams 会议室设置帐户和许可证，告知其如何处理会议请求，并告知它何时可以和不能在会议中执行。

## <a name="before-you-begin"></a>开始之前

- 需要全局管理员和 Teams 管理员才能完成以下步骤。 有关详细信息， [请参阅关于 Microsoft 365 管理员角色](/microsoft-365/admin/add-users/about-admin-roles)。

## <a name="set-up-the-teams-room-account"></a>设置 Teams 会议室帐户

以下步骤演示如何为Teams 会议室控制台购买许可证、为其创建帐户，然后向其分配许可证。 每个 Teams 会议室控制台都需要自己的帐户和许可证才能正常工作。 创建的帐户将显示在组织的地址列表中，作为 Outlook 中可供预留的房间。

[步骤 1 - 购买Teams 会议室控制台的许可证](hybrid-meetings-device-config-license.md)

[步骤 2 - 创建资源帐户](hybrid-meetings-device-config-account.md)

[步骤 3 - 分配会议室许可证](hybrid-meetings-device-config-assign.md)

## <a name="configure-mailbox-and-account-properties"></a>配置邮箱和帐户属性

若要允许组织人员预订 Teams 会议室，需要在控制台使用的帐户上配置一些属性。 通过设置这些属性，Teams 会议室可以根据需要自动处理会议请求，删除或添加有关控制台上会议的信息，并设置会议请求响应中应包含的内容。

需要在Teams 会议室资源帐户上关闭密码过期，以便控制台能够登录到该帐户。

[步骤 4 - 配置邮箱属性](hybrid-meetings-device-config-mailbox.md)

[步骤 5 - 关闭密码过期](hybrid-meetings-device-config-password.md)

## <a name="configure-meeting-policies-and-options"></a>配置会议策略和选项

会议策略Meeting policies用于控制组织中用户安排的会议的与会者可用的功能。 例如，可以控制参与者是否可以共享视频、允许或阻止匿名参与者、控制是否可以录制会议以及存储这些录制内容，等等。

使用日历选项可以组织Teams 会议室位置，以便仅显示特定地理位置中用户的会议室。 还可以设置会议室容量和其他可在 Outlook 中显示的信息。

[步骤 6 - 配置会议策略](hybrid-meetings-device-config-policies.md)

[步骤 7 - 配置日历选项](hybrid-meetings-device-config-calendar.md)

> [!div class="nextstepaction"]
> [后续步骤](hybrid-meetings-device-config-license.md)