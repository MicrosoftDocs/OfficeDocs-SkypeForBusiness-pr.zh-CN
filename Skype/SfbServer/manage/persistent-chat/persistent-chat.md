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
description: 摘要： 了解如何管理 Persistent Chat Server in Skype for Business Server 2015。
ms.openlocfilehash: 2511de09c321c70d73d824f5fc94bf21fa674131
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20967896"
---
# <a name="manage-persistent-chat-server-in-skype-for-business-server-2015"></a>管理 Skype for Business Server 2015 中的持久聊天服务器
 
**摘要：** 了解如何管理 Persistent Chat Server in Skype 的业务服务器 2015年。
  
当您为组织设置了持久聊天服务器时，则指定部署过程中的初始配置。 但是，有时可能时您想要更改如何实现持久聊天服务器支持。 例如，您可能需要设置持久聊天服务器支持和不同的特定团队或组织内的组的控件。 本节提供的信息和过程可帮助您自定义持久聊天服务器部署。 有关的特性和功能，您可以配置持久聊天服务器的详细信息，请参阅[Plan for Persistent Chat Server in Skype 的业务服务器 2015年](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)。 有关部署持久聊天服务器的详细信息，请参阅[部署持久聊天服务器中的业务服务器 2015 Skype](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)。 

> [!NOTE]
> 持久聊天中的业务服务器 2015 Skype 可用但业务服务器 2019年不再支持在 Skype。 中团队提供了相同的功能。 有关详细信息，请参阅[从企业对 Microsoft 团队的 Skype 旅程](/microsoftteams/journey-skypeforbusiness-teams)。 如果您需要使用持久聊天，您的选择是也迁移要求给团队，此功能的用户或继续对业务服务器 2015年使用 Skype。 
  
使用控制面板，或使用 Windows PowerShell cmdlet，您可以管理持久聊天服务器。 
  
要使用控制面板：
  
1. 使用分配给 CsPersistentChatAdministrator 或 CsAdministrator 角色的用户帐户登录您的本地部署中的任一计算机。
    
2. 从**开始**菜单上，选择业务 Server Control Panel Skype 或打开一个浏览器窗口中，，然后输入管理 URL。
    
3. 在左侧的导航栏中，单击**持久聊天**。
    
下表汇总了可用于帮助您管理持久聊天服务器的 Windows PowerShell cmdlet。 有关语法，包括所有可用的参数的详细信息，请参阅[Skype 的业务服务器 2015年命令行管理程序](../management-shell.md)。
  

|**Cmdlet**|**说明**|
|:-----|:-----|
|New-cspersistentchatcategory  <br/> |创建新类别  <br/> |
|Set-cspersistentchatcategory  <br/> |配置现有类别的设置  <br/> |
|Get-cspersistentchatcategory  <br/> |检索有关类别的信息  <br/> |
|删除 CsPersistentChatCategory  <br/> |删除类别  <br/> |
|New-cspersistentchatroom  <br/> |新建聊天室  <br/> |
|Set-cspersistentchatroom  <br/> |配置现有聊天室的设置；向聊天室分配用户和用户组  <br/> |
|Get-cspersistentchatroom  <br/> |检索有关聊天室的信息  <br/> |
|Clear-cspersistentchatroom  <br/> |清除聊天室或清除聊天室中的消息  <br/> |
|即 Remove-cspersistentchatroom  <br/> |删除聊天室  <br/> |
|删除 CsPersistentChatMessage  <br/> |从聊天室删除消息  <br/> |
|New-cspersistentchataddin  <br/> |创建新的外接程序  <br/> |
|Set-cspersistentchataddin  <br/> |配置现有外接程序的设置  <br/> |
|Get-cspersistentchataddin  <br/> |检索有关外接程序的信息  <br/> |
|删除 CsPersistentChatAddin  <br/> |删除外接程序  <br/> |
|Set-cspersistentchatcomplianceconfiguration  <br/> |修改现有的合规性配置设置集合  <br/> |
|Export-cspersistentchatdata  <br/> |从持久聊天数据库中导出数据  <br/> |
|Import-cspersistentchatdata  <br/> |导入从先前版本 Lync Server 导出的数据  <br/> |
   

