---
title: Manage Persistent Chat Server in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c58ee4f4-563b-4d0c-be91-c62df886caa9
description: 摘要：了解如何在 Skype for Business Server 2015 中管理持久聊天服务器。
ms.openlocfilehash: 3fc0027d8984a3c4ea4249f0d44a2d21a4913a3a
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60859999"
---
# <a name="manage-persistent-chat-server-in-skype-for-business-server-2015"></a>Manage Persistent Chat Server in Skype for Business Server 2015
 
**摘要：** 了解如何在 Skype for Business Server 2015 中管理持久聊天服务器。
  
为组织设置持久聊天服务器时，在部署过程中指定初始配置。 但是，有时可能需要更改实现持久聊天服务器支持。 例如，您可能需要为组织中特定的团队或组设置不同的持久聊天服务器支持和控制。 本节提供可帮助您自定义持久聊天服务器部署的信息和过程。 有关您可以为持久聊天服务器配置的特性和功能的详细信息，请参阅 Plan [for Persistent Chat Server in Skype for Business Server 2015。](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md) 有关部署持久聊天服务器的详细信息，请参阅[Deploy Persistent Chat Server in Skype for Business Server 2015。](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md) 

> [!NOTE]
> 持久聊天在 2015 Skype for Business Server可用，但在 2019 年 2 月不再Skype for Business Server支持。 相同的功能在 Teams 中可用。 有关详细信息，请参阅开始[升级Microsoft Teams升级](/microsoftteams/upgrade-start-here)。 如果您需要使用持久聊天，您的选择是迁移需要此功能的用户以Teams或继续使用 Skype for Business Server 2015。 
  
您可以使用控制面板或 cmdlet 管理持久聊天Windows PowerShell服务器。 
  
若要使用控制面板：
  
1. 使用分配给 CsPersistentChatAdministrator 或 CsAdministrator 角色的用户帐户登录到您的本地部署中的任一计算机。
    
2. 从"**开始**"菜单中，Skype for Business Server控制面板或打开浏览器窗口，然后输入管理 URL。
    
3. 在左侧导航栏中，单击"**持久聊天"。**
    
下表总结了可用于Windows PowerShell持久聊天服务器的 cmdlet。 有关语法的详细信息，包括所有可用参数，请参阅 Skype for Business Server [2015 Management Shell](../management-shell.md)。
  

|**Cmdlet**|**说明**|
|:-----|:-----|
|New-CsPersistentChatCategory  <br/> |创建新类别  <br/> |
|Set-CsPersistentChatCategory  <br/> |配置现有类别的设置  <br/> |
|Get-CsPersistentChatCategory  <br/> |检索有关类别的信息  <br/> |
|Remove-CsPersistentChatCategory  <br/> |删除类别  <br/> |
|New-CsPersistentChatRoom  <br/> |创建新的聊天室  <br/> |
|Set-CsPersistentChatRoom  <br/> |配置现有聊天室的设置;将用户和用户组分配给聊天室  <br/> |
|Get-CsPersistentChatRoom  <br/> |检索有关聊天室的信息  <br/> |
|Clear-CsPersistentChatRoom  <br/> |清除聊天室或聊天室的消息  <br/> |
|Remove-CsPersistentChatRoom  <br/> |删除聊天室  <br/> |
|Remove-CsPersistentChatMessage  <br/> |从聊天室中删除邮件  <br/> |
|New-CsPersistentChatAddin  <br/> |创建新的外接程序  <br/> |
|Set-CsPersistentChatAddin  <br/> |配置现有外接程序的设置  <br/> |
|Get-CsPersistentChatAddin  <br/> |检索有关外接程序的信息  <br/> |
|Remove-CsPersistentChatAddin  <br/> |删除加载项  <br/> |
|Set-CsPersistentChatComplianceConfiguration  <br/> |修改现有的合规性配置设置集合  <br/> |
|Export-CsPersistentChatData  <br/> |从持久聊天数据库导出数据  <br/> |
|Import-CsPersistentChatData  <br/> |导入从以前版本的 Lync Server 导出的数据  <br/> |
   

