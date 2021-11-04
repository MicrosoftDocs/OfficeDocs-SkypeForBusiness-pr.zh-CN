---
title: 持久聊天类别
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.PersistentChatCategory
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 6875d930-7502-4e47-bdb3-45eaeb065350
description: 您可以使用"持久聊天"页的"类别"部分来配置类别。 持久聊天室类别是组织聊天室的逻辑结构。 类别定义一组默认的访问控制列表 (ACL)，以便控制可以创建或加入聊天室的用户和用户组。 您还可以使用类别强制在组织中不同部门之间使用信息隔离墙。
ms.openlocfilehash: 57e97faa0dd7c3cb80d75f9a06a8f5d2602ba162
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60760840"
---
# <a name="persistent-chat-category"></a>持久聊天类别
 
您可以使用" **持久聊天"** 页的"类别 **"** 部分来配置类别。 持久聊天室类别是组织聊天室的逻辑结构。 类别定义一组默认的访问控制列表 (ACL)，以便控制可以创建或加入聊天室的用户和用户组。 您还可以使用类别强制在组织中不同部门之间使用信息隔离墙。
  
聊天室类别可以包含聊天室，但不包含其他类别。 每个类别都使用元数据（如 Name 和 _Description）__描述_ 其内容。 此外，类别还具有可设置以控制其所属聊天室的行为的属性，例如聊天室是否允许邀请或文件上载，或者包含 _聊天历史记录_。  
  
若要创建新类别，请参阅 Manage [categories in Persistent Chat Server in Skype for Business Server 2015。](../../manage/persistent-chat/categories.md) 如果您是持久聊天管理员，可以使用控制面板或 cmdlet 创建Windows PowerShell类别。
  
## <a name="tasks-that-you-can-perform"></a>可执行的任务

您可以在“类别”页上执行以下任务：
  
- 创建或编辑新类别
    
- 将聊天室从一个类别移动到另一个类别
    
- 删除聊天室或类别
    
## <a name="to-configure-categories-for-chat-rooms"></a>配置聊天室的类别

1. 使用分配给 CsPersistentChatAdministrator 或 CsAdministrator 角色的用户帐户登录到您的本地部署中的任一计算机。
    
2. 从"**开始**"菜单中，Skype for Business Server控制面板或打开浏览器窗口，然后输入管理 URL。
    
3. 在左侧导航栏中，单击“持久聊天”，然后单击“类别”。
    
    对于多个持久聊天服务器池部署，请从下拉列表中选择相应的池。
    
4. 在“类别”页上，单击“新建”或“编辑”。
    
5. 在 **"选择服务**"中，选择与需要创建类别的持久聊天服务器池对应的服务。 该服务是持久聊天服务器池，持久聊天 (客户端) 用于标识类别所属的池。 类别只能属于一个持久聊天服务器池，并且不能移动到另一个池，也不能与另一个池共享。
    
6. 在“新建类别”中，执行下列操作：
    
7. 在“名称”中，指定新聊天室类别的名称。
    
8. 在“描述”中，提供有关聊天室类别（例如 Contoso 聊天室类别）的详细描述。
    
9. 若要控制是否能为属于此类别的聊天室启用邀请，请选中或清除“启用邀请”复选框。 如果选中，此类别中的聊天室将可以打开或关闭邀请；如果清除，则不允许该类别中的聊天室执行邀请操作。 如果聊天室已打开邀请，则当向聊天室中添加一位新成员时，他/她会收到其持久聊天客户端中新聊天室的通知。
    
10. 若要控制属于此类别的聊天室中的文件上载，请选中或清除“启用文件上载”复选框。如果选中，该类别的聊天室可以启用或禁用文件上载；如果清除，则不允许该类别的聊天室执行文件上载操作。
    
     > [!IMPORTANT]
     > 在服务器上强制执行此设置，因为使用 Office Communications Server 2007 R2 群聊服务器或 Lync Server 2010 的自定义应用程序或以前的群聊客户端可以将文件张贴到聊天室。 Lync 2013 客户端没有文件上载/下载功能，因此，如果您具有纯 Lync 2013 部署或 Lync 2013 客户端，则不能将文件张贴在持久聊天服务器聊天室中。 
  
11. 若要控制聊天历史记录，请选中或清除 **"启用聊天历史记录** "复选框。 如果选中，聊天室聊天内容将是持久的；否则，聊天消息将不是持久的。 如果启用了合规性，将合规保存聊天室聊天内容，但用户无法访问较早的消息。 此选项可用于指定为不需要保留聊天历史记录实时临时协作的聊天室。
    
12. 在“编辑类别”中，执行下列操作：
    
    - 在"成员身份"的"允许的成员"部分，添加或删除用户和其他 Active Directory 域服务主体 (用户、通讯组、组织单位等) 允许添加为属于类别的聊天室的成员。 类别允许的主体可以搜索该类别中的聊天室（除非聊天室处于隐藏状态，在这种情况下只有聊天室的成员才能在目录中搜索它）。
    
    - 在 **"成员身份**"中的" **拒绝** 的成员"部分，添加或删除与聊天室中被拒绝的成员关联的用户和其他 Active Directory 主体。
    
    - 在 **"成员身份**"的" **创建者** "部分，添加或删除与类别的创建者关联的用户和其他 Active Directory 主体。 创建者是有权创建聊天室并指定聊天室管理员和成员的用户。
    
13. 单击“提交”。
    
## <a name="see-also"></a>另请参阅

有关持久聊天服务器特性和功能的详细信息，请参阅 Plan [for Persistent Chat Server in Skype for Business Server 2015、Deploy](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md) [Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)和 Manage Persistent Chat Server in [Skype for Business Server2015](../../manage/persistent-chat/persistent-chat.md)。
  

