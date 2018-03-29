---
title: 管理 Skype for Business Server 2015 中的持久聊天服务器
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c58ee4f4-563b-4d0c-be91-c62df886caa9
description: 摘要： 了解如何管理业务服务器 2015 Skype 的持久聊天服务器。
ms.openlocfilehash: 294c6bcecbbfb57bb8d2a6a785cdf20775119510
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="manage-persistent-chat-server-in-skype-for-business-server-2015"></a>管理 Skype for Business Server 2015 中的持久聊天服务器
 
**摘要：**了解如何管理业务服务器 2015 Skype 的持久聊天服务器。
  
当持久聊天服务器设置为您的组织时，您指定在部署过程中的初始配置。 但是，可能有的次当想要更改实现持久聊天服务器支持的方式。 例如您可能需要设置持久聊天服务器支持和控件以不同的方式为特定团队或组织中的组。 本节提供的信息和过程以帮助您自定义持久性聊天服务器的部署。 有关的特性和功能可持久聊天服务器的配置的详细信息，请参阅[规划业务服务器 2015年的 Skype 的持久聊天服务器](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)。 有关部署持续聊天服务器的详细信息，请参阅[部署持续聊天中的服务器业务服务器 2015年的 Skype](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)。 
  
通过使用控制面板或通过使用 Windows PowerShell 的 cmdlet，您可以管理持久聊天服务器。 
  
要使用控制面板：
  
1. 使用分配给 CsPersistentChatAdministrator 或 CsAdministrator 角色的用户帐户登录您的本地部署中的任一计算机。
    
2. 从**开始**菜单中，选择 Skype 业务服务器的控制面板或打开浏览器窗口，然后输入管理 URL。
    
3. 在左侧的导航栏中，单击**持续对话**。
    
下表总结了可用于帮助您管理持久聊天服务器的 Windows PowerShell cmdlet。 有关语法，包括所有的可用参数的详细信息请参阅[业务服务器 2015年管理外壳的 Skype](../management-shell.md)。
  

|**Cmdlet**|**说明**|
|:-----|:-----|
|新 CsPersistentChatCategory  <br/> |创建新类别  <br/> |
|一组 CsPersistentChatCategory  <br/> |配置现有类别的设置  <br/> |
|获得 CsPersistentChatCategory  <br/> |检索有关类别的信息  <br/> |
|删除 CsPersistentChatCategory  <br/> |删除类别  <br/> |
|新 CsPersistentChatRoom  <br/> |新建聊天室  <br/> |
|一组 CsPersistentChatRoom  <br/> |配置现有聊天室的设置；向聊天室分配用户和用户组  <br/> |
|获得 CsPersistentChatRoom  <br/> |检索有关房间的信息  <br/> |
|清除-CsPersistentChatRoom  <br/> |清除聊天室或清除聊天室中的消息  <br/> |
|删除 CsPersistentChatRoom  <br/> |删除聊天室  <br/> |
|删除 CsPersistentChatMessage  <br/> |从聊天室删除消息  <br/> |
|新 CsPersistentChatAddin  <br/> |创建新的外接程序  <br/> |
|一组 CsPersistentChatAddin  <br/> |配置现有外接程序的设置  <br/> |
|获得 CsPersistentChatAddin  <br/> |检索有关外接程序的信息  <br/> |
|删除 CsPersistentChatAddin  <br/> |删除外接程序  <br/> |
|一组 CsPersistentChatComplianceConfiguration  <br/> |修改现有的合规性配置设置集合  <br/> |
|导出 CsPersistentChatData  <br/> |从持久聊天数据库中导出数据  <br/> |
|导入 CsPersistentChatData  <br/> |导入从先前版本 Lync Server 导出的数据  <br/> |
   

