---
title: 在 Microsoft Teams 中管理外部访问权限（联合身份验证）
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 01/30/2019
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: karvell
search.appverid: MET150
description: IT 管理员可以为其他域 (联盟) 配置外部访问以允许这些域中的用户参与团队。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3f6a3dc6016eb52d58e82e9e9022d1bb8575404b
ms.sourcegitcommit: b9e7a11d8332a029a4f1cd4e396787f5a74f0a44
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2019
ms.locfileid: "34702717"
---
<a name="manage-external-access-federation-in-microsoft-teams"></a>在 Microsoft Teams 中管理外部访问权限（联合身份验证）
======================================================

通过 Microsoft 团队外部访问, 其他域中的用户可以参与您的聊天和通话。 您还可以允许仍在使用 Skype for Business Online 或 Skype for business 本地的外部用户参与。 

外部访问 (联盟) 和来宾访问不同:

- 来宾访问提供对个人的访问权限。 外部访问提供对整个域的访问权限。

- 来宾访问权限由团队所有者授权后, 允许来宾访问特定团队的[资源](guest-experience.md)(如频道讨论和文件), 并与他们被邀请的团队中的其他用户进行聊天。 通过外部访问 (联合聊天), 外部聊天参与者不能访问邀请组织的团队或团队资源。 他们只能参与一对一联合聊天。 租户管理员可以在两种通信选项之间进行选择, 具体取决于外部方需要的协作级别。 管理员可以选择两种方法或两者之一, 具体取决于它们的组织需求, 但我们建议启用来宾访问以实现更完整的协作团队体验。 

有关外部和来宾访问功能的比较, 请参阅下表。

| 功能 | 外部 access 用户 | 来宾访问用户 |
|---------|-----------------------|--------------------|
| 用户可以与其他公司的人员进行聊天 | 是 |是  |
| 用户可以呼叫其他公司中的人员 | 是 | 是  |
| 用户可以查看其他公司的人员是否可以进行呼叫或聊天 | 是 | 是<sup>1</sup> |
| 用户可以跨外部租户搜索用户 | 是<sup>2</sup> | 否 |
| 用户可以共享文件 | 否 | 是 |
| 用户可以访问团队资源 | 否 | 是 |
| 用户可以添加到群组聊天 | 否 | 是 |
| 可将用户添加到会议 | 是 | 是  |
| 可将其他用户添加到与外部用户的聊天 | 无<sup>3</sup> | 不适用 |
| 用户被标识为外部当事方 | 是 | 是  |
| 显示状态 | 是 | 是  |
| 显示 "外出" 消息 | 否 | 是 |
| 可以阻止单个用户 | 否 | 是 |
| 支持 @mentions | 否 | 是 |
| 拨打私人电话 | 是 | 是  |
| 允许 IP 视频 | 是 | 是  |
| 屏幕共享模式 | 是 | 是  |
| 允许立即开会 | 否 | 是 |
| 编辑已发送的邮件 | 是 | 是  |
| 可以删除已发送的邮件 | 是 | 是  |
| 在对话中使用 Giphy | 是 | 是  |
| 在对话中使用 Meme | 是 | 是  |
| 在对话中使用贴纸 | 是 | 是  |
||||

<sup>1</sup>假设已将用户添加为来宾, 并以来宾身份登录到来宾租户。<br>
<sup>2</sup>仅通过电子邮件或会话初始协议 (SIP) 地址。<br>
<sup>3</sup>仅限1:1 的外部 (联合) 聊天。

> [!NOTE]
> 有关来宾功能和来宾体验的详细信息, 请参阅[打开或关闭来宾对 Microsoft 团队的访问权限](https://docs.microsoft.com/microsoftteams/set-up-guests)和[来宾体验等](https://docs.microsoft.com/microsoftteams/guest-experience)。

## <a name="turn-on-or-turn-off-external-access-users-can-communicate-with-skype-for-business-and-teams-users"></a>打开或关闭外部访问 (用户可以与 Skype for Business 和团队用户通信)

你可以使用 Microsoft 团队 & Skype for Business 管理中心来管理外部访问。

1. 在 "Microsoft 团队 & Skype for business 管理中心" 中, 选择 "**组织范围的设置** > **外部访问**"。

     ![组织范围设置外部访问的屏幕截图](media/manage-external-access-1.png).

2. 切换**用户可以与 Skype For business 和团队用户进行通信**切换到 **"打开" 或 "** **关闭**"。

     ![打开了外部访问切换器的屏幕截图](media/manage-external-access-2.png).

3. 单击“**保存**”。 

## <a name="add-or-block-a-domain"></a>添加或阻止域

请按照以下步骤添加域或关闭域的外部访问。

1. 在 "Microsoft 团队 & Skype for business 管理中心" 中, 选择 "**组织范围的设置** > **外部访问**"。

2. 选择“**添加域**”。 
 
    ![带有 "添加域" 链接的外部访问页面的屏幕截图](media/manage-external-access-3.png).

   将显示 "**添加域**" 窗格。

    !["添加域" 窗格的屏幕截图](media/manage-external-access-4.png).


3. 在 "**添加域**" 下, 键入域的名称;例如, 键入 Contoso.com。

4. 选择“**已允许**”或“**已阻止**”。 您可以随时更改此设置。

2. 选择 "**完成**"。

添加域后, 您将看到添加到外部访问页面上的域列表中的域名和状态。

## <a name="more-information"></a>详细信息

有关 Microsoft 团队中的来宾访问的信息, 请参阅[管理 Microsoft 团队中的来宾访问](manage-guests.md)。
