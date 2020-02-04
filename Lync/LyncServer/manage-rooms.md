---
title: 管理聊天室
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Manage rooms
ms:assetid: d4835cf4-cd09-4769-a08e-e92706861b64
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205292(v=OCS.15)
ms:contentKeyID: 48185505
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 416da390f277dfc7179a45e0b1dc989b240ab394
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757156"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-rooms"></a>管理聊天室

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-02-21_

创建新的持久聊天服务器聊天室

    New-CsPersistentChatRoom -Name Foo1 -PersistentChatPoolFqdn client.contoso.com -Category client.contoso.com\Foo [other parameters]

<div>


> [!IMPORTANT]  
> 如果满足下列条件之一，则不需要 -PersistentChatPoolFqdn： 
> <UL>
> <LI>
> <P>只有一个持久聊天服务器池。</P>
> <LI>
> <P>您为类别提供了一个池 FQDN。</P>
> <LI>
> <P>您提供了一个池 Fqdn 以添加聊天室。</P></LI></UL>



</div>

对现有持久聊天服务器聊天室进行更改

    Set-CsPersistentChatRoom -Identity testCat -Members @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}
    Set-CsPersistentChatRoom -Identity testCat -Managers @{Add="sip:user2@contoso.com"}
    Set-CsPersistentChatRoom -Identity testCat -Presenters @{Add="sip:user1@contoso.com"}

Windows PowerShell：成员、经理和演示者可以同时进行设置。 它们都应是主机类别的 AllowedMembers 减去 DeniedMembers 的子集。 类型为 normal 的聊天室不能包含演示者。

<div>

## <a name="create-get-set-clear-or-remove-a-room"></a>创建、获取、设置、清除或删除聊天室

创建新聊天室

    New-CsPersistentChatRoom -Name <String> [-PersistentChatPoolFqdn <String>]-Category <String> [-Description <String>] [-Disabled <Switch Parameter>] [-Type <Normal | Auditorium>] [-AddIn <String>] [-Privacy <ChatRoomPrivacy> {Open | Closed | Secret}] [-Invitations <Switch Parameter>]

设置会议室

    Set-CsPersistentChatRoom -Identity <String> [-Name <String>] [-Category <String>] [-Description <String>] [-Disabled <boolean>] [-Type <Normal | Auditorium>] [-AddIn <String>] [-Privacy <ChatRoomPrivacy> {Open | Closed | Secret}] [-Invitations <Enum>] [-Members <PSListModifier<String>>] [-Managers <PSListModifier<String>>] [-Presenters <PSListModifier<String>>] [-Force < Switch Parameter >] [-Confirm <Switch Parameter>][-WhatIf <Switch Parameter>]

获取聊天室

    Get-CsPersistentChatRoom -Identity <String>

或者

    Get-CsPersistentChatRoom -filter <String> [-PersistentChatPoolFqdn <String>] [-SearchDescription] [-Member <String>] [-Manager <string>] [-Category <string>] [-Addin <string>] [-Disabled <bool>] [-Privacy <ChatRoomPrivacy> {Open | Closed | Secret}] [-Type <ChatRoomType> {Normal | Auditorium}] [-Invitations <ChatRoomInvitations> {False | Inherit}] [-ChatContentExceedsMB <int>] [-ResultSize <int>]

其中-筛选器仅支持名称和说明，并可帮助你查找名称/描述与关键字字符串匹配的聊天室。 PoolFqdn 在给定的持久聊天服务器池中进行搜索。

清除聊天室并从聊天室中清除消息

    Clear-CsPersistentChatRoom [-Identity] <string> -EndDate <DateTime> [-WhatIf] [-Confirm]  [<CommonParameters>]

或者

    Clear-CsPersistentChatRoom [-Instance] <ChatRoomObject> -EndDate <DateTime> [-WhatIf] [-Confirm] [<CommonParameters>]

删除聊天室

    Remove-CsPersistentChatRoom [-Identity] <string> [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]

或者

    Remove-CsPersistentChatRoom [-Instance] <ChatRoomObject> [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]

</div>

</div>

<span> </span>

</div>

</div>

</div>

