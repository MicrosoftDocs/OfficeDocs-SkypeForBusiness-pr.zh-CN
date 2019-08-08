---
title: 在 Microsoft Teams 中管理外部访问权限（联合身份验证）
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 07/12/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: vinbel
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.externalaccess.overview
description: IT 管理员可以为其他域 (联盟) 配置外部访问以允许这些域中的用户参与团队。
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 71aad6a5b19c1d641347b9e0f119acf2f72d5ce9
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36242125"
---
<a name="manage-external-access-in-microsoft-teams"></a>管理 Microsoft 团队中的外部访问
======================================================

使用 Microsoft 团队外部访问, 其他域中的团队用户可以参与您的聊天和通话。 你还可以允许仍在使用 Skype for Business Online 的 othe 外部用户、本地的 Skype for business 或甚至 Skype for business 参与。

在下列情况下，请按照本文的步骤进行操作：
  
- 您的企业中有不同域的用户: 例如, Rob@contoso.com 和 Ann@northwindtraders.com。

- 您希望组织中的人员可以使用团队与组织外部的特定企业中的人员联系。

- 您希望世界上任何其他使用团队的人都能够使用您的电子邮件地址查找和与您联系。 如果您和其他用户都启用了外部访问并允许彼此的域, 则这将起作用。 如果不起作用, 另一用户应确保他或她的配置不会阻止您的域。

外部访问允许外部用户查找、呼叫和发送即时消息, 以及设置会议。 但是, 如果希望外部用户有权访问团队和频道, 来宾访问可能是更好的途径。 有关外部访问和来宾访问之间的区别的详细信息, 请参阅下面的[外部访问与来宾访问](#external-access-vs-guest-access)。 若要启用来宾访问, 请参阅[启用来宾访问](set-up-guests.md), 以便用户可以进行通信。

> [!IMPORTANT]
> 当前, 若要将 Microsoft 团队应用内的外部用户联合到你的组织外部的外部用户 (当前不是 Azure Active Directory (Azure AD) 或租户的来宾), 你必须为混合正确设置, 并将其移动到 Skype for business Online。 从2/25/2019 起, 团队不支持不带 SIP 档案用户在 Skype for business Online 中托管的本机联合身份验证。 有关设置混合帐户和迁移到团队的详细信息, 请参阅将[Skype For business 混合部署升级到团队](https://docs.microsoft.com/en-us/microsoftteams/upgrade-to-teams-execute-skypeforbusinesshybrid)。

## <a name="external-access-vs-guest-access"></a>外部访问与来宾访问

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
| 屏幕共享模式 | 否 | 是 |
| 允许立即开会 | 否 | 是 |
| 编辑已发送的邮件 | 否 | 是 |
| 可以删除已发送的邮件 | 否 | 是 |
| 在对话中使用 Giphy | 否 | 是 |
| 在对话中使用 meme | 否 | 是 |
| 在对话中使用贴纸 | 否 | 是 |
||||

<sup>1</sup>假设已将用户添加为来宾, 并以来宾身份登录到来宾租户。<br>
<sup>2</sup>仅通过电子邮件或会话初始协议 (SIP) 地址。<br>
<sup>3</sup>仅限1:1 的外部 (联合) 聊天。

有关来宾功能和来宾体验的详细信息, 请参阅[打开或关闭来宾对 Microsoft 团队的访问权限](https://docs.microsoft.com/microsoftteams/set-up-guests)和[来宾体验等](https://docs.microsoft.com/microsoftteams/guest-experience)。

有关团队的免费版本以及它如何处理在外部 Access 中找到的功能的详细信息, 请参阅[Microsoft 团队和 Microsoft 团队之间的差异免费](https://support.office.com/article/differences-between-microsoft-teams-and-microsoft-teams-free-0b69cf39-eb52-49af-b255-60d46fdf8a9c?ui=en-US&rs=en-US&ad=US)。

## <a name="quick-steps-for-scenarios"></a>方案的快速步骤

|**您需要 .。。**  |**快速步骤**  |
|---------|-----------------------|
|你希望让你的组织中的**团队用户**与另一个 (外部) 组织中的**团队用户**通信。|在 "外部访问" 中, 将外部域添加到 "允许列表" 或 "使用开放联盟"。 <p>然后让其他团队组织中的管理员执行相同操作。      |
|您希望让您的组织中的**团队用户**与同一组织中的**Skype for business Online 用户**通信。  |启用共存模式或选择 "孤岛" 升级模式以支持组织中的 Skype for business 用户。   |
|你希望让你的组织中的**团队用户**与另一个 (外部) 组织中的**Skype for business Online 用户**通信。      |在 "外部访问" 中, 将外部域添加到 "允许列表" 或 "使用开放联盟"。  <p>打开**用户可与 Skype For business 和团队用户进行通信**在外部访问中设置。 <p>然后让其他团队组织中的管理员执行相同操作。 <p>**注意**: 具有 Skype for business 用户的外部域必须启用共存模式, 或者选择 "孤岛" 升级模式以支持该组织中的 Skype for business 用户。|
|您希望让您的组织中的**团队用户**与您的组织内部或外部的**Skype**用户进行通信。   | 目前不支持的方案。 <p>**重要提示**: 你的团队用户无法与 Skype 用户通信, 但你的组织中的 Skype for business 用户可以与组织内部或外部的 skype 用户进行通信, 前提是满足这两项要求: <p>1) 打开**用户可以与 skype For business 和团队用户通信**, 并且**skype for business 用户可以与外部 Access 中的 skype 用户设置通信**。 <p> 2) 你的组织正在共存模式下运行。 |
|您希望让**团队用户**与**Skype for business Online 用户**通过本地组织和**skype 用户**与 skype for business Online 用户进行通信。   |在 "外部访问" 中, 将外部域添加到 "允许列表" 或 "使用开放联盟"。 . <p>打开**用户可与 Skype For business 和团队用户进行通信**在外部访问中设置。 <p>打开 Skype for business 用户可以在外部访问中**与 skype 用户进行通信**。 <p> 然后让本地组织中的管理员执行相同操作。<p>**重要提示**在此方案中, 你的团队用户无法与 Skype 用户通信, 但你的组织中的 Skype for business 用户可以与你的组织内部或外部的 Skype 用户通信 (如果你打开**用户可以与 skype For business 通信)和团队用户**和**Skype for business 用户可以与外部 Access 中的 skype 用户设置进行通信**。|
|您希望让**Skype For Business Online 用户**与其他 Office 365 组织中的**团队用户**进行通信。|启用共存模式或选择 "孤岛" 升级模式以支持组织中的 Skype for business 用户。 <p>在 "外部访问" 中, 将外部域添加到 "允许列表" 或 "使用开放联盟"。  <p> 打开**用户可与 Skype For business 和团队用户进行通信**在外部访问中设置。 <p>然后让其他团队组织中的管理员执行相同操作。 |
|您希望让**skype For Business online 用户**与其他 Office 365 组织中的**Skype for business online 用户**进行通信。    | 启用共存模式或选择 "孤岛" 升级模式以支持组织中的 Skype for business 用户。 <p>在 "外部访问" 中, 将外部域添加到 "允许列表" 或 "使用开放联盟"。 <p> 打开**用户可与 Skype For business 和团队用户进行通信**在外部访问中设置。<p>然后让其他团队组织中的管理员执行所有相同操作。 |
|您希望让**skype For Business online 用户**与本地组织中的**Skype for business online 用户**进行通信。     |启用共存模式或选择 "孤岛" 升级模式以支持组织中的 Skype for business 用户。 <p>在 "外部访问" 中, 将外部域添加到 "允许列表" 或 "使用开放联盟"。  <p>打开**用户可与 Skype For business 和团队用户进行通信**在外部访问中设置。  <p> 然后让本地组织中的管理员执行相同操作。 |
|您希望让**skype For Business Online 用户**与**skype 用户**(在您的组织内部或外部) 进行通信。   |启用共存模式或选择 "孤岛" 升级模式以支持组织中的 Skype for business 用户。 <p>打开**skype For business 用户可以在外部访问中与 skype 用户进行通信**。         |
|您希望让**skype For Business online 用户**与其他组织中的**Skype for business online 用户**和您的组织内部或外部的**skype 用户**进行通信。    |启用共存模式或选择 "孤岛" 升级模式以支持组织中的 Skype for business 用户。 <p>在 "外部访问" 中, 将外部域添加到 "允许列表" 或 "使用开放联盟"。  <p> 打开**用户可与 skype For business 和团队用户通信**, 并且**skype for business 用户可以在外部访问中与 skype 用户进行通信**。 <p>然后让其他团队组织中的管理员执行相同操作。       <p> **注意**: 其他外部域的管理员无需打开 skype for business 用户可以在外部访问中**与 skype 用户进行通信**。|

> [!IMPORTANT]
> 您不必将任何 **"Skype 域"** 添加为 "允许的域", 使团队或 Skype For business Online 用户能够与组织内部或外部的 skype 用户进行通信。 所有**Skype 域**均为白名单, 这意味着所有这些域均被视为允许。

## <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-organization"></a>让你的团队用户与其他组织中的用户进行聊天和通信

外部访问允许你的团队和 Skype for business 用户与你的组织外部的其他用户进行通信。 默认情况下, 你的组织可以与所有外部域通信。 如果添加被阻止的域, 则允许所有其他域, 但如果您添加允许的域, 所有其他域都将被阻止。 您可以轻松地为您的组织设置外部访问。 有三种设置方案:

- **方案 1** -您可以使用**开放联盟**。 这是默认设置, 可让你的组织中的人员查找、呼叫和发送即时消息/聊天, 以及与你的组织外部的人员设置会议。

    使用此设置时, 你的用户可以与运行团队或 Skype for business 的所有外部域通信, 并且使用开放联盟或已将你的域添加到允许列表。

- **方案 2** -您可以将域或域添加到 "**允许**" 列表。 若要执行此操作, 请单击 "**添加域**", 添加域名, 单击 "**操作" 以在此域上执行操作**, 然后选择 "**允许**"。 请务必知道, 如果执行此操作, 它将**阻止**所有其他域。

- **情形 3** -您可以将一个或多个域添加到**阻止**列表。 若要执行此操作, 请单击 "**添加域**", 添加域名, 单击 "**操作" 以在此域上执行操作**, 然后选择 "已**阻止**"。 请务必知道, 如果您这样做, 它将**允许**所有其他域。

请按照以下步骤操作以允许或阻止域。

### <a name="step-1---enable-your-organization-to-communicate-with-another-teams-organization"></a>步骤 1-使你的组织能够与另一个团队组织通信

![](media/teams-logo-30x30.png)**使用 microsoft 团队管理中心**显示 microsoft 团队徽标的图标  

1. 在左侧导航中, 转到 "**组织范围的设置** > **外部访问**"。

2. 切换**用户可以与 Skype For business 和团队用户进行通信,** 切换到 **"打开"**。

     ![打开了外部访问切换器的屏幕截图](media/manage-external-access-2.png).

3. 如果你希望允许所有团队组织与你的组织中的用户进行通信, 请跳至步骤5。

4. 如果你想要限制可与组织中的用户进行通信的组织, 你可以允许除某些域之外的所有域, 或者你只能允许特定的域。 

    - 若要允许除某些域之外的所有域, 请单击 "**添加域**" 以添加要阻止的域。 在 "**添加域**" 窗格中, 键入域名, 单击 "已**阻止**", 然后 clik "**完成**"。 
    - 若要限制特定组织的通信, 请将这些域添加到状态为 "**允许**" 的列表中。 将任何域添加到 "允许" 列表后, 与其他组织的通信将仅限于其域位于 "允许" 列表中的组织。 

5. 单击“**保存**”。

6. 请确保其他团队组织中的管理员完成这些相同步骤。 例如, 在 "**允许的域**" 列表中, 他们的管理员需要为您的企业输入域, 前提是他们限制了可以与他们的用户进行通信的组织。

### <a name="step-2---test-it"></a>步骤 2-测试

若要测试你的设置, 你需要一个不在防火墙后面的团队用户。
  
1. 当您和组织的管理员更改了**外部访问**设置后, 您应该可以继续。

2. 在 "团队" 应用中, 按电子邮件地址搜索人员, 然后发送聊天请求。

3. 让您的团队联系人向您发送聊天请求。 如果你未收到其请求，那么你的防火墙有问题（假设他们已确认其防火墙设置正确）。

4. 测试问题是否是你的防火墙的另一种方法是转到不在防火墙后面的 wifi 位置。 例如咖啡店, 使用团队将请求发送给您的联系人进行聊天。 如果邮件通过 wifi 位置, 但未在工作, 则您知道问题是您的防火墙。

## <a name="communicate-with-users-in-a-skype-for-business-online-organization"></a>与 Skype for Business Online 组织中的用户进行通信

如果你要设置外部访问权限, 让你的团队用户找到并联系 Skype for business 组织中的用户以限制谁可以联系他们的用户, 请按照以下步骤设置从你的域到其他组织的域的外部访问。 然后, 让其他组织中的管理员按照以下步骤配置 Skype for business Online 的外部访问。

![](media/sfb-logo-30x30.png) **使用 skype for business 管理中心**显示 skype for business 徽标的图标

让该组织中的管理员执行以下步骤:

1. 在 Microsoft 365 管理中心, 转到 "**管理中心** > "**团队 & Skype** > **旧版门户**。
  
2. 在 **Skype for Business 管理中心**，选择“**组织**” > “**外部通信**”。

3. 若要设置与特定企业或与其他域中的用户的通信, 请在下拉框中选择 **"仅针对允许的域"**。

    或者, 如果他们想要与世界上的所有其他人 (具有打开的 Skype for Business 策略) 进行通信, 请选择 **"开" (阻止的域除外**)。 这是默认设置。

4. 在 "已**阻止或允许**的**+** 域" 下, 选择, 然后添加要允许的域的名称。

## <a name="related-topics"></a>相关主题

有关 Microsoft 团队中的来宾访问的信息, 请参阅[管理 Microsoft 团队中的来宾访问](manage-guests.md)。
