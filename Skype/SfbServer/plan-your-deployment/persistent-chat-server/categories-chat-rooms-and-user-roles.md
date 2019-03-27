---
title: Skype for Business Server 2015 中的持久聊天类别、聊天室和用户角色
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 343a0563-9ca5-4ad0-b4f3-a72f1d7f1a81
description: 摘要： 阅读此主题以了解有关类别、 聊天室和用户和管理员角色对于 Persistent Chat Server in Skype 的业务服务器 2015年。
ms.openlocfilehash: 0a65d5d8944d28ba834fac461051f23fcdd98800
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30898857"
---
# <a name="persistent-chat-categories-chat-rooms-and-user-roles-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的持久聊天类别、聊天室和用户角色
 
**摘要：** 阅读此主题以了解有关类别、 聊天室和用户和管理员角色对于 Persistent Chat Server in Skype 的业务服务器 2015年。
  
您可以控制聊天室的访问，方法是创建聊天室类别，然后指定类别以及类别中的聊天室的访问权限。 您也可以指定各种管理员角色。 本主题介绍了： 
  
- 用于组织聊天室的类别
    
- 聊天室和用户角色
    
- 管理员角色

> [!NOTE] 
> 持久聊天中的业务服务器 2015 Skype 可用但业务服务器 2019年不再支持在 Skype。 中团队提供了相同的功能。 有关详细信息，请参阅[从企业对 Microsoft 团队的 Skype 旅程](/microsoftteams/journey-skypeforbusiness-teams)。 如果您需要使用持久聊天，您的选择是也迁移要求给团队，此功能的用户或继续对业务服务器 2015年使用 Skype。 
    
## <a name="categories-for-organizing-chat-rooms"></a>用于组织聊天室的类别

类别允许您组织聊天室并控制可创建或加入这些类别中的聊天室的用户和组。 每个类别都具有关联的属性，这些属性决定了可用于该类别中的聊天室的选项。 您可控制特定类别的访问权限，方法是指定“允许”或“拒绝”用户的访问权限。
  
“允许”和“拒绝”的成员概念的主要原理是信息隔离墙。例如，银行和财务机构通常设立了阻止贸易商和分析师在实施策略和约定时共享通信的信息隔离区域。若要满足此要求，管理员可以创建相应类别，以便一个类别允许创建聊天室并允许贸易商使用该聊天室，而另一个类别允许创建聊天室并允许分析师使用该聊天室。父类别阻止某用户时，将无法把该用户添加为聊天室的成员。
  
> [!IMPORTANT]
> 允许和拒绝类别中的成员不与**成员**角色，它适用于持久聊天 room.> 搜索显示所有打开和关闭聊天室为其执行搜索用户所允许和拒绝的成员身份列表相同。 不会显示加密聊天室，除非进行搜索的用户是加密聊天室的成员。 用户只能搜索自己已经是其成员的聊天室，或者他们可以请求成员身份的聊天室。 
  
## <a name="chat-rooms-and-user-roles"></a>聊天室和用户角色

除了允许的和拒绝的成员的类别，您还可以控制向聊天室的访问通过指定下列用户角色： 创建者、 管理器、 成员和演示者。
  
- **创建者**：有权创建聊天室的用户。这些用户位于特定类别的“创建者”列表中：他们可以创建该类别的聊天室，还可以根据该类别分配成员身份，以及指派管理员管理聊天室。创建聊天室的用户将自动添加为聊天室的管理员。
    
    > [!NOTE]
    > 成为创建者仅仅为其提供创建聊天室的权限。通过自动升级为管理员，创建者才能够在已创建的聊天服务中进一步细化成员身份、管理员等等。 
  
    此角色使您能够控制在您的组织中创建聊天室的用户，尤其是当您要集中管理聊天室创建活动以强制实施策略和约定并且随后将聊天室管理权委派给组织中的其他用户时。
    
- **管理者**：管理聊天室属性的用户。 聊天室管理员可以修改成员列表（添加和移除成员），以及修改聊天室管理员列表（添加和移除管理员）。 聊天室管理员可以将自己添加到成员或演示者列表（对于大会堂聊天室）中以便他们可以加入聊天室。 聊天室管理员还可以禁用聊天室（管理员可查询已禁用聊天室且可以将其永久删除）。 除聊天室的类别外，管理员可以更改聊天室的所有属性。 创建聊天室后，只有持久聊天管理员可以更改的类别。
    
    > [!IMPORTANT]
    > 如果该管理员还是其他类别的创建者，则他/她可以更改该类别以使自己有权创建聊天室。 
  
- **成员**： 用户的聊天室的成员。 这些用户可以看到该目录中的聊天室 （即使聊天室是机密），以及订阅 （包括元数据的选项，如未读的邮件、 自我筛选器和关键字筛选器） 的聊天室，以及参与聊天室 (可以发布，除非聊天室为大会堂聊天室，仅演示者可以发布、 获取内容和搜索）。 不是聊天室的成员的用户可以搜索聊天室它们是否允许成员列表中的类别，但需要请求加入这些聊天室访问内容的访问。 （没有访问请求或系统中内置的审批; 这些的电子邮件、 电话或其他形式的联系人由外部完成）。
    
- **演示者**：可以在大会堂聊天室发布消息的用户。
    
## <a name="administrator-roles"></a>管理员角色

持久聊天服务器的管理员角色如下：
  
- **Persistent Chat Administrator**: 持久聊天管理员角色可以管理聊天室 （修改包括成员资格、 经理、 类别标记为已禁用的聊天室的所有属性），以及创建和管理定义用户的聊天室类别可以创建和访问聊天室。 Administrators can also mark chat rooms as disabled and clean up chat rooms that are no longer active. Administrators are not subject to the Creators or Allowed Members restrictions. Administrators can create any kind of chat room and add themselves as a member to any chat room. 管理员可以修改和管理持久聊天配置 （池属性，全局设置和合规性配置） 和可以还规划和实施迁移从旧群聊服务器部署到 Skype 的业务服务器 2015持久聊天服务器。
    
    持久聊天管理员可使用远程 Windows PowerShell cmdlet 管理持久聊天服务器 (即，从持久聊天服务器之外的计算机)。 持久聊天服务器检查 Persistent Chat Administrator 是持久聊天服务器前端服务器上 RTC Local administrator 本地组的成员。
    
- **Skype 业务服务器 2015年管理员**： 负责部署的 Business Server 2015 的 Skype 的整个企业管理员。
    
- **操作管理员**：负责管理日常操作的用户。
    
- **第三方开发人员和合作伙伴**：第三方开发人员可扩展系统，特别是针对组会话、合规性支持和工具、Web/移动客户端和自动程序开发框架提供信息隔离墙解决方案。
    
## <a name="for-more-information"></a>有关详细信息

有关配置和管理聊天室和用户角色的更多信息，请参阅以下主题：
  
- [在 Skype for Business Server 2015 中创建持久聊天管理员](../../deploy/deploy-persistent-chat-server/create-a-persistent-chat-administrator.md)
    
- [在 Skype for Business Server 2015 中管理持久聊天服务器内的类别](../../manage/persistent-chat/categories.md)
    
- [在 Skype for Business Server 2015 中管理持久聊天服务器内的聊天室](../../manage/persistent-chat/chat-rooms.md)
    

