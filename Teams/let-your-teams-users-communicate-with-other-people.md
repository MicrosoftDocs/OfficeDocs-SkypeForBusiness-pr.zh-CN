---
title: 与其他组织中的 Teams 用户通信
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 09/12/2018
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
audience: Admin
search.appverid: MET150
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: ms.teamsadmincenter.externalaccess.overview
description: 了解如何配置团队以允许用户与其他组织中的用户进行通信。
ms.openlocfilehash: e9e2a60c7f1f93df56408976a92e4aa47f3e486e
ms.sourcegitcommit: 75b2cd0d2d39c50dc1e1513860841e2ae3f84324
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/28/2019
ms.locfileid: "34494687"
---
# <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-teams-organization"></a>让你的团队用户与其他团队组织中的用户进行聊天和通信

在下列情况下，请按照本文的步骤进行操作：
  
- 您的企业中有不同域的用户。 例如，Rob@ContosoEast.com 和 Ann@ContosoWest.com。
    
- 您希望组织中的人员可以使用团队与组织外部的特定企业中的人员联系。
    
- 您希望世界上任何其他使用团队的人都能够使用您的电子邮件地址查找和与您联系。 如果您和其他用户都启用了外部访问并允许彼此的域, 则这将起作用。 如果不起作用, 另一用户应确保他或她的配置不会阻止您的域。

这将允许用户查找、呼叫和发送即时消息, 以及设置会议。 如果希望外部用户有权访问团队和频道, 来宾访问可能是更好的途径。 按照本文中的步骤操作, 并确保[启用来宾访问](set-up-guests.md), 以便用户可以进行通信。

> [!IMPORTANT]
> 若要当前将 Microsoft 团队客户端中的外部用户与你的组织外部的外部用户 (当前不是 AAD/租户的来宾) 联合, 则必须正确设置混合并将其移动到 Skype for business Online。 从2/25/2019 起, 团队尚不支持不带 SIP 档案的用户在 Skype for business Online 中托管的本机联合。 有关设置混合帐户和迁移到团队的详细信息, 请参阅将[Skype for Business 混合部署升级到团队](https://docs.microsoft.com/en-us/microsoftteams/upgrade-to-teams-execute-skypeforbusinesshybrid)。

## <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-teams-organization"></a>让你的团队用户与其他团队组织中的用户进行聊天和通信

请按照以下步骤操作。

### <a name="step-1---make-sure-to-set-up-the-ports-and-urls-that-are-needed"></a>步骤 1-确保设置所需的端口和 Url。

**人们在设置企业到企业通信时遇到的最常见的问题是正确完成[Office 365 URL 和 IP 地址范围](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges)。**

### <a name="step-2---enable-your-organization-to-communicate-with-another-teams-organization"></a>步骤 2-使你的组织能够与另一个团队组织通信

![](media/teams-logo-30x30.png) **使用 microsoft 团队管理中心**显示 microsoft 团队徽标的图标

   1. 在左侧导航中, 转到 "**组织范围的设置** > **外部访问**"。 

   2. 在 "**外部访问**" 页面顶部, 单击 "**外部访问** **"**。 

   3. 如果你希望允许所有团队组织与你的组织中的用户进行通信, 请跳至步骤5。 
   
   4. 如果想要限制哪些组织可以与你的组织中的用户进行通信, 你可以允许除某些域之外的所有域, 或者仅允许特定组织。 若要允许除某些域之外的所有域, 请通过单击 "**添加域**" 来添加要阻止的域。 在 "**添加域**" 窗格中, 输入域名, 单击 "已**阻止**", 然后单击 "**完成**"。 若要限制特定 organizatioins 的通信, 请将这些域添加到状态为 "**允许**" 的列表中。 将任何域添加到 "允许" 列表后, 与其他组织的通信将仅限于其域位于 "允许" 列表中的组织。 
   
   5. 单击“**保存**”。 

   6. 然后确保其他团队组织中的管理员执行这些相同步骤。 例如, 在 "**允许的域**" 列表中, 他们的管理员需要为你的企业输入域, 前提是这些组织可以与他们的用户进行通信。 

### <a name="step-3---test-it"></a>步骤 3-测试
若要测试你的设置, 你需要一个不在防火墙后面的团队用户。
  
   1. 当您和组织的管理员更改了**外部访问**设置后, 您应该可以继续。
    
   2. 在 "团队" 应用中, 按电子邮件地址搜索人员, 然后发送聊天请求。
    
   3. 让您的团队联系人向您发送聊天请求。 如果你未收到其请求，那么你的防火墙有问题（假设他们已确认其防火墙设置正确）。
    
   4. 测试问题是否是你的防火墙的另一种方法是转到不在防火墙后面的 wifi 位置 (如咖啡店), 并使用团队向你的联系人发送有关聊天的请求。 如果消息顺利传送，但不是在你工作的时候，那么问题出自你的防火墙。

## <a name="communicate-with-users-in-a-skype-for-business-online-organization"></a>与 Skype for Business Online 组织中的用户进行通信

如果你将其设置为让你的团队用户找到并联系 Skype for business 组织中的用户以限制谁可以联系他们的用户, 你将要求该组织中的管理员执行以下步骤。

![](media/sfb-logo-30x30.png) **使用 skype for business 管理中心**显示 skype for business 徽标的图标 

让该组织中的管理员执行以下步骤:
    
1. 在 Office 365 管理中心中, 转到 "**管理中心** > "**团队 & Skype** > **旧版门户**。
  
2. 在 **Skype for Business 管理中心**，选择“**组织**” > “**外部通信**”。
    
3. 若要设置与特定企业或与其他域中的用户的通信, 请在下拉框中选择 **"仅针对允许的域"**。
    
    或者, 如果他们想要与世界上的所有其他人 (具有打开的 Skype for Business 策略) 进行通信, 请选择 **"开" (阻止的域除外**)。 这是默认设置。
    
4. 在 "**被阻止或允许**的**+** 域" 下, 选择并添加您要允许的域的名称。 请确保其他组织中的管理员执行这些相同步骤。 例如，在其" **允许的域**"列表中，其管理员需要输入贵企业的域。
    
### <a name="related-topics"></a>相关主题

[登录 Microsoft 团队](sign-in-teams.md)
[最终用户培训团队](enduser-training.md)

