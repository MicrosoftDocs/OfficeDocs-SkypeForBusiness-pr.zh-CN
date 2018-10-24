---
title: Lync Server 2013：集成本地统一消息的部署过程
TOCTitle: 集成本地统一消息与 Lync Server 的部署过程
ms:assetid: 269a4436-f09f-415b-96ab-49a64370a385
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425737(v=OCS.15)
ms:contentKeyID: 49312291
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 集成本地统一消息与 Lync Server 2013 的部署过程

 

_**上一次修改主题：** 2016-12-08_

如果要将 Exchange 统一消息 (UM) 与 Lync Server 2013 集成，则必须执行本主题中所述的任务。此外，还应确保查看 [集成本地统一消息与 Lync Server 2013 的指南](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)中所述的规划和部署最佳做法。本主题假定您已经部署 Lync Server 2013 和并置的中介服务器，并且已经为用户启用 Lync Server 2013，但是不一定执行了部署文档的 [在 Lync Server 2013 中部署企业语音](lync-server-2013-deploying-enterprise-voice.md)中所述的用于启用 企业语音的所有部署和配置步骤。

## 统一消息集成过程

> [!IMPORTANT]
> 与组织的 Exchange 管理员协调，以确认为帮助确保实现顺利而又成功的集成每人所需执行的任务，这一点很重要。



<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>阶段</th>
<th>步骤</th>
<th>所需的组和角色</th>
<th>部署文档</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>部署下列各项之一：</p>
<ul>
<li><p>Microsoft Exchange Server 2007 Service Pack 1 (SP2) 或最新的 Service Pack</p></li>
<li><p>Microsoft Exchange Server 2010 或最新的 Service Pack</p></li>
<li><p>Microsoft Exchange Server 2013</p></li>
</ul></td>
<td><p>如果使用的是 Microsoft Exchange Server 2013，在与 Lync Server 2013 相同或不同的林中安装下列 Exchange Server 角色：</p>
<ul>
<li><p>客户端访问</p></li>
<li><p>邮箱</p></li>
</ul>
<p>如果 Microsoft Exchange Server 2013 和 Exchange 统一消息 (UM) 安装在不同的林中，则将每个 Exchange 林配置为信任 Lync Server 2013 林。</p>
<p>如果使用的是 Exchange 2010，在与 Lync Server 2013 相同或不同的林中安装下列 Exchange Server 角色：</p>
<ul>
<li><p>统一消息</p></li>
<li><p>集线器传输</p></li>
<li><p>客户端访问</p></li>
<li><p>邮箱</p></li>
</ul>
<p>如果 Lync Server 2013 和 Exchange 统一消息 (UM) 安装在不同的林中，则将每个 Exchange 林配置为信任 Lync Server 2013 林。</p></td>
<td><p>企业管理员（如果这是组织中的第一个 Exchange Server）</p>
<p>- 或者 -</p>
<p>Exchange 组织管理员（如果这不是组织中的第一个 Exchange Server）</p></td>
<td><p>请参阅适用于您的 Exchange Server 版本的文档：</p>
<dl>
<dd><p>Exchange Server 2007 部署文档，网址为 <a href="http://go.microsoft.com/fwlink/p/?linkid=268694">http://go.microsoft.com/fwlink/p/?LinkId=268694</a>。</p>
</dd>
<dd><p>Exchange Server 2010 或最新的 Service Pack 部署文档，网址为 <a href="http://go.microsoft.com/fwlink/p/?linkid=268695">http://go.microsoft.com/fwlink/p/?LinkId=268695</a>。</p>
</dd>
<dd><p>Microsoft Exchange Server 2013 规划和部署，网址为 <a href="http://go.microsoft.com/fwlink/p/?linkid=266569">http://go.microsoft.com/fwlink/p/?LinkId=266569</a>。</p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p>安装证书。</p></td>
<td><p>从受信任的根证书颁发机构 (CA) 中为每台 Exchange UM 服务器下载并安装证书。证书是在运行 Exchange UM 和 Lync Server 2013 的服务器之间实现相互传输层安全性 (MTLS) 所必需的。</p></td>
<td><p>管理员</p></td>
<td><p><a href="lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md">在运行 Microsoft Exchange Server 统一消息的服务器上配置证书</a></p></td>
</tr>
<tr class="odd">
<td><p>创建和配置新的 Exchange UM SIP 拨号计划。</p></td>
<td><p>在 Exchange UM 服务器上，根据组织的特定部署要求创建 SIP 拨号计划。</p></td>
<td><p>Exchange 组织管理员</p></td>
<td><p>对于 Exchange 2007 SP1 或最新的 Service Pack，请参阅“如何创建统一消息 SIP URI 拨号计划”，网址为 <a href="http://go.microsoft.com/fwlink/p/?linkid=268632">http://go.microsoft.com/fwlink/p/?linkId=268632</a>。</p>
<p>对于 Exchange 2010 或最新的 Service Pack，请参阅“创建 UM 拨号计划”，网址为 <a href="http://go.microsoft.com/fwlink/p/?linkid=268674">http://go.microsoft.com/fwlink/p/?linkId=268674</a>。</p>
<p>对于 Exchange 2013，请参阅“统一消息”，网址为 <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>。</p></td>
</tr>
<tr class="even">
<td><p>配置 Exchange UM SIP 拨号计划的安全设置。</p></td>
<td><p>要加密企业语音流量，请将 Exchange UM SIP 拨号计划上的安全设置配置为“SIP 安全”或“安全”。如果已经或计划在环境中部署 Lync Phone Edition 设备，则该步骤尤其重要。要使 Lync Phone Edition 设备在 Exchange UM 集成的环境中正常工作，Lync Server 加密设置必须与 Exchange UM 拨号计划安全设置一致。有关详细信息，请参考部署文档。</p></td>
<td><p>Exchange 组织管理员</p></td>
<td><p><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">在 Microsoft Exchange 中为 Lync Server 2013 配置统一消息</a></p>
<p>对于 Exchange 2007 SP1 或最新的 Service Pack，另请参阅：</p>
<p>“配置统一消息拨号计划上的安全性设置”，网址为 <a href="http://go.microsoft.com/fwlink/p/?linkid=268696">http://go.microsoft.com/fwlink/p/?LinkId=268696</a>。</p>
<p></p>
<p>对于 Exchange 2010 或最新的 Service Pack，另请参阅：</p>
<p>“在 UM 拨号计划中配置 VoIP 安全性”，网址为 <a href="http://go.microsoft.com/fwlink/p/?linkid=268697">http://go.microsoft.com/fwlink/p/?LinkId=268697</a>。</p>
<p></p>
<p>对于 Exchange 2013，请参阅“统一消息”，网址为 <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>。</p></td>
</tr>
<tr class="odd">
<td><p>向 Exchange UM SIP 拨号计划中添加统一消息服务器。</p></td>
<td><p>要使新安装的统一消息服务器可以应答和处理传入呼叫，必须将该统一消息服务器添加到 UM 拨号计划中。在这种情况下，将服务器添加到 Exchange UM SIP 拨号计划中。</p></td>
<td><p>管理员</p>
<p>Exchange Server 管理员</p></td>
<td><p>对于 Exchange 2007 SP1 或最新的 Service Pack，请参阅“如何将统一消息服务器添加到拨号计划中”，网址为 <a href="http://go.microsoft.com/fwlink/p/?linkid=268681">http://go.microsoft.com/fwlink/p/?linkId=268681</a>。</p>
<p>对于 Exchange 2010 或最新的 Service Pack，请参阅“查看或配置 UM 服务器的属性”，网址为 <a href="http://go.microsoft.com/fwlink/p/?linkid=268682">http://go.microsoft.com/fwlink/p/?linkId=268682</a>。</p>
<p></p>
<p>对于 Exchange 2013，请参阅“统一消息”，网址为 <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>。</p></td>
</tr>
<tr class="even">
<td><p>配置使用 SIP 地址的邮箱。</p></td>
<td><p>为将使用 Exchange UM 功能的企业语音用户的邮箱分配 SIP 地址。</p></td>
<td><p>Lync Server 2013 管理员</p>
<p>Exchange 收件人管理员</p></td>
<td><p>对于 Exchange 2007 SP1 或最新的 Service Pack，请参阅“如何添加、删除或修改已启用 UM 的用户的 SIP 地址”，网址为 <a href="http://go.microsoft.com/fwlink/p/?linkid=268698">http://go.microsoft.com/fwlink/p/?LinkId=268698</a>。</p>
<p>对于 Exchange 2010 或最新的 Service Pack，请参阅“为启用了 UM 的用户修改 SIP 地址”，网址为 <a href="http://go.microsoft.com/fwlink/p/?linkid=268699">http://go.microsoft.com/fwlink/p/?LinkId=268699</a>。</p>
<p></p>
<p>对于 Exchange 2013，请参阅“统一消息”，网址为 <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>。</p></td>
</tr>
<tr class="odd">
<td><p>运行 exchucutil.ps1 脚本。</p></td>
<td><p>在运行 Exchange UM 的服务器上，打开 Exchange 命令行管理程序并运行 exchucutil.ps1 脚本，这会执行下列操作：</p>
<ul>
<li><p>授予 Lync Server 2013 对 Exchange UMActive Directory 域服务 对象（特别是在上个任务中创建的 SIP 拨号计划）的读取权限。</p></li>
<li><p>在 Active Directory 中为启用企业语音的用户所在的 Lync Server 2013 Enterprise Edition 池或 Standard Edition Server 创建一个统一消息 IP 网关对象。</p></li>
<li><p>为每个网关创建一个 Exchange UM 智能寻线。该智能寻线的前导标识符将是与相应网关相关联的拨号计划的名称。如果存在多个拨号计划，则需要进行一对一映射。</p></li>
</ul></td>
<td><p>Exchange 组织管理员</p>
<p>Exchange 收件人管理员</p></td>
<td><p><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">在 Microsoft Exchange 中为 Lync Server 2013 配置统一消息</a></p></td>
</tr>
<tr class="even">
<td><p>配置 Lync Server 2013 拨号计划。</p></td>
<td><p>如果要与 Exchange 2007 SP1 或最新的 Service Pack 或者 Exchange 2010 集成，请创建名称与 Exchange UM 拨号计划完全限定的域名 (FQDN) 匹配的新 企业语音拨号计划。</p>
<div>

> [!NOTE]  
> 您需要对每个 UM 拨号计划执行此操作。


</div>
<p>如果要与 Exchange 2010 SP1 集成，请确保已配置合适的全局/站点级别或池级别的 企业语音拨号计划。</p>
<div>

> [!NOTE]  
> 如果要与 Exchange 2010 SP1 集成， Lync Server 拨号计划和 Exchange UM SIP 拨号计划的名称则不需要匹配。


</div></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-configuring-dial-plans.md">在 Lync Server 2013 中配置拨号计划</a></p></td>
</tr>
<tr class="odd">
<td><p>运行 Exchange UM 集成工具。</p></td>
<td><p>在 Lync Server 2013 上运行 <strong>ocsumutil.exe</strong>，将执行下列操作：</p>
<ul>
<li><p>创建订阅者访问和自动助理联系对象。</p></li>
<li><p>验证是否存在名称与 Exchange UM 拨号计划 FQDN 匹配的 企业语音拨号计划。如果运行的是 Exchange 2010 SP1 或更高版本，则拨号计划名称不需要匹配，可以忽略工具中的相关警告。</p></li>
</ul>
<p>此工具的工作方式是，扫描 Active Directory 中的 Exchange UM 设置并允许 Lync Server 2013 管理员查看、创建和编辑联系对象。</p></td>
<td><p>RTCUniversalServerAdmins <em>和</em> RTCUniversalUserAdmins</p>
<div>

> [!IMPORTANT]
> 要成功运行 ocsumutil.exe，用户必须同时属于这两个组。

</div>
<div>

> [!NOTE]  
> 要创建联系对象，运行 ocsumutil.exe 的用户必须对存储新联系对象的 Active Directory 组织单位 (OU) 具有正确的权限。可以通过运行 <strong>Grant-CsOUPermission</strong> cmdlet 授予此权限。有关详细信息，请参阅 Lync Server 命令行管理程序文档。


</div></td>
<td><p><a href="lync-server-2013-configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server.md">配置 Lync Server 2013 以使用 Microsoft Exchange Server 统一消息</a></p></td>
</tr>
<tr class="even">
<td><p>如有必要，执行其他 企业语音配置步骤。</p></td>
<td><p>如果尚未配置有关服务器或用户的 企业语音设置，请执行下列一项或多项操作：</p>
<ul>
<li><p>部署和配置</p>
<p>公用电话交换网 (PSTN) 网关和中介服务器</p></li>
<li><p>定义语音策略、PSTN 用法记录和出站呼叫路由。</p></li>
<li><p>为用户启用企业语音。</p></li>
<li><p>（可选）为特定用户配置拨号计划。</p></li>
</ul>
<p>可能还需要其他配置步骤，具体取决于启用的 企业语音功能。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>RTCUniversalUserAdmins</p></td>
<td><p>请参阅以下各节中的主题：</p>
<ul>
<li><p><a href="lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md">在 Lync Server 2013 中配置语音策略、PSTN 用法记录和语音路由</a></p></li>
<li><p><a href="lync-server-2013-deploying-enterprise-voice.md">在 Lync Server 2013 中部署企业语音</a></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>为企业语音用户启用 Exchange UM。</p></td>
<td><p>在 Exchange UM 服务器上，确保已创建统一消息邮箱策略并为每个用户分配了唯一的分机号，然后为用户启用统一消息。</p></td>
<td><p>Exchange 收件人管理员</p></td>
<td><p>对于 Exchange 2007 SP1 或最新的 Service Pack，请参阅“如何为用户启用统一消息”，网址为 <a href="http://go.microsoft.com/fwlink/p/?linkid=268700">http://go.microsoft.com/fwlink/p/?LinkId=268700</a>。</p>
<p>对于 Exchange 2010 或最新的 Service Pack，请参阅“为用户启用统一消息”，网址为 <a href="http://go.microsoft.com/fwlink/p/?linkid=268701">http://go.microsoft.com/fwlink/p/?LinkId=268701</a>。</p>
<p></p>
<p>对于 Exchange 2013，请参阅“统一消息”，网址为 <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>。</p></td>
</tr>
</tbody>
</table>

