---
title: Lync Server 2013：规划远程呼叫控制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for remote call control
ms:assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558658(v=OCS.15)
ms:contentKeyID: 48184371
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 99cf4d98f02554e7de344ded843b60406e755a3a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526449"
---
# <a name="planning-for-remote-call-control-in-lync-server-2013"></a>在 Lync Server 2013 中规划远程呼叫控制

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-05_

在 Lync Server 2013 中，支持远程呼叫控制方案使用户能够通过在其台式计算机上使用 Lync 2013 控制其专用的分支 exchange (PBX) 电话。 本节介绍远程呼叫控制功能以及部署远程呼叫控制的要求。

通过 PBX 和 Lync Server 2013 之间的集成，启用远程呼叫控制的用户可以使用 Lync 2013 用户界面 (UI) 通过以下方式控制其 PBX 手机上的呼叫：

<div>


> [!NOTE]  
> 最终，承载用户 PBX 电话的 PBX 的功能将决定可供该用户使用的远程呼叫控制功能。



</div>

  - 发出传出呼叫

  - 应答传入呼叫

  - 使用即时消息应答传入呼叫
    
    <div>
    

    > [!NOTE]  
    > 也就是说，当呼叫者的电话号码可以与组织的全局地址列表中的即时消息地址关联时 (GAL) 、被叫方的 Lync 联系人列表中或联盟伙伴的组织中。

    
    </div>

  - 转接呼叫

  - 转接传入呼叫

  - 将呼叫置于保持状态

  - 交替处理多个并发呼叫

  - 在呼叫过程中应答第二个呼叫（即，呼叫等待）

  - 双音多频 (DTMF) 数字拨号

  - 在“对话”窗口中，键入 Microsoft Office OneNote 的做笔记程序的注释

此外，当用户启用远程呼叫控制时，Lync 2013 向用户提供以下呼叫信息：

  - 当呼叫者的电话号码存在于远程呼叫控制启用的用户的 Microsoft Office Outlook 消息和协作客户端、Lync 联系人列表或组织的 GAL 中时，按名称标识呼叫者。

  - 以前的传入和传出呼叫，保存在 Outlook 的“对话历史记录”文件夹中。

  - 未接来电通知将被发送到用户的 Outlook 收件箱文件夹，但仅当接收到传入呼叫时，才会生成 Lync。

<div>

## <a name="remote-call-control-and-enterprise-voice"></a>远程呼叫控制和企业语音

虽然远程呼叫控制功能是独立于企业语音功能的，并且用户不能同时启用，但企业语音也提供了可供启用远程呼叫控制的用户使用的功能子集。 如果部署了企业语音，则启用远程呼叫控制的用户可以使用 Lync 访问以下企业语音功能：

  - 发出和接收对其他 Lync 客户端的音频呼叫

  - 加入由启用了企业语音的用户创建的会议的音频部分

</div>

<div>

## <a name="in-this-section"></a>本部分内容

  - [Lync Server 2013 中的远程呼叫控制的部署任务](lync-server-2013-deployment-tasks-for-remote-call-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

