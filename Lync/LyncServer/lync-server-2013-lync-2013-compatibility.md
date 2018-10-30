---
title: Lync 2013 兼容性
TOCTitle: Lync 2013 兼容性
ms:assetid: ac3a1046-b438-4e21-9d4f-3b0057dd685d
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412817(v=OCS.15)
ms:contentKeyID: 52061094
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync 2013 兼容性

 

_**上一次修改主题：** 2015-03-09_

本节将讨论 Lync 2013 与各种版本的 Microsoft Office 套件、Microsoft Exchange Server、Windows 操作系统和指定公共即时消息 (IM) 客户端的兼容性。

## Office 和 Lync 2013

下表介绍的是 Office 各种版本所支持的 Lync 2013 功能。

### Lync 2013 与 Microsoft Office 兼容性

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>功能</th>
<th>Microsoft Office 2003 Service Pack 3 (SP3)（必需）或最新的 Service Pack（推荐）</th>
<th>Microsoft Office 2007</th>
<th>Microsoft Office 2010</th>
<th>Microsoft Office 2013</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>自定义 Outlook 会议邀请（添加徽标、帮助 URL、免责声明、页脚文本）</p></td>
<td><p>不支持</p></td>
<td><p>不支持</p></td>
<td><p>不支持</p></td>
<td><p>支持</p></td>
</tr>
<tr class="even">
<td><p>在 Outlook 中，配置会议选项以便在默认情况下将与会者音频和视频设为静音</p></td>
<td><p>不支持</p></td>
<td><p>不支持</p></td>
<td><p>不支持</p></td>
<td><p>支持</p></td>
</tr>
<tr class="odd">
<td><p>统一联系人存储跨 Office 和 Lync 管理联系人列表</p></td>
<td><p>不支持</p></td>
<td><p>不支持</p></td>
<td><p>不支持</p></td>
<td><p>支持（需要 Exchange 2013）1</p></td>
</tr>
<tr class="even">
<td><p>高分辨率图片</p></td>
<td><p>不支持</p></td>
<td><p>不支持</p></td>
<td><p>不支持</p></td>
<td><p>支持（需要 Exchange 2013）1</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2013 安装集成到 Office 安装程序中</p></td>
<td><p>不支持</p></td>
<td><p>不支持</p></td>
<td><p>不支持</p></td>
<td><p>支持</p></td>
</tr>
<tr class="even">
<td><p>OneNote 共享笔记</p></td>
<td><p>不支持</p></td>
<td><p>不支持</p></td>
<td><p>不支持</p></td>
<td><p>支持</p></td>
</tr>
<tr class="odd">
<td><p>PowerPoint 演示文稿内容</p></td>
<td><p>不支持</p></td>
<td><p>不支持</p></td>
<td><p>支持</p></td>
<td><p>支持</p></td>
</tr>
<tr class="even">
<td><p>Microsoft Outlook“收件人”和“抄送”字段中的状态</p></td>
<td><p>不支持</p></td>
<td><p>不支持</p></td>
<td><p>支持</p></td>
<td><p>支持</p></td>
</tr>
<tr class="odd">
<td><p>“可用性”菜单上的回复会议呼叫</p></td>
<td><p>不支持</p></td>
<td><p>不支持</p></td>
<td><p>支持（从联系人卡片）</p></td>
<td><p>支持（从联系人卡片）</p></td>
</tr>
<tr class="even">
<td><p>“日程安排助理”选项卡上“会议请求”中的状态</p></td>
<td><p>不支持</p></td>
<td><p>不支持</p></td>
<td><p>支持</p></td>
<td><p>支持</p></td>
</tr>
<tr class="odd">
<td><p>通过 IM 回复，或者在已接收的电子邮件中从工具栏或功能区呼叫</p></td>
<td><p>不支持</p></td>
<td><p>不支持</p></td>
<td><p>支持</p></td>
<td><p>支持</p></td>
</tr>
<tr class="even">
<td><p>Outlook“发件人”字段中的状态</p></td>
<td><p>不支持</p></td>
<td><p>不支持</p></td>
<td><p>支持</p></td>
<td><p>支持</p></td>
</tr>
<tr class="odd">
<td><p>“可用性”菜单上的回复 IM 或语音电话</p></td>
<td><p>不支持</p></td>
<td><p>不支持</p></td>
<td><p>支持（从联系人卡片）</p></td>
<td><p>支持（从联系人卡片）</p></td>
</tr>
<tr class="even">
<td><p>Microsoft Word 和 Microsoft Excel 文件（启用了智能标记）中的 IM 和状态</p></td>
<td><p>不支持</p></td>
<td><p>不支持</p></td>
<td><p>仅 Microsoft Word</p></td>
<td><p>仅 Microsoft Word</p></td>
</tr>
<tr class="odd">
<td><p>Microsoft SharePoint 站点（必须已安装 Outlook）中的 IM 和状态</p></td>
<td><p>不支持</p></td>
<td><p>不支持</p></td>
<td><p>支持</p></td>
<td><p>支持</p></td>
</tr>
</tbody>
</table>


1 有关更多信息，请参阅规划文档中的[集成 Microsoft Lync Server 2013 和 Microsoft Exchange Server 2013](lync-server-2013-integrating-with-microsoft-exchange-server-2013.md)。

仅 Office 2010 或 Office 2013 提供以下功能：

  - 带扩展选项的联系人卡片，如视频呼叫和桌面共享

  - Outlook“查找联系人”字段中的快速搜索

  - Outlook 主功能区“邮件”、“日历”、“联系人”和“任务”文件夹中的回复 IM 或呼叫

  - Outlook“待办事项”栏中的 Lync 联系人列表

  - Office Backstage（“文件”选项卡）状态、程序共享和文件传输

  - Microsoft Office SharePoint Workspace 2010（以前称为 Microsoft Office Groove 2007）中的“状态”菜单

  - “状态”菜单可扩展性

## Exchange Server 与 Lync 2013

下表介绍的是对 Exchange Server 各种版本的 Lync 2013 支持。客户端计算机上必须安装 Outlook 才能处理扩展的 MAPI 呼叫，并且某些功能要求启用 Exchange Web 服务 (EWS)。

### Lync 2013 与 Exchange Server 兼容性

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Exchange Server 版本</th>
<th>Lync 2013 支持</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Exchange Server 2013</p></td>
<td><p>与 Exchange Server 2010 支持相同，增加了统一联系人存储、高分辨率图片以及存档集成。</p>
<div>

> [!NOTE]  
> 有关详细信息，请参阅<a href="lync-server-2013-integrating-with-microsoft-exchange-server-2013.md">集成 Microsoft Lync Server 2013 和 Microsoft Exchange Server 2013</a>。


</div></td>
</tr>
<tr class="even">
<td><p>Exchange Server 2010</p></td>
<td><p>与 Exchange Server 2007 支持相同，并添加了 Exchange 联系人同步。</p></td>
</tr>
<tr class="odd">
<td><p>Exchange Server 2007 Service Pack 1 (SP1)（必需）或最新的 Service Pack（推荐）</p></td>
<td><p>只有通过 EWS 才能使用以下功能：</p>
<ul>
<li><p>读取或删除“对话历史记录”文件夹中的项</p></li>
<li><p>读取或删除语音邮件项</p></li>
<li><p>显示扩展的忙/闲信息以及会议主题和位置</p></li>
</ul>
<p>公共文件夹在 Exchange Server 2007 Service Pack 1 (SP1)（必需）或最新的 Service Pack 或发行版（推荐）中是可选的。</p></td>
</tr>
<tr class="even">
<td><p>Exchange Server 2003</p></td>
<td><p>仅支持 Outlook MAPI。仅支持 EWS 的功能不可用（请参阅上一行内容）。</p></td>
</tr>
</tbody>
</table>


## Windows 与 Lync 2013

有关 Lync 2013 与 Windows 支持能力的信息，请参阅规划文档中的 [Lync Server 2013 中的 Lync 客户端软件支持](lync-server-2013-lync-client-software-support.md)。

## Macintosh 与 Lync 2013

Lync Server 2013 支持运行 Macintosh 操作系统的计算机上的某些客户端。有关详细信息，请参阅规划文档中的 [Lync Server 2013 中的 Lync 客户端软件支持](lync-server-2013-lync-client-software-support.md)。

## 公共即时消息客户端与 Lync 2013

如果已经针对公共 IM 连接配置了服务器，Lync 将通过公共 IM 网络支持以下功能。当前状态筛选为公共 IM 客户端支持的那些当前状态。有关详细信息，请参阅规划文档中的[规划公共即时消息连接](lync-server-2013-planning-for-public-instant-messaging-connectivity.md)和操作文档中的[在 Lync Server 2013 中管理组织的外部访问策略](lync-server-2013-manage-external-access-policy-for-your-organization.md)。

此外，利用 Lync Server 2013 的 XMPP 集成功能，用户可以与使用可扩展消息处理和状态协议（如 Google Talk）的公共 IM 提供商的用户交换即时消息和状态信息。有关详细信息，请参阅规划文档中的[在 Lync Server 2013 中规划可扩展消息和状态协议 (XMPP) 联盟](lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md)。

### Lync 2013 与公共 IM 客户端兼容性

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>客户端</th>
<th>支持的功能</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Windows Live Messenger</p></td>
<td><p>IM、基本状态、音频/视频 (A/V)*</p></td>
</tr>
<tr class="even">
<td><p>Skype</p></td>
<td><p>IM、基本状态、音频</p></td>
</tr>
<tr class="odd">
<td><p>AOL</p></td>
<td><p>IM 和基本状态</p></td>
</tr>
<tr class="even">
<td><p>Yahoo!</p></td>
<td><p>IM 和基本状态</p></td>
</tr>
<tr class="odd">
<td><p>Google Talk</p></td>
<td><p>IM 和基本状态</p></td>
</tr>
</tbody>
</table>


\*Windows Live Messenger 的最新版本支持 A/V。如果要实现与 Windows Live Messenger 的音频/视频 (A/V) 联盟，必须修改服务器加密级别。默认情况下，加密级别为“必需”。必须使用 Lync Server 命令行管理程序将此设置更改为“支持”。

> [!IMPORTANT]  
> <ul>
> <li><p>自 2012 年 9 月 1 日起，新订或续订合同不能再购买 Microsoft Lync 公共 IM 连接用户订阅许可证 (“PIC USL”)。拥有有效许可证的客户可继续与 Yahoo! Messenger 联盟直至服务关闭。AOL 和 Yahoo! 的生命周期结束日期已宣布，为 2014 年 6 月。有关详细信息，请参阅 <a href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公共即时消息连接支持</a>。</p></li>
> <li><p>PIC USL 是一个每用户每月订阅许可证，是 Lync Server 或 Office Communications Server 与 Yahoo! Messenger 联盟所必需的。Microsoft 之所以能够提供此服务离不开 Yahoo! 的支持，但这项支持的基础协议正在逐步终止。</p></li>
> <li><p>Lync 是一个比以往更强大的工具，它实现了人员跨组织、跨地域的连接。除 Lync 标准 CAL 外，与 Windows Live Messenger 联盟不需要任何附加用户/设备许可证。</p></li>
> </ul>

## 另请参阅

#### 概念

[Lync 2013 中的客户端互操作性](lync-server-2013-client-interoperability-in-lync-2013.md)  
[Lync Server 2013 中的 Lync 客户端软件支持](lync-server-2013-lync-client-software-support.md)  
[Lync Server 2013 中 Lync Web App 支持的平台](lync-server-2013-lync-web-app-supported-platforms.md)  
[Lync Windows Store 应用程序要求](lync-server-2013-lync-windows-store-app-requirements.md)  

#### 其他资源

[客户端系统要求](lync-server-2013-client-system-requirements.md)

