---
title: 管理 Skype for Business Server 2015 中的持久聊天服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c58ee4f4-563b-4d0c-be91-c62df886caa9
description: '摘要: 了解如何在 Skype for Business Server 2015 中管理持久聊天服务器。'
ms.openlocfilehash: 17b9770d2cc3385eb797a1e868c7623f3f09a3ba
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279275"
---
# <a name="manage-persistent-chat-server-in-skype-for-business-server-2015"></a>管理 Skype for Business Server 2015 中的持久聊天服务器
 
**摘要:** 了解如何在 Skype for Business Server 2015 中管理持久聊天服务器。
  
为您的组织设置持久聊天服务器时, 请在部署期间指定初始配置。 但是, 有时你可能需要更改实现持久聊天服务器支持的方式。 例如, 你可能需要为组织内的特定团队或组设置持久聊天服务器支持和控件。 本部分提供了可帮助您自定义持久聊天服务器部署的信息和过程。 有关可针对持久聊天服务器配置的功能和功能的详细信息, 请参阅[在 Skype for Business server 2015 中规划持久聊天服务器](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)。 有关部署持久聊天服务器的详细信息, 请参阅[在 Skype For Business server 2015 中部署持久聊天服务器](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)。 

> [!NOTE]
> Skype for business Server 2015 中提供了持久聊天, 但 Skype for business Server 2019 不再支持此功能。 团队中提供了相同的功能。 有关详细信息, 请参阅[从 Skype For Business 迁移到 Microsoft 团队](/microsoftteams/journey-skypeforbusiness-teams)。 如果需要使用持久聊天, 您可以选择将需要此功能的用户迁移到团队, 或继续使用 Skype for Business Server 2015。 
  
你可以通过使用控制面板或使用 Windows PowerShell cmdlet 管理持久聊天服务器。 
  
要使用控制面板：
  
1. 使用分配给 CsPersistentChatAdministrator 或 CsAdministrator 角色的用户帐户登录您的本地部署中的任一计算机。
    
2. 从 "**开始**" 菜单中, 选择 "Skype For business 服务器" 控制面板或打开一个浏览器窗口, 然后输入管理员 URL。
    
3. 在左侧导航栏中, 单击 "**持久聊天**"。
    
下表总结了可帮助你管理持久聊天服务器的 Windows PowerShell cmdlet。 有关语法的详细信息，包括所有可用参数，请参阅[Skype for Business Server 2015 Management Shell](../management-shell.md)。
  

|**Cmdlet**|**说明**|
|:-----|:-----|
|New-CsPersistentChatCategory  <br/> |创建新类别  <br/> |
|Set-CsPersistentChatCategory  <br/> |配置现有类别的设置  <br/> |
|Get-CsPersistentChatCategory  <br/> |检索有关类别的信息  <br/> |
|Remove-CsPersistentChatCategory  <br/> |删除类别  <br/> |
|New-CsPersistentChatRoom  <br/> |新建聊天室  <br/> |
|Set-CsPersistentChatRoom  <br/> |配置现有聊天室的设置；向聊天室分配用户和用户组  <br/> |
|Get-CsPersistentChatRoom  <br/> |检索有关会议室的信息  <br/> |
|Clear-CsPersistentChatRoom  <br/> |清除聊天室或清除聊天室中的消息  <br/> |
|Remove-CsPersistentChatRoom  <br/> |删除聊天室  <br/> |
|Remove-CsPersistentChatMessage  <br/> |从聊天室删除消息  <br/> |
|New-CsPersistentChatAddin  <br/> |创建新的外接程序  <br/> |
|Set-CsPersistentChatAddin  <br/> |配置现有外接程序的设置  <br/> |
|Get-CsPersistentChatAddin  <br/> |检索有关外接程序的信息  <br/> |
|Remove-CsPersistentChatAddin  <br/> |删除外接程序  <br/> |
|Set-CsPersistentChatComplianceConfiguration  <br/> |修改现有的合规性配置设置集合  <br/> |
|Export-CsPersistentChatData  <br/> |从持久聊天数据库中导出数据  <br/> |
|Import-CsPersistentChatData  <br/> |导入从先前版本 Lync Server 导出的数据  <br/> |
   

