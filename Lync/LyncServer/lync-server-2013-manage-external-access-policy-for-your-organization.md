---
title: Lync Server 2013：管理组织的外部访问策略
TOCTitle: 管理组织的外部访问策略
ms:assetid: 5571811e-34c8-443a-b94c-1ab5d4275581
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg520995(v=OCS.15)
ms:contentKeyID: 49312885
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中管理组织的外部访问策略

 

_**上一次修改主题：** 2013-10-07_

部署一台或多台 边缘服务器后，必须启用组织支持的外部访问类型。

默认情况下，即使已为组织启用对外部用户访问的支持，也不会将任何策略配置为支持外部用户访问（包括远程用户访问、联盟用户访问）。要控制外部用户访问的使用，必须配置一个或多个策略，并指定每个策略支持的外部用户访问类型。可创建和配置以下策略范围。默认情况下，将创建全局策略且无法被删除。

  - **全局策略** 全局策略是在部署边缘服务器时创建的。默认情况下，不会在全局策略中启用任何外部用户访问选项。要在全局级别支持外部用户访问，请配置全局策略以支持一个或多个外部用户访问选项类型。全局策略适用于组织中的所有用户，但是站点策略和用户策略会覆盖全局策略。删除全局策略并不会将其实际移除，而只是将其重置为默认设置。

  - **站点策略** 可以创建并配置一个或多个站点策略以将对外部用户访问的支持限制为特定站点。站点策略中的配置将覆盖全局策略，但是仅限于站点策略所涉及的特定站点。例如，即使在全局策略中启用远程用户访问，仍然可以指定站点策略为特定站点禁用远程用户访问。默认情况下，站点策略将应用于该站点的所有用户，但是可以为用户分配用户策略以覆盖站点策略设置。

  - **用户策略** 可以创建并配置一个或多个用户策略以将对远程用户访问的支持限制为特定用户。用户策略配置将覆盖全局策略和站点策略，但是仅限于分配了该用户策略的特定用户。例如，即使在全局策略和站点策略中启用了远程用户访问，仍然可以指定禁用远程用户访问的用户策略，然后将该用户策略分配给特定用户。如果创建用户策略，则必须将其应用于一个或多个用户，此后该策略才能生效。

> [!IMPORTANT]
> 在一个策略级别应用的 Lync Server 策略设置可能会覆盖在另一个策略级别应用的设置。Lync Server 策略优先顺序为：用户策略（影响力最大）覆盖站点策略，站点策略覆盖全局策略（影响力最小）。这意味着，策略设置与策略所影响的对象距离越近，它对该对象的影响力越大。


这些选项包括以下类型的外部访问：

  - **启用与联盟用户的通信**    如果您需要支持针对联盟合作伙伴域的用户访问，请启用此选项。此设置将为用户配置与其他 SIP 联盟域和托管提供程序（如 Microsoft Office 365）进行通信的能力。通过选择此设置，您可以选择允许与 XMPP 联盟域进行通信。
    
    作为一种选择，如果您先选择“启用与联盟用户的通信”，则可以选择“启用与 XMPP 联盟伙伴的通信”。XMPP 联盟是与使用可扩展消息传递和状态协议 (XMPP) 的组织的联盟。
    
    > [!NOTE]  
    > 如果启用 XMPP 联盟，您还必须选择在拓扑生成器的边缘池配置节中部署“XMPP 联盟”。对 XMPP 联盟进行配置时，将在边缘服务器上部署一个 XMPP 代理并在前端服务器上部署一个 XMPP 网关。
    


  - **启用与远程用户的通信**    如果您希望组织中位于防火墙之外的用户（如远程工作者和正在旅行的用户）能够通过 Internet 连接到 Lync Server，请启用此选项。

  - **启用与公共用户的通信**    如果您希望内部用户能够与公共 IM 提供程序联系人（如 Windows Live、Yahoo\! 和 America Online (AOL) 提供的联系人）进行通信，请启用此选项。
    
    > [!IMPORTANT]  
	> <ul>
    > <li><p>自 2012 年 9 月 1 日起，新订或续订合同不能再购买 Microsoft Lync 公共 IM 连接用户订阅许可证 (“PIC USL”)。拥有有效许可证的客户可继续与 Yahoo! Messenger 联盟直至服务关闭。AOL 和 Yahoo! 的生命周期结束日期已宣布，为 2014 年 6 月。有关详细信息，请参阅 <a href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公共即时消息连接支持</a>。</p></li>
    > <li><p>PIC USL 是一个每用户每月订阅许可证，是 Lync Server 或 Office Communications Server 与 Yahoo! Messenger 联盟所必需的。Microsoft 之所以能够提供此服务离不开 Yahoo! 的支持，但这项支持的基础协议正在逐步终止。</p></li>
    > <li><p>Lync 是一个比以往更强大的工具，它实现了人员跨组织、跨地域的连接。除 Lync 标准 CAL 外，与 Windows Live Messenger 联盟不需要任何附加用户/设备许可证。Skype 联盟将添加到此列表中，以便 Lync 用户能够通过 IM 和语音与数亿用户取得联系。</p></li>
    > </ul>

> [!NOTE]  
> 除了启用外部用户访问支持外，还必须在用户可以使用任何类型的外部用户访问之前，配置策略以控制组织中外部用户访问的使用。有关为外部用户访问创建、配置和应用策略的详细信息，请参阅 <a href="lync-server-2013-enable-or-disable-remote-user-access.md">在 Lync Server 2013 中启用或禁用远程用户访问</a>。



**使用 Windows PowerShell cmdlet 查看外部访问策略**

  - 您可以使用 Lync Server 命令行管理程序和 **Get-CsExternalAccessPolicy** cmdlet 查看外部访问策略。可以从 Lync Server 2013 命令行管理程序或 Windows PowerShell 的远程会话中运行此 cmdlet。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。
    
    若要查看有关所有外部访问策略的信息，请在 Lync Server 命令行管理程序中键入以下命令，然后按 Enter：
    
        Get-CsExternalAccessPolicy
    
    此命令会返回类似下列信息：
    
        Identity                          : Global
        Description                       :
        EnableFederationAccess            : False
        EnableXmppAccess                  : False
        EnablePublicCloudAccess           : False
        EnablePublicCloudAudioVideoAccess : False
        EnableOutsideAccess               : False

## 本部分内容

  - [在 Lync Server 2013 中配置策略以控制联盟用户访问](lync-server-2013-configure-policies-to-control-federated-user-access.md)

  - [在 Lync Server 2013 中配置策略以控制 XMPP 联盟用户访问](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)

  - [在 Lync Server 2013 中配置策略以控制远程用户访问](lync-server-2013-configure-policies-to-control-remote-user-access.md)

  - [在 Lync Server 2013 中配置策略以控制公共用户访问](lync-server-2013-configure-policies-to-control-public-user-access.md)

  - [在 Lync Server 2013 中将外部用户访问策略分配到启用 Lync 的用户](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)

  - [在 Lync Server 2013 中重置或删除外部用户访问策略](lync-server-2013-resetting-or-deleting-external-user-access-policies.md)

