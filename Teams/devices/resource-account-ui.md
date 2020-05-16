---
title: 使用 Microsoft 365 管理中心创建资源帐户
description: 如果你希望使用图形用户界面，可以使用 Microsoft 365 管理中心为 microsoft 团队聊天室和协作栏创建资源帐户。
ms.reviewer: payurevi
manager: serdars
audience: ITPro
keywords: 创建设备帐户，Microsoft 365 UI，Microsoft 365 管理中心
ms.sitesec: library
ms.service: msteams
author: flinchbot
ms.author: mitressl
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: 1137f462b9c21455f3a65a87075fd653b5c081b9
ms.sourcegitcommit: f0ccafb7e9c2d382ab4545e085657e8129024f1d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/16/2020
ms.locfileid: "44268012"
---
# <a name="create-a-microsoft-365-resource-account-using-the-microsoft-365-admin-center"></a>使用 Microsoft 365 管理中心创建 Microsoft 365 资源帐户

Microsoft 365 资源帐户是指专用于特定资源（如房间、投影仪等）的邮箱和团队帐户。 这些资源帐户可以使用在创建规则时定义的规则自动答复会议邀请。 例如，如果您有一个常见的资源（如会议室），则可以为该会议室设置资源帐户，这样将根据其日历可用性自动接受或拒绝会议邀请。

<!-- The steps in this article show you how to set up a resource account using the Microsoft 365 admin center. If you'd rather use PowerShell to create resource accounts, [Create a resource account using the PowerShell](resource-account-ps.md). -->

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

## <a name="licensing"></a>许可

在创建 Microsoft 365 资源帐户之前，请检查以查看它所需的许可证类型。 如果你仅使用资源帐户预订资源（即，邀请资源加入你的会议并自动接受或拒绝邀请），则无需为资源帐户分配许可证。 在以下情况下，您需要为资源帐户分配许可证：

- **团队会议**如果你希望资源（如 Microsoft 团队聊天室控制台、协作栏等）加入团队会议，以便与会者可以使用它通过它演示视频和音频，你需要一个会议室许可证。 
- **PSTN 呼叫**如果您希望资源拨打或接听外部电话号码（称为公共交换电话网络或 PSTN 呼叫）的来电，您需要 Microsoft 365 手机系统或 Microsoft 365 商用语音许可证。

有关会议室、电话系统和商业语音许可证的详细信息，请参阅[Microsoft 团队附加设备许可证](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md)

## <a name="create-a-resource-account-in-the-microsoft-365-admin-center"></a><a href="" id="create-device-acct-m365-admin-ctr"></a>在 Microsoft 365 管理中心创建资源帐户

1. 通过访问登录到 Microsoft 365https://admin.microsoft.com
2. 提供 Microsoft 365 租户的管理员凭据。 这将把你转到 Microsoft 365 管理中心。

:::image type="content" source="../media/collaboration-bar-m365-admin-center.png" alt-text="Microsoft 365 管理中心":::
3. 在管理中心中，导航到左侧面板中的 "**资源**" （可能需要先选择 "**全部显示**"），然后选择 "**会议室" & 设备**。

:::image type="content" source="../media/collaboration-bar-m365-resources-rooms.png" alt-text="Microsoft 365 管理中心-资源":::
4. 选择 "**添加资源邮箱**" 以创建新的聊天室帐户。 输入帐户的显示名称和电子邮件地址，选择 "**添加**"，然后选择 "**关闭**"。 我们建议你对所有资源帐户的命名约定进行标准化。

> [!NOTE]
> 默认情况下，使用以下设置设置资源帐户。 如果要更改它们，请选择 "**设置计划选项**"，然后选择 "**关闭**"。 如果以后要更改它们，请导航到 "**资源**  >  **室 & 设备**"，选择资源帐户，然后选择 "**预定选项**" 下的 "**编辑**"。
>
> - 允许重复会议
> - 自动拒绝超出以下限制的会议
>   - 预定窗口（天）：180
>   - 最长持续时间（小时）：24
> - 自动接受会议请求

:::image type="content" source="../media/collaboration-bars-admin-resources.png" alt-text="Microsoft 365 管理中心-添加资源":::
5. 导航到管理中心中的 "**用户**" 部分，在 "**活动用户**" 列表中，你将看到刚创建的聊天室。

:::image type="content" source="../media/collaboration-bars-M3565-admin-active-users.png" alt-text="Microsoft 365 管理中心-请参阅活动用户":::
6. 选择聊天室的名称，将在右侧显示 "帐户属性" 面板。

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-settings.png" alt-text="Microsoft 365 管理中心-用户属性":::
7. 现在，你需要为资源帐户分配密码。 在面板中，你可以查看帐户属性和几个可选操作。 选择 "用户名" 下的 "**重置密码**密钥" 图标以更改密码。 "取消选择 **" 要求此用户在首次登录时更改其密码**。 不能通过设备登录过程更改密码。 选择 "**重置**"。

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-password.png" alt-text="Microsoft 365 管理中心-重置密码":::
8. 在 "**许可证和应用**" 部分中，设置将在其中安装设备的国家或地区的 "**选择位置**"。 向下滚动并选中要分配的许可证旁边的框（例如会议室），然后选择 "**保存更改**"。 许可证可能有所不同，具体取决于您的组织。

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-assign-license.png" alt-text="Microsoft 365 管理中心-分配许可证":::
