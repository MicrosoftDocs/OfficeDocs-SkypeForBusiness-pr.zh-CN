---
title: Lync Server 2013：规划专用电话线路
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for private telephone lines
ms:assetid: 9cc4f9e1-7b7a-4699-bd05-f16669ef2d21
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412728(v=OCS.15)
ms:contentKeyID: 48184909
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f8051fc18fd42c2c9773d4e0b8904f2923687fe2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184135"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-private-telephone-lines-with-lync-server-2013"></a>规划 Lync Server 2013 的专用电话线路

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-11_

Lync Server 2013 引入了向用户提供第二条专用电话线路以及其主要电话线路的功能。 专用电话线路通常分配给需要一个未列出的电话号码以便他人直接与其取得联系的高管和其他人员。

专用电话线路只能使用 Lync Server 命令行管理程序进行配置。 您不能使用 Lync Server 控制面板配置专用电话线路。 专用电话线路应仅在 Lync Server 的部署中而不是在混合部署中配置。

<div>

## <a name="characteristics-of-private-telephone-lines"></a>专用电话线路的特征

虽然第二条专用电话线路的概念从根本上讲很简单，但是，理解专用线路的特征及其与用户主要电话线路的异同很重要。

<div>

## <a name="general-characteristics-of-private-telephone-lines"></a>专用电话线路的常规特征

  - 每个用户只能有一条专用电话线路。

  - 具有专用电话线路的用户只有一个语音邮箱，并且只使用一个电子邮件地址接收错过的呼叫通知。

  - 具有专用电话线路的用户没有第二个 SIP 地址，并且第二条专用电话线路不会在网络上为用户提供第二个状态（如第二个即时消息身份）。

  - 专用电话线路仅适用于本地部署。 它们在托管的 Lync Server 部署中不可用。

</div>

<div>

## <a name="how-private-telephone-lines-differ-from-primary-telephone-lines"></a>专用电话线路与主要电话线路的不同之处

  - 专用电话线路的电话号码不会显示在派生自 Active Directory 域服务的电话簿或联系人列表中。

  - 专用电话线路没有以下功能：呼叫转接、团队呼叫、委派、团队环、组呼叫应答和响应组应用程序。

  - 对专用电话线路的呼叫有特殊的响铃，呼叫的系统通知会告知用户传入呼叫位于其专用线路上。

  - 对专用电话线路的呼叫始终会发出响铃。它们不会遵循“请勿打扰”规则。

  - 专用电话线路仅限于入站呼叫，不能用于进行传出呼叫。具有专用电话线路的用户发出呼叫时，该呼叫来自于该用户的主要电话线路，并且不会向被叫方隐藏该用户的名称或该用户的主要电话号码。

</div>

<div>

## <a name="how-private-telephone-lines-are-similar-to-primary-telephone-lines"></a>专用电话线路与主要电话线路的相似之处

  - 专用电话线路上的未接听呼叫将路由到与主要电话线路相同的语音邮件收件箱（如果已启用语音邮件）。

  - 呼叫寄存和呼叫应答与专用电话线路协同工作的方式和其与用户主要电话线路协同工作的方式完全相同。

  - 在用户的主要电话线路上启用同时响铃后，也会在专用电话线路上启用该功能。

  - 专用电话线路的电话号码记录在呼叫详细信息记录中，方式与用户主要电话线路的电话号码相同，但会指明这是专用电话号码。

  - 用户应答专用电话线路上的呼叫后，该呼叫的处理方式与该用户的主要电话线路上的呼叫相同。 例如，如果在专用电话线路上接收呼叫的用户转发呼叫或邀请其他人参加会议呼叫，则用户的名称将显示在 Lync 2013 中，并且用户的主要电话线路的电话号码将显示在呼叫者 ID 中。

  - 用户可以转接来自于专用电话线路的呼叫（应答前，将呼叫重定向到其他目标，如移动电话或家庭电话），方式与主要电话线路相同。
    
    <div>
    

    > [!NOTE]  
    > 专用线路的呼叫路由到备用电话号码后，专用电话线路的电话号码将提供给备用电话号码，并可以显示在该号码的日志中。

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > 对于从会议向专用电话线路发出的呼叫，传入系统通知中不会指示“专线”。<EM></EM>

    
    </div>

</div>

</div>

<div>

## <a name="administering-private-telephone-lines"></a>管理专用电话线路

除创建和管理专用电话线路的技术方面外，还需要为其建立管理过程。这包括确定组织中谁可以使用专线的策略，创建和维护人员及其电话号码的列表，还可能要为高管创建专用电话簿，安排用户培训和相关任务。

<div>


> [!NOTE]  
> 专用电话线路将在 Active Directory 中作为用户对象的 msRTCSIP-PrivateLine 属性存储。默认情况下，Authenticated Users 组的任何成员对此属性具有读取访问权限。



</div>

<div>

## <a name="assigning-telephone-numbers"></a>分配电话号码

需要专用电话线路的新用户的帐户是通过使用 Lync Server 控制面板或 Lync Server 命令行管理程序，而不是使用专用电话线路的帐户创建的。

使用 Lync Server 命令行管理程序中的**get-csuser** cmdlet 将电话号码分配给用户的专用电话线路，例如， **get-csuser-Identity "Sip:joe@contoso.com"-PrivateLine "电话： + 14255551212"**。

专用电话线路的电话号码长度可以在3到15个号码之间，并且必须以 "电话：" 前缀开头。 这些号码可以具有任何区号和国家/地区代码，前提是您的组织有该区号和国家/地区代码的外线直拨分机。

有关 cmdlet 和 Lync Server 命令行管理程序的详细信息，请参阅[Lync server 2013 命令行管理](lync-server-2013-lync-server-management-shell.md)程序文档。

</div>

<div>

## <a name="private-telephone-lines-in-mixed-deployments"></a>混合部署中的专用电话线路

专用电话线路仅应配置 Lync Server 的部署。 在其中同时包含 Lync Server 和 Office 通信服务器2007或 Office 通信服务器 2007 R2 服务器的部署中，当早期版本的用户尝试呼叫专用电话线路时，路由呼叫失败，因为服务器无法对专用电话线路执行反向号码查找。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

