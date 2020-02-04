---
title: Lync Server 2013：管理对 Lync Server 2013 的联盟和外部访问
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing federation and external access to Lync Server 2013
ms:assetid: 26f806c1-f284-4637-b06b-06270336c540
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520966(v=OCS.15)
ms:contentKeyID: 48183665
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9dadc455389d95c91996b75928def8f03b06c64e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729312"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-federation-and-external-access-to-lync-server-2013"></a>管理对 Lync Server 2013 的联盟和外部访问

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-10-07_

部署边缘服务器或边缘池是支持外部用户的第一步。 有关部署边缘服务器的详细信息，请参阅部署文档中[Lync Server 2013 中的 "部署外部用户访问](lync-server-2013-deploying-external-user-access.md)"。

在安装并配置 Lync Server 2013 的内部部署之后，你组织中的内部用户可以与在你的 Active Directory 域服务（AD DS）中具有 SIP 帐户的其他内部用户进行协作。 协作可以包括发送和接收即时消息，以及更新状态和参与会议（也称为 "会议"）。 启用和配置外部用户访问以控制受支持的外部用户是否可以与内部 Lync Server 用户进行协作。 外部用户可以包括部署的远程用户、联盟用户（包括公共即时消息（IM）服务提供商的支持用户）、XMPP 联盟和会议中的匿名参与者。

如果你的部署包括 Lync Server 2013 Edge 服务器或边缘池的安装，则可能的通信类型的范围很大程度上与外部用户访问、与其他 SIP 联盟域的成员通信有关的选项很大扩展。SIP 联合提供商和 XMPP 联盟用户。 在设置边缘服务器或边缘池后，启用要提供的外部用户访问类型，并配置策略以控制外部访问。 在 Lync Server 2013 中，你可以使用 Lync Server 控制面板、Lync Server Management Shell 或两者（基于任务要求）启用和配置外部用户访问和策略。 有关这些管理工具的详细信息，请参阅 operations 文档中的[Lync server 2013 管理工具](lync-server-2013-lync-server-administrative-tools.md)、操作文档中的[Lync Server 2013 管理外壳](lync-server-2013-lync-server-management-shell.md)以及安装操作文档中的[lync server 2013 管理工具](lync-server-2013-install-lync-server-administrative-tools.md)。

<div>


> [!IMPORTANT]  
> 为外部用户访问设计配置和策略时，必须了解策略的优先级以及策略的应用方式。 在一个策略级别应用的 Lync Server 策略设置可以覆盖在其他策略级别应用的设置。 Lync 服务器策略优先级为：用户策略（最受影响）覆盖网站策略，然后网站策略覆盖全局策略（最不影响）。 这意味着，策略设置与策略所影响的对象距离越近，它对该对象的影响力越大。



</div>

默认情况下，未将任何策略配置为支持外部用户访问，包括远程用户访问权限、联合用户访问，即使你已启用组织的外部用户访问支持。 若要控制外部用户访问的使用，必须配置一个或多个策略，指定每个策略支持的外部用户访问类型。 这包括以下外部访问策略：

  - **全局策略**   当你部署 Edge 服务器时，将创建全局策略。 默认情况下，全局策略中未启用任何外部用户访问选项。 若要在全局级别支持外部用户访问，请将全局策略配置为支持一种或多种类型的外部用户访问选项。 全局策略适用于组织中的所有用户，但网站策略和用户策略替代全局策略。 如果您删除全局策略，则不会将其删除。 而是将其重置为默认设置。

  - **网站策略**   您可以创建和配置一个或多个网站策略，以限制对特定网站的外部用户访问的支持。 站点策略中的配置将覆盖全局策略，但是仅限于站点策略所涉及的特定站点。 例如，如果在全局策略中启用 "远程用户访问"，则可以指定一个网站策略，该策略可禁用特定网站的远程用户访问。 默认情况下，网站策略应用于该网站的所有用户，但你可以将用户策略分配给用户以替代网站策略设置。

  - **用户策略**   您可以创建和配置一个或多个用户策略，以限制对特定用户的远程用户访问的支持。 用户策略中的配置替代全局和网站策略，但仅适用于为其分配用户策略的特定用户。 例如，如果在全局策略和网站策略中启用远程用户访问，则可以指定禁用远程用户访问的用户策略，然后将该用户策略分配给特定用户。 如果创建用户策略，则必须将其应用于一个或多个用户，然后它才会生效。

若要确定要创建或编辑哪些配置设置以及需要哪些策略，请参阅以下决策点：

**您是否希望允许您的域的内部和外部用户能够使用即时消息、Web 会议和音频/视频进行协作？**

按照主题[配置策略来控制 Lync server 2013 中的远程用户访问](lync-server-2013-configure-policies-to-control-remote-user-access.md)，以及[在 lync Server 2013 中启用或禁用联盟和公共 IM 连接](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)，详细配置设置

**你是否希望允许匿名用户出席并邀请你的部署中的用户托管的会议？**

详细配置本主题中的详细设置在 lync server 2013 中的 "[分配会议策略" 以支持匿名用户](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md)、在 lync server [2013 中创建或修改会议策略](lync-server-2013-create-or-modify-a-conferencing-policy.md)以及[lync server 2013 的会议策略设置参考](lync-server-2013-conferencing-policy-settings-reference.md)

**是否希望允许用户与 SIP 联盟域联系人通信？**

配置有关在[Lync server 2013 中配置用于控制联盟用户访问的策略](lync-server-2013-configure-policies-to-control-federated-user-access.md)的设置，在 lync server [2013 中启用或禁用联盟和公共 IM 连接](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)，以及[在 lync SERVER 中管理组织的 SIP 联盟域 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)

**如果已启用与 SIP 联合域的通信，是否要启用与 XMPP 联盟合作伙伴联系人的通信？**

配置在 Lync Server 2013 中的 "[配置策略以控制 XMPP 联盟用户访问](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)" 和["在 lync Server 2013 中管理 XMPP 联盟合作伙伴](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)" 中详细介绍的设置。

**如果已启用与 SIP 联盟域的通信，是否要启用 SIP 联合自动发现？**

配置在[Lync Server 2013 中启用或禁用联合身份验证合作伙伴的发现](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)中详细介绍的设置。

**如果你已启用与 SIP 联合域的通信，你是否希望允许将免责声明发送给联盟联系人，通知他们你使用存档，并且该通信可能已存档？**

在[Lync Server 2013 中启用或禁用向联盟伙伴发送存档免责声明](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)的详细信息，配置这些设置。

**是否希望允许用户与支持公共提供商（如 Windows Live Messenger、AOL 和 Yahoo\!）的通信的 SIP 联合提供商进行通信？**

在 lync server [2013 中配置策略以控制公共用户访问的策略](lync-server-2013-configure-policies-to-control-public-user-access.md)，在 lync server[2013 中启用或禁用联盟和公共 IM 连接](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)，以及[在 lync server 2013 中创建或编辑公共 SIP 联合提供程序](lync-server-2013-create-or-edit-public-sip-federated-providers.md)，详细说明了这些设置。

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>从2012年9月1日起，Microsoft Lync 公共 IM 连接用户订阅许可证（"PIC USL"）不再可用于购买新的或续订协议。 具有活动许可证的客户将能够继续与 Yahoo！进行联盟 Messenger，直到服务关闭日期。 AOL 和 Yahoo！的有效期结束日期为2014年6月 已宣布。 有关详细信息，请参阅<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公共即时消息连接支持</A>。</P>
> <LI>
> <P>PIC USL 是 Lync Server 或 Office 通信服务器与 Yahoo！联合所需的每个每个用户每月订阅许可证。 Messenger. Microsoft 提供此服务的能力已作为对 Yahoo！的支持，它的底层协议被向下缠绕。</P>
> <LI>
> <P>Lync 比以往更多，是一种强大的工具，用于跨组织和全球各地的人员进行连接。 与 Windows Live Messenger 的联盟不需要除 Lync 标准 CAL 之外的其他用户/设备许可证。 Skype 联盟将添加到此列表，使 Lync 用户可以通过 IM 和语音与成百上千人联系。</P></LI></UL>



</div>

**是否希望允许用户与运行 Microsoft Office 365、Microsoft Lync Online 和 Microsoft Lync Online 2010 的托管提供商的 SIP 联合提供商通信？**

按主题中的详细信息配置设置在[lync server 2013 中创建或编辑公共 SIP 联合提供程序](lync-server-2013-create-or-edit-public-sip-federated-providers.md)，在[lync server 2013 中启用或禁用联盟和公共 IM 连接](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)，以及[创建或编辑托管 SIP 联合提供商 Lync Server 2013](lync-server-2013-create-or-edit-hosted-sip-federated-providers.md)

**你的部署是在拆分（也称为混合）域中配置的，其中某些用户在内部部署中拥有主服务器，而其他用户在联机环境中配置了主服务器？**

配置有关在[Lync server 2013 中配置用于控制联盟用户访问的策略](lync-server-2013-configure-policies-to-control-federated-user-access.md)的设置，在 lync server [2013 中启用或禁用联盟和公共 IM 连接](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)，以及[创建或编辑托管 SIP 联合提供商 Lync server 2013](lync-server-2013-create-or-edit-hosted-sip-federated-providers.md)

如果您更喜欢列出要求的表格，请执行以下操作：


<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th>联盟和外部访问（跨）联盟或外部访问类型（向下）中的选项卡</th>
<th>外部访问策略</th>
<th>Access Edge 配置</th>
<th>SIP 联盟域</th>
<th>SIP 联盟提供商</th>
<th>XMPP 联盟合作伙伴</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>远程用户</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-remote-user-access.md">在 Lync Server 2013 中配置策略以控制远程用户访问</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-remote-user-access.md">在 Lync Server 2013 中启用或禁用远程用户访问</a></p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>SIP 联盟联系人</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">在 Lync Server 2013 中配置策略以控制联盟用户访问</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">在 Lync Server 2013 中启用或禁用联盟和公共 IM 连接</a></p>
<p><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">在 Lync Server 2013 中启用或禁用联盟伙伴发现</a></p>
<p><a href="lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md">在 Lync Server 2013 中启用或禁用向联盟伙伴发送存档免责声明</a></p></td>
<td><p><a href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">在 Lync Server 2013 中管理组织的 SIP 联盟域</a></p></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>XMPP 联盟联系人</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">在 Lync Server 2013 中配置策略以控制联盟用户访问</a></p>
<p><a href="lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md">在 Lync Server 2013 中配置策略以控制 XMPP 联盟用户访问</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">在 Lync Server 2013 中启用或禁用联盟和公共 IM 连接</a></p></td>
<td></td>
<td></td>
<td><p><a href="lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md">在 Lync Server 2013 中管理组织的 XMPP 联盟伙伴</a></p></td>
</tr>
<tr class="even">
<td><p>拆分域/混合用户</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">在 Lync Server 2013 中配置策略以控制联盟用户访问</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">在 Lync Server 2013 中启用或禁用联盟和公共 IM 连接</a></p></td>
<td></td>
<td><p><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">在 Lync Server 2013 中创建或编辑托管的 SIP 联盟提供程序</a></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>公用 IM 服务联系人</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-public-user-access.md">在 Lync Server 2013 中配置策略以控制公共用户访问</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">在 Lync Server 2013 中启用或禁用联盟和公共 IM 连接</a></p></td>
<td></td>
<td><p><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">在 Lync Server 2013 中创建或编辑公共 SIP 联盟提供程序</a></p></td>
<td></td>
</tr>
<tr class="even">
<td><p>对会议和会议的匿名用户访问</p></td>
<td></td>
<td><p><a href="lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md">在 Lync Server 2013 中分配会议策略以支持匿名用户</a></p>
<div>

> [!NOTE]  
> 还必须考虑 "会议策略" 下的以下配置设置：<A href="lync-server-2013-create-or-modify-a-conferencing-policy.md">在 lync server 2013 中创建或修改会议策略</A>和<A href="lync-server-2013-conferencing-policy-settings-reference.md">lync Server 2013 的会议策略设置参考</A>


</div></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


你可以配置外部用户访问设置，包括你希望用于控制外部用户访问的任何策略，即使你未启用组织的外部用户访问权限也是如此。 但是，你配置的策略和其他设置仅在你为你的组织启用外部用户访问时才有效。 当外部用户访问被禁用或者没有配置任何外部用户访问策略来支持它时，外部用户无法与组织用户通信。

边缘部署对外部用户的类型进行身份验证（匿名用户除外，这些用户是通过会议 ID 进行身份验证的，而在创建会议和邀请参与者时发送给匿名参与者）和控件的密钥基于配置 edge 支持的方式进行访问。 为了控制通信，你可以配置一个或多个策略，并配置定义你的部署内部和外部的用户之间如何相互通信的设置。 除了可创建和配置以启用特定网站或用户的一种或多种类型的外部用户访问的网站和用户策略之外，策略和设置包括外部用户访问的默认全局策略。

<div>

## <a name="in-this-section"></a>本节内容

  - [在 Lync Server 2013 中管理组织的外部访问策略](lync-server-2013-manage-external-access-policy-for-your-organization.md)

  - [在 Lync Server 2013 中管理您的组织的访问边缘配置](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)

  - [在 Lync Server 2013 中管理组织的 SIP 联盟域](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)

  - [在 Lync Server 2013 中管理组织的 SIP 联盟提供程序](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)

  - [在 Lync Server 2013 中管理组织的 XMPP 联盟伙伴](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)

  - [在 Lync Server 2013 中为 Lync Online 客户配置联合身份验证支持](lync-server-2013-configuring-federation-support-for-a-lync-online-customer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

