---
title: '管理外部访问 (证平) '
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: vinbel
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.externalaccess.overview
- seo-marvel-mar2020
description: 你的 Teams 管理员或 IT 管理员可以为其他域配置外部访问（联合身份验证），使来自这些域的用户能参与到 Teams 中。
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: e845012b35bddc32c357d416d8fbb2cbe160d84a
ms.sourcegitcommit: 34f407a6a40317056005e3bf38ce58f792c04810
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814188"
---
<a name="manage-external-access-in-microsoft-teams"></a>在 Microsoft Teams 中管理外部访问
======================================================

外部访问是一种让 Teams 用户从整个外部域中查找、通话、聊天和设置 Teams 与你的会议的方式。 你也可以使用外部访问与仍在使用 Skype for Business (Online 和本地) 和 Skype (的预览) 的外部用户通) 。

如果希望外部用户拥有访问团队和频道的权限，则选择使用“来宾访问”可能是更好的方法。 有关外部访问和来宾访问之间的差异的详细信息，请参阅[比较外部访问和来宾访问](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access)。 

在以下情况下使用外部访问：
  
- 你拥有在不同域中需要协作的用户。 例如，Rob@contoso.com 和 Ann@northwindtraders.com 与 contoso.com 和 northwindtraders.com 域中的其他一些人协作处理某个项目。

- 你希望自己组织内的人员使用 Teams 联系组织外特定企业中的人员。

- 你希望世界各地使用 Teams 的所有其他人都能够通过使用你的电子邮件地址找到并联系你。 

> [!IMPORTANT]
> 目前，若要在 Microsoft Teams 应用中联合组织之外的外部用户（即，当前不是你的 Azure Active Directory (Azure AD) 或租户的来宾），你必须已正确设置以便进行混合，并已移至 Skype for Business Online。 自 2019 年 2 月 25 日起，不支持**native**非用户在 Skype for Business Online 上购买的 SIP 配置文件的本机联合身份验证。 有关设置帐户以便进行混合以及随后移至 Teams 的详细信息，请参阅 [将 Skype for Business 混合部署升级到 Teams](https://docs.microsoft.com/microsoftteams/upgrade-to-teams-execute-skypeforbusinesshybrid)。

## <a name="plan-for-external-access"></a>规划外部访问

默认情况下，Teams 中的外部访问处于启用状态，这意味着你的组织可以与所有外部域进行通信。 如果添加阻止的域，将允许所有其他域；如果添加允许的域，将阻止所有其他域。 在 Teams 管理中心（“**组织范围的设置**” > “**外部访问**”）设置外部访问有三种情形：

- **开放式联合身份验证**：这是 Teams 中的默认设置，可让你组织中的用户查找你组织外部任何域中的人员，并与这些人员进行通话、聊天和安排会议。

    在这种情形中，你的用户能够与符合以下条件的所有外部域进行通信：正在运行 Teams 或 Skype for Business，并且正在使用开放式联合身份验证，或者已将你的域添加到他们允许列表中。

- **允许特定域**：通过将域添加到“**允许**”列表中，将外部访问限制为仅允许的域。 设置允许的域列表后，将阻止所有其他域。 若要允许特定域，请单击“**添加域**”，添加域名，单击“**要在此域上执行的操作**”，然后选择“**已允许**”。

- **阻止特定域** - 通过将域添加到“**阻止**”列表中，可与*除阻止的域之外*的所有外部域进行通信。 若要阻止特定域，请单击“**添加域**”，添加域名，单击“**要在此域上执行的操作**”，然后选择“**已阻止**”。 设置阻止的域列表后，将允许所有其他域。

## <a name="allow-or-block-domains"></a>允许或阻止域

### <a name="step-1---enable-your-organization-to-communicate-with-another-teams-or-skype-for-business-organizations"></a>第 1 步 - 让你的组织能够与其他 Teams 或 Skype for Business 组织通信

![显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png)  **使用 Microsoft Teams 管理中心**

1. 在左侧导航栏中，转到“**组织范围的设置**” > “**外部访问**”。

2. 启用“**用户可以与其他 Skype for Business 和 Teams 用户通信**”设置。

     ![已启用“用户可以与其他 Skype for Business 和 Teams 用户通信”设置的屏幕截图](media/manage-external-access-2.png)。

3. 如果想要允许所有 Teams 组织与你组织中的用户进行通信，请跳到步骤 5。

4. 如果想要限制可与你组织中的用户进行通信的组织，你可以允许除某些域之外的所有域，或者你可以仅允许特定域。 

    - 若要允许除某些域之外的所有域，请单击“**添加域**”，添加要阻止的域。 在“**添加域**”窗格中，键入域名，单击“**已阻止**”，然后单击“**完成**”。 
    - 若要限制为仅与特定组织进行通信，请将这些域添加到具有“**已允许**”状态的列表中。 将任何域添加到“允许”列表后，与其他组织的通信将仅限于所在域位于“允许”列表中的组织。 

5. 单击“**保存**”。

6. 确保其他 Teams 组织中的管理员完成了上述相同步骤。 例如，如果他们要限制可与其用户通信的组织，其管理员需要在“**允许的域**”列表中输入你企业的域。

### <a name="step-2---test-it"></a>步骤 2 - 测试

若要测试你的设置，你需要一名不在你防火墙后方的 Teams 用户。
  
1. 在你和你组织的管理员更改了“**外部访问**”设置后，应该可以继续进行操作。

2. 在 Teams 应用中，通过电子邮件地址搜索该用户，并发送聊天请求。

3. 让你的 Teams 联系人向你发送聊天请求。 如果未收到其请求，则问题源于你的防火墙设置（假设他们已确认他们的防火墙设置正确）。

4. 测试问题是否源于防火墙的另一种方法是转到一个不在你防火墙后方的 WiFi 位置。 例如前往某家咖啡店，然后使用 Teams 向联系人发送聊天请求。 如果在这个 WiFi 位置可以顺利传送消息，但在你的工作地点不行，那么可以确定问题源于你的防火墙。

> [!NOTE]
> 如果你和另一名用户都启用了外部访问并允许了彼此的域，应该可以正常工作。 如果不正常，另一名用户应确保其配置未阻止你的域。


## <a name="communicate-with-skype-users-in-preview"></a>与 Skype 用户进行通信（处于预览阶段）

请按照以下步骤，让你组织中的 Teams 用户与 Skype 用户聊天和通话。 然后，Teams 用户可以搜索和启动与 Skype 用户之间的一次性文本对话或音频/视频通话，以及反向操作。

![显示 Microsoft Teams 徽标的图标](media/teams-logo-30x30.png)  **使用 Microsoft Teams 管理中心**

1. 在左侧导航栏中，转到“**组织范围的设置**” > “**外部访问**”。

2. 启用“**用户可与 Skype 用户通信**”设置。

    ![已启用“用户可与 Skype 用户通信”设置的屏幕截图](media/manage-external-access-5.png).

若要深入了解 Teams 用户和 Skype 用户之间的通信方式（包括适用的限制），请参阅 [Teams 和 Skype 的互操作性](teams-skype-interop.md)。

## <a name="common-external-access-scenarios"></a>常见外部访问情形

|**如果希望....**  |**要执行的操作**  |
|---------|-----------------------|
|让你组织中的 **Teams 用户**与另一个（外部）组织中的 **Teams 用户**进行通信。|在“外部访问”中，将外部域添加到“已允许”列表或使用开放式联合身份验证。 然后让另一个 Teams 组织中的管理员执行相同的操作。      |
|让你组织中的 **Teams 用户**与同一组织中的 **Skype for Business Online 用户**进行通信。  |启用共存模式或选择并行升级模式来支持你组织中的 Skype for Business 用户。   |
|让你组织中的 **Teams 用户**与另一个（外部）组织中的 **Skype for Business Online 用户**进行通信。      |在“外部访问”中，将外部域添加到“已允许”列表或使用开放式联合身份验证。 <br><br>在“外部访问”中启用“**用户可以与其他 Skype for Business 和 Teams 用户通信**”设置。 然后让另一个 Teams 组织中的管理员执行相同的操作。 <br><br>**注意**：具有 Skype for Business 用户的外部域必须启用共存模式或选择并行升级模式来支持该组织中的 Skype for Business 用户。|
|让 **你组织** 中的组织中的组织中的组织内部组织内部和 **Skype for Business** () 通信。      |在“外部访问”中，将外部域添加到“已允许”列表或使用开放式联合身份验证。 <br><br>在“外部访问”中启用“**用户可以与其他 Skype for Business 和 Teams 用户通信**”设置。 然后让其他组织中的管理员配置 Skype for Business 本地服务器，以允许与你的域实现混合。|
|让你组织中的 **Teams 用户**与 **Skype** 用户进行通信。<br> （处于预览阶段）  |在“外部访问”中启用“**用户可与 Skype 用户通信**”设置。 |
|让**Skype for Business Online 用户与**其他 Microsoft 365 或 Office 365 中的 Teams 用户通信。 **Teams users**| 如果你的 Skype for Business Online 用户处于以下升级模式之一：Islands、SfBOnly、SfBWIthTeamsCollab、SfBWithTeamsCollabAndMeetings，而另一个组织的 Teams 用户处于 TeamsOnly 模式，那么你的用户可以与另一个组织中的 Teams 用户进行通信。 <br><br>在“外部访问”中启用“**用户可以与其他 Skype for Business 和 Teams 用户通信**”设置。 然后让另一个 Teams 组织中的管理员执行相同的操作。|
|让 **Skype for Business Online 用户与** 其他 Microsoft 365 或 Office 365 中的 **Skype for Business Online** 用户通信。    | 如果你的 Skype for Business Online 用户处于以下升级模式之一：Islands、SfBOnly、SfBWIthTeamsCollab、SfBWithTeamsCollabAndMeetings，而另一个组织的 Skype for Business Online 用户处于以下升级模式之一：Islands、SfBOnly、SfBWIthTeamsCollab、SfBWithTeamsCollabAndMeetings，那么你的用户可以与另一个组织中的 Skype for Business Online 用户进行通信。<br><br>在“外部访问”中启用“**用户可以与其他 Skype for Business 和 Teams 用户通信**”设置。 然后让另一个 Teams 组织中的管理员执行相同的操作。|
|让你的 **Skype for Business Online 用户**与本地组织中的 **Skype for Business 用户**进行通信。     |如果你的用户处于以下某种升级模式，则 Skype for Business Online 用户可以从本地组织与 Skype for Business 用户进行通信：Islands、SfBOnly、SfBWIthTeamsCollab、SfBWithTeamsCollabAndMeetings。 <br><br> 在“外部访问”中启用“**用户可以与其他 Skype for Business 和 Teams 用户通信**”设置。 然后让其他组织中的管理员配置 Skype for Business 本地服务器，以允许与你的域实现混合。|
|让你的 **Skype for Business Online 用户** 与 **Skype 用户**（在你组织的内部或外部）进行通信。   |在“外部访问”中启用“**用户可与 Skype 用户通信**”设置。|

> [!IMPORTANT]
> 你无需添加任何 **Skype 域**作为允许的域，就可以使 Teams 或 Skype for Business Online 用户与你组织内部或外部的 Skype 用户进行通信。 所有 **Skype 域**均列入允许列表，这意味着所有这些域均被视为“已允许”。

## <a name="how-does-external-access-compare-with-guest-access"></a>外部访问与来宾访问有何不同？

若要了解外部访问和来宾访问之间的区别，请参阅[与其他组织的用户通信](communicate-with-users-from-other-organizations.md)。

## <a name="related-topics"></a>相关主题

- [外部（联合身份验证）用户的本机聊天体验](native-chat-for-external-users.md)
