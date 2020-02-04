---
title: Lync Server 2013：设置 Lync 联盟
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Lync federation
ms:assetid: 374ddc43-26f9-499d-be68-a5158adfa49c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204800(v=OCS.15)
ms:contentKeyID: 48183822
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7df0dd85bac0aa3053fb6a3496d6a13fa1f4a85e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764598"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-lync-federation-in-lync-server-2013"></a>在 Lync Server 2013 中设置 Lync 联盟

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2014-03-27_

如果你已部署了 Edge 服务器或服务器，则添加联合方案功能是直接的。 如果尚未设置边缘服务器，则必须首先执行此操作。 有关详细信息，请参阅：在[Lync server 2013 中规划外部用户访问](lync-server-2013-planning-for-external-user-access.md)在部署文档中的 "lync server 2013" 中的 "规划文档" 和 "[部署外部用户访问](lync-server-2013-deploying-external-user-access.md)"。

<div>


> [!NOTE]  
> 如果想要设置 XMPP 联盟、Lync 联合身份验证或公共即时消息连接的任意组合，可以同时部署它们或一次一个。 如果通过拓扑生成器和 Lync Server Management shell 配置选项，则在配置了一种、两种或三种联合身份的选项后，在 Edge 服务器上运行部署向导，可以减少所需的步骤数。



</div>

<div>

## <a name="setting-up-lync-federation-in-topology-builder-and-the-deployment-wizard"></a>在拓扑生成器和部署向导中设置 Lync Federation

1.  在前端服务器上，打开拓扑生成器。 展开 "边缘池"，然后右键单击 "边缘服务器" 或 "边缘服务器" 池。 选择 "编辑属性"。

2.  在 "常规" 下的 "编辑属性" 下，选择 "为此边缘池启用联盟（端口5061）"。 单击“确定”。

3.  单击 "操作"，选择 "拓扑"，选择 "发布"。 当系统提示发布拓扑时，单击 "下一步"。 发布完成后，单击 "完成"。

4.  在边缘服务器上，打开 "Lync Server 部署向导"。 单击 "安装或更新 Lync 服务器系统"，然后单击 "设置" 或 "删除 Lync Server 组件"。 再次单击 "运行"。

5.  在 "安装 Lync 服务器组件" 中，单击 "下一步"。 "摘要" 屏幕将显示执行时的操作。 部署完成后，单击 "查看日志" 以查看可用的日志文件。 单击 "完成" 以完成部署。
    
    <div>
    

    > [!IMPORTANT]  
    > 你可以选择此选项，但你的组织中只能为联盟发布一个 Edge 池或边缘服务器。 联盟用户（包括公共即时消息（IM）用户）的所有访问权限，请访问同一 Edge 池或单个边缘服务器。 例如，如果你的部署包括在纽约部署的 Edge 池或单层服务器，并且在伦敦部署了一个，并且你在纽约的 Edge 池或单边服务器上启用了联合身份验证支持，则联盟用户的信号流量将通过纽约边缘池或单边服务器。 这同样适用于 London 用户的通信，尽管 London 内部用户呼叫 London 联盟用户时将使用 London 池或边缘服务器路由 A/V 流量。

    
    </div>

</div>

<div>

## <a name="configuring-federation-with-partners"></a>与合作伙伴配置联盟

1.  若要与另一个 Microsoft Lync Server 2013、Lync Server 2010、Office 通信服务器 2007 R2 或 Office Communicator 2007 设置成功的联盟，请从下表中选择联盟的类型并定义 DNS SRV 记录、DNS 主机（A 或 AAAA）IPv6）和配置适用于联盟类型的策略：
    
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>联合身份验证类型</th>
    <th>DNS 记录</th>
    <th>策略定义</th>
    <th>注释</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>已发现合作伙伴域</p></td>
    <td><p>配置 _sipfederationtls _tcp 格式的 SRV 记录。&lt;外部域名&gt;，SRV 记录的端口值为 TCP 5061，并且<strong>提供此服务的主机</strong>定义为 sip。 &lt;外部域名&gt; -您的访问边缘服务的 FQDN。 有关创建 SRV 记录的详细信息，请参阅<a href="lync-server-2013-configure-dns-for-edge-support.md">在 Lync Server 2013 中配置 edge 支持的 DNS</a></p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">在 Lync Server 2013 中启用或禁用联盟和公共 IM 连接</a></p></li>
    <li><p><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">在 Lync Server 2013 中启用或禁用联盟伙伴发现</a></p></li>
    </ul></td>
    <td><p>以前的版本称为 "<strong>增强联盟</strong>" 这种类型的联合。 这种类型的联盟需要创建 SRV 记录，这是为了允许其他合作伙伴发现你的联盟。</p></td>
    </tr>
    <tr class="even">
    <td><p>允许的伙伴域</p></td>
    <td><p>配置 _sipfederationtls _tcp 格式的 SRV 记录。&lt;外部域名&gt;，SRV 记录的端口值为 TCP 5061，并且<strong>提供此服务的主机</strong>定义为 sip。 &lt;外部域名&gt; -您的访问边缘服务的 FQDN。 有关创建 SRV 记录的详细信息，请参阅<a href="lync-server-2013-configure-dns-for-edge-support.md">在 Lync Server 2013 中配置 edge 支持的 DNS</a></p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">在 Lync Server 2013 中启用或禁用联盟和公共 IM 连接</a></p></li>
    </ul></td>
    <td><p>以前版本将此类型的联合称为<strong>增强联盟</strong>。 SRV 记录的创建对于这种类型的联盟是可选的，并且允许其他合作伙伴发现你的联盟。 当然，这是一个打开的<strong>增强联盟</strong>，或者是已<strong>发现的合作伙伴域</strong></p></td>
    </tr>
    <tr class="odd">
    <td><p>允许的合作伙伴服务器</p></td>
    <td><p>在策略中将 SIP 域名和合作伙伴边缘服务器 FQDN 配置为联盟伙伴</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">在 Lync Server 2013 中启用或禁用联盟和公共 IM 连接</a></p></li>
    <li><p><a href="lync-server-2013-configure-support-for-allowed-external-domains.md">在 Lync Server 2013 中配置对允许的外部域的支持</a></p></li>
    <li><p><a href="lync-server-2013-configure-support-for-blocked-external-domains.md">在 Lync Server 2013 中配置对阻止的外部域的支持</a></p></li>
    </ul></td>
    <td><p>此联合类型是一对一关系的定义，不允许发现其他联合合作伙伴。 每个联盟伙伴都是明确配置的。 在以前的版本中，这称为<strong>直接联盟</strong></p></td>
    </tr>
    <tr class="even">
    <td><p>托管提供商和公共 IM 提供商</p></td>
    <td><p>没有为此类型的联合定义特定的 DNS 要求</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">在 Lync Server 2013 中启用或禁用联盟和公共 IM 连接</a></p></li>
    <li><p><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">在 Lync Server 2013 中创建或编辑公共 SIP 联盟提供程序</a></p></li>
    <li><p><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">在 Lync Server 2013 中创建或编辑托管的 SIP 联盟提供程序</a></p></li>
    </ul></td>
    <td><p>此联合类型定义你希望为你的用户配置的服务和托管提供程序。 典型用法包括公共 IM 提供商（如 Windows Live Messenger）的配置 Yahoo！ 和 AOL 以及托管提供商（如 Lync Online 和 Office 365）</p>
    <div>

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P>从2012年9月1日起，Microsoft Lync 公共 IM 连接用户订阅许可证（"PIC USL"）不再可用于购买新的或续订协议。 具有活动许可证的客户将能够继续与 Yahoo！进行联盟 Messenger，直到服务关闭日期。 AOL 和 Yahoo！的有效期结束日期为2014年6月 已宣布。 有关详细信息，请参阅<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公共即时消息连接支持</A>。</P>
    > <LI>
    > <P>PIC USL 是 Lync Server 或 Office 通信服务器与 Yahoo！联合所需的每个每个用户每月订阅许可证。 Messenger. Microsoft 提供此服务的能力已作为对 Yahoo！的支持，它的底层协议被向下缠绕。</P>
    > <LI>
    > <P>Lync 比以往更多，是一种强大的工具，用于跨组织和全球各地的人员进行连接。 与 Windows Live Messenger 的联盟不需要除 Lync 标准 CAL 之外的其他用户/设备许可证。 Skype 联盟将添加到此列表，使 Lync 用户可以通过 IM 和语音与成百上千人联系。</P></LI></UL>


    </div></td>
    </tr>
    </tbody>
    </table>


2.  定义和配置任何所需的 DNS 主机（A 或 AAAA for IPv6）和 DNS SRV 记录

3.  使用 Lync Server 控制面板或使用 Lync Server 命令行管理程序和相应的 cmdlet 定义和配置任何策略。 有关 Lync Server Management Shell cmdlet 的详细信息，请参阅[Lync server 2013 中的联盟和外部访问 cmdlet](https://docs.microsoft.com/powershell/module/skype/)
    
    <div>
    

    > [!NOTE]  
    > Lync 会议室系统（LRS）不显示由联盟 Lync 合作伙伴中的组织者发送的会议的 "联接" 按钮。 若要在 LRS 上显示会议加入链接，发送组织必须使用以下 cmdlet 启用 TNEF：<BR><BR><CODE>New-RemoteDomain -DomainName Contoso.com -Name Contoso</CODE><BR><CODE>Set-RemoteDomain -Identity Contoso -TNEFEnabled $true</CODE><BR>请注意，这不是 LRS 的特定功能。 在这种情况下，outlook 和 Lync 也不会显示联接链接，因为 MAPI 属性未传输，但在 Outlook 情况下，用户可以打开会议邀请，然后单击会议 URL。 当 TNEFEnabled 设置为 true 时，Exchange 2013 不会去除 MAPI 属性（包括 OnlineMeetingExternalLink），并且将在提醒中显示 "加入" 按钮。

    
    </div>

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中规划 SIP、XMPP 联盟和公共即时消息](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md)  
[管理对 Lync Server 2013 的联盟和外部访问](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

