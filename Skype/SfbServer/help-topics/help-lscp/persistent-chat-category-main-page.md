---
title: 持久聊天类别主页
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.PersistentChatCategoryMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b71c6e6f-681c-4230-954d-3e95ab64ca00
description: 您可以使用“持久聊天”页的“类别”部分配置类别。 持久聊天聊天室类别是组织聊天室的逻辑结构。 类别定义一组默认的访问控制列表 (ACL)，以便控制可以创建或加入聊天室的用户和用户组。 您还可以使用类别强制在组织中不同部门之间使用信息隔离墙。
ms.openlocfilehash: 651e5096d716711b055f8bd6f5ba126c0bc095a8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33910551"
---
# <a name="persistent-chat-category-main-page"></a>持久聊天类别主页
 
您可以使用“**持久聊天**”页的“**类别**”部分配置类别。 持久聊天聊天室类别是组织聊天室的逻辑结构。 类别定义一组默认的访问控制列表 (ACL)，以便控制可以创建或加入聊天室的用户和用户组。 您还可以使用类别强制在组织中不同部门之间使用信息隔离墙。
  
聊天室类别可以包含聊天室，但不包含其他类别。 每个类别描述其内容和元数据，例如_名称_和_说明_。 此外，该类别具有属性可设置来控制行为的聊天室属于该功能，例如，如果聊天室允许_邀请_或_文件上载_，或包含_聊天历史记录_。
  
若要创建新类别，请参阅[Persistent Chat Server 中的业务服务器 2015 Skype 中管理类别](../../manage/persistent-chat/categories.md)。 如果您是 a Persistent Chat Administrator，您可以使用控制面板或 Windows PowerShell cmdlet 创建类别。
  
## <a name="tasks-that-you-can-perform"></a>可执行的任务

您可以在“**类别**”页上执行以下任务：
  
- 创建或编辑新类别
    
- 将聊天室从一个类别移动到另一个类别
    
- 删除聊天室或类别
    
## <a name="to-configure-categories-for-persistent-chat-rooms"></a>配置持久聊天聊天室的类别

1. 使用分配给 CsPersistentChatAdministrator 或 CsAdministrator 角色的用户帐户登录您的本地部署中的任一计算机。
    
2. 从**开始**菜单上，选择业务 Server Control Panel Skype 或打开一个浏览器窗口中，，然后输入管理 URL。 .
    
3. 在左侧导航栏中，单击“**持久聊天**”，然后单击“**类别**”。
    
    对于多个持久聊天服务器池部署，从下拉列表中选择相应的池。
    
4. 在“**类别**”页上，单击“**新建**”或“**编辑**”。
    
5. 在**选择服务**，选择对应于需要创建类别的持久聊天服务器池的服务。 持久聊天服务器池的持久聊天 （客户端） 用于标识其池类别属于该服务。 类别可以属于只有一个持久聊天服务器池，，无法移动到另一个，或与另一个池共享。
    
6. 在“**新建类别**”中，执行下列操作：
    
7. 在“**名称**”中，指定新聊天室类别的名称。
    
8. 在“**描述**”中，提供有关聊天室类别（例如 Contoso 聊天室类别）的详细描述。
    
9. 要控制是否为属于此类别的聊天室启用邀请，请选中或清除“**启用邀请**”复选框。 如果选中，则此类别的聊天室将打开或关闭邀请；如果清除，则不允许此类别的聊天室具有邀请。 如果聊天室具有上时将新的成员添加到聊天室的邀请，他/她获取其持久聊天的客户端中新的聊天室的通知。
    
10. 要控制属于此类别的聊天室中的文件上载，请选中或清除“**启用文件上载**”复选框。如果选中，该类别的聊天室可以启用或禁用文件上载；如果清除，则不允许该类别的聊天室执行文件上载操作。
    
11. 若要控制聊天历史记录，请选中或清除**启用聊天历史记录**复选框。 如果选中，则聊天室聊天内容将变成持久的；否则，将不会保留聊天消息。 如果启用了合规性，则将按合规性保存聊天室聊天内容，但用户无法访问较早的消息。 此选项可用于指定以进行实时、 临时无需聊天历史记录要保留的协作的聊天室。
    
12. 在“**编辑类别**”中，执行下列操作：
    
    - 在**成员资格**，在**允许成员**部分中，添加或删除用户和其他 Active Directory 域服务主体 （用户、 通讯组、 组织单位，等） 允许添加为聊天室的成员属于类别。 类别允许的主体可搜索此类别的聊天室（除非隐藏了聊天室，在这种情况下，仅聊天室的成员可在此目录中搜索聊天室）。
    
    - 中的**成员资格**，**拒绝成员**部分中添加或删除用户和其他与聊天室拒绝的成员关联的 Active Directory 主体。
    
    - 在**成员资格**，在**创建者**部分中，添加或删除用户和其他类别的创建者相关联的 Active Directory 主体。 创建者是有权创建聊天室并指定聊天室管理员和成员的用户。
    
13. 单击“**提交**”。
    
## <a name="see-also"></a>另请参阅

有关详细信息 Persistent Chat Server 特性和功能，请参阅[Plan for Persistent Chat Server in 业务服务器 2015年的 Skype](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)、[部署持久聊天服务器中的 Business Server 2015 Skype](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)和[管理持久聊天服务器在业务服务器 2015 Skype](../../manage/persistent-chat/persistent-chat.md)。
  

