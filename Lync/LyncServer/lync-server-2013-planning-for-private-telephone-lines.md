---
title: 'Lync Server 2013: 规划私人电话线'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for private telephone lines
ms:assetid: 9cc4f9e1-7b7a-4699-bd05-f16669ef2d21
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412728(v=OCS.15)
ms:contentKeyID: 48184909
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4287e4b80b146e26fe5e548c07e5df189b1960e8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824566"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-private-telephone-lines-with-lync-server-2013"></a>在 Lync Server 2013 中规划私人电话线路

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-02-11_

Lync Server 2013 引入了一种除了主要电话线之外为用户提供第二条专用电话线的功能。 专用电话线路通常分配给需要一个未列出的电话号码以便他人直接与其取得联系的高管和其他人员。

专用电话线只能通过 Lync Server 命令行管理程序进行配置。 您不能通过 Lync Server 控制面板配置私人电话线。 专用电话线应仅在 Lync Server 的部署中而不是在混合部署中配置。

<div>

## <a name="characteristics-of-private-telephone-lines"></a>专用电话线路的特征

虽然第二条专用电话线路的概念从根本上讲很简单，但是，理解专用线路的特征及其与用户主要电话线路的异同很重要。

<div>

## <a name="general-characteristics-of-private-telephone-lines"></a>专用电话线路的常规特征

  - 每个用户只能有一条专用电话线路。

  - 具有专用电话线路的用户只有一个语音邮箱，并且只使用一个电子邮件地址接收错过的呼叫通知。

  - 具有专用电话线路的用户没有第二个 SIP 地址，并且第二条专用电话线路不会在网络上为用户提供第二个状态（如第二个即时消息身份）。

  - 专用电话线路仅适用于本地部署。 它们不适用于 Lync Server 的托管部署。

</div>

<div>

## <a name="how-private-telephone-lines-differ-from-primary-telephone-lines"></a>专用电话线路与主要电话线路的不同之处

  - 专用电话线路的电话号码不会显示在派生自 Active Directory 域服务的电话簿或联系人列表中。

  - 专用电话线路不具备以下功能：呼叫转接、团队呼叫、委派、小组电话、组内呼叫应答和响应组应用程序。

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

  - 用户应答专用电话线路上的呼叫后，该呼叫的处理方式与该用户的主要电话线路上的呼叫相同。 例如, 如果通过专用电话线接收呼叫的用户转发呼叫或邀请其他人加入电话会议, 则用户的名称将显示在 Lync 2013 中, 并且用户的主电话线的电话号码将显示在 "来电显示" 中。

  - 用户可以转接来自于专用电话线路的呼叫（应答前，将呼叫重定向到其他目标，如移动电话或家庭电话），方式与主要电话线路相同。
    
    <div>
    

    > [!NOTE]  
    > 专用线路的呼叫路由到备用电话号码后，专用电话线路的电话号码将提供给备用电话号码，并可以显示在该号码的日志中。

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > 对于从会议向专用电话线路发出的呼叫，传入系统通知中不会指示“<EM>专线</EM>”。

    
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

对于需要私人电话线的新用户, 其帐户的创建方式与没有私人电话线的帐户相同, 使用 Lync Server 控制面板或 Lync Server 命令行管理程序。

使用 Lync Server Management Shell 中的**move-csuser** cmdlet 为用户将电话号码分配给专用电话线, 例如, **move-csuser-Identity "Sip:joe@contoso.com"-PrivateLine "电话: + 14255551212"**。

专用电话线的电话号码长度可以介于3到15个号码之间, 并且前面必须带有 "电话:" 前缀。 这些号码可以具有任何区号和国家/地区代码，前提是您的组织有该区号和国家/地区代码的外线直拨分机。

有关 cmdlet 和 Lync Server 命令行管理程序的详细信息, 请参阅[Lync server 2013 管理外壳](lync-server-2013-lync-server-management-shell.md)文档。

</div>

<div>

## <a name="private-telephone-lines-in-mixed-deployments"></a>混合部署中的专用电话线路

专用电话线应仅针对 Lync Server 的部署进行配置。 在具有 Lync Server 和 Office 通信服务器2007或 Office 通信服务器 2007 R2 服务器的部署中, 如果早期版本的用户尝试呼叫专用电话线, 则呼叫路由失败的原因是服务器无法在专用电话线路上执行反向号码查找。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

