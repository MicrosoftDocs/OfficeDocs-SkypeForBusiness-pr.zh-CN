---
title: 管理聊天室
TOCTitle: 管理聊天室
ms:assetid: d4835cf4-cd09-4769-a08e-e92706861b64
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205292(v=OCS.15)
ms:contentKeyID: 49314364
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 管理聊天室

 

_**上一次修改主题：** 2013-02-21_

创建新的 持久聊天服务器聊天室

    New-CsPersistentChatRoom -Name Foo1 -PersistentChatPoolFqdn client.contoso.com -Category client.contoso.com\Foo [other parameters]

> [!IMPORTANT]  
> 如果满足下列条件之一，则不需要 -PersistentChatPoolFqdn：
> <ul>
> <li><p>仅有一个 持久聊天服务器池。</p></li>
> <li><p>您为类别提供了一个池 FQDN。</p></li>
> <li><p>您提供了一个池 Fqdn 以添加聊天室。</p></li>> 
> </ul>

对现有 持久聊天服务器聊天室进行更改

    Set-CsPersistentChatRoom -Identity testCat -Members @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}
    Set-CsPersistentChatRoom -Identity testCat -Managers @{Add="sip:user2@contoso.com"}
    Set-CsPersistentChatRoom -Identity testCat -Presenters @{Add="sip:user1@contoso.com"}

Windows PowerShell：可同时设置成员、管理员和演示者。他们都应为主机类别的 AllowedMembers 减去 DeniedMembers 所得到的子集的一部分。type=normal 的聊天室无法包含演示者。

## 创建、获取、设置、清除或删除聊天室

创建新聊天室

    New-CsPersistentChatRoom -Name <String> [-PersistentChatPoolFqdn <String>]-Category <String> [-Description <String>] [-Disabled <Switch Parameter>] [-Type <Normal | Auditorium>] [-AddIn <String>] [-Privacy <ChatRoomPrivacy> {Open | Closed | Secret}] [-Invitations <Switch Parameter>]

设置聊天室

    Set-CsPersistentChatRoom -Identity <String> [-Name <String>] [-Category <String>] [-Description <String>] [-Disabled <boolean>] [-Type <Normal | Auditorium>] [-AddIn <String>] [-Privacy <ChatRoomPrivacy> {Open | Closed | Secret}] [-Invitations <Enum>] [-Members <PSListModifier<String>>] [-Managers <PSListModifier<String>>] [-Presenters <PSListModifier<String>>] [-Force < Switch Parameter >] [-Confirm <Switch Parameter>][-WhatIf <Switch Parameter>]

获取聊天室

    Get-CsPersistentChatRoom -Identity <String>

或者

    Get-CsPersistentChatRoom -filter <String> [-PersistentChatPoolFqdn <String>] [-SearchDescription] [-Member <String>] [-Manager <string>] [-Category <string>] [-Addin <string>] [-Disabled <bool>] [-Privacy <ChatRoomPrivacy> {Open | Closed | Secret}] [-Type <ChatRoomType> {Normal | Auditorium}] [-Invitations <ChatRoomInvitations> {False | Inherit}] [-ChatContentExceedsMB <int>] [-ResultSize <int>]

其中 –filter 仅支持名称和说明，并可帮助您查找其名称/说明与关键字字符串匹配的聊天室。PoolFqdn 将在给定的 持久聊天服务器池中进行搜索。

清除聊天室并清除聊天室中的消息

    Clear-CsPersistentChatRoom [-Identity] <string> -EndDate <DateTime> [-WhatIf] [-Confirm]  [<CommonParameters>]

或者

    Clear-CsPersistentChatRoom [-Instance] <ChatRoomObject> -EndDate <DateTime> [-WhatIf] [-Confirm] [<CommonParameters>]

删除聊天室

    Remove-CsPersistentChatRoom [-Identity] <string> [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]

或者

    Remove-CsPersistentChatRoom [-Instance] <ChatRoomObject> [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]

