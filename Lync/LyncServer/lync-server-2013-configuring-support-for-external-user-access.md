---
title: Lync Server 2013：配置对外部用户访问的支持
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring support for external user access
ms:assetid: f8424f8c-f965-4414-8485-30f07e10214a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413051(v=OCS.15)
ms:contentKeyID: 48185874
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd25dabcf0f3f908d6fa90515cc59179abe784f8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036210"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-support-for-external-user-access-in-lync-server-2013"></a>在 Lync Server 2013 中配置对外部用户访问的支持

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-21_

部署边缘服务器或边缘池是支持外部用户的第一步。 有关部署边缘服务器的详细信息，请参阅部署文档中的在[Lync Server 2013 中部署外部用户访问](lync-server-2013-deploying-external-user-access.md)。 对策略配置的重要注意事项是了解策略的优先级及如何应用策略。 在一个策略级别应用的 Lync Server 策略设置可以覆盖在另一个策略级别应用的设置。 Lync Server 策略优先级为：用户策略（最具影响力）替代网站策略，然后网站策略将覆盖全局策略（最不影响）。 这意味着，策略设置越接近策略所影响的对象，它对对象的影响越大。

边缘服务器或边缘池设置完成后，必须启用要提供的外部用户访问类型并配置对外部访问的支持。 在 Lync Server 2013 中，你可以根据任务要求，使用 Lync Server 控制面板、Lync Server Management Shell 或两者来启用和配置外部用户访问和策略。

要支持外部用户访问，必须执行以下两项操作：

  - **启用对组织**   的支持若要在部署中启用对外部用户访问的支持，您可以启用要支持的每种类型的外部访问。 通过在 Lync Server 控制面板的 "**联盟和外部访问**" 组中或通过使用 Lync Server 命令行管理程序和关联的 cmdlet，在 "**外部访问策略**" 页上编辑全局设置或创建和配置站点或用户策略，可启用和禁用对外部用户访问的支持。 在[Lync Server 2013 中的主题联盟和外部访问 cmdlet](https://docs.microsoft.com/powershell/module/skype/)中，可以找到用于管理**外部访问策略**的 cmdlet。 启用对外部访问的支持指定运行 Lync Server 访问边缘服务的服务器支持与外部用户和服务器的通信。 外部用户访问被禁用，或者策略尚未配置为支持策略时，内部和外部用户无法进行通信。

  - **配置和分配一个或多个策略**   以支持外部用户访问，请配置策略以满足包括以下各项的要求：
    
      - ****   使用站点或用户作用域创建的外部访问策略（默认情况下存在全局策略，并且没有已启用的设置）。 您可以创建和配置策略以控制使用一种或多种类型的外部用户访问，包括联合用户访问（包括（如果已选中，联合 XMPP 域）远程用户用户访问和受支持的公共 IM 服务提供商。 在**联盟和外部访问**组中的 "**外部访问策略**" 页上，使用全局策略或一个或多个以管理方式创建的网站和用户策略，在 Lync Server 控制面板中配置外部策略。 无法删除全局策略。 您可以创建和配置任何要用于限制特定网站或用户的外部用户访问的网站和用户策略。 自动分配全局和站点策略。 如果创建并配置了用户策略，则必须使用 "**用户**" 页上的 "Lync Server 控制面板" 中的 "用户配置" 页将其分配给特定用户。 查找要应用此策略的一个或一用户，并分配该策略。 要对其应用的用户。 若要将已配置的用户策略分配给用户，请参阅[在 Lync Server 2013 中向启用 Lync 的用户分配外部用户访问策略](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)。 每个外部用户访问策略都可以支持以下一个或多个操作：远程用户访问、SIP 联合用户访问、XMPP 联盟用户访问和公共 IM 连接。
    
      - **会议策略**   您创建并配置策略以控制组织中的会议，包括组织中的哪些用户可以向匿名用户邀请他们托管的会议。 在 Lync Server 控制面板 **会议**页面上，是全局、站点和用户作用域的策略设置，用于控制实际会议的设置。 有关详细信息，请参阅[在 Lync Server 2013 中管理会议和会议](lync-server-2013-managing-meetings-and-conferences.md)。 您可启用参加会议的匿名用户及“访问边缘配置”**** 页面上的远程用户和联盟用户。 “访问边缘配置**** 上的策略是作用域中的全局策略。 没有可用于定义站点或用户策略的选项。 通过使用全局、站点或用户策略设置在“外部访问策略”**** 页面上控制作用域。
        
        例如，如果您想允许用户借助远程用户创建、邀请和管理会议，则必须在“外部访问策略”**** 全局、站点或用户策略上设置“启用与远程用户的通信”**** 及在“访问边缘配置”**** 页面上设置“启用与远程用户的通信”****。同样，要允许与有定义关系的匿名用户或联盟合作伙伴开展会议（如，配置的联盟 SIP 域和提供商 – XMPP 联盟不支持会议），则要在“外部访问策略”**** 全局、站点或用户策略中设置“启用与公共用户的通信”**** 和“启用与联盟用户的通信”****。然后在“访问边缘配置”**** 页面上选择赠送全局策略设置“允许匿名用户访问会议”**** 和“启用联盟和公共 IM 连接”****。

即使没有为组织启用外部用户访问，也可以配置外部用户访问设置，包括要用于控制外部用户访问的任何策略。但是，只有为组织启用外部用户访问之后，配置的策略和其他设置才会生效。如果禁用外部用户访问或没有配置支持此功能的外部用户访问策略，外部用户将无法与组织的用户进行通信。

边缘部署会根据边缘支持的配置方式来对外部用户（匿名用户除外，他们通过会议 ID 和密钥（当您创建会议和邀请参与者时发送给匿名参与者）进行身份验证）类型进行身份验证并控制访问。为了控制通信，可以配置一个或多个策略并配置设置以定义部署内外的用户如何相互通信。除了可以创建和配置为特定站点或用户启用一种或多种类型外部用户访问的站点和用户策略之外，这些策略和设置还包括默认的外部用户访问全局策略。

<div>

## <a name="in-this-section"></a>本部分内容

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

