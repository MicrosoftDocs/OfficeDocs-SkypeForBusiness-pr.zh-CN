---
title: Microsoft Teams 中的来宾体验
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: rafarhi
search.appverid: MET150
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-apr2020
- chat-teams-channels-revamp
description: 本文介绍可供来宾使用Microsoft Teams 功能。
ms.openlocfilehash: 960688d49f634ff5665fe4e1da2436e9bad669ac
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198904"
---
# <a name="guest-experience-in-teams"></a>Teams 中的来宾体验

邀请来宾加入团队时，他们会收到欢迎电子邮件。 此消息包含有关团队的一些信息，以及他们成为成员后的预期情况。 来宾必须通过选择电子邮件中的“**打开Microsoft Teams**”来接受邀请，然后才能访问团队及其频道。

> [!NOTE]
> 将来宾添加到团队后，可能需要几个小时才能获得访问权限。
    
![显示欢迎电子邮件示例的屏幕截图。](media/guest-experience-image1.png)
    
所有团队成员将在频道线索中看到一条消息，告知团队所有者添加了来宾并提供该来宾的姓名。 团队中的所有人都可以轻松识别谁是来宾。 频道线程右上角的标记指示团队中的来宾数，每个来宾名称旁边会显示 **(来宾)** 标签。

![显示标记的屏幕截图，该标记指示团队中的来宾数。](media/guest-experience-image2.png)

查看以下有关 Teams 中的来宾体验的视频：
- [以来宾身份加入 Teams 会议](https://support.microsoft.com/office/join-a-teams-meeting-078e9868-f1aa-4414-8bb9-ee88e9236ee4)
- [在 Teams 会议中与外部来宾协作](https://support.microsoft.com/office/work-with-external-guests-180ed260-d3ef-4247-9f24-1984fc76d5f0)

## <a name="comparison-of-team-member-and-guest-capabilities"></a>团队成员和来宾功能的比较

下表比较了组织团队成员及其来宾可用的 Teams 功能。 Teams 管理员控制来宾可用的功能。

| Teams 中的功能 | 组织中的 Teams 用户 | 来宾 |
|:-----|:-----|:-----|
|创建通道  <br/>  *团队所有者控制此设置。*  <br/> |&#x2713;|&#x2713;|
|参与私人聊天  <br/> |&#x2713;|&#x2713;|
|参与频道对话  <br/> |&#x2713;|&#x2713;|
|发布、删除和编辑消息  <br/> |&#x2713;|&#x2713;|
|共享频道文件  <br/> |&#x2713;|&#x2713;|
|访问 SharePoint 文件<br/> |&#x2713;|&#x2713;|
|附加文件<br/> |&#x2713;|仅限频道帖子|
|下载私人聊天文件<br/> |&#x2713;|&#x2713;|
|在文件中搜索<br/> |&#x2713;||
|共享聊天文件  <br/> |&#x2713;||
|添加应用（选项卡、聊天机器人或连接器）  <br/> |&#x2713;||
|创建会议或访问计划  <br/> |&#x2713;||
|访问 OneDrive for Business 存储  <br/> |&#x2713;||
|创建租户范围和团队/频道来宾访问策略  <br/> |&#x2713;||
|邀请 Microsoft 365 或Office 365组织的域之外的用户 <br/>  *团队所有者控制此设置。*  <br/> <br/> |&#x2713;||
|创建团队  <br/> |&#x2713;||
|发现和加入公用团队  <br/> |&#x2713;||
|查看组织结构图  <br/> |&#x2713;||
|使用内联翻译  <br/> |&#x2713;||
|成为团队所有者  <br/> |&#x2713;||

下表显示了与其他类型的用户相比，来宾可用的通话和会议功能。

| 呼叫功能 | 来宾 | E1 和 E3 用户 | E5 和 企业语音 用户 |
| --------------- | ----- | -------------- | -------------- |
| VOIP 呼叫 | 是 | 是 | 是 |
| 群组通话 | 是 | 是 | 是 |
| 受支持的核心通话控件（保留、静音、打开/关闭视频、屏幕共享） | 是 | 是 | 是 |
| 转接目标 | 是 | 是 | 是 |
| 电话可转接 | 是 | 是 | 是 |
| 可协商转接 | 是 | 是 | 是 |
| 可通过 VOIP 将其他用户添加到通话中 | 是 | 是 | 是 |
| 可通过电话号码将用户添加到通话中 | 否 | 否 | 是 |
| 转发目标 | 否 | 是 | 是 |
| 通话群组目标 | 否 | 是 | 是 |
| 未应答目标 | 否 | 是 | 是 |
| 可为联合呼叫的目标 | 否 | 是 | 是 |
| 可进行联合呼叫 | 否 | 是 | 是 |
| 可立即转发其呼叫 | 否 | 否 | 是 |
| 拨打时可同时响铃 | 否 | 否 | 是 |
| 可路由未应答的通话 | 否 | 否 | 是 |
| 漏接来电可转到语音邮件 | 否 | 否<sup>1</sup> |是 |
| 具有可接听电话的电话号码 | 否 | 否 | 是 |
| 可拨打电话号码 | 否 | 否 | 是 |
| 可访问呼叫设置 | 否 | 否 | 是 |
| 可更改语音邮件问候语 | 否 | 否<sup>1</sup> | 是 |
| 可更改铃声 | 否 | 否  | 是 |
| 支持 TTY | 否 | 否 | 是 |
| 可具有委派 | 否 | 否 | 是 |
|  可为代理 | 否 | 否 | 是 |

<sup>1</sup>即将推出此功能。

> [!NOTE]
> Azure Active Directory (Azure AD 中的 **来宾用户访问限制** 策略) 确定目录中来宾的权限。 有三种政策选择。
>  - "**来宾用户拥有与成员（最包容）相同的访问权限**"设置表示来宾与目录中的普通用户一样具有相同的目录数据访问权限。
>  - "**来宾用户对目录对象的属性和成员身份拥有有限的访问权限** "设置表示来宾对某些目录任务没有权限，如枚举用户、组或其他使用 Microsoft Graph的目录资源。
>  - "**来宾用户访问权限仅限于其自己的目录对象属性和成员身份（最严格）**"设置表示来宾仅可访问自己的目录对象。
>
>要了解详细信息，请参阅[Azure Active Directory 中的默认用户权限是什么？?](/azure/active-directory/fundamentals/users-default-permissions)

## <a name="related-topics"></a>相关主题

[将组织保留为来宾](/azure/active-directory/b2b/leave-the-organization)

[使用来宾访问权限和外部访问权限与组织外部的人员进行协作](communicate-with-users-from-other-organizations.md)
