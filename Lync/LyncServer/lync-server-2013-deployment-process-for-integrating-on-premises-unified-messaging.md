---
title: 集成本地统一消息的部署过程
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for integrating on-premises Unified Messaging and Lync Server
ms:assetid: 269a4436-f09f-415b-96ab-49a64370a385
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425737(v=OCS.15)
ms:contentKeyID: 48183664
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53dcbeb362387c31a97ad1e26713b642f82b2390
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529119"
---
# <a name="deployment-process-for-integrating-on-premises-unified-messaging-and-lync-server-2013"></a>集成本地统一消息和 Lync Server 2013 的部署过程

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-12-17_

如果要将 Exchange 统一消息 (UM) 与 Lync Server 2013 集成，则必须执行本主题中所述的任务。 此外，请务必查看有关 [集成本地统一消息和 Lync Server 2013 指南](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)中所述的规划和部署最佳做法。 本主题假定您已使用并置中介服务器部署了 Lync Server 2013，并且您已为用户启用 Lync Server 2013，但并不一定已执行了所有部署和配置步骤来启用企业语音，如部署文档中的 "在 [Lync Server 2013 中部署企业语音](lync-server-2013-deploying-enterprise-voice.md) " 中所述。

<div>

## <a name="unified-messaging-integration-process"></a>统一消息集成过程

<div>


> [!IMPORTANT]
> 一定要与组织的 Exchange 管理员进行协调以确认您要执行的任务，以帮助确保顺利、成功的集成，这一点非常重要。



</div>


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
<li><p>Microsoft Exchange Server 2007 Service Pack 1 (SP2) 或最新的 Service pack</p></li>
<li><p>Microsoft Exchange Server 2010 或最新的 service pack</p></li>
<li><p>Microsoft Exchange Server 2013</p></li>
</ul></td>
<td><p>如果使用的是 Microsoft Exchange Server 2013，请在与 Lync Server 2013 相同的林或不同林中安装以下 Exchange 服务器角色：</p>
<ul>
<li><p>客户端访问</p></li>
<li><p>邮箱</p></li>
</ul>
<p>如果 Microsoft Exchange Server 2013 和 Exchange 统一消息 (UM) 安装在不同的林中，则将每个 Exchange 林配置为信任 Lync Server 2013 林。</p>
<p>如果使用的是 Exchange 2010，请在与 Lync Server 2013 相同的林中或不同的林中安装以下 Exchange 服务器角色：</p>
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
<dt><span></span></dt>
<dd><p>Exchange Server 2007 中的部署文档 <a href="https://go.microsoft.com/fwlink/p/?linkid=268694">https://go.microsoft.com/fwlink/p/?LinkId=268694</a> 。</p>
</dd>
<dt><span></span></dt>
<dd><p>上的 Exchange Server 2010 或最新的 service pack 部署文档 <a href="https://go.microsoft.com/fwlink/p/?linkid=268695">https://go.microsoft.com/fwlink/p/?LinkId=268695</a> 。</p>
</dd>
<dt><span></span></dt>
<dd><p>Microsoft Exchange Server 2013 规划和部署位置 <a href="https://go.microsoft.com/fwlink/p/?linkid=266569">https://go.microsoft.com/fwlink/p/?LinkId=266569</a> 。</p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p>安装证书。</p></td>
<td><p>从受信任的根证书颁发机构 (CA) 中为每个 Exchange UM 服务器下载并安装证书。 证书是运行 Exchange UM 和 Lync Server 2013 的服务器之间的相互传输级安全性 (MTLS) 所必需的。</p></td>
<td><p>管理员</p></td>
<td><p><a href="lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md">在运行 Microsoft Exchange Server 统一消息的服务器上配置证书</a></p></td>
</tr>
<tr class="odd">
<td><p>创建和配置新的 Exchange UM SIP 拨号计划。</p></td>
<td><p>在 Exchange UM 服务器上，根据您的组织的特定部署要求创建 SIP 拨号计划。</p></td>
<td><p>Exchange 组织管理员</p></td>
<td><p>对于 Exchange 2007 SP1 或最新的 service pack，请参阅 &quot; 如何在中创建统一消息 SIP URI 拨号计划 &quot; <a href="https://go.microsoft.com/fwlink/p/?linkid=268632">https://go.microsoft.com/fwlink/p/?linkId=268632</a> 。</p>
<p>有关 Exchange 2010 或最新的 service pack，请参阅 &quot; 在上创建 UM 拨号计划 &quot; <a href="https://go.microsoft.com/fwlink/p/?linkid=268674">https://go.microsoft.com/fwlink/p/?linkId=268674</a> 。</p>
<p>对于 Exchange 2013，请参阅中的统一消息 <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a> 。</p></td>
</tr>
<tr class="even">
<td><p>配置 Exchange UM SIP 拨号计划的安全设置。</p></td>
<td><p>若要加密企业语音流量，请将 Exchange UM SIP 拨号计划中的安全设置配置为 " <strong>SIP 安全</strong> " 或 " <strong>安全</strong>"。 如果你已部署或计划在你的环境中部署 Lync Phone Edition 设备，则这是一个非常重要的步骤。 为了使 Lync Phone Edition 设备在具有 Exchange UM 集成的环境中正常运行，Lync Server 加密设置必须与 Exchange UM 拨号计划安全设置一致。 有关详细信息，请参考部署文档。</p></td>
<td><p>Exchange 组织管理员</p></td>
<td><p><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">在 Microsoft Exchange 上为 Lync Server 2013 配置统一消息</a></p>
<p>对于 Exchange 2007 SP1 或最新的 service pack，另请参阅：</p>
<p>&quot;如何在的统一消息拨号计划上配置安全性 &quot; <a href="https://go.microsoft.com/fwlink/p/?linkid=268696">https://go.microsoft.com/fwlink/p/?LinkId=268696</a> 。</p>
<p>对于 Exchange 2010 或最新的 Service Pack，另请参阅：</p>
<p>&quot;在 UM 拨号计划中配置 VoIP 安全性 &quot; <a href="https://go.microsoft.com/fwlink/p/?linkid=268697">https://go.microsoft.com/fwlink/p/?LinkId=268697</a> 。</p>
<p>对于 Exchange 2013，请参阅中的统一消息 <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a> 。</p></td>
</tr>
<tr class="odd">
<td><p>将统一消息服务器添加到 Exchange UM SIP 拨号计划。</p></td>
<td><p>要使新安装的统一消息服务器可以应答和处理传入呼叫，必须将该统一消息服务器添加到 UM 拨号计划中。 在这种情况下，请将服务器添加到 Exchange UM SIP 拨号计划中。</p></td>
<td><p>管理员</p>
<p>Exchange Server 管理员</p></td>
<td><p>对于 Exchange 2007 SP1 或最新的 service pack，请参阅 &quot; 如何将统一消息服务器添加到拨号计划 &quot; <a href="https://go.microsoft.com/fwlink/p/?linkid=268681">https://go.microsoft.com/fwlink/p/?linkId=268681</a> 。</p>
<p>有关 Exchange 2010 或最新的 service pack，请参阅 &quot; 在上查看或配置 UM 服务器的属性 &quot; <a href="https://go.microsoft.com/fwlink/p/?linkid=268682">https://go.microsoft.com/fwlink/p/?linkId=268682</a> 。</p>
<p>对于 Exchange 2013，请参阅中的统一消息 <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a> 。</p></td>
</tr>
<tr class="even">
<td><p>配置使用 SIP 地址的邮箱。</p></td>
<td><p>将 SIP 地址分配给将使用 Exchange UM 功能的企业语音用户的邮箱。</p></td>
<td><p>Lync Server 2013 管理员</p>
<p>Exchange 收件人管理员</p></td>
<td><p>对于 Exchange 2007 SP1 或最新的 service pack，请参阅 &quot; 如何在上添加、删除或修改 UM-Enabled 用户的 SIP &quot; 地址 <a href="https://go.microsoft.com/fwlink/p/?linkid=268698">https://go.microsoft.com/fwlink/p/?LinkId=268698</a> 。</p>
<p>对于 Exchange 2010 或最新的 service pack，请参阅 &quot; 在上修改 UM-Enabled 用户的 SIP 地址 &quot; <a href="https://go.microsoft.com/fwlink/p/?linkid=268699">https://go.microsoft.com/fwlink/p/?LinkId=268699</a> 。</p>
<p>对于 Exchange 2013，请参阅中的统一消息 <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a> 。</p></td>
</tr>
<tr class="odd">
<td><p>运行 exchucutil.ps1 脚本。</p></td>
<td><p>在运行 Exchange UM 服务的服务器上，打开 Exchange 命令行管理程序并运行 exchucutil.ps1 脚本，该脚本执行以下操作：</p>
<ul>
<li><p>授予 Lync Server 2013 权限，以读取 Exchange UM Active Directory 域服务对象，尤其是在上一任务中创建的 SIP 拨号计划。</p></li>
<li><p>在 Active Directory 中为每个 Lync Server 2013 Enterprise Edition pool 或 Standard Edition server 创建一个统一消息 IP 网关对象，该对象承载为已启用企业语音的用户。</p></li>
<li><p>为每个网关创建一个 Exchange UM 智能寻线。 该智能寻线的前导标识符将是与相应网关相关联的拨号计划的名称。 如果存在多个拨号计划，则需要进行一对一映射。</p></li>
</ul></td>
<td><p>Exchange 组织管理员</p>
<p>Exchange 收件人管理员</p></td>
<td><p><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">在 Microsoft Exchange 上为 Lync Server 2013 配置统一消息</a></p></td>
</tr>
<tr class="even">
<td><p>配置 Lync Server 2013 拨号计划。</p></td>
<td><p>如果要与 Exchange 2007 SP1 或最新的 service pack 或 Exchange 2010 集成，请使用与 Exchange UM 拨号计划完全限定的域名 (FQDN) 相匹配的名称创建一个新的企业语音拨号计划。</p>



> [!NOTE]
> 您将需要为每个 UM 拨号计划执行此操作。


<p>如果要与 Exchange 2010 SP1 集成，请确保已配置合适的全局/站点级别或池级别的企业语音拨号计划。</p>



> [!NOTE]
> 如果要与 Exchange 2010 SP1 集成，则 Lync Server 拨号计划和 Exchange UM SIP 拨号计划名称不需要匹配。

</td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-configuring-dial-plans.md">在 Lync Server 2013 中配置拨号计划</a></p></td>
</tr>
<tr class="odd">
<td><p>运行 Exchange UM 集成工具。</p></td>
<td><p>在 Lync Server 2013 上，运行 <strong>ocsumutil.exe</strong>，它是：</p>
<ul>
<li><p>创建订阅者访问和自动助理联系人对象。</p></li>
<li><p>验证是否存在具有与 Exchange UM 拨号计划 FQDN 相匹配的名称的企业语音拨号计划。 如果您运行的是 Exchange 2010 SP1 或更高版本，则拨号计划名称不需要匹配，您可以忽略该工具关于此工具的警告。</p></li>
</ul>
<p>此工具的工作方式为：扫描 Active Directory 以获取 Exchange UM 设置，并允许 Lync Server 2013 管理员查看、创建和编辑联系人对象。</p></td>
<td><p>RTCUniversalServerAdmins <em>和</em> RTCUniversalUserAdmins</p>



> [!IMPORTANT]
> 要成功运行 ocsumutil.exe，用户必须同时属于这两个组。





> [!NOTE]
> 要创建联系人对象，运行 ocsumutil.exe 的用户必须对存储新联系人对象的 Active Directory 组织单位 (OU) 具有正确的权限。 可以通过运行 <STRONG>CsOUPermission</STRONG> cmdlet 来授予此权限。 有关详细信息，请参阅 Lync Server 命令行管理程序文档。

</td>
<td><p><a href="lync-server-2013-configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server.md">配置 Lync Server 2013 以使用 Microsoft Exchange Server 上的统一消息</a></p></td>
</tr>
<tr class="even">
<td><p>如有必要，执行其他企业语音配置步骤。</p></td>
<td><p>如果尚未配置有关服务器或用户的企业语音设置，请执行下列一项或多项操作：</p>
<ul>
<li><p>部署并配置</p>
<p>公开交换电话网络 (PSTN) 网关和中介服务器</p></li>
<li><p>定义语音策略、PSTN 用法记录和出站呼叫路由。</p></li>
<li><p>为用户启用企业语音。</p></li>
<li><p>（可选）为特定用户配置拨号计划。</p></li>
</ul>
<p>可能还需要其他配置步骤，具体取决于启用的企业语音功能。</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>RTCUniversalUserAdmins</p></td>
<td><p>请参阅以下各节中的主题：</p>
<ul>
<li><p><a href="lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md">在 Lync Server 2013 中配置语音策略、PSTN 用法记录和语音路由</a></p></li>
<li><p><a href="lync-server-2013-deploying-enterprise-voice.md">在 Lync Server 2013 中部署企业语音</a></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>为 Exchange UM 启用企业语音用户。</p></td>
<td><p>在 Exchange UM 服务器上，确保已创建统一消息邮箱策略，并且每个用户都有一个唯一的分机号码分配，然后为该用户启用统一消息。</p></td>
<td><p>Exchange 收件人管理员</p></td>
<td><p>对于 Exchange 2007 SP1 或最新的 service pack，请参阅 &quot; 如何为用户启用统一 &quot; 消息 <a href="https://go.microsoft.com/fwlink/p/?linkid=268700">https://go.microsoft.com/fwlink/p/?LinkId=268700</a> 。</p>
<p>对于 Exchange 2010 或最新的 service pack，请参阅 &quot; 在上为用户启用统一消息 &quot; <a href="https://go.microsoft.com/fwlink/p/?linkid=268701">https://go.microsoft.com/fwlink/p/?LinkId=268701</a> 。</p>
<p>对于 Exchange 2013，请参阅中的统一消息 <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a> 。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

