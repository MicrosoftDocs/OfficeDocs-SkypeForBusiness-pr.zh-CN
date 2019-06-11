---
title: Lync Server 2013：创建或编辑新聊天室
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Creating or editing a new room
ms:assetid: aa8f4349-cfd9-4036-9c4d-de8fb2c4c8a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215880(v=OCS.15)
ms:contentKeyID: 48706008
ms.date: 03/19/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1442454b2afb129fda50d98ed17ccdc2c7ba35c2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830753"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-editing-a-new-room-in-lync-server-2013"></a>在 Lync Server 2013 中创建或编辑新聊天室

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2015-03-19_

配置持久聊天室通常由用户处理;持久聊天管理员通常不会配置或管理聊天室。 用于管理聊天室的 Windows PowerShell cmdlet 仅适用于**CsPersistentChatAdministrator**管理员。

任何给定类别的**创建者**用户都可以使用 Lync 客户端来创建和管理会议室。 被指定为特定聊天室的管理员的用户也可以执行会议室的持续管理, 例如编辑会议室属性或成员身份。

<div>


> [!TIP]  
> 持久聊天管理员也可以是创建者, 它们不受限于创建者的限制。



</div>

或者, 如果您是持久的聊天管理员, 则可以使用用户界面创建和管理聊天室, 而不是使用 Windows PowerShell cmdlet。 为此, SIP-启用持久聊天服务器的管理员, 然后使用 Lync 客户创建和管理聊天室。

如果要为用户创建自定义房间管理工作流, 可以在持久聊天服务器配置上设置**RoomManagementUrl**属性, 以将用户从 Lync 客户端重定向到您的自定义解决方案。

有关使用 Windows PowerShell 命令行界面配置聊天室的详细信息, 请参阅[使用 Windows powershell Cmdlet 配置持久聊天服务器](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)中的 "会议室管理"。

有关配置聊天室的详细信息, 请参阅部署文档中[Lync Server 2013](lync-server-2013-configure-rooms.md)中的 "配置聊天室"。

<div>


> [!NOTE]  
> 持久聊天服务器允许用户为特定网站创建和管理聊天室。 但是, 用户无法在同一拓扑中的其他网站上创建或管理聊天室。 请确保为组织中的所有网站指定聊天室创建者和管理人员。



</div>

<div>


> [!NOTE]  
> 在 Lync Server Survivable 分支设备上托管的用户无法创建新的聊天室或查看现有聊天室的聊天室卡片。



</div>

</div>

<span> </span>

</div>

</div>

</div>

