---
title: Lync Server 2013：配置对外部用户访问的支持
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring support for external user access
ms:assetid: f8424f8c-f965-4414-8485-30f07e10214a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413051(v=OCS.15)
ms:contentKeyID: 48185874
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f10e266674d102b25753aeb58c89a365e7bb8e7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837181"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-support-for-external-user-access-in-lync-server-2013"></a>在 Lync Server 2013 中配置对外部用户访问的支持

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-02-21_

部署边缘服务器或边缘池是支持外部用户的第一步。 有关部署边缘服务器的详细信息, 请参阅部署文档中[Lync Server 2013 中的 "部署外部用户访问](lync-server-2013-deploying-external-user-access.md)"。 策略配置的一个重要考虑因素是了解策略的优先级以及策略的应用方式。 在一个策略级别应用的 Lync Server 策略设置可以覆盖在其他策略级别应用的设置。 Lync 服务器策略优先级为: 用户策略 (最受影响) 覆盖网站策略, 然后网站策略覆盖全局策略 (最不影响)。 这意味着，策略设置与策略所影响的对象距离越近，它对该对象的影响力越大。

完成边缘服务器或边缘池的设置后, 必须启用要提供的外部用户访问类型, 并配置外部访问的设置。 在 Lync Server 2013 中, 你可以使用 Lync Server 控制面板、Lync Server Management Shell 或两者 (基于任务要求) 启用和配置外部用户访问和策略。

若要支持外部用户访问, 必须执行以下两项操作:

  - **启用组织**   支持对于你的部署中的外部用户访问, 你可以启用希望支持的每种外部访问类型。 通过在 Lync Server 控制面板的 "**联盟和外部访问**" 组中编辑全局设置或在 "**外部访问策略**" 页面上创建和配置网站或用户策略, 可启用和禁用对外部用户访问的支持或者使用 Lync Server 命令行管理程序和关联的 cmdlet。 用于管理**外部访问策略**的 Cmdlet 位于[Lync Server 2013 中的主题联盟和外部访问 cmdlet](https://docs.microsoft.com/powershell/module/skype/)中。 启用对外部访问的支持指定运行 Lync Server Access Edge 服务的服务器支持与外部用户和服务器的通信。 外部用户访问被禁用, 或者策略尚未配置为支持它时, 内部和外部用户无法进行通信。

  - **配置和分配一个或多个策略**   以支持外部用户访问, 请配置策略来解决要求, 包括:
    
      - ****   使用网站或用户作用域创建的外部访问策略 (默认情况下存在全局策略且没有启用的设置)。 你可以创建和配置策略来控制使用一个或多个类型的外部用户访问权限, 包括联合用户访问 (包括 (如果已选中、联盟 XMPP 域) 远程用户访问以及受支持的公共 IM 服务提供商。 在 "**联盟和外部访问**" 组中的 "**外部访问策略**" 页面上, 使用全局策略或一个或多个管理员创建的网站和用户策略在 Lync Server 控制面板中配置外部策略。 无法删除全局策略。 你可以创建和配置你希望用于限制特定网站或用户的外部用户访问的任何网站和用户策略。 全局和网站策略将自动分配。 如果创建和配置用户策略, 则必须使用 "**用户**" 页面上 "Lync Server 控制面板" 中的 "用户配置" 页面将其分配给特定用户。 查找要应用此策略的一个或一用户, 然后分配该策略。 要对其应用。 若要为用户分配已配置的用户策略, 请参阅[在 Lync Server 2013 中将外部用户访问策略分配给启用 Lync 的用户](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)。 每个外部用户访问策略都可以支持下列一项或多项操作: 远程用户访问、SIP 联合用户访问、XMPP 联盟用户访问和公共 IM 连接。
    
      - **会议策略**   您创建和配置策略来控制组织中的会议, 包括组织中哪些用户可以邀请匿名用户参与会议。 在 Lync Server "控制面板 **会议**" 页面上是全局、网站和用户范围内的策略设置, 用于控制实际会议的设置。 有关详细信息, 请参阅[在 Lync Server 2013 中管理会议和会议](lync-server-2013-managing-meetings-and-conferences.md)。 在 "**访问边缘配置**" 页面上为会议、远程用户和联盟用户启用匿名用户。 **访问边缘配置**上的策略在范围内为全局。 没有可用于定义网站或用户策略的选项。 通过使用全局、网站或用户策略设置, 可在**外部访问策略**页面上控制范围。
        
        例如, 如果要允许用户创建、邀请和管理与远程用户的会议, 则必须在**外部访问策略**全局、网站或用户策略上设置 "**启用与远程用户的通信**", 并**启用通信使用**"**访问边缘配置**" 页面上的远程用户。 同样, 若要允许具有已定义关系的匿名用户或联盟合作伙伴的会议 (如配置的联合 SIP 域和提供商-XMPP 联盟不支持会议), 请设置 "**启用通信"通过公共用户**和**外部访问策略**全局、网站或用户策略中的**联盟用户启用通信**。 然后, 选择 "已获取的全局策略设置", 在 "**访问边缘配置**" 页面上**启用对会议的匿名用户访问**并**启用联盟和公共 IM 连接**。

你可以配置外部用户访问设置, 包括你希望用于控制外部用户访问的任何策略, 即使你未启用组织的外部用户访问权限也是如此。 但是, 你配置的策略和其他设置仅在你为你的组织启用外部用户访问时才有效。 当外部用户访问被禁用或者没有配置任何外部用户访问策略来支持它时, 外部用户无法与组织用户通信。

边缘部署对外部用户的类型进行身份验证 (匿名用户除外, 这些用户是通过会议 ID 进行身份验证的, 而在创建会议和邀请参与者时发送给匿名参与者) 和控件的密钥基于配置 edge 支持的方式进行访问。 为了控制通信, 你可以配置一个或多个策略, 并配置定义你的部署内部和外部的用户之间如何相互通信的设置。 除了可创建和配置以启用特定网站或用户的一种或多种类型的外部用户访问的网站和用户策略之外, 策略和设置包括外部用户访问的默认全局策略。

<div>

## <a name="in-this-section"></a>本节内容

  - [在 Lync Server 2013 中配置策略以控制远程用户访问](lync-server-2013-configure-policies-to-control-remote-user-access.md)

  - [在 Lync Server 2013 中启用或禁用远程用户访问](lync-server-2013-enable-or-disable-remote-user-access.md)

  - [在 Lync Server 2013 中启用或禁用匿名用户访问](lync-server-2013-enable-or-disable-anonymous-user-access.md)

  - [在 Lync Server 2013 中分配会议策略以支持匿名用户](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

