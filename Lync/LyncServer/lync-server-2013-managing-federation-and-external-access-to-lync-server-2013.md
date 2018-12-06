---
title: Lync Server 2013：管理对 Lync Server 2013 的联盟和外部访问
TOCTitle: 管理对 Lync Server 2013 的联盟和外部访问
ms:assetid: 26f806c1-f284-4637-b06b-06270336c540
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg520966(v=OCS.15)
ms:contentKeyID: 49312299
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 管理对 Lync Server 2013 的联盟和外部访问

 

_**上一次修改主题：** 2015-03-09_

部署边缘服务器或边缘池是支持外部用户的第一步。有关部署边缘服务器的详细信息，请参阅部署文档中的 [在 Lync Server 2013 中部署外部用户访问](lync-server-2013-deploying-external-user-access.md)。

安装和配置 Lync Server 2013 内部部署后，组织中的内部用户可以与在 Active Directory 域服务 (AD DS) 中拥有 SIP 帐户的其他内部用户进行协作。协作可包括发送和接收即时消息以及更新当前状态和参与会议（也称为“会议”）。可以启用和配置外部用户访问权，以控制受支持的外部用户能否与内部 Lync Server 用户进行协作。外部用户可以包括部署的远程用户、联盟用户（包括支持的公共即时消息 (IM) 服务提供商用户）、XMPP 联盟以及会议的匿名参与者。

如果您的部署包括 Lync Server 2013  边缘服务器或 边缘池安装，则可以通过许多用于外部用户访问，以及用于与其他 SIP 联盟域成员、SIP 联盟提供商和 XMPP 联盟用户进行通信的选项大大扩展可能的通信类型的范围。在设置 边缘服务器或 边缘池后，可启用要提供的外部用户访问类型和配置控制外部访问的策略。在 Lync Server 2013 中，可以根据任务要求使用 Lync Server 控制面板和/或 Lync Server 命令行管理程序启用和配置外部用户访问和策略。有关这些管理工具的详细信息，请参阅操作文档中的 [Lync Server 2013 管理工具](lync-server-2013-lync-server-administrative-tools.md)、 [Lync Server 命令行管理程序](lync-server-2013-lync-server-management-shell.md)和 [安装 Lync Server 2013 管理工具](lync-server-2013-install-lync-server-administrative-tools.md)。

> [!IMPORTANT]
> 在为外部用户访问设计您的配置和策略时，您必须了解策略的优先级以及如何应用这些策略。 在一个策略级别应用的 Lync Server 策略设置可能会覆盖在另一个策略级别应用的设置。Lync Server 策略优先顺序为：用户策略（影响力最大）覆盖站点策略，站点策略覆盖全局策略（影响力最小）。这意味着，策略设置与策略所影响的对象距离越近，它对该对象的影响力越大。


默认情况下，即使已为组织启用对外部用户访问的支持，也不会将任何策略配置为支持外部用户访问（包括远程用户访问、联盟用户访问）。要控制外部用户访问的使用，必须配置一个或多个策略，同时指定每个策略支持的外部用户访问类型。其中包括以下外部访问策略：

  - **全局策略** 全局策略是在部署边缘服务器时创建的。默认情况下，不会在全局策略中启用任何外部用户访问选项。要在全局级别支持外部用户访问，请配置全局策略以支持一个或多个外部用户访问选项类型。全局策略适用于组织中的所有用户，但是站点策略和用户策略会覆盖全局策略。删除全局策略并不会将其实际移除，而只是将其重置为默认设置。

  - **站点策略** 可以创建并配置一个或多个站点策略以将对外部用户访问的支持限制为特定站点。站点策略中的配置将覆盖全局策略，但是仅限于站点策略所涉及的特定站点。例如，即使在全局策略中启用远程用户访问，仍然可以指定站点策略为特定站点禁用远程用户访问。默认情况下，站点策略将应用于该站点的所有用户，但是可以为用户分配用户策略以覆盖站点策略设置。

  - **用户策略** 可以创建并配置一个或多个用户策略以将对远程用户访问的支持限制为特定用户。用户策略配置将覆盖全局策略和站点策略，但是仅限于分配了该用户策略的特定用户。例如，即使在全局策略和站点策略中启用了远程用户访问，仍然可以指定禁用远程用户访问的用户策略，然后将该用户策略分配给特定用户。如果创建用户策略，则必须将其应用于一个或多个用户，此后该策略才能生效。

若要确定您需要创建或编辑哪些配置设置和哪些策略，请参阅以下决策点：

**是否要允许域的内部和外部用户能够使用即时消息、Web 会议和音频/视频进行协作？**

按[在 Lync Server 2013 中配置策略以控制远程用户访问](lync-server-2013-configure-policies-to-control-remote-user-access.md)和[在 Lync Server 2013 中启用或禁用联盟和公共 IM 连接](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)主题中所述配置相应设置

**是否要允许匿名用户参加和受邀参加由您的部署中的用户主持的会议？**

按[在 Lync Server 2013 中分配会议策略以支持匿名用户](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md)、[在 Lync Server 2013 中创建或修改会议策略](lync-server-2013-create-or-modify-a-conferencing-policy.md)和[在 Lync Server 2013 中会议策略设置参考](lync-server-2013-conferencing-policy-settings-reference.md)主题中所述配置相应设置

**是否要允许用户与 SIP 联盟域联系人通信？**

按[在 Lync Server 2013 中配置策略以控制联盟用户访问](lync-server-2013-configure-policies-to-control-federated-user-access.md)、[在 Lync Server 2013 中启用或禁用联盟和公共 IM 连接](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)和[在 Lync Server 2013 中管理组织的 SIP 联盟域](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)主题中所述配置相应设置

**如果您已允许与 SIP 联盟域进行通信，是否希望允许与 XMPP 联盟伙伴联系人进行通信？**

按[在 Lync Server 2013 中配置策略以控制 XMPP 联盟用户访问](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)和[在 Lync Server 2013 中管理组织的 XMPP 联盟伙伴](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)主题中所述配置相应设置。

**如果您已允许与 SIP 联盟域进行通信，是否要启用 SIP 联盟自动发现？**

按[在 Lync Server 2013 中启用或禁用联盟伙伴发现](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)主题中所述配置相应设置。

**如果您已允许与 SIP 联盟域进行通信，是否要允许向联盟联系人发送弃用声明，以通知他们您使用存档且可以对通信进行存档？**

按[在 Lync Server 2013 中启用或禁用向联盟伙伴发送存档免责声明](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)主题中所述配置相应设置。

**是否要允许用户与 SIP 联盟提供商进行通信，以支持与公共提供商（如 Windows Live Messenger、AOL 和 Yahoo\!）的通信？**

按[在 Lync Server 2013 中配置策略以控制公共用户访问](lync-server-2013-configure-policies-to-control-public-user-access.md)、[在 Lync Server 2013 中启用或禁用联盟和公共 IM 连接](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)和[在 Lync Server 2013 中创建或编辑公共 SIP 联盟提供程序](lync-server-2013-create-or-edit-public-sip-federated-providers.md)主题中所述配置相应设置。

> [!IMPORTANT]  
> <ul>
> <li><p>自 2012 年 9 月 1 日起，新订或续订合同不能再购买 Microsoft Lync 公共 IM 连接用户订阅许可证 (“PIC USL”)。拥有有效许可证的客户可继续与 Yahoo! Messenger 联盟直至服务关闭。AOL 和 Yahoo! 的生命周期结束日期已宣布，为 2014 年 6 月。有关详细信息，请参阅 <a href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公共即时消息连接支持</a>。</p></li>
> <li><p>PIC USL 是一个每用户每月订阅许可证，是 Lync Server 或 Office Communications Server 与 Yahoo! Messenger 联盟所必需的。Microsoft 之所以能够提供此服务离不开 Yahoo! 的支持，但这项支持的基础协议正在逐步终止。</p></li>
> <li><p>Lync 是一个比以往更强大的工具，它实现了人员跨组织、跨地域的连接。除 Lync 标准 CAL 外，与 Windows Live Messenger 联盟不需要任何附加用户/设备许可证。Skype 联盟将添加到此列表中，以便 Lync 用户能够通过 IM 和语音与数亿用户取得联系。</p></li>
> </ul>

**是否要允许用户与 SIP 联盟提供商（运行 Microsoft Office 365、 Microsoft Lync Online 和 Microsoft Lync Online 2010 的宿主提供商）进行通信？**

按[在 Lync Server 2013 中创建或编辑公共 SIP 联盟提供程序](lync-server-2013-create-or-edit-public-sip-federated-providers.md)、[在 Lync Server 2013 中启用或禁用联盟和公共 IM 连接](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)和[在 Lync Server 2013 中创建或编辑托管的 SIP 联盟提供程序](lync-server-2013-create-or-edit-hosted-sip-federated-providers.md)主题中所述配置相应设置

**是否在拆分（也称为混合）域中配置您的部署？在该域中，某些用户的主服务器位于本地部署中，而其他用户的主服务器配置为位于联机环境中**

按[在 Lync Server 2013 中配置策略以控制联盟用户访问](lync-server-2013-configure-policies-to-control-federated-user-access.md)、 [在 Lync Server 2013 中启用或禁用联盟和公共 IM 连接](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)和 [在 Lync Server 2013 中创建或编辑托管的 SIP 联盟提供程序](lync-server-2013-create-or-edit-hosted-sip-federated-providers.md)主题中所述配置相应设置

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
<th>联盟和外部访问中的选项卡（横向） 联盟或外部访问类型（向下）</th>
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
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>SIP 联盟联系人</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">在 Lync Server 2013 中配置策略以控制联盟用户访问</a></p>
<p></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">在 Lync Server 2013 中启用或禁用联盟和公共 IM 连接</a></p>
<p><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">在 Lync Server 2013 中启用或禁用联盟伙伴发现</a></p>
<p><a href="lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md">在 Lync Server 2013 中启用或禁用向联盟伙伴发送存档免责声明</a></p></td>
<td><p><a href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">在 Lync Server 2013 中管理组织的 SIP 联盟域</a></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>XMPP 联盟联系人</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">在 Lync Server 2013 中配置策略以控制联盟用户访问</a></p>
<p><a href="lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md">在 Lync Server 2013 中配置策略以控制 XMPP 联盟用户访问</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">在 Lync Server 2013 中启用或禁用联盟和公共 IM 连接</a></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p><a href="lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md">在 Lync Server 2013 中管理组织的 XMPP 联盟伙伴</a></p></td>
</tr>
<tr class="even">
<td><p>拆分域 / 混合用户</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">在 Lync Server 2013 中配置策略以控制联盟用户访问</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">在 Lync Server 2013 中启用或禁用联盟和公共 IM 连接</a></p></td>
<td><p></p></td>
<td><p><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">在 Lync Server 2013 中创建或编辑托管的 SIP 联盟提供程序</a></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>公共 IM 服务联系人</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-public-user-access.md">在 Lync Server 2013 中配置策略以控制公共用户访问</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">在 Lync Server 2013 中启用或禁用联盟和公共 IM 连接</a></p></td>
<td><p></p></td>
<td><p><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">在 Lync Server 2013 中创建或编辑公共 SIP 联盟提供程序</a></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>匿名用户对会议的访问权限</p></td>
<td><p></p></td>
<td><p><a href="lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md">在 Lync Server 2013 中分配会议策略以支持匿名用户</a></p>
<div>

> [!NOTE]  
> 您还必须考虑“配置策略”下的以下配置设置：<a href="lync-server-2013-create-or-modify-a-conferencing-policy.md">在 Lync Server 2013 中创建或修改会议策略</a>和<a href="lync-server-2013-conferencing-policy-settings-reference.md">在 Lync Server 2013 中会议策略设置参考</a>


</div></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>


即使没有为组织启用外部用户访问，也可以配置外部用户访问设置，包括要用于控制外部用户访问的任何策略。但是，只有为组织启用外部用户访问之后，配置的策略和其他设置才会生效。如果禁用外部用户访问或没有配置支持此功能的外部用户访问策略，外部用户将无法与组织的用户进行通信。

边缘部署会根据边缘支持的配置方式来对外部用户（匿名用户除外，他们通过会议 ID 和密钥（当您创建会议和邀请参与者时发送给匿名参与者）进行身份验证）类型进行身份验证并控制访问。为了控制通信，可以配置一个或多个策略并配置设置以定义部署内外的用户如何相互通信。除了可以创建和配置为特定站点或用户启用一种或多种类型外部用户访问的站点和用户策略之外，这些策略和设置还包括默认的外部用户访问全局策略。

## 本部分内容

  - [在 Lync Server 2013 中管理组织的外部访问策略](lync-server-2013-manage-external-access-policy-for-your-organization.md)

  - [在 Lync Server 2013 中管理您的组织的访问边缘配置](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)

  - [在 Lync Server 2013 中管理组织的 SIP 联盟域](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)

  - [在 Lync Server 2013 中管理组织的 SIP 联盟提供程序](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)

  - [在 Lync Server 2013 中管理组织的 XMPP 联盟伙伴](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)

  - [为 Lync Online 客户配置联盟支持](lync-server-2013-configuring-federation-support-for-a-lync-online-customer.md)

