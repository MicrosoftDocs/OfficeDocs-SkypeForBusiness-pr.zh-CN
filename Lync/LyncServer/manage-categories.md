---
title: 管理类别
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Manage categories
ms:assetid: 1b118d91-b4c4-4b2f-b842-b451417ec2c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204719(v=OCS.15)
ms:contentKeyID: 48183543
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 80aa7ec290611563f3c8a035a5c45fd508f61b43
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42210111"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="manage-categories"></a>管理类别

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-06_

创建新的持久聊天服务器类别

    New-CsPersistentChatCategory -Name Foo -PersistentChatPoolFqdn client.contoso1b118d91-b4c4-4b2f-b842-b451417ec2c6.com [other parameters]

<div>


> [!IMPORTANT]  
> 仅当存在多个持久聊天服务器池时，才需要 PersistentChatPoolFqdn。



</div>

对现有的持久聊天服务器类别进行更改

    Set-CsPersistentChatCategory -Identity testCat -AllowedMembers @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}  -DeniedMembers @{Add="sip:user2@contoso.com"}
    Set-CsPersistentChatCategory -Identity testCat -Creators @{Add="sip:user1@contoso.com"}

Windows PowerShell：可以同时设置 AllowedMembers、DeniedMembers 和创建者。 Creators 应该是 AllowedMembers 减去 DeniedMembers 的子集。 还可以在设置成员和创建者的同时设置类别的属性。

<div>

## <a name="create-get-set-or-remove-a-category"></a>创建、获取、设置或删除类别

创建新类别

    New-CsPersistentChatCategory -Name <String> [-PersistentChatPoolFqdn <String>] [-Description <String>] [-EnableInvitations<Switch Parameter>] [-EnableFileUpload <Switch Parameter>] [-RemoveChatHistory <Switch Parameter>] [-MaxContentSize <Integer>]

获取类别

    Get-CsPersistentChatCategory -Identity <String>

或

    Get-CsPersistentChatCategory -PersistentChatPoolFqdn <String>

设置类别

    Set-CsPersistentChatCategory -Instance <CategoryObject> [-WhatIf] [-Confirm] [<CommonParameters>]

或

    Set-CsPersistentChatCategory [-Identity] <string> [-Name <string>] [-Description <string>] [-Invitations <bool>] [-FileUpload <bool>] [-ChatHistory <bool>] [-AllowedMembers <PSListModifier[string]>] [-DeniedMembers <PSListModifier[string]>] [-Creators <PSListModifier[string]>] [-WhatIf] [-Confirm]  [<CommonParameters>]

删除类别

    Remove-CsPersistentChatCategory -Instance <CategoryObject> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

或

    Remove-CsPersistentChatCategory -Identity <String> [-Force <Switch Parameter>] [-Confirm <Switch Parameter>]

</div>

</div>

<span> </span>

</div>

</div>

</div>

