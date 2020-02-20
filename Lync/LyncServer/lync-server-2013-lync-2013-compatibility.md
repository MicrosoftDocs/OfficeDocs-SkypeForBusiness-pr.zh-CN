---
title: Lync Server 2013： Lync 2013 兼容性
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync 2013 compatibility
ms:assetid: ac3a1046-b438-4e21-9d4f-3b0057dd685d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412817(v=OCS.15)
ms:contentKeyID: 51541502
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af2c342e894fc15fe81ba4651ca66b5293d11c9a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151292"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-2013-compatibility"></a>Lync 2013 兼容性

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-10-07_

本节介绍了 Lync 2013 与各种版本的 Microsoft Office 套件、Microsoft Exchange Server、Windows 操作系统和所选的公共即时消息（IM）客户端的兼容性。

<div>

## <a name="office-and-lync-2013"></a>Office 和 Lync 2013

下表介绍了各种 Office 版本支持的 Lync 2013 功能。

### <a name="lync-2013-and-microsoft-office-compatibility"></a>Lync 2013 和 Microsoft Office 兼容性

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
<th>Microsoft Office 2003 Service Pack 3 （SP3）（必需）或最新的 service pack （推荐）</th>
<th>Microsoft Office 2007</th>
<th>Microsoft Office 2010</th>
<th>Microsoft Office 2013</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>自定义 Outlook 会议邀请（添加徽标、帮助 URL、免责声明、页脚文本）</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>可访问</p></td>
</tr>
<tr class="even">
<td><p>在 Outlook 中，"配置会议" 选项默认为 "与会者音频和视频静音"</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>可访问</p></td>
</tr>
<tr class="odd">
<td><p>用于跨 Office 和 Lync 管理联系人列表的统一联系人存储</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>是（需要 Exchange 2013）1</p></td>
</tr>
<tr class="even">
<td><p>高分辨率图片</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>是（需要 Exchange 2013）1</p></td>
</tr>
<tr class="odd">
<td><p>将 Lync 2013 安装程序集成到 Office 安装程序中</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>可访问</p></td>
</tr>
<tr class="even">
<td><p>OneNote 共享笔记</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>可访问</p></td>
</tr>
<tr class="odd">
<td><p>PowerPoint 演示文稿内容</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>可访问</p></td>
<td><p>是</p></td>
</tr>
<tr class="even">
<td><p>Microsoft Outlook "收件人" 和 "抄送" 字段中的状态</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>可访问</p></td>
<td><p>是</p></td>
</tr>
<tr class="odd">
<td><p>从可用性菜单答复会议呼叫</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>是（来自联系人卡片）</p></td>
<td><p>是（来自联系人卡片）</p></td>
</tr>
<tr class="even">
<td><p>"日程安排助理" 选项卡上的会议请求中的状态</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>可访问</p></td>
<td><p>是</p></td>
</tr>
<tr class="odd">
<td><p>在收到的电子邮件中使用即时消息答复或从工具栏或功能区呼叫</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>可访问</p></td>
<td><p>是</p></td>
</tr>
<tr class="even">
<td><p>"Outlook 发件人" 字段中的状态</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>可访问</p></td>
<td><p>是</p></td>
</tr>
<tr class="odd">
<td><p>通过 IM 或从 "可用性" 菜单中的语音进行答复</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>是（来自联系人卡片）</p></td>
<td><p>是（来自联系人卡片）</p></td>
</tr>
<tr class="even">
<td><p>Microsoft Word 和 Microsoft Excel 文件中的 IM 和状态（启用智能标记）</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>仅 Microsoft Word</p></td>
<td><p>仅 Microsoft Word</p></td>
</tr>
<tr class="odd">
<td><p>Microsoft SharePoint 网站中的 IM 和状态（必须安装 Outlook）</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>可访问</p></td>
<td><p>是</p></td>
</tr>
</tbody>
</table>


1有关详细信息，请参阅规划文档中的[集成 Microsoft Lync Server 2013 和 Microsoft Exchange Server 2013](lync-server-2013-integrating-with-microsoft-exchange-server-2013.md) 。

以下功能仅适用于 Office 2010 或 Office 2013：

  - 带有扩展选项（例如视频呼叫和桌面共享）的联系人卡片

  - Outlook“查找联系人”字段中的快速搜索

  - 使用来自 "邮件"、"日历"、"联系人" 和 "任务" 文件夹中的 Outlook 主页功能区的 IM 或呼叫进行答复

  - Outlook To Do 栏中的 Lync 联系人列表

  - Office Backstage （"文件" 选项卡）状态、程序共享和文件传输

  - Microsoft Office SharePoint Workspace 2010 中的 "状态" 菜单（以前称为 Microsoft Office Groove 2007）

  - 状态菜单扩展性

</div>

<div>

## <a name="exchange-server-and-lync-2013"></a>Exchange Server 和 Lync 2013

下表介绍了适用于各种 Exchange Server 版本的 Lync 2013 支持。 必须在客户端计算机上安装 Outlook 才能处理扩展的 MAPI 呼叫，并且某些功能需要使用 Exchange Web 服务（EWS）。

### <a name="lync-2013-and-exchange-server-compatibility"></a>Lync 2013 和 Exchange Server 兼容性

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
<td><p>与 Exchange Server 2010 支持相同，其中添加了统一的联系人存储、高分辨率图片和存档集成。</p>
<div>

> [!NOTE]  
> 有关详细信息，请参阅<A href="lync-server-2013-integrating-with-microsoft-exchange-server-2013.md">集成 Microsoft Lync Server 2013 和 Microsoft Exchange Server 2013</A>。


</div></td>
</tr>
<tr class="even">
<td><p>Exchange Server 2010</p></td>
<td><p>与 Exchange Server 2007 支持相同，其中添加了 Exchange 联系人同步。</p></td>
</tr>
<tr class="odd">
<td><p>Exchange Server 2007 Service Pack 1 （SP1）（必需）或最新的 service pack （推荐）</p></td>
<td><p>以下功能仅可通过 EWS 使用：</p>
<ul>
<li><p>读取或删除对话历史记录文件夹中的项目</p></li>
<li><p>读取或删除语音邮件项</p></li>
<li><p>显示扩展的忙/闲信息和会议主题和位置</p></li>
</ul>
<p>公用文件夹在 Exchange Server 2007 Service Pack 1 （SP1）（必需）或最新的 service pack 或版本（推荐）中是可选的。</p></td>
</tr>
<tr class="even">
<td><p>Exchange Server 2003</p></td>
<td><p>仅 Outlook MAPI。 仅 EWS 功能不可用（请参阅上一行）。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="windows-and-lync-2013"></a>Windows 和 Lync 2013

有关 Lync 2013 和 Windows 可支持性的信息，请参阅规划文档中的 lync [Server 2013 中的 lync 客户端软件支持](lync-server-2013-lync-client-software-support.md)。

</div>

<div>

## <a name="macintosh-and-lync-2013"></a>Macintosh 和 Lync 2013

Lync Server 2013 支持运行 Macintosh 操作系统的计算机上的特定客户端。 有关详细信息，请参阅规划文档中的 lync [Server 2013 中的 lync 客户端软件支持](lync-server-2013-lync-client-software-support.md)。

</div>

<div>

## <a name="public-instant-messaging-clients-and-lync-2013"></a>公共即时消息客户端和 Lync 2013

如果您已将服务器配置为使用公用 IM 连接，Lync 支持使用公共 IM 网络的以下功能。 状态被筛选为公共 IM 客户端支持的那些状态。 有关详细信息，请参阅操作文档中的在 lync server 2013 中的规划文档和[管理外部访问策略](lync-server-2013-manage-external-access-policy-for-your-organization.md)中的在[lync Server 2013 中规划公共即时消息连接](lync-server-2013-planning-for-public-instant-messaging-connectivity.md)。

此外，Lync Server 2013 的 XMPP 集成功能使用户可以通过使用可扩展消息和状态协议（如 Google 谈话）的公共 IM 提供商的用户交换即时消息和状态信息。 有关详细信息，请参阅规划文档中的在[Lync Server 2013 中规划可扩展消息和状态协议（XMPP）联盟](lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md)。

### <a name="lync-2013-and-public-im-clients-compatibility"></a>Lync 2013 和公共 IM 客户端兼容性

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Client</th>
<th>支持的功能</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Windows Live Messenger</p></td>
<td><p>IM、基本状态、音频/视频（A/V） *</p></td>
</tr>
<tr class="even">
<td><p>Skype</p></td>
<td><p>即时消息、基本状态、音频</p></td>
</tr>
<tr class="odd">
<td><p>寻求</p></td>
<td><p>IM 和基本状态</p></td>
</tr>
<tr class="even">
<td><p>Yahoo！</p></td>
<td><p>IM 和基本状态</p></td>
</tr>
<tr class="odd">
<td><p>Google 对话</p></td>
<td><p>IM 和基本状态</p></td>
</tr>
</tbody>
</table>


\*最新版本的 Windows Live Messenger 支持 A/V。 如果要实现与 Windows Live Messenger 的音频/视频（A/V）联合，则还必须修改服务器加密级别。 默认情况下，加密级别为“必需”。 必须使用 Lync Server 命令行管理程序将此设置更改为 "受支持"。

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>从2012年9月1日起，Microsoft Lync 公共 IM 连接用户订阅许可证（"PIC USL"）不再可用于购买新的或更新的协议。 拥有主动许可证的客户将能够继续与 Yahoo！联合联合 信使，直到服务关闭日期。 AOL 和 Yahoo！的生命周期结束日期为2014年6月 已宣布。 有关详细信息，请参阅<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的支持公用即时信使连接</A>。</P>
> <LI>
> <P>PIC USL 是 Lync Server 或 Office 通信服务器与 Yahoo！联合所需的每个用户每月订阅许可证。 Messenger. Microsoft 提供此服务的能力因 Yahoo！中的支持而受到了支持，其下凸的底层协议。</P>
> <LI>
> <P>Lync 是前所未有的强大工具，用于跨组织和世界各地的个人进行连接。 与 Windows Live Messenger 的联盟不需要除 Lync Standard CAL 之外的其他用户/设备许可证。</P></LI></UL>



</div>

</div>

<div>

## <a name="see-also"></a>另请参阅


[Lync 2013 中的客户端互操作性](lync-server-2013-client-interoperability-in-lync-2013.md)  
[Lync Server 2013 中的 lync 客户端软件支持](lync-server-2013-lync-client-software-support.md)  
[Lync Server 2013 支持的 lync Web App 平台](lync-server-2013-lync-web-app-supported-platforms.md)  
[Lync Server 2013 的 lync Windows 应用商店应用程序要求](lync-server-2013-lync-windows-store-app-requirements.md)  


[Lync Server 2013 的客户端系统要求](lync-server-2013-client-system-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

