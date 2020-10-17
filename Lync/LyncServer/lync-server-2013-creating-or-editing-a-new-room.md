---
title: Lync Server 2013：创建或编辑新聊天室
description: Lync Server 2013：创建或编辑新聊天室。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or editing a new room
ms:assetid: aa8f4349-cfd9-4036-9c4d-de8fb2c4c8a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215880(v=OCS.15)
ms:contentKeyID: 48706008
ms.date: 03/19/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d822eb05993f77c57200e29364f0a6a68509450b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562978"
---
# <a name="creating-or-editing-a-new-room-in-lync-server-2013"></a>在 Lync Server 2013 中创建或编辑新聊天室

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2015-03-19_

配置持久聊天室通常由用户处理;持久聊天管理员通常不配置或管理聊天室。 用于管理聊天室的 Windows PowerShell cmdlet 仅适用于 **CsPersistentChatAdministrator** 管理员。

任何给定类别中的 **创建者** 的用户都可以使用 Lync 客户端来创建和管理会议室。 已被指定为特定聊天室的管理员的用户也可以对聊天室执行持续的管理，如编辑聊天室属性或成员身份。

<div>


> [!TIP]  
> 持久聊天管理员也可以是创建者，它们不受限于创建者的限制。



</div>

（可选）如果您是持久聊天管理员，则可以使用用户界面来创建和管理聊天室，而不是使用 Windows PowerShell cmdlet。 为此，SIP 启用持久聊天服务器的管理员，然后使用 Lync 客户端来创建和管理聊天室。

如果要为用户创建自定义会议室管理工作流，可以在持久聊天服务器配置上设置 **RoomManagementUrl** 属性，以将用户重定向到 Lync 客户端的自定义解决方案。

有关使用 Windows PowerShell 命令行界面配置聊天室的详细信息，请参阅 [使用 Windows powershell Cmdlet 配置持久聊天服务器](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)中的 "会议室管理"。

有关配置聊天室的详细信息，请参阅部署文档中的在 [Lync Server 2013 中配置会议室](lync-server-2013-configure-rooms.md) 。

<div>


> [!NOTE]  
> 持久聊天服务器允许用户为特定网站创建和管理聊天室。 但是，用户无法在同一拓扑中的其他网站上创建或管理聊天室。 请务必为你组织中的所有网站指定聊天室创建者和经理。



</div>

<div>


> [!NOTE]  
> 驻留在 Lync Server Survivable 分支设备上的用户无法创建新的聊天室或查看现有聊天室的会议室卡片。



</div>

</div>

<span> </span>

</div>

</div>

</div>

