---
title: Skype for Business Server 2015 中的持久聊天类别、聊天室和用户角色
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 8/17/2015
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 343a0563-9ca5-4ad0-b4f3-a72f1d7f1a81
description: '摘要: 阅读本主题, 了解 Skype for business Server 2015 中持久聊天服务器的类别、聊天室和用户和管理员角色。'
ms.openlocfilehash: bffdebdf6bbb57165b902026083de5628cdbc404
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2019
ms.locfileid: "35418467"
---
# <a name="persistent-chat-categories-chat-rooms-and-user-roles-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的持久聊天类别、聊天室和用户角色
 
**摘要:** 阅读本主题, 了解 Skype for business Server 2015 中持久聊天服务器的类别、聊天室和用户和管理员角色。
  
您可以控制聊天室的访问，方法是创建聊天室类别，然后指定类别以及类别中的聊天室的访问权限。 您也可以指定各种管理员角色。 本主题介绍了： 
  
- 用于组织聊天室的类别
    
- 聊天室和用户角色
    
- 管理员角色

> [!NOTE] 
> Skype for business Server 2015 中提供了持久聊天, 但 Skype for business Server 2019 不再支持此功能。 团队中提供了相同的功能。 有关详细信息, 请参阅[Microsoft 团队升级](/microsoftteams/upgrade-start-here)入门。 如果需要使用持久聊天, 您可以选择将需要此功能的用户迁移到团队, 或继续使用 Skype for Business Server 2015。 
    
## <a name="categories-for-organizing-chat-rooms"></a>用于组织聊天室的类别

类别允许您组织聊天室并控制可创建或加入这些类别中的聊天室的用户和组。 每个类别都具有关联的属性，这些属性决定了可用于该类别中的聊天室的选项。 您可控制特定类别的访问权限，方法是指定“允许”或“拒绝”用户的访问权限。
  
“允许”和“拒绝”的成员概念的主要原理是信息隔离墙。例如，银行和财务机构通常设立了阻止贸易商和分析师在实施策略和约定时共享通信的信息隔离区域。若要满足此要求，管理员可以创建相应类别，以便一个类别允许创建聊天室并允许贸易商使用该聊天室，而另一个类别允许创建聊天室并允许分析师使用该聊天室。父类别阻止某用户时，将无法把该用户添加为聊天室的成员。
  
> [!IMPORTANT]
> 类别中允许和拒绝的成员与应用于持久聊天室的**成员**角色不同。 > 搜索显示用户在 "允许" 和 "拒绝" 成员列表中执行搜索的所有打开和关闭的聊天室。 不会显示加密聊天室，除非进行搜索的用户是加密聊天室的成员。 用户只能搜索自己已经是其成员的聊天室，或者他们可以请求成员身份的聊天室。 
  
## <a name="chat-rooms-and-user-roles"></a>聊天室和用户角色

除了类别的允许和拒绝成员外, 你还可以通过指定以下用户角色来控制对聊天室的访问: 创建者、管理者、成员和演示者。
  
- **创建者**：有权创建聊天室的用户。这些用户位于特定类别的“创建者”列表中：他们可以创建该类别的聊天室，还可以根据该类别分配成员身份，以及指派管理员管理聊天室。创建聊天室的用户将自动添加为聊天室的管理员。
    
    > [!NOTE]
    > 成为创建者仅仅为其提供创建聊天室的权限。通过自动升级为管理员，创建者才能够在已创建的聊天服务中进一步细化成员身份、管理员等等。 
  
    此角色使您能够控制在您的组织中创建聊天室的用户，尤其是当您要集中管理聊天室创建活动以强制实施策略和约定并且随后将聊天室管理权委派给组织中的其他用户时。
    
- **管理者**：管理聊天室属性的用户。 聊天室管理员可以修改成员列表（添加和移除成员），以及修改聊天室管理员列表（添加和移除管理员）。 聊天室管理员可以将自己添加到成员或演示者列表（对于大会堂聊天室）中以便他们可以加入聊天室。 聊天室管理员还可以禁用聊天室（管理员可查询已禁用聊天室且可以将其永久删除）。 除聊天室的类别外，管理员可以更改聊天室的所有属性。 创建聊天室后, 只有持久聊天管理员才能更改类别。
    
    > [!IMPORTANT]
    > 如果该管理员还是其他类别的创建者，则他/她可以更改该类别以使自己有权创建聊天室。 
  
- **成员**: 是聊天室成员的用户。 这些用户可以查看目录中的聊天室 (即使聊天室是保密的), 还可以订阅聊天室 (包括元数据选项, 如 "未读消息"、"ego 筛选器" 和 "关键字筛选器"), 并参与聊天室 (可以发布, 除非聊天室是只有演示者可以发布、获取内容和搜索的 auditorium 房间。 如果用户不是聊天室的成员, 则可以搜索聊天室 (如果他们位于该类别的 "允许的成员" 列表中), 但需要请求访问权限才能加入这些聊天室以访问内容。 (没有在系统中内置的请求访问权限或审批; 这些权限通过电子邮件、电话或其他形式的联系人外部完成。)
    
- **演示者**：可以在大会堂聊天室发布消息的用户。
    
## <a name="administrator-roles"></a>管理员角色

以下是持久聊天服务器的管理员角色:
  
- **持久聊天管理员**: 持久聊天管理员角色可以管理聊天室 (修改所有属性, 包括成员身份、管理器、类别、将聊天室标记为已禁用), 以及创建和管理聊天室类别, 这些类别定义可以创建和访问聊天室。 Administrators can also mark chat rooms as disabled and clean up chat rooms that are no longer active. Administrators are not subject to the Creators or Allowed Members restrictions. Administrators can create any kind of chat room and add themselves as a member to any chat room. 管理员还可以修改和管理持久聊天配置 (池属性、全局设置和合规性配置), 还可以计划和实施从较旧的组聊天服务器部署到 Skype for business Server 2015 的迁移和实施迁移持久聊天服务器。
    
    持久聊天管理员能够远程使用 Windows PowerShell cmdlet (即从持久聊天服务器之外的计算机) 管理持久聊天服务器。 持久聊天服务器检查永久聊天管理员是否是持久聊天服务器前端服务器上 RTC 本地管理员本地组的成员。
    
- **Skype for Business 服务器2015管理员**: skype For business server 2015 的整体企业管理员负责部署。
    
- **操作管理员**：负责管理日常操作的用户。
    
- **第三方开发人员和合作伙伴**：第三方开发人员可扩展系统，特别是针对组会话、合规性支持和工具、Web/移动客户端和自动程序开发框架提供信息隔离墙解决方案。
    
## <a name="for-more-information"></a>有关详细信息

有关配置和管理聊天室和用户角色的更多信息，请参阅以下主题：
  
- [在 Skype for Business Server 2015 中创建持久聊天管理员](../../deploy/deploy-persistent-chat-server/create-a-persistent-chat-administrator.md)
    
- [在 Skype for Business Server 2015 中管理持久聊天服务器内的类别](../../manage/persistent-chat/categories.md)
    
- [在 Skype for Business Server 2015 中管理持久聊天服务器内的聊天室](../../manage/persistent-chat/chat-rooms.md)
    

