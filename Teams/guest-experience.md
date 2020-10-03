---
title: Microsoft 团队中的来宾体验
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
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
description: 本文介绍了适用于来宾用户的 Microsoft 团队功能。
ms.openlocfilehash: 95d0fec7a1af8f735c66cc76fc27ecd3cf8bf956
ms.sourcegitcommit: 43e5a4aac11c20dd5a4c35b59695f309e1559e82
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/03/2020
ms.locfileid: "48346203"
---
# <a name="guest-experience-in-teams"></a>团队中的来宾体验

当来宾被邀请加入团队时，他们将收到欢迎电子邮件。 此消息包括有关团队的一些信息，以及现在所期望的成员。 来宾必须先通过在电子邮件中选择 " **打开 Microsoft 团队** " 来接受邀请，然后才能访问团队及其频道。
    
![显示欢迎电子邮件示例的屏幕截图](media/guest-experience-image1.png)
    
所有团队成员将在频道线索中看到一条消息，告知团队所有者添加了来宾并提供该来宾的姓名。 团队中的所有人都可以轻松识别谁是来宾。 频道线程右上角的标签表示团队的来宾数，以及每个来宾的名称旁边显示 ** (来宾) ** 标签。

![显示指示团队中的来宾数的标记的屏幕截图](media/guest-experience-image2.png)

查看有关团队中的来宾体验的这些视频：
- [作为来宾加入团队](https://support.office.com/article/join-a-team-as-a-guest-928d1eef-61e2-49ec-b754-c2fe86b34824)
- [加入与来宾的团队会议](https://support.office.com/article/join-a-company-meeting-a120c282-063d-46b8-b973-851197ab75d8)

## <a name="comparison-of-team-member-and-guest-capabilities"></a>工作组成员和来宾功能的比较

下表比较了适用于组织的团队成员及其来宾的团队功能。 团队管理员控制来宾可使用的功能。

|**Teams 中的功能**|**组织中的 Teams 用户**|**来宾用户**|
|:-----|:-----|:-----|
|创建通道  <br/>  *团队所有者控制此设置。*  <br/> |&#x2713;|&#x2713;|
|参与私人聊天  <br/> |&#x2713;|&#x2713;|
|参与频道对话  <br/> |&#x2713;|&#x2713;|
|发布、删除和编辑消息  <br/> |&#x2713;|&#x2713;|
|共享频道文件  <br/> |&#x2713;|&#x2713;|
|访问 SharePoint 文件<br/> |&#x2713;|&#x2713;|
|附加文件<br/> |&#x2713;|&#x2713;|
|下载私人聊天文件<br/> |&#x2713;|&#x2713;|
|在文件中搜索<br/> |&#x2713;||
|共享聊天文件  <br/> |&#x2713;||
|添加应用（选项卡、聊天机器人或连接器）  <br/> |&#x2713;||
|创建会议或访问计划  <br/> |&#x2713;||
|访问 OneDrive for Business 存储  <br/> |&#x2713;||
|创建租户范围和团队/频道来宾访问策略  <br/> |&#x2713;||
|邀请 Microsoft 365 或 Office 365 组织域外部的用户 <br/>  *团队所有者控制此设置。*  <br/> <br/> |&#x2713;||
|创建团队  <br/> |&#x2713;||
|发现和加入公用团队  <br/> |&#x2713;||
|查看组织结构图  <br/> |&#x2713;||
|使用内联转换  <br/> |&#x2713;||
|成为团队所有者  <br/> |&#x2713;||

下表显示了与其他类型的用户相比，来宾可使用的呼叫和会议功能。

| 呼叫功能 | 来宾 | E1 和 E3 用户 | E5 和企业语音用户 |
| --------------- | ----- | -------------- | -------------- |
| VOIP 呼叫 | 是 | 是 | 是 |
| 群组通话 | 是 | 是 | 是 |
| 受支持的核心通话控件（保留、静音、打开/关闭视频、屏幕共享） | 是 | 是 | 是 |
| 转接目标 | 是 | 必需 | 是 |
| 电话可转接 | 是 | 必需 | 是 |
| 可协商转接 | 是 | 必需 | 是 |
| 可通过 VOIP 将其他用户添加到通话中 | 是 | 必需 | 是 |
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
> Azure Active Directory 中的 **来宾用户访问限制** 策略 (azure AD) 确定你的目录中的来宾的权限。 有三种政策选择。
>  - "**来宾用户拥有与成员（最包容）相同的访问权限**"设置表示来宾与目录中的普通用户一样具有相同的目录数据访问权限。
>  - "**来宾用户对目录对象的属性和成员身份拥有有限的访问权限** "设置表示来宾对某些目录任务没有权限，如枚举用户、组或其他使用 Microsoft Graph的目录资源。
>  - "**来宾用户访问权限仅限于其自己的目录对象属性和成员身份（最严格）**"设置表示来宾仅可访问自己的目录对象。
>
>要了解详细信息，请参阅[Azure Active Directory 中的默认用户权限是什么？?](https://go.microsoft.com/fwlink/?linkid=2135493)

## <a name="related-topics"></a>相关主题

[将组织保留为来宾用户](https://docs.microsoft.com/azure/active-directory/b2b/leave-the-organization)