---
title: 使用管理中心创建Microsoft 365帐户
description: 如果希望使用图形用户界面，可以使用管理中心为 Microsoft Teams 会议室 和协作Microsoft Teams创建Microsoft 365帐户。
ms.reviewer: payurevi
manager: serdars
audience: ITPro
keywords: 创建设备帐户、Microsoft 365 UI、Microsoft 365管理中心
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
# <a name="create-a-microsoft-365-resource-account-using-the-microsoft-365-admin-center"></a>使用 Microsoft 365 管理中心创建Microsoft 365资源帐户

Microsoft 365资源帐户是Teams资源（如会议室、投影仪等）的邮箱帐户和专用帐户。 这些资源帐户可以使用创建会议邀请时定义的规则自动响应会议邀请。 例如，如果您有一个公用资源（如会议室），您可以为该会议室设置一个资源帐户，该资源帐户将自动接受或拒绝会议邀请，具体取决于其日历可用性。

<!-- The steps in this article show you how to set up a resource account using the Microsoft 365 admin center. If you'd rather use PowerShell to create resource accounts, [Create a resource account using the PowerShell](resource-account-ps.md). -->

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

## <a name="licensing"></a>许可

创建资源Microsoft 365之前，请检查它所需的许可证类型。 如果您仅使用资源帐户预订资源 (即邀请资源加入您的会议，并自动接受或拒绝邀请) ，则无需向资源帐户分配许可证。 在以下情况中，需要向资源帐户分配许可证：

- **Teams会议** 如果希望 (（如 Microsoft Teams 会议室 控制台、协作栏等）) 加入 Teams 会议，以便与会者可以使用它通过它演示视频和音频，则需要 会议室 许可证。 
- **PSTN 呼叫** 如果您希望资源拨打或接听外部电话号码（称为公用电话交换网 (PSTN 呼叫) ）的呼叫，则需要 Microsoft 365 电话系统 或 Microsoft 365 商务语音 许可证。

有关用户、会议室电话系统和 Business Voice 许可证[Microsoft Teams，请参阅附加许可证](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md)

## <a name="create-a-resource-account-in-the-microsoft-365-admin-center"></a><a href="" id="create-device-acct-m365-admin-ctr"></a>在管理中心Microsoft 365帐户

1. 通过访问 Microsoft 365登录到https://admin.microsoft.com
2. 为租户提供管理员Microsoft 365凭据。 这会将你Microsoft 365管理中心。

:::image type="content" source="../media/collaboration-bar-m365-admin-center.png" alt-text="Microsoft 365管理中心":::
3. 在管理中心中，导航到左侧面板中的"资源 (可能需要选择"显示所有第一) "，然后选择"会议室&**设备"。** 

:::image type="content" source="../media/collaboration-bar-m365-resources-rooms.png" alt-text="Microsoft 365管理中心 - 资源":::
4. 选择 **"添加资源邮箱** "以创建新的聊天室帐户。 输入帐户显示名称电子邮件地址，选择"**添加"，** 然后选择"关闭 **"。** 建议标准化所有资源帐户的命名约定。

> [!NOTE]
> 默认情况下，资源帐户设置如下设置。 如果要更改它们，请在选择"关闭 **"之前选择**"设置计划 **选项"。** 如果以后想要更改它们，请导航到"资源&  >  **设备"，** 选择资源帐户，然后选择"预订选项"下的"**编辑"。**
>
> - 允许重复会议
> - 自动拒绝超出以下限制的会议
>   - 预订时段 (天) ：180
>   - 最长持续时间 (小时) ：24
> - 自动接受会议请求

:::image type="content" source="../media/collaboration-bars-admin-resources.png" alt-text="Microsoft 365管理中心 - 添加资源":::
5. 导航到 **管理中心** 中的"用户"部分，在" **活动** 用户"列表中，你将看到刚创建的聊天室。

:::image type="content" source="../media/collaboration-bars-M3565-admin-active-users.png" alt-text="Microsoft 365管理中心 - 查看活动用户":::
6. 选择聊天室的名称，右侧会显示帐户属性面板。

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-settings.png" alt-text="Microsoft 365管理中心 - 用户属性":::
7. 现在，需要为资源帐户分配密码。 在面板中，可以看到帐户属性和多个可选操作。 选择 **用户名下的** "重置密码密钥"图标以更改密码。 取消选择 **"要求此用户在首次登录时更改其密码"。** 无法通过设备登录过程更改密码。 选择"**重置"。**

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-password.png" alt-text="Microsoft 365管理中心 - 重置密码":::
8. 在" **许可证和应用"** 部分中 **，将"** 选择位置"设置为要安装设备的国家/地区。 向下滚动并选中要分配的许可证旁边的框（例如"会议室"，然后选择"保存 **更改"。** 许可证可能因组织而异。

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-assign-license.png" alt-text="Microsoft 365管理中心 - 分配许可证":::
