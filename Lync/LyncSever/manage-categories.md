---
title: 管理类别
TOCTitle: 管理类别
ms:assetid: 1b118d91-b4c4-4b2f-b842-b451417ec2c6
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204719(v=OCS.15)
ms:contentKeyID: 49312156
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 管理类别

 

_**上一次修改主题：** 2012-10-06_

创建新持久聊天服务器类别

    New-CsPersistentChatCategory -Name Foo -PersistentChatPoolFqdn client.contoso1b118d91-b4c4-4b2f-b842-b451417ec2c6.com [other parameters]

> [!IMPORTANT]
> 仅当存在多个持久聊天服务器池时，才需要 PersistentChatPoolFqdn。


更改现有持久聊天服务器类别

    Set-CsPersistentChatCategory -Identity testCat -AllowedMembers @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}  -DeniedMembers @{Add="sip:user2@contoso.com"}
    Set-CsPersistentChatCategory -Identity testCat -Creators @{Add="sip:user1@contoso.com"}

Windows PowerShell：AllowedMembers、DeniedMembers 和 Creators 可以同时设置。Creators 应该是 AllowedMembers 减去 DeniedMembers 的子集。还可以在设置成员和创建者的同时设置类别的属性。

## 创建、获取、设置或删除类别

创建新类别

    New-CsPersistentChatCategory -Name <String> [-PersistentChatPoolFqdn <String>] [-Description <String>] [-EnableInvitations<Switch Parameter>] [-EnableFileUpload <Switch Parameter>] [-RemoveChatHistory <Switch Parameter>] [-MaxContentSize <Integer>]

获取类别

    Get-CsPersistentChatCategory -Identity <String>

或者

    Get-CsPersistentChatCategory -PersistentChatPoolFqdn <String>

设置类别

    Set-CsPersistentChatCategory -Instance <CategoryObject> [-WhatIf] [-Confirm] [<CommonParameters>]

或者

    Set-CsPersistentChatCategory [-Identity] <string> [-Name <string>] [-Description <string>] [-Invitations <bool>] [-FileUpload <bool>] [-ChatHistory <bool>] [-AllowedMembers <PSListModifier[string]>] [-DeniedMembers <PSListModifier[string]>] [-Creators <PSListModifier[string]>] [-WhatIf] [-Confirm]  [<CommonParameters>]

删除类别

    Remove-CsPersistentChatCategory -Instance <CategoryObject> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

或者

    Remove-CsPersistentChatCategory -Identity <String> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

