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
ms.openlocfilehash: 2adaff02f6533b463199b5d295f65cc519a784e4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150373"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-federation-and-external-access-to-lync-server-2013"></a>管理对 Lync Server 2013 的联盟和外部访问

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-10-07_

部署边缘服务器或边缘池是支持外部用户的第一步。 有关部署边缘服务器的详细信息，请参阅部署文档中的在[Lync Server 2013 中部署外部用户访问](lync-server-2013-deploying-external-user-access.md)。

在安装并配置 Lync Server 2013 的内部部署后，组织中的内部用户可以与在 Active Directory 域服务（AD DS）中具有 SIP 帐户的其他内部用户进行协作。 协作可包括发送和接收即时消息以及更新当前状态和参与会议（也称为“会议”）。 启用和配置外部用户访问，以控制受支持的外部用户是否可以与内部 Lync Server 用户进行协作。 外部用户可以包括部署的远程用户、联盟用户（包括支持的公共即时消息 (IM) 服务提供商用户）、XMPP 联盟以及会议的匿名参与者。

如果您的部署包括安装 Lync Server 2013 边缘服务器或边缘池，则可能的通信类型的范围将大大扩展，其中包含用于外部用户访问的多个选项，与其他 SIP 联盟域的成员进行通信。SIP 联合提供程序和 XMPP 联合用户。 在设置边缘服务器或边缘池之后，您可以启用要提供的外部用户访问的类型，并配置策略以控制外部访问。 在 Lync Server 2013 中，你可以根据任务要求，使用 Lync Server 控制面板、Lync Server Management Shell 或两者来启用和配置外部用户访问和策略。 有关这些管理工具的详细信息，请参阅 operations 文档中的[Lync server 2013 管理工具](lync-server-2013-lync-server-administrative-tools.md)、操作文档中的[Lync Server 2013 命令行](lync-server-2013-lync-server-management-shell.md)管理程序，并在操作文档中[安装 lync server 2013 管理工具](lync-server-2013-install-lync-server-administrative-tools.md)。

<div>


> [!IMPORTANT]  
> 在为外部用户访问设计您的配置和策略时，您必须了解策略的优先级以及如何应用这些策略。 在一个策略级别应用的 Lync Server 策略设置可以覆盖在另一个策略级别应用的设置。 Lync Server 策略优先级为：用户策略（最具影响力）替代网站策略，然后网站策略将覆盖全局策略（最不影响）。 这意味着，策略设置越接近策略所影响的对象，它对对象的影响越大。



</div>

默认情况下，即使已为组织启用对外部用户访问的支持，也不会将任何策略配置为支持外部用户访问（包括远程用户访问、联盟用户访问）。要控制外部用户访问的使用，必须配置一个或多个策略，同时指定每个策略支持的外部用户访问类型。其中包括以下外部访问策略：

  - **全局策略**   ：部署边缘服务器时创建全局策略。 默认情况下，不会在全局策略中启用任何外部用户访问选项。 若要在全局级别支持外部用户访问，请将全局策略配置为支持一种或多种类型的外部用户访问选项。 全局策略适用于组织中的所有用户，但网站策略和用户策略会覆盖全局策略。 如果删除全局策略，则不会将其删除。 而是将其重置为默认设置。

  - **站点策略**   您可以创建和配置一个或多个站点策略，以限制对特定站点的外部用户访问的支持。 站点策略中的配置将覆盖全局策略，但是仅限于站点策略所涉及的特定站点。 例如，如果在全局策略中启用远程用户访问，则可以指定一个站点策略，该策略将禁用特定网站的远程用户访问。 默认情况下，网站策略应用于该网站的所有用户，但您可以向用户分配用户策略以覆盖网站策略设置。

  - **用户策略**   您可以创建和配置一个或多个用户策略，以限制对特定用户的远程用户访问的支持。 用户策略中的配置会覆盖全局策略和站点策略，但仅适用于为其分配用户策略的特定用户。 例如，如果在全局策略和站点策略中启用远程用户访问，则可以指定禁用远程用户访问的用户策略，然后将该用户策略分配给特定用户。 如果创建了用户策略，则必须将其应用到一个或多个用户，然后它才会生效。

若要确定您需要创建或编辑哪些配置设置和哪些策略，请参阅以下决策点：

**是否要允许域的内部和外部用户能够使用即时消息、Web 会议和音频/视频进行协作？**

配置在[Lync server 2013 中配置策略以控制远程用户访问](lync-server-2013-configure-policies-to-control-remote-user-access.md)和在[lync Server 2013 中启用或禁用联盟和公共 IM 连接](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)的主题中的详细设置。

**是否要允许匿名用户参加和受邀参加由您的部署中的用户主持的会议？**

按照主题[分配会议策略以支持 lync server 2013 中的匿名用户](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md)、在 lync server [2013 中创建或修改会议策略](lync-server-2013-create-or-modify-a-conferencing-policy.md)和[lync server 2013 的会议策略设置参考](lync-server-2013-conferencing-policy-settings-reference.md)中的详细信息配置设置

**是否要允许用户与 SIP 联盟域联系人通信？**

配置在 lync server 2013 中的 "[配置策略以控制联盟用户访问](lync-server-2013-configure-policies-to-control-federated-user-access.md)"、"在 lync [server 2013 中启用或禁用联盟和公共 IM 连接](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)" 和 "[在 lync 2013 SERVER 中管理组织的 SIP 联盟域](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)" 中详细说明的设置。

**如果您已允许与 SIP 联盟域进行通信，是否希望允许与 XMPP 联盟伙伴联系人进行通信？**

配置在 Lync server 2013 中的 "[配置策略以控制 XMPP 联盟用户访问](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)" 和 "[在 lync Server 2013 中管理 XMPP 联盟伙伴](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)" 主题中详细介绍的设置。

**如果已启用与 SIP 联盟域的通信，是否要启用 SIP 联合自动发现？**

按照在[Lync Server 2013 中启用或禁用联合合作伙伴的发现](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)主题中的详细说明配置这些设置。

**如果您已允许与 SIP 联盟域进行通信，是否要允许向联盟联系人发送弃用声明，以通知他们您使用存档且可以对通信进行存档？**

按照在[Lync Server 2013 中启用或禁用向联盟伙伴发送存档免责声明一](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)主题中的详细说明配置这些设置。

**您是否希望允许用户与 SIP 联合提供程序通信，以启用与公用提供程序（如 Windows Live Messenger、AOL 和 Yahoo\!）的通信？**

配置在 lync server 2013 中的 "[配置策略以控制公用用户访问](lync-server-2013-configure-policies-to-control-public-user-access.md)" 主题中的详细信息，在 lync server[2013 中启用或禁用联盟和公共 IM 连接](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)，以及[在 lync server 2013 中创建或编辑公共 SIP 联合提供程序](lync-server-2013-create-or-edit-public-sip-federated-providers.md)。

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>从2012年9月1日起，Microsoft Lync 公共 IM 连接用户订阅许可证（"PIC USL"）不再可用于购买新的或更新的协议。 拥有主动许可证的客户将能够继续与 Yahoo！联合联合 信使，直到服务关闭日期。 AOL 和 Yahoo！的生命周期结束日期为2014年6月 已宣布。 有关详细信息，请参阅<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的支持公用即时信使连接</A>。</P>
> <LI>
> <P>PIC USL 是 Lync Server 或 Office 通信服务器与 Yahoo！联合所需的每个用户每月订阅许可证。 Messenger. Microsoft 提供此服务的能力因 Yahoo！中的支持而受到了支持，其下凸的底层协议。</P>
> <LI>
> <P>Lync 是前所未有的强大工具，用于跨组织和世界各地的个人进行连接。 与 Windows Live Messenger 的联盟不需要除 Lync Standard CAL 之外的其他用户/设备许可证。 Skype 联合身份验证将添加到此列表中，使 Lync 用户可以使用即时消息和语音访问成百上千人。</P></LI></UL>



</div>

**您是否希望允许用户与运行 Microsoft Office 365、Microsoft Lync Online 和 Microsoft Lync Online 2010 的托管提供商的 SIP 联合提供程序进行通信？**

配置在[lync server 2013 中创建或编辑公共 SIP 联合提供程序](lync-server-2013-create-or-edit-public-sip-federated-providers.md)的主题中详细介绍的设置，在[lync server 2013 中启用或禁用联盟和公共 IM 连接](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)，以及[创建或编辑托管的 SIP 联合提供者 Lync server 2013](lync-server-2013-create-or-edit-hosted-sip-federated-providers.md)

**是否在拆分（也称为混合）域中配置您的部署？在该域中，某些用户的主服务器位于本地部署中，而其他用户的主服务器配置为位于联机环境中**

配置在 Lync server 2013 中的 "[配置策略以控制联盟用户访问](lync-server-2013-configure-policies-to-control-federated-user-access.md)" 中的详细信息，在[lync server 2013 中启用或禁用联盟和公共 IM 连接](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)，并[创建或编辑托管的 SIP 联合提供者 Lync server 2013](lync-server-2013-create-or-edit-hosted-sip-federated-providers.md)

如果您选择列出相关要求的表：


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
<th>访问边缘配置</th>
<th>SIP 联盟域</th>
<th>SIP 联盟提供商</th>
<th>XMPP 联盟伙伴</th>
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
<td><p><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">在 Lync Server 2013 中配置用于控制联合用户访问的策略</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">在 Lync Server 2013 中启用或禁用联盟和公共 IM 连接</a></p>
<p><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">在 Lync Server 2013 中启用或禁用联盟伙伴发现</a></p>
<p><a href="lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md">在 Lync Server 2013 中启用或禁用向联盟伙伴发送存档免责声明</a></p></td>
<td><p><a href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">在 Lync Server 2013 中管理组织的 SIP 联盟域</a></p></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>XMPP 联盟联系人</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">在 Lync Server 2013 中配置用于控制联合用户访问的策略</a></p>
<p><a href="lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md">在 Lync Server 2013 中配置策略以控制 XMPP 联盟用户访问</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">在 Lync Server 2013 中启用或禁用联盟和公共 IM 连接</a></p></td>
<td></td>
<td></td>
<td><p><a href="lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md">在 Lync Server 2013 中管理 XMPP 联盟伙伴</a></p></td>
</tr>
<tr class="even">
<td><p>拆分域 / 混合用户</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">在 Lync Server 2013 中配置用于控制联合用户访问的策略</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">在 Lync Server 2013 中启用或禁用联盟和公共 IM 连接</a></p></td>
<td></td>
<td><p><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">创建或编辑托管的 SIP 联合提供商 Lync Server 2013</a></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>公共 IM 服务联系人</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-public-user-access.md">配置策略以控制 Lync Server 2013 中的公共用户访问</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">在 Lync Server 2013 中启用或禁用联盟和公共 IM 连接</a></p></td>
<td></td>
<td><p><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">在 Lync Server 2013 中创建或编辑公共 SIP 联合提供程序</a></p></td>
<td></td>
</tr>
<tr class="even">
<td><p>匿名用户对会议的访问权限</p></td>
<td></td>
<td><p><a href="lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md">在 Lync Server 2013 中分配会议策略以支持匿名用户</a></p>
<div>

> [!NOTE]  
> 您还必须考虑会议策略：在 lync server <A href="lync-server-2013-create-or-modify-a-conferencing-policy.md">2013 中创建或修改会议策略</A>和<A href="lync-server-2013-conferencing-policy-settings-reference.md">lync Server 2013 的会议策略设置参考</A>中的以下配置设置


</div></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


即使没有为组织启用外部用户访问，也可以配置外部用户访问设置，包括要用于控制外部用户访问的任何策略。但是，只有为组织启用外部用户访问之后，配置的策略和其他设置才会生效。如果禁用外部用户访问或没有配置支持此功能的外部用户访问策略，外部用户将无法与组织的用户进行通信。

边缘部署会根据边缘支持的配置方式来对外部用户（匿名用户除外，他们通过会议 ID 和密钥（当您创建会议和邀请参与者时发送给匿名参与者）进行身份验证）类型进行身份验证并控制访问。为了控制通信，可以配置一个或多个策略并配置设置以定义部署内外的用户如何相互通信。除了可以创建和配置为特定站点或用户启用一种或多种类型外部用户访问的站点和用户策略之外，这些策略和设置还包括默认的外部用户访问全局策略。

<div>

## <a name="in-this-section"></a>本部分内容

  - [在 Lync Server 2013 中管理外部访问策略](lync-server-2013-manage-external-access-policy-for-your-organization.md)

  - [在 Lync Server 2013 中管理您的组织的访问边缘配置](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)

  - [在 Lync Server 2013 中管理组织的 SIP 联盟域](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)

  - [在 Lync Server 2013 中管理组织的 SIP 联合提供程序](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)

  - [在 Lync Server 2013 中管理 XMPP 联盟伙伴](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)

  - [在 Lync Server 2013 中为 Lync Online 客户配置联合支持](lync-server-2013-configuring-federation-support-for-a-lync-online-customer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

