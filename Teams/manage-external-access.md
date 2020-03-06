---
title: 在 Microsoft Teams 中管理外部访问权限（联合身份验证）
author: LolaJacobsen
ms.author: lolaj
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
description: 你的团队或 IT 管理员可以为其他域（联盟）配置外部访问，以使来自这些域的用户参与团队。
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 61ce8219125f6dad47ef516aa9f849acb09ec3dd
ms.sourcegitcommit: 87022aa009eae868e1fd945dc299367e16733a3c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2020
ms.locfileid: "42544988"
---
<a name="manage-external-access-in-microsoft-teams"></a>管理 Microsoft 团队中的外部访问
======================================================

外部访问是来自整个域的外部团队用户在团队中查找、呼叫、聊天和设置会议的一种方式。 您也可以使用外部访问与仍在使用 Skype for business （联机和本地）和 Skype （在预览中）的外部用户进行通信。

如果希望外部用户拥有访问团队和频道的权限，则选择使用来宾访问可能是更好的方法。 有关外部访问和来宾访问之间的差异的详细信息，请参阅[比较外部访问和来宾访问](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access)。 

在以下情况中使用外部访问：
  
- 您在不同的域中拥有需要协作的用户。 例如，Rob@contoso.com 和 Ann@northwindtraders.com 正在与 contoso.com 和 northwindtraders.com 域中的其他人一起处理项目。

- 您希望组织中的人员可以使用团队与组织外部的特定企业中的人员联系。

- 您希望世界上任何其他使用团队的人都能够使用您的电子邮件地址查找和与您联系。 

> [!IMPORTANT]
> 当前，若要将 Microsoft 团队应用内的外部用户联合到你的组织外部的外部用户（当前不是 Azure Active Directory （Azure AD）或租户的来宾），你必须为混合正确设置，并将其移动到 Skype for business Online。 从2019年2月25日起，团队不支持不带 SIP 档案用户在 Skype for business Online 中托管的本机联合身份验证。 有关设置混合帐户和迁移到团队的详细信息，请参阅将[Skype For business 混合部署升级到团队](https://docs.microsoft.com/microsoftteams/upgrade-to-teams-execute-skypeforbusinesshybrid)。

## <a name="plan-for-external-access"></a>规划外部访问

默认情况下，在团队中启用外部访问，这意味着你的组织可以与所有外部域通信。 如果添加被阻止的域，则允许所有其他域;如果您添加允许的域，所有其他域都将被阻止。 在团队管理中心中设置外部访问有三种方案（**组织范围设置** > **外部访问**）：

- **打开联盟**：这是团队中的默认设置，可让你的组织中的人员查找、呼叫、聊天和设置与你的组织外部的人员在任何域中的会议。

    在此方案中，你的用户可以与运行团队或 Skype for business 的所有外部域进行通信，并且使用开放联盟或已将你的域添加到其允许列表。

- **允许特定域**：通过将域添加到 "**允许**" 列表，你可以将外部访问限制为仅允许的域。 设置允许域的列表后，所有其他域都将被阻止。 若要允许特定域，请单击 "**添加域**"，添加域名，单击 "**操作" 以在此域上执行操作**，然后选择 "**允许**"。

- **阻止特定域**-通过将域添加到**阻止**列表，您可以与除已阻止的外部域*之外*的所有外部域进行通信。 若要阻止特定域，请单击 "**添加域**"，添加域名，单击 "**操作" 以在此域上执行操作**，然后选择 "**阻止**"。 设置被阻止域的列表后，将允许所有其他域。

## <a name="allow-or-block-domains"></a>允许或阻止域

### <a name="step-1---enable-your-organization-to-communicate-with-another-teams-organization"></a>步骤 1-使你的组织能够与另一个团队组织通信

![](media/teams-logo-30x30.png)**使用 microsoft 团队管理中心**显示 microsoft 团队徽标的图标  

1. 在左侧导航中，转到 "**组织范围的设置** > **外部访问**"。

2. 打开**用户可与其他 Skype For business 和团队用户进行通信**。

     ![用户可以与打开的其他 Skype for Business 和团队用户进行通信的屏幕截图](media/manage-external-access-2.png).

3. 如果你希望允许所有团队组织与你的组织中的用户进行通信，请跳至步骤5。

4. 如果你想要限制可与组织中的用户进行通信的组织，你可以允许除某些域之外的所有域，或者你只能允许特定的域。 

    - 若要允许除某些域之外的所有域，请单击 "**添加域**" 以添加要阻止的域。 在 "**添加域**" 窗格中，键入域名，单击 "已**阻止**"，然后单击 "**完成**"。 
    - 若要限制特定组织的通信，请将这些域添加到状态为 "**允许**" 的列表中。 将任何域添加到 "允许" 列表后，与其他组织的通信将仅限于其域位于 "允许" 列表中的组织。 

5. 单击“**保存**”。

6. 请确保其他团队组织中的管理员完成这些相同步骤。 例如，在 "**允许的域**" 列表中，他们的管理员需要为您的企业输入域，前提是他们限制了可以与他们的用户进行通信的组织。

### <a name="step-2---test-it"></a>步骤 2-测试

若要测试你的设置，你需要一个不在防火墙后面的团队用户。
  
1. 当您和组织的管理员更改了**外部访问**设置后，您应该可以继续。

2. 在 "团队" 应用中，按电子邮件地址搜索人员，然后发送聊天请求。

3. 让您的团队联系人向您发送聊天请求。 如果你未收到其请求，那么你的防火墙有问题（假设他们已确认其防火墙设置正确）。

4. 测试问题是否是你的防火墙的另一种方法是转到不在防火墙后面的 WiFi 位置。 例如咖啡店，使用团队将请求发送给您的联系人进行聊天。 如果邮件通过 WiFi 位置，但未在工作，则您知道问题是您的防火墙。

> [!NOTE]
> 如果您和其他用户都启用了外部访问并允许另一个用户的域，这将起作用。 如果不起作用，则其他用户应确保其配置未阻止您的域。

## <a name="communicate-with-users-in-a-skype-for-business-online-organization"></a>与 Skype for Business Online 组织中的用户进行通信

如果你要设置外部访问权限，以便你的团队用户在 Skype for Business 组织中查找和联系用户以限制谁可以联系他们的用户，请按照以下步骤设置从你的域到其他组织的域的外部访问。 然后，让其他组织中的管理员按照以下步骤配置 Skype for business Online 的外部访问。

有关常见 Skype for Business Online 方案的特定指导，请参阅下面的[常见外部访问方案](#common-external-access-scenarios)。

![](media/sfb-logo-30x30.png) **使用 skype for business 管理中心**显示 skype for business 徽标的图标

让该组织中的管理员执行以下步骤：

1. 在 Microsoft 365 管理中心，转到 "**管理中心** > "**团队 & Skype** > **旧版门户**。
  
2. 在 **Skype for Business 管理中心**，选择“**组织**” > “**外部通信**”。

3. 若要设置与特定企业或与其他域中的用户的通信，请在下拉框中选择 **"仅针对允许的域"**。

    或者，如果他们想要与世界上的所有其他人（具有打开的 Skype for Business 策略）进行通信，请选择 **"开" （阻止的域除外**）。 这是默认设置。

4. 在 "已**阻止或允许**的**+** 域" 下，选择，然后添加要允许的域的名称。

## <a name="communicate-with-skype-users-in-preview"></a>与 Skype 用户通信（在预览中）

请按照以下步骤，让你的组织中的团队用户与 Skype 用户聊天和呼叫 Skype 用户。 然后，团队用户可以搜索和启动与 Skype 用户之间的一次性文本对话或音频/视频通话，反之亦然。

![](media/teams-logo-30x30.png)**使用 microsoft 团队管理中心**显示 microsoft 团队徽标的图标  

1. 在左侧导航中，转到 "**组织范围的设置** > **外部访问**"。

2. 打开 "**用户可以与 Skype 用户通信**" 设置。

    ![用户可以通过打开的 Skype 设置进行通信的屏幕截图](media/manage-external-access-5.png).

若要深入了解团队用户和 Skype 用户可以进行通信的方式，包括应用的限制，请参阅[团队和 Skype 互操作性](teams-skype-interop.md)。

## <a name="common-external-access-scenarios"></a>常见的外部访问方案

|**如果需要 .。。**  |**执行此操作**  |
|---------|-----------------------|
|让你的组织中的**团队用户**与另一个（外部）组织中的**团队用户**通信。|在 "外部访问" 中，将外部域添加到 "允许列表" 或 "使用开放联盟"。 然后让其他团队组织中的管理员执行相同操作。      |
|让你的组织中的**团队用户**与同一组织中的**Skype for business Online 用户**通信。  |启用共存模式或选择 "孤岛" 升级模式以支持组织中的 Skype for business 用户。   |
|让你的组织中的**团队用户**与另一个（外部）组织中的**Skype for business Online 用户**通信。      |在 "外部访问" 中，将外部域添加到 "允许列表" 或 "使用开放联盟"。 <br><br>打开**用户可与其他 Skype For business 和团队用户通信，** 在外部访问中设置。 然后让其他团队组织中的管理员执行相同操作。 <br><br>**注意**：具有 Skype for business 用户的外部域必须启用共存模式，或者选择 "孤岛" 升级模式以支持该组织中的 Skype for business 用户。|
|让你的组织中的**团队用户**与**Skype**用户通信。<br> （在预览中）  |打开 "外部访问" 中的 "**用户可以与 Skype 用户通信**" 设置。 |
|让**Skype For Business Online 用户**与其他 Office 365 组织中的**团队用户**通信。| 如果你的用户处于以下升级模式之一，则你的 Skype for Business Online 用户可以与其他组织中的团队用户进行通信： SfBOnly、SfBWIthTeamsCollab、SfBWithTeamsCollabAndMeetings;其他组织的团队用户处于 TeamsOnly 模式。 <br><br>打开**用户可与其他 Skype For business 和团队用户通信，** 在外部访问中设置。 然后让其他团队组织中的管理员执行相同操作。|
|让**skype For Business online 用户**与其他 Office 365 组织中的**Skype for business online 用户**通信。    | 如果你的用户处于以下升级模式之一，则你的 Skype for Business Online 用户可以与其他组织中的 Skype for business Online 用户通信： SfBOnly、SfBWIthTeamsCollab、SfBWithTeamsCollabAndMeetings;其他组织的 Skype for Business Online 用户处于以下升级模式之一： SfBOnly、SfBWIthTeamsCollab、SfBWithTeamsCollabAndMeetings。<br><br>打开**用户可与其他 Skype For business 和团队用户通信，** 在外部访问中设置。 然后让其他团队组织中的管理员执行相同操作。|
|让**skype For Business Online 用户**与本地组织中的**skype for business 用户**进行通信。     |如果你的用户处于以下升级模式之一，则你的 Skype for Business Online 用户可以与本地组织中的 Skype for business 用户进行通信： SfBOnly、SfBWIthTeamsCollab、SfBWithTeamsCollabAndMeetings;其他组织的 Skype for Business Online 用户处于以下升级模式之一： SfBOnly、SfBWIthTeamsCollab、SfBWithTeamsCollabAndMeetings。<br><br>打开**用户可与其他 Skype For business 和团队用户通信，** 在外部访问中设置。 然后让其他团队组织中的管理员执行相同操作。|
|让**skype For Business Online 用户**与**skype 用户**通信（在您的组织内部或外部）。   |打开 "外部访问" 中的 "**用户可以与 Skype 用户通信**" 设置。|

> [!IMPORTANT]
> 您不必将任何**Skype 域**添加为 "允许的域"，以便让团队或 Skype For business Online 用户能够与组织内部或外部的 skype 用户进行通信。 所有**Skype 域**均为白名单，这意味着所有这些域均被视为允许。

## <a name="how-does-external-access-compare-with-guest-access"></a>外部访问与来宾访问的比较情况如何？

若要了解外部访问和来宾访问之间的区别，请阅读[与其他组织中的用户进行通信](communicate-with-users-from-other-organizations.md)。

## <a name="related-topics"></a>相关主题

- [外部（联合）用户的本机聊天体验](native-chat-for-external-users.md)
