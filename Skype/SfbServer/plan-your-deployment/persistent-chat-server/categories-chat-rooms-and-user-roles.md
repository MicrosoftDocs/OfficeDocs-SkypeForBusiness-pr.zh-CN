---
title: Skype for Business Server 2015 中的持久聊天类别、聊天室和用户角色
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 8/17/2015
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 343a0563-9ca5-4ad0-b4f3-a72f1d7f1a81
description: 摘要：阅读本主题，了解 Skype for Business Server 2015 中持久聊天服务器的类别、聊天室以及用户和管理员角色。
ms.openlocfilehash: e3740702f43ae677ef451049bfce2a4497a0b992
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58615558"
---
# <a name="persistent-chat-categories-chat-rooms-and-user-roles-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的持久聊天类别、聊天室和用户角色
 
**摘要：** 阅读本主题，了解 2015 年 2015 年持久聊天服务器的类别、聊天室、用户和管理员Skype for Business Server角色。
  
您可以通过创建聊天室类别，然后指定对类别中的类别和聊天室的访问权限来控制对聊天室的访问。 还可以指定各种管理员角色。 本主题介绍： 
  
- 用于组织聊天室的类别
    
- 聊天室和用户角色
    
- 管理员角色

> [!NOTE] 
> 持久聊天在 Skype for Business Server 2015 中可用，但在 2019 年 2 Skype for Business Server不再受支持。 相同的功能在 Teams。 有关详细信息，请参阅[开始升级Microsoft Teams升级](/microsoftteams/upgrade-start-here)。 如果您需要使用持久聊天，则选择将需要此功能的用户迁移到 Teams，或者继续使用 Skype for Business Server 2015。 
    
## <a name="categories-for-organizing-chat-rooms"></a>用于组织聊天室的类别

利用类别，您可以组织聊天室并控制允许哪些用户和组创建或加入这些类别中的聊天室。 每个类别都有关联的属性，这些属性确定可用于该类别中的聊天室的选项。 通过指定用户是允许访问还是拒绝访问，可以控制对特定类别的访问。
  
"允许"和"拒绝的成员"概念的主要原理是信息墙。 例如，银行和财务机构通常设立了阻止贸易商和分析师在实施策略和约定时共享通信的信息隔离区域。 若要满足此要求，管理员可以创建相应类别，以便一个类别允许创建聊天室并允许贸易商使用该聊天室，而另一个类别允许创建聊天室并允许分析师使用该聊天室。 如果父类别阻止了用户，则不能将用户添加为聊天室的成员。
  
> [!IMPORTANT]
> 类别中允许的成员和拒绝的成员与成员角色不同，该角色适用于持久聊天室。> 搜索显示执行搜索的用户位于其"允许"和"拒绝"成员列表中的所有开放和关闭的聊天室。 不会显示加密聊天室，除非进行搜索的用户是加密聊天室的成员。 用户只能搜索自己已经是其成员的聊天室，或者他们可以请求成员身份的聊天室。 
  
## <a name="chat-rooms-and-user-roles"></a>聊天室和用户角色

除了类别允许和拒绝的成员之外，您还可以通过指定以下用户角色来控制对聊天室的访问：创建者、管理者、成员和演示者。
  
- **创建者**：有权创建聊天室的用户。 这些用户位于特定类别的“创建者”列表中：他们可以在该类别中创建聊天室，还可以根据该类别分配成员身份，以及指派管理员管理聊天室。 创建聊天室的用户将自动添加为聊天室的管理员。
    
    > [!NOTE]
    > 成为创建者仅仅为其提供创建聊天室的权限。通过自动升级为管理员，创建者才能够在已创建的聊天服务中进一步细化成员身份、管理员等等。 
  
    此角色使您能够控制在您的组织中创建聊天室的用户，尤其是当您要集中管理聊天室创建活动以强制实施策略和约定并且随后将聊天室管理权委派给组织中的其他用户时。
    
- **管理员**：管理聊天室属性的用户。 聊天室管理员可以修改成员列表（添加和移除成员），以及修改聊天室管理员列表（添加和移除管理员）。 聊天室管理员可以将自己添加到成员或演示者列表（对于大会堂聊天室）中以便他们可以加入聊天室。 聊天室管理员还可以禁用聊天室（管理员可查询已禁用聊天室且可以将其永久删除）。 除聊天室的类别外，管理员可以更改聊天室的所有属性。 创建聊天室后，只有持久聊天管理员可以更改类别。
    
    > [!IMPORTANT]
    > 如果该管理员还是其他类别的创建者，则他/她可以更改该类别以使自己有权创建聊天室。 
  
- **成员**：是聊天室成员的用户。 这些用户可以查看目录中的聊天室 (即使聊天室是机密) ，也可以订阅聊天室 (包括元数据选项（如未读消息、自我筛选器和关键字筛选器) ）并参与聊天室 (可以发布的内容，除非聊天室是只有演示者才能发布、获取内容和搜索) 的大会堂聊天室。 不是聊天室成员的用户可以搜索该聊天室（如果他们位于类别的"允许的成员"列表中，但需要请求访问才能加入这些聊天室来访问内容。  (系统中没有内置的请求访问或审批;这些操作通过电子邮件、电话或其他形式的联系人在外部) 
    
- **演示者**：可以在大会堂聊天室发布消息的用户。
    
## <a name="administrator-roles"></a>管理员角色

以下是持久聊天服务器的管理员角色：
  
- **持久** 聊天管理员：持久聊天管理员角色可以管理聊天室 (修改所有属性，包括成员身份、管理员、类别、将聊天室标记为禁用) ，以及创建和管理定义可以创建和访问聊天室的聊天室类别。 管理员还可以将聊天室标记为禁用并清理不再处于活动状态的聊天室。 管理员不会受到“创建者”或“允许的成员”限制的影响。 管理员可以创建任何类型的聊天室以及将自己添加为任何聊天室的成员。 管理员还可以修改和管理持久聊天配置 (池属性、全局设置和合规性配置) 还可以规划和实施从旧群聊服务器部署到 Skype for Business Server 2015 持久聊天服务器的迁移。
    
    持久聊天管理员能够通过远程使用 Windows PowerShell cmdlet 管理持久聊天 (，即从除持久聊天服务器) 。 持久聊天服务器检查持久聊天管理员是持久聊天服务器前端服务器上 RTC 本地管理员本地组的成员。
    
- **Skype for Business Server 2015 管理员**：负责部署的 Skype for Business Server 2015 的整体企业管理员。
    
- **操作管理员**：负责管理日常操作的用户。
    
- **第三方开发人员和合作伙伴**：第三方开发人员可扩展系统，特别是针对组会话、合规性支持和工具、Web/移动客户端和自动程序开发框架提供信息隔离墙解决方案。
    
## <a name="for-more-information"></a>详细信息

有关配置和管理聊天室和用户角色的信息，请参阅下列主题：
  
- [在 2015 Skype for Business Server持久聊天管理员](../../deploy/deploy-persistent-chat-server/create-a-persistent-chat-administrator.md)
    
- [Manage categories in Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/categories.md)
    
- [Manage chat rooms in Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/chat-rooms.md)
    

