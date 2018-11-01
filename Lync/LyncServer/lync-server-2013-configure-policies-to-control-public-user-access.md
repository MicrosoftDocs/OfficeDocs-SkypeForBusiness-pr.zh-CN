---
title: Lync Server 2013：配置策略以控制公共用户访问
TOCTitle: 配置策略以控制公共用户访问
ms:assetid: 090aea0f-ef0b-49da-9c80-02d9279f2fa6
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg520946(v=OCS.15)
ms:contentKeyID: 49311927
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中配置策略以控制公共用户访问

 

_**上一次修改主题：** 2016-12-08_

公共即时消息 (IM) 连接允许您的组织中的用户使用 IM 与公共 IM 服务提供商提供的 IM 服务（包括 Inernet 服务的 Windows Live 网络、Yahoo\! 和 AOL）的用户进行通信。您配置一个或多个外部用户访问策略来控制公共用户能否与内部 Lync Server 用户协作。公共即时消息连接是一项增加的功能，它依赖于您的部署和用户的配置。此外，它还依赖于公共 IM 提供商对于服务的设置。有关如何设置您的部署以使用公共提供程序的信息，请参阅“Microsoft Lync Server、Office Communications Server 和 Live Communications Server 的公共 IM 连接设置指南”： <http://go.microsoft.com/fwlink/?linkid=269821>

> [!IMPORTANT]  
> <ul>
> <li><p>自 2012 年 9 月 1 日起，新订或续订合同不能再购买 Microsoft Lync 公共 IM 连接用户订阅许可证 (“PIC USL”)。拥有有效许可证的客户可继续与 Yahoo! Messenger 联盟直至服务关闭。AOL 和 Yahoo! 的生命周期结束日期已宣布，为 2014 年 6 月。有关详细信息，请参阅 <a href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公共即时消息连接支持</a>。</p></li>
> <li><p>PIC USL 是一个每用户每月订阅许可证，是 Lync Server 或 Office Communications Server 与 Yahoo! Messenger 联盟所必需的。Microsoft 之所以能够提供此服务离不开 Yahoo! 的支持，但这项支持的基础协议正在逐步终止。</p></li>
> <li><p>Lync 是一个比以往更强大的工具，它实现了人员跨组织、跨地域的连接。除 Lync 标准 CAL 外，与 Windows Live Messenger 联盟不需要任何附加用户/设备许可证。Skype 联盟将添加到此列表中，以便 Lync 用户能够通过 IM 和语音与数亿用户取得联系。</p></li>
> </ul>


若要访问 Microsoft Lync Server 公共 IM 连接设置网站，请使用下面的链接：[http://go.microsoft.com/fwlink/p/?linkId=212638](http://go.microsoft.com/fwlink/p/?linkid=212638)

若要控制公共用户访问，可以在全局、站点和用户级别配置策略。有关可以配置的策略类型的详细信息，请参阅部署文档或规划文档中的 [在 Lync Server 2013 中配置对外部用户访问的支持](lync-server-2013-configuring-support-for-external-user-access.md)。 在一个策略级别应用的 Lync Server 策略设置可能会覆盖在另一个策略级别应用的设置。Lync Server 策略优先顺序为：用户策略（影响力最大）覆盖站点策略，站点策略覆盖全局策略（影响力最小）。这意味着，策略设置与策略所影响的对象距离越近，它对该对象的影响力越大。

对于 IM 邀请，响应取决于客户端软件。除非外部发件人被用户配置的规则（即，用户客户端的“允许”和“阻止”列表中的设置）显式阻止，否则将接受请求。此外，如果用户选择阻止来自其“允许”列表之外的用户的所有 IM，也可以阻止 IM 邀请。

> [!NOTE]  
> 即使没有为组织启用联盟，也可以配置控制公共用户访问的策略。但是，只有为组织启用联盟后，配置的策略才会生效。有关启用联盟的详细信息，请参阅部署文档或操作文档中的 <a href="lync-server-2013-enable-or-disable-remote-user-access.md">在 Lync Server 2013 中启用或禁用远程用户访问</a>。此外，如果指定某个用户策略来控制公共用户访问，则该策略仅应用于已启用 Lync Server 并配置为使用该策略的用户。有关指定可登录 Lync Server 的公共用户的详细信息，请参阅部署文档或操作文档中的 <a href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">在 Lync Server 2013 中将外部用户访问策略分配到启用 Lync 的用户</a>。



使用以下过程来配置策略，以支持一个或多个公共 IM 提供商的用户进行访问。

## 配置外部访问策略以支持公共用户访问

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“外部用户访问”，然后单击“外部访问策略”。

4.  在“外部访问策略”页上，执行下列操作之一：
    
      - 要将全局策略配置为支持公共用户访问，请单击该全局策略，再单击“编辑”，然后单击“显示详细信息”。
    
      - 要创建新的站点策略，请单击“新建”，然后单击“站点策略”。在“选择站点”中，单击列表中相应的站点，然后单击“确定”。
    
      - 要创建新的用户策略，请单击“新建”，然后单击“用户策略”。在“新建外部访问策略”的“名称”字段中，创建一个唯一的名称以指示用户策略的作用范围（例如， **EnablePublicUsers** 代表启用公共用户通信的用户策略）。
    
      - 要更改现有的策略，请单击表中列出的相应策略，再单击“编辑”，然后单击“显示详细信息”。

5.  （可选）如果要添加或编辑说明，请在“说明”中为策略指定相应的信息。

6.  执行下列操作之一：
    
      - 要为策略启用公共用户访问，请选中“启用与公共用户的通信”复选框。
    
      - 要为策略禁用公共用户访问，请清除“启用与公共用户的通信”复选框。

7.  单击“提交”。

要启用公共用户访问，您还必须在组织中启用对联盟的支持。有关详细信息，请参阅 [在 Lync Server 2013 中配置策略以控制联盟用户访问](lync-server-2013-configure-policies-to-control-federated-user-access.md)。

如果这是一个用户策略，您还必须将该策略应用到您希望能与公共用户协作的公共用户。有关详细信息，请参阅 [分配每用户策略](lync-server-2013-assigning-per-user-policies.md)。

## 另请参阅

#### 任务

[在 Lync Server 2013 中创建或编辑公共 SIP 联盟提供程序](lync-server-2013-create-or-edit-public-sip-federated-providers.md)  

#### 其他资源

[在 Lync Server 2013 中管理组织的 SIP 联盟提供程序](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)

