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
ms.audience: Admin
search.appverid: MET150
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: ms.teamsadmincenter.externalaccess.overview
description: 请参阅如何配置团队以使用户可以与其他组织中的用户进行通信。
ms.openlocfilehash: c3faf65dd3f36c193a75e74e73d90bf5e9be11df
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30894185"
---
# <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-teams-organization"></a>让您的团队用户聊天并与其他团队组织中的用户进行通信

在下列情况下，请按照本文的步骤进行操作：
  
- 您有用户在不同域中您的业务。 例如，Rob@ContosoEast.com 和 Ann@ContosoWest.com。
    
- 在您的组织团队用于联系外部组织的特定企业中的人员，您希望他人。
    
- 您希望任何其他人在世界上使用团队能够找到并与您联系，使用您的电子邮件地址。 如果您和其他用户同时启用外部访问，并允许彼此的域，这将正常工作。 如果它不起作用，其他用户应确保他或她配置不阻止您的域。

这将使用户能够查找、 呼叫，并向您发送即时消息，以及设置与您的会议。 如果您希望外部用户有权访问工作组和通道，来宾访问可能转更好的方法。 请按照本文和确保到[启用来宾访问](set-up-guests.md)，以便用户可以进行通信。

> [!IMPORTANT]
> 为了当前给外部用户的 Microsoft 团队客户端中联盟组织当前不是您的 AAD/租户的来宾之外，您必须是正确的混合的安装程序和业务 online 移至 Skype。 从 2/25/2019年团队尚未不支持本机联盟用户的情况下被业务 online 驻留在 Skype 的 SIP 配置文件。 有关混合注册您的帐户，然后移到团队的其他设置，请参阅[升级业务混合部署到团队的 Skype](https://docs.microsoft.com/en-us/microsoftteams/upgrade-to-teams-execute-skypeforbusinesshybrid)。

## <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-teams-organization"></a>让您的团队用户聊天并与其他团队组织中的用户进行通信

按照以下步骤。

### <a name="step-1---make-sure-to-set-up-the-ports-and-urls-that-are-needed"></a>步骤 1-请务必设置的端口和所需的 Url。

**人们在设置企业到企业通信时遇到的最常见的问题是正确完成[Office 365 URL 和 IP 地址范围](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges)。**

### <a name="step-2---enable-your-organization-to-communicate-with-another-teams-organization"></a>步骤 2-启用组织与另一个团队组织进行通信

![团队-徽标-30x30.png](media/teams-logo-30x30.png) **使用的 Microsoft 团队管理中心**

   1. 在左侧导航窗格中，转到**组织范围的设置** > **外部访问**。 

   2. 在**外部访问**页的顶部，单击对**上**的**外部访问**。 

   3. 如果您希望允许的所有工作组组织，与您的组织中的用户进行通信，请跳到步骤 5。 
   
   4. 如果您想要限制进行通信的组织可以与用户在组织中可以允许所有但某些域，或仅允许特定的部门。 若要允许所有但某些域，请添加您想要阻止通过单击**添加域**的域。 在**添加域**窗格置于域名，单击**已阻止**，然后**完成**。 若要限制到特定 organizatioins 通信，请将这些域添加到**Alowed**状态的列表。 一旦您已添加到允许列表的任何域，与其他组织的通信将被限制为仅这些组织其域是允许列表中。 
   
   5. 单击“**保存**”。 

   6. 然后确保其他团队组织中的管理员执行相同的步骤。 例如，在其**允许域**列表中，其管理员需要为您的业务输入的域，如果这些限制的组织可以与他们的用户通信。 

### <a name="step-3---test-it"></a>步骤 3-对其进行测试
若要测试您的安装程序，您需要的团队用户在防火墙背后处于不是。
  
   1. 您和从组织管理员已更改的**外部访问**设置后，您应正确运行。
    
   2. 在工作组应用程序中，按电子邮件地址搜索人员并发送一个请求聊天。
    
   3. 让您的团队联系人向您发送请求聊天。 如果你未收到其请求，那么你的防火墙有问题（假设他们已确认其防火墙设置正确）。
    
   4. 测试您的防火墙问题是否另一种方法是转到咖啡馆，如在防火墙背后不处于 wifi 位置并使用团队将请求发送到您的联系人聊天。 如果消息顺利传送，但不是在你工作的时候，那么问题出自你的防火墙。

## <a name="communicate-with-users-in-a-skype-for-business-online-organization"></a>与 Skype 的业务 Online 组织中的用户进行通信

如果您可以将其设置可以让您的团队用户查找和 Skype 限制可以联系的用户的业务组织中的联系人用户，您将询问要执行这些步骤的组织中的管理员。

![sfb-徽标-30x30.png](media/sfb-logo-30x30.png) **的业务管理中心使用 Skype** 

具有管理员，组织执行以下步骤：
    
1. 在 Office 365 管理中心，转到**管理中心** > **团队 & Skype** > **旧门户**。
  
2. 在 **Skype for Business 管理中心**，选择“**组织**” > “**外部通信**”。
    
3. 若要设置通信与特定的企业或用户在另一个域中，在下拉列表框中，选择**在仅允许域**。
    
    或者，是否要启用世界上拥有打开与其他人进行通信的业务策略的 Skype 选择**上除外被阻止的域**。 这是默认设置。
    
4. 在**已阻止或允许的域**，下，选择**+**，添加您希望允许的域的名称。 确保其他组织中的管理员执行相同的步骤。 例如，在其" **允许的域**"列表中，其管理员需要输入贵企业的域。
    
### <a name="related-topics"></a>相关主题

[登录到 Microsoft 团队](sign-in-teams.md)
[最终用户培训团队](enduser-training.md)

