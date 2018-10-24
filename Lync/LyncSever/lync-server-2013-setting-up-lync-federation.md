---
title: Lync Server 2013：设置 Lync 联盟
TOCTitle: 设置 Lync 联盟
ms:assetid: 374ddc43-26f9-499d-be68-a5158adfa49c
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204800(v=OCS.15)
ms:contentKeyID: 49312486
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中设置 Lync 联盟

 

_**上一次修改主题：** 2015-03-09_

如果您已经部署了一台或多台边缘服务器，那么添加联盟方案功能就非常简单。如果尚未设置边缘服务器，则必须先设置边缘服务器。有关详细信息，请参阅规划文档中的 [在 Lync Server 2013 中规划外部用户访问](lync-server-2013-planning-for-external-user-access.md)和部署文档中的 [在 Lync Server 2013 中部署外部用户访问](lync-server-2013-deploying-external-user-access.md)。

> [!NOTE]  
> 如果打算设置 XMPP 联盟、Lync 联盟或公共即时消息连接的任意组合，则可以并行部署它们，也可以一次部署一个。如果通过拓扑生成器和 Lync Server 命令行管理程序配置选项，则应在为一个、两个或全部三个联盟类型配置选项后在边缘服务器上运行部署向导，这样您可以减少需要执行的步骤数目。



## 在拓扑生成器和部署向导中设置 Lync 联盟

1.  在前端服务器上，打开拓扑生成器。展开“边缘池”，然后右键单击您的边缘服务器或边缘服务器池。选择“编辑属性”。

2.  在“编辑属性”中的“常规”下，选择“为此边缘池启用联盟（端口 5061）”。单击“确定”。

3.  单击“操作”，选择“拓扑”，再选择“发布”。当“发布拓扑”中出现提示时，单击“下一步”。完成发布后，单击“完成”。

4.  在边缘服务器上，打开 Lync Server 部署向导。单击“安装或更新 Lync Server 系统”，然后单击“安装或删除 Lync Server 组件”。单击“再次运行”。

5.  在“设置 Lync Server 组件”中，单击“下一步”。摘要屏幕将显示已执行的操作。部署完成后，单击“查看日志”可查看可用日志文件。单击“完成”以完成部署。
    
    > [!IMPORTANT]
    > 您可以选择此选项，但只能为联盟对外发布组织中的一个边缘池或边缘服务器。联盟用户（包括公共即时消息 (IM) 用户）的所有访问都将通过相同的边缘池或单台边缘服务器。例如，如果部署中有一个边缘池或单台边缘服务器部署在纽约，另一个部署在伦敦，并对纽约的边缘池或单台边缘服务器启用联盟支持，则联盟用户的信号流量将通过纽约的边缘池或单台边缘服务器。这同样适用于伦敦用户的通信，尽管伦敦内部用户呼叫伦敦联盟用户时将使用伦敦的池或边缘服务器路由 A/V 流量。


## 对合作伙伴配置联盟

1.  若要设置与其他 Microsoft Lync Server 2013、 Lync Server 2010、 Office Communications Server 2007 R2 或 Office Communicator 2007 的成功联盟，请从下表中选择联盟类型并定义 DNS SRV 记录、DNS 主机（IPv6 的 A 或 AAAA）以及配置适用于该联盟类型的策略：
    
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>联盟类型</th>
    <th>DNS 记录</th>
    <th>策略定义</th>
    <th>说明</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>已发现的伙伴域</p></td>
    <td><p>以 _sipfederationtls._tcp.&lt;外部域名&gt; 格式配置 SRV 记录，其中 SRV 记录的端口值为 TCP 5061 并且“提供此服务的主机”定义为 sip. &lt;外部域名&gt; – 访问边缘服务的 FQDN。有关创建 SRV 记录的详细信息，请参阅<a href="lync-server-2013-configure-dns-for-edge-support.md">在 Lync Server 2013 中配置边缘支持的 DNS</a></p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">在 Lync Server 2013 中启用或禁用联盟和公共 IM 连接</a></p></li>
    <li><p><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">在 Lync Server 2013 中启用或禁用联盟伙伴发现</a></p></li>
    </ul></td>
    <td><p>以前版本将此联盟类型称为 <strong>开放增强联盟</strong>。创建 SRV 记录对于此联盟类型是必需的，并且将允许其他合作伙伴发现您的联盟。</p></td>
    </tr>
    <tr class="even">
    <td><p>所允许的伙伴域</p></td>
    <td><p>以 _sipfederationtls._tcp.&lt;外部域名&gt; 格式配置 SRV 记录，其中 SRV 记录的端口值为 TCP 5061 并且“提供此服务的主机”定义为 sip. &lt;外部域名&gt; – 访问边缘服务的 FQDN。有关创建 SRV 记录的详细信息，请参阅<a href="lync-server-2013-configure-dns-for-edge-support.md">在 Lync Server 2013 中配置边缘支持的 DNS</a></p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">在 Lync Server 2013 中启用或禁用联盟和公共 IM 连接</a></p></li>
    </ul></td>
    <td><p>以前版本将此联盟类型称为 <strong>增强联盟</strong>。创建 SRV 记录对于此联盟类型是可选的，并且将允许其他合作伙伴发现您的联盟。当然，这之后将是 <strong>开放增强联盟</strong>或者 <strong>已发现的伙伴域</strong></p></td>
    </tr>
    <tr class="odd">
    <td><p>允许的伙伴服务器</p></td>
    <td><p>配置 SIP 域名和伙伴 边缘服务器 FQDN 作为策略中的联盟伙伴</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">在 Lync Server 2013 中启用或禁用联盟和公共 IM 连接</a></p></li>
    <li><p><a href="lync-server-2013-configure-support-for-allowed-external-domains.md">在 Lync Server 2013 中配置对允许的外部域的支持</a></p></li>
    <li><p><a href="lync-server-2013-configure-support-for-blocked-external-domains.md">在 Lync Server 2013 中配置对阻止的外部域的支持</a></p></li>
    </ul></td>
    <td><p>此联盟类型定义为一对一关系并且不允许发现其他联盟伙伴。每个联盟伙伴是显式配置的。在以前版本中，这称为 <strong>直接联盟</strong></p></td>
    </tr>
    <tr class="even">
    <td><p>宿主提供商和公共 IM 提供商</p></td>
    <td><p>没有为此联盟类型定义特定 DNS 要求</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">在 Lync Server 2013 中启用或禁用联盟和公共 IM 连接</a></p></li>
    <li><p><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">在 Lync Server 2013 中创建或编辑公共 SIP 联盟提供程序</a></p></li>
    <li><p><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">在 Lync Server 2013 中创建或编辑托管的 SIP 联盟提供程序</a></p></li>
    </ul></td>
    <td><p>此联盟类型定义您要为用户配置的服务和宿主提供商。典型用法包括配置 Windows Live Messenger、Yahoo! 和 AOL 等公共 IM 提供商，以及配置 Lync Online 和 Office 365 等宿主提供商</p>
    
	> [!IMPORTANT]  
	> <ul>
    > <li><p>自 2012 年 9 月 1 日起，新订或续订合同不能再购买 Microsoft Lync 公共 IM 连接用户订阅许可证 (“PIC USL”)。拥有有效许可证的客户可继续与 Yahoo! Messenger 联盟直至服务关闭。AOL 和 Yahoo! 的生命周期结束日期已宣布，为 2014 年 6 月。有关详细信息，请参阅 <a href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公共即时消息连接支持</a>。</p></li>
    > <li><p>PIC USL 是一个每用户每月订阅许可证，是 Lync Server 或 Office Communications Server 与 Yahoo! Messenger 联盟所必需的。Microsoft 之所以能够提供此服务离不开 Yahoo! 的支持，但这项支持的基础协议正在逐步终止。</p></li>
    > <li><p>Lync 是一个比以往更强大的工具，它实现了人员跨组织、跨地域的连接。除 Lync 标准 CAL 外，与 Windows Live Messenger 联盟不需要任何附加用户/设备许可证。Skype 联盟将添加到此列表中，以便 Lync 用户能够通过 IM 和语音与数亿用户取得联系。</p></li>
    > </ul>
	
	</td>
    </tr>
    </tbody>
    </table>


2.  定义和配置任何必需的 DNS 主机（IPv6 的 A 或 AAAA）和 DNS SRV 记录

3.  使用 Lync Server 控制面板或通过使用 Lync Server 命令行管理程序和相应的 cmdlet 定义和配置任何策略。有关 Lync Server 命令行管理程序 cmdlet 的详细信息，请参阅 [联盟和外部访问 Cmdlet](https://docs.microsoft.com/en-us/powershell/module/skype/)
    
    > [!NOTE]  
	> 对于由作为联盟 Lync 合作伙伴的组织者发送的会议，Lync Room System (LRS) 不显示加入按钮。要在 LRS 上显示会议加入链接，发送组织必须使用以下 cmdlet 启用 TNEF：<br />
    > 
    > <code>New-RemoteDomain -DomainName Contoso.com -Name Contoso</code><br />
    > <code>Set-RemoteDomain -Identity Contoso -TNEFEnabled $true</code><br />
    > 请注意，这不是 LRS 特有的。Outlook 和 Lync 在这种情况下也不会显示“加入”链接，因为不传输 MAPI 属性；但在 Outlook 中，用户可以打开会议邀请并单击会议 URL。当 TNEFEnabled 设置为 true 时，Exchange 2013 不会除去包括 OnlineMeetingExternalLink 在内的 MAPI 属性，提醒中将显示“加入”按钮。
    


## 另请参阅

#### 其他资源

[规划 SIP、XMPP 联盟和公共即时消息](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md)  
[管理对 Lync Server 2013 的联盟和外部访问](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)

