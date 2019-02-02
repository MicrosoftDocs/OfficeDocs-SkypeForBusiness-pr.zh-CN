---
title: 管理 Microsoft 团队中的外部访问 （联合身份验证）
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 01/30/2019
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: karvell
search.appverid: MET150
description: 您的 IT 管理员可以配置外部访问的其他域 （联合身份验证），以使用户可以从这些域参与团队。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 56e4171421cc52ec1ca79895aba3c0f259d20201
ms.sourcegitcommit: 7f235c2c2cd350e8552a84ae1877b2d659a6aa53
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/01/2019
ms.locfileid: "29708794"
---
<a name="manage-external-access-federation-in-microsoft-teams"></a>管理 Microsoft 团队中的外部访问 （联合身份验证）
======================================================

与 Microsoft 团队外部访问来自其他域的用户可以参加您聊天和呼叫。 您还可以允许外部用户仍使用 for Business 的 Skype 参与。 

外部访问 （联合身份验证） 和来宾访问是不同：

- 来宾访问向个人授予访问权限。 外部访问提供对整个域访问权限。

- 来宾授予访问权限，一次的团队所有者，允许[访问资源](guest-experience.md)，如通道讨论和文件，为来宾特定团队，以及与其他用户被邀请参加的团队中的聊天。 外部访问 （联合聊天），与外部聊天参与者均没有访问权邀请组织的团队或工作组资源。 他们只能参与一对一联盟聊天。 租户管理员可以选择之间的两个通信选项，具体取决于哪个级别的协作是理想与外部方。 管理员可以选择方法或同时，具体取决于其组织的需求，但建议启用更完整、 协作式团队体验的来宾访问。 

请参阅下面的有关外部的比较的表和来宾访问功能。

| 功能 | 外部访问用户 | 来宾访问用户 |
|---------|-----------------------|--------------------|
| 用户可以与另一家公司中的某个人聊天 | 是 |是 |
| 用户可以在另一家公司呼叫某人 | 是 | 是 |
| 用户可以看到另一家公司的某个人是否可用于调用或聊天 | 是 | 是<sup>1</sup> |
| 用户可以搜索外部租户的用户 | 是<sup>2</sup> | 否 |
| 用户可以共享文件 | 否 | 是 |
| 用户可以访问团队资源 | 否 | 是 |
| 可以将用户添加到群聊 | 否 | 是 |
| 可以将用户添加到会议 | 是 | 是 |
| 其他用户可以与外部用户添加到聊天 | 没有<sup>3</sup> | 不适用 |
| 用户被标识为外部方 | 是 | 是 |
| 显示状态 | 是 | 是 |
| 显示邮件是外出 | 否 | 是 |
| 单个用户可以被阻止 | 否 | 是 |
| 支持 @mentions | 否 | 是 |
||||

<sup>1</sup>提供用户已添加以来宾身份，并作为来宾到来宾租户登录。<br>
<sup>2</sup>仅通过电子邮件或会话初始协议 (SIP) 地址。<br>
<sup>3</sup>外部 （联盟） 聊天是仅 1:1。

## <a name="turn-on-or-turn-off-external-access"></a>打开或关闭外部访问

Microsoft 团队 & Business Admin Center 的 Skype 可用于管理外部访问。

1. 在 Microsoft 团队 & Skype 的业务管理中心中，选择**组织范围的设置** > **外部访问**。

     ![组织范围设置外部访问的屏幕截图](media/manage-external-access-1.png).

2. 切换到**打开**或**关闭**的**外部访问**开关。

     ![外部访问开关开启的屏幕截图](media/manage-external-access-2.png).

3. 单击“**保存**”。 

## <a name="add-or-block-a-domain"></a>添加或阻止域

按照以下步骤添加域或关闭外部访问域。

1. 在 Microsoft 团队 & Skype 的业务管理中心中，选择**组织范围的设置** > **外部访问**。

2. 选择**添加域**。 
 
    ![使用的屏幕快照的外部访问页添加域链接](media/manage-external-access-3.png).

   **添加域**窗格中显示。

    ![添加域窗格中的屏幕截图](media/manage-external-access-4.png).


3. 在**添加域**，下键入域名;例如，键入 Contoso.com。

4. 选择**允许**或**阻止**。 您可以更改此设置在任何时间。

2. 选择**完成**。

添加域之后，您将看到的域名和状态添加到外部访问页上的域的列表。

## <a name="more-information"></a>更多信息

有关来宾访问中的 Microsoft 团队的信息，请参阅[管理中的 Microsoft 团队的来宾访问](manage-guests.md)。