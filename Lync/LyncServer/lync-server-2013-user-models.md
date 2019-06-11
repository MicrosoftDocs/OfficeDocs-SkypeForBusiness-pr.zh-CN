---
title: 'Lync Server 2013: 用户模型'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync Server 2013 user models
ms:assetid: c551371c-d740-4372-bada-f0d713ec0d33
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398811(v=OCS.15)
ms:contentKeyID: 49733811
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8185fc2fdb92f907eb013349b8a202df2b7b62bb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845503"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-models-in-lync-server-2013"></a>Lync Server 2013 中的用户模型

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-10-07_

此处介绍的用户模型为[使用用户模型在 Lync Server 2013 的容量规划](lync-server-2013-capacity-planning-using-the-user-models.md)中介绍的容量规划测量和建议提供了基础。

<div>

## <a name="lync-server-2013-user-models"></a>Lync Server 2013 用户模型

下表介绍了 Lync Server 2013 的注册、联系人、即时消息 (IM) 和联机状态的用户模型。

### <a name="environment-and-registration-user-model"></a>环境和注册用户模型

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>类别</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>部署大小和通讯组</p></td>
<td><p>我们对含有三个中央站点（每个站点有一个前端池）的大型部署进行了建模。</p></td>
</tr>
<tr class="even">
<td><p>Active Directory 用户的百分比</p></td>
<td><p>我们假定组织中所有 Active Directory 用户的 70% 已启用 Lync Server。 80% 的已启用用户每天都登录到 Lync Server (80% 并发)。 本节下文中的数字都以并发用户为基础。</p></td>
</tr>
<tr class="odd">
<td><p>Active Directory 更改</p></td>
<td><p>我们假定每周在 Active Directory 中为 Lync 创建和启用每周的总用户数 0.5%, 并且每周从 Active Directory 和 Lync 禁用总用户的 0.5%。 5% 的用户每周至少更改了一个 Active Directory 属性。</p></td>
</tr>
<tr class="even">
<td><p>Active Directory 通讯组</p></td>
<td><p>我们假定组织中的 Active Directory 通讯组数等于 Active Directory 中所有用户数的三倍。 通讯组的大小如下：</p>
<ul>
<li><p>64% 具有 2-30 个用户</p></li>
<li><p>13% 具有 31-50 个用户</p></li>
<li><p>10% 具有 51-100 个用户</p></li>
<li><p>13% 具有 101-500 个用户</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>IP 语音 (VoIP) 用户</p></td>
<td><p>60% 的 Lync Server 用户已启用统一通信 (UC) (即他们的电话号码由 Lync Server 拥有)。</p></td>
</tr>
<tr class="even">
<td><p>注册的客户端分布</p></td>
<td><p>65% 的客户端运行 Lync 2013 软件, 包括 Lync 和 Lync Phone Edition。</p>
<p>从早期版本的 Lync 运行客户端软件的客户的 30%。</p>
<p>5% 使用 Lync Web App 的客户端。</p>
<p>如果启用移动功能，假设 40% 的用户正在使用与前面提到的已注册客户端选项同时存在的移动功能，这种情况下，客户端多点登录 (MPOP) 比率为 1:1.9。如果禁用移动，MPOP 比率为1:1.5。</p></td>
</tr>
<tr class="odd">
<td><p>远程用户分布</p></td>
<td><p>70% 的用户从内部连接。</p>
<p>通过 Edge 服务器和 Director 连接的用户的 30%。</p></td>
</tr>
<tr class="even">
<td><p>联系人分布</p></td>
<td><p>一个用户拥有的最大联系人数为 1,000。拥有 1,000 个联系人的用户低于 1%。拥有 100 个或更多联系人的用户低于 25%。</p>
<p>使用公共云连接的用户平均拥有 80 个联系人。在这些用户中：</p>
<ul>
<li><p>50% 的联系人在组织内。这些用户中的 10% 为远程用户，从防火墙以外连接。</p></li>
<li><p>40% 的联系人是公共云用户 (如 AOL、Yahoo!、MSN 或 Google 通话的用户)。</p></li>
<li><p>10% 的联系人来自联盟伙伴。</p>
<div>

> [!IMPORTANT]  
> <UL>
> <LI>
> <P>从2012年9月1日起, Microsoft Lync 公共 IM 连接用户订阅许可证 ("PIC USL") 不再可用于购买新的或续订协议。 具有活动许可证的客户将能够继续与 Yahoo! 进行联盟 Messenger, 直到服务关闭日期。 AOL 和 Yahoo! 的有效期结束日期为2014年6月 已宣布。 有关详细信息, 请参阅<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公共即时消息连接支持</A>。</P>
> <LI>
> <P>PIC USL 是 Lync Server 或 Office 通信服务器与 Yahoo! 联合所需的每个每个用户每月订阅许可证。 Messenger. Microsoft 提供此服务的能力已作为对 Yahoo! 的支持, 它的底层协议被向下缠绕。</P>
> <LI>
> <P>Lync 比以往更多, 是一种强大的工具, 用于跨组织和全球各地的人员进行连接。 与 Windows Live Messenger 的联盟不需要除 Lync 标准 CAL 之外的其他用户/设备许可证。 Skype 联盟将添加到此列表, 使 Lync 用户可以通过 IM 和语音与成百上千人联系。</P></LI></UL>


</div></li>
</ul>
<p>未使用公共云连接的用户平均拥有 50 个联系人。在这些用户中：</p>
<ul>
<li><p>80% 的联系人在组织内。这些用户中的 10% 为远程用户，从防火墙以外连接。</p></li>
<li><p>20% 的联系人来自联盟伙伴。</p>
<p>每个用户在其联系人列表中都有一个通讯组。为了进行性能测试，我们假设通讯组始终是展开的。</p></li>
</ul>
<p>用户的联系人的 25% 使用 XMPP。</p></td>
</tr>
<tr class="odd">
<td><p>会话时间</p></td>
<td><p>平均用户登录会话持续 12 个小时。所有用户在会话开始后的 120 分钟内登录。</p></td>
</tr>
</tbody>
</table>


### <a name="im-and-presence-user-model"></a>IM 和状态用户模型

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>类别</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>对等 IM 会话</p></td>
<td><p>平均每个用户每天发起六个对等 IM 会话。</p>
<p>每个会话 10 条即时消息。</p>
<p>每封邮件都通过两个 SIP 信息消息和2个 SIP 200 OK 消息 (适用于状态指示器,&lt;如&gt; "名称正在键入") 进行匹配</p></td>
</tr>
<tr class="even">
<td><p>状态轮询</p></td>
<td><p>总体上讲，假设状态轮询为平均每个用户每小时 60 次轮询。对于每个用户，假设平均：</p>
<ul>
<li><p>在用户的组织选项卡（而非联系人列表）中每天一次用户状态轮询。用户的组织选项卡中非联系人的平均数为 15 个用户。每天执行两次联系人卡片查看操作。</p></li>
<li><p>每次用户单击其他用户以开始对话时发生一次状态轮询，预计为每小时一次。</p></li>
<li><p>每小时六次用户搜索。每次执行搜索时，都会针对搜索结果列表中的每个人发送批轮询。假设搜索结果的平均大小为 20。如果搜索结果停留在屏幕上，则每 5 分钟就会刷新一次批轮询；假设每小时将进行两次这样的刷新。</p></li>
<li><p>当用户在 Outlook 中打开或预览电子邮件时，电子邮件的“收件人:”和“抄送:”字段中将发生一次用户状态轮询，预计为每小时五封电子邮件、每封电子邮件四个用户。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>状态订阅</p></td>
<td><p>当用户将其他用户添加为联系人时，第一个用户将“<em>订阅</em>”第二个用户的五类信息。这些类别的信息的更新会自动发送给第一个用户。</p>
<p>针对每个客户端，会发送单个订阅请求以获取平均 40 个联系人状态，以及发送其他 40 个对话以获取联盟联系人状态。</p>
<p>扩展通讯组成员的状态可通过持久状态订阅（而非轮询）进行查找，并建模为每个用户每两小时一次扩展。</p>
<p>在以下情况下会发生 <em>短期订阅 </em>：某位用户登录，针对所有用户联系人存在批订阅，然后该用户很快注销。假设每个用户每小时有 6 个短期订阅，其中每个订阅持续 10 分钟。</p></td>
</tr>
<tr class="even">
<td><p>状态发布</p></td>
<td><p>平均每个用户每小时发布状态 4 次，最多每个用户每小时发布 6 次。</p></td>
</tr>
<tr class="odd">
<td><p>状态文档大小</p></td>
<td><p>假设完整状态文档的平均大小为 4K，最大为 25K。</p></td>
</tr>
</tbody>
</table>


下表介绍了通讯簿使用用户模型。

### <a name="address-book-usage-user-model"></a>通讯簿使用用户模型

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>通讯簿搜索模式</th>
<th>使用</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>仅通讯簿 Web 查询（通讯簿 Web 查询服务执行的所有查询）</p></td>
<td><p>每个用户每天四次前缀查询。</p>
<p>每个用户每天 60 次精确搜索查询。在这些查询中，40% 为批处理查询，平均每次查询 20 个联系人。剩余的 60% 为单个联系人查询。</p>
<p>每个用户每天 25 次照片查询。其中 24 次为单张照片查询，另外一次为批处理查询，平均查询 20 个联系人。</p>
<p>每个用户每天一次彻底的组织搜索查询。</p></td>
</tr>
<tr class="even">
<td><p>混合模式，结合使用通讯簿文件和 Web 查询。这是默认模式。</p></td>
<td><p>只有两种查询会连接到网络，即照片查询和彻底的组织搜索查询。</p>
<p>每个用户每天 25 次照片查询。其中 24 次为单张照片查询，另外一次为批处理查询，平均查询 20 个联系人。</p>
<p>每个用户每天一次彻底的组织搜索查询。</p></td>
</tr>
</tbody>
</table>


下表介绍了会议模型。

### <a name="conferencing-model"></a>会议模型

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>类别</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>计划会议与&quot;"立即&quot;开会" 会议</p></td>
<td><p>60% 计划内会议，40% 计划外会议。</p>
<p>在计划的会议中, 我们假定 80% 分配有会议, 这是定期会议的一个实例;10% 是一次打开的会议;8% 是一次性匿名会议, 2% 是一次性关闭的会议。</p></td>
</tr>
<tr class="even">
<td><p>会议客户端分布</p></td>
<td><p>对于计划内会议：</p>
<ul>
<li><p>65% 的会议用户使用 Lync 2013。</p></li>
<li><p>5% 的会议用户使用 Microsoft Lync Web App。</p></li>
<li><p>30% 的会议用户使用以前的客户端, 包括 Microsoft Lync 2010、Office Communicator 2007 R2、Office Communicator 2007 和 Microsoft Office Communicator Web Access (2007 发布)。</p></li>
</ul>
<p>对于计划外会议：</p>
<ul>
<li><p>70% 的会议用户使用 Lync 2013。</p></li>
<li><p>30% 的会议用户使用以前的客户端, 包括 Microsoft Lync 2010、Office Communicator 2007 R2、Office Communicator 2007 和 Microsoft Office Communicator Web Access (2007 发布)。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>会议并发</p></td>
<td><p>5% 的用户将在工作时间参加会议。因此，在一个有 80,000 个用户的池中，在任何时候都可能有多达 4,000 个用户参加会议。</p></td>
</tr>
<tr class="even">
<td><p>会议音频分布</p></td>
<td><p>40% VoIP 音频和电话拨入式混合会议，VoIP 用户和电话拨入用户的比率为 3:1。</p>
<p>35% 仅 VoIP 音频。</p>
<p>15% 仅电话拨入式会议音频。</p>
<p>10% 无音频（仅 IM 会议，平均每个用户发出 5 条消息）。</p></td>
</tr>
<tr class="odd">
<td><p>会议媒体混合</p></td>
<td><p>75% 的会议为 Web 会议，其中包括音频以及一些其他协作形式。</p>
<p>这些会议的其他协作方式如下：</p>
<div>

> [!NOTE]  
> 这些数字合计达 100% 以上，因为一个会议可以有多种协作方式。


</div>
<ul>
<li><p>50% 添加应用程序共享。假设一个用户以每秒 1.1 MB 的峰值发送数据。</p></li>
<li><p>50% 添加即时消息（平均每个用户两条消息）。</p></li>
<li><p>20% 添加数据协作，包括 PowerPoint 或白板。其中，平均每次会议使用两个 PowerPoint 文件，文件平均大小为 10 MB（不含嵌入式视频）或 30 MB（含嵌入式视频）。平均每个白板 20 个批注。</p></li>
<li><p>20% 添加视频。在这些用户当中，70% 的用户参加启用了多视图视频的会议，其中每个用户会收到 2-3 个视频流。</p></li>
<li><p>15% 添加共享便笺。</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>会议参与者分布</p></td>
<td><p>50% 为经过身份验证的内部用户。</p>
<p>25% 为经过身份验证的远程访问用户。</p>
<p>15% 为匿名用户。</p>
<p>10% 为联盟用户。</p></td>
</tr>
<tr class="odd">
<td><p>与会分布</p></td>
<td><p>用户被模拟为在前 5 分钟内加入会议。</p></td>
</tr>
</tbody>
</table>


在常规前端池内, Lync Server 2013 的最大受支持的会议大小为250用户。 每个池一次可承载一个 250 个用户的会议。 召开这样的大型会议的同时，池还可以承载其他较小的会议。 另外，通过设置专用池承载这些会议，可以支持多达 1000 位用户的会议。 有关详细信息, 请参阅[Lync Server 2013 中的大型会议支持](lync-server-2013-support-for-large-meetings.md)。

模拟会议的方式如下：

  - 85% 的会议有 4 个参与者。

  - 10% 的会议有 6 个参与者。

  - 5% 的会议有 11 个参与者。

  - 用户数为 250 的一次大型会议。

下表详细说明了涉及电话拨入用户的会议的用户模型。

### <a name="dial-in-conferencing-user-model"></a>电话拨入式会议用户模型

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>类别</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>经过身份验证/匿名</p></td>
<td><p>70% 的呼叫者通过匿名加入，并提示输入记录的名称。30% 经过身份验证加入。</p></td>
</tr>
<tr class="even">
<td><p>呼叫持续时间和保持音乐</p></td>
<td><p>不包括保持音乐的平均呼叫持续时间：50 秒。</p>
<p>50% 的电话拨入用户会听到保持音乐，平均持续 5 分钟。</p></td>
</tr>
<tr class="odd">
<td><p>双音多频 (DTMF)</p></td>
<td><p>15% 的仅电话拨入式会议有电话领导。10% 包含电话拨入用户的混合会议也有电话领导。</p>
<p>20% 的电话领导在每次会议中使用 2 个 DTMF 命令。</p></td>
</tr>
<tr class="even">
<td><p>通知语言</p></td>
<td><p>模拟使用英语作为通知语言。</p></td>
</tr>
</tbody>
</table>


下表详细说明了会议厅的用户模型。

### <a name="conference-lobby-user-model"></a>会议厅用户模型

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>类别</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>会议厅中的用户数量</p></td>
<td><p>5% 的电话拨入用户通过会议厅，25% 其他用户通过会议厅</p></td>
</tr>
<tr class="even">
<td><p>从会议厅加入</p></td>
<td><p>在模拟中，所有用户在客户端超时之前由演示者许可加入。</p></td>
</tr>
</tbody>
</table>


下表说明了其他对等会话的用户模型。

### <a name="peer-to-peer-sessions-user-model"></a>对等会话用户模型

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>类别</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>应用程序共享</p></td>
<td><p>每个用户每个月参加 5 个对等应用程序共享会话，平均每天参加 0.25 个会话。</p></td>
</tr>
<tr class="even">
<td><p>文件传输</p></td>
<td><p>每个用户每个月参加 1 个对等文件传输会话（IM 会话的一部分），平均每天参加 0.05 个会话。传输的会话文件平均大小为 1 MB。</p></td>
</tr>
</tbody>
</table>


下表介绍了用于策略的用户模型。

### <a name="policies-user-model"></a>策略用户模型

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>类别</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>会议、状态和存档策略</p></td>
<td><p>假设有一个全局策略、10 个标记会议策略、4 个存档策略和 10 个标记状态策略。</p></td>
</tr>
<tr class="even">
<td><p>语音策略</p></td>
<td><p>假设每个站点有一个全局策略和 2 个标记策略。 100% 的站点都有站点策略，并为 30% 的用户分配每用户策略。 假设每个站点有一个拨号计划和两个路由。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="busy-hour"></a>忙时

对于对等会话，使用忙时呼叫尝试 (BHCA) 计算峰值负载。此语音行业术语假设将在 20% 的时间内完成一天中 50% 的呼叫。可使用以下公式进行计算：

`BHCA=(total calls * 0.5) / 1.6`

通过运行 VoIP 模拟忙时的性能测试和每天至少 1.6 小时的忙时负载的其他对等会话。

会议峰值负载假设在 4 小时的高峰时间内发生 8 小时工作日 75% 的会议。这些高峰时间的负载是平均会议负载的 1.5 倍。

</div>

<div>

## <a name="enterprise-voice-to-pstn-calls"></a>企业语音到 PSTN 呼叫

以下假设适用于企业语音呼叫:

  - 50% 的用户支持企业语音, 并且这些用户的 60% 已启用 PSTN 呼叫。

  - 启用了 PSTN 呼叫的其中每一位用户在忙碌时段都发出 4 个 PSTN 呼叫。每个呼叫的持续时间为 3 分钟。

  - 其中 65% 的 PSTN 语音呼叫使用媒体旁路。

</div>

<div>

## <a name="mobility"></a>移动性

假设为 40% 的注册用户启用了移动。对于启用了移动的每一位用户，假设移动客户端的活动是在该用户其他 MPOP 实例活动的基础上进行增加，但会议交互除外，对其而言，移动客户端只是可用来参与会议的另一种客户端类型。

</div>

<div>

## <a name="persistent-chat"></a>持久聊天

假设 25% 的注册用户将参与到持久聊天会话中，并具有以下特征：

  - 每个用户平均 1.5 个聊天室

  - 每个聊天室每小时将产生 12 个轮询请求，每个轮询请求平均针对 10 个用户

</div>

<div>

## <a name="response-group-and-call-park"></a>响应组和呼叫驻留

假设 0.15% 的注册用户属于响应组。假设 0.02% 的注册用户在任何给定的时间点都有驻留呼叫。

</div>

</div>

<span> </span>

</div>

</div>

</div>

