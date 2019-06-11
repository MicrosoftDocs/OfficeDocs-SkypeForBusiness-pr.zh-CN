---
title: 'Lync Server 2013: Lync 2013 兼容性'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync 2013 compatibility
ms:assetid: ac3a1046-b438-4e21-9d4f-3b0057dd685d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412817(v=OCS.15)
ms:contentKeyID: 51541502
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e177003efb73cd1e16ae8fd772d579eb222af8bd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829934"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-2013-compatibility"></a>Lync 2013 兼容性

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-10-07_

本部分介绍了 Lync 2013 与各种版本的 Microsoft Office 套件、Microsoft Exchange Server、Windows 操作系统和所选公共即时消息 (IM) 客户端的兼容性。

<div>

## <a name="office-and-lync-2013"></a>Office 和 Lync 2013

下表介绍了各种版本的 Office 支持的 Lync 2013 功能。

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
<th>Microsoft Office 2003 Service Pack 3 (SP3) (必需) 或最新服务包 (推荐)</th>
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
<td><p>是</p></td>
</tr>
<tr class="even">
<td><p>在 Outlook 中, "配置会议" 选项默认将与会者的音频和视频设为静音</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>是</p></td>
</tr>
<tr class="odd">
<td><p>用于管理跨 Office 和 Lync 的联系人列表的统一联系人存储</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>是 (需要 Exchange 2013) 1</p></td>
</tr>
<tr class="even">
<td><p>高分辨率图片</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>是 (需要 Exchange 2013) 1</p></td>
</tr>
<tr class="odd">
<td><p>将 Lync 2013 设置集成到 Office 安装程序中</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>是</p></td>
</tr>
<tr class="even">
<td><p>OneNote 共享笔记</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>是</p></td>
</tr>
<tr class="odd">
<td><p>PowerPoint 演示文稿内容</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>是</p></td>
<td><p>是 </p></td>
</tr>
<tr class="even">
<td><p>Microsoft Outlook“收件人”和“抄送”字段中的状态</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>是</p></td>
<td><p>是 </p></td>
</tr>
<tr class="odd">
<td><p>从可用性菜单通过电话会议回复</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>是（从联系人卡片）</p></td>
<td><p>是（从联系人卡片）</p></td>
</tr>
<tr class="even">
<td><p>“日程安排助理”选项卡上的会议请求中的状态</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>是</p></td>
<td><p>是 </p></td>
</tr>
<tr class="odd">
<td><p>通过 IM 回复，或者在已接收的电子邮件中从工具栏或功能区呼叫</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>是</p></td>
<td><p>是 </p></td>
</tr>
<tr class="even">
<td><p>Outlook“发件人”字段中的状态</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>是</p></td>
<td><p>是</p></td>
</tr>
<tr class="odd">
<td><p>从可用性菜单通过 IM 或语音回复</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>是（从联系人卡片）</p></td>
<td><p>是（从联系人卡片）</p></td>
</tr>
<tr class="even">
<td><p>Microsoft Word 文件和 Microsoft Excel 文件（启用了智能标记）中的 IM 和状态</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>仅 Microsoft Word</p></td>
<td><p>仅 Microsoft Word</p></td>
</tr>
<tr class="odd">
<td><p>Microsoft SharePoint 站点（必须已安装 Outlook）中的 IM 和状态</p></td>
<td><p>否</p></td>
<td><p>否</p></td>
<td><p>是</p></td>
<td><p>是 </p></td>
</tr>
</tbody>
</table>


1有关详细信息, 请参阅规划文档中的[集成 Microsoft Lync server 2013 和 Microsoft Exchange server 2013](lync-server-2013-integrating-with-microsoft-exchange-server-2013.md) 。

以下功能仅适用于 Office 2010 或 Office 2013:

  - 带扩展选项（如视频呼叫和桌面共享）的联系人卡片

  - 从 Outlook 中的“查找联系人”字段执行快速搜索

  - 从 Outlook 主功能区“邮件”、“日历”、“联系人”和“任务”文件夹通过 IM 或呼叫回复

  - Outlook 待办事项栏中的 Lync 联系人列表

  - Office Backstage（“文件”选项卡）状态、程序共享和文件传输

  - Microsoft Office SharePoint Workspace 2010 中的 "状态" 菜单 (以前称为 Microsoft Office Groove 2007)

  - “状态”菜单可扩展性

</div>

<div>

## <a name="exchange-server-and-lync-2013"></a>Exchange Server 和 Lync 2013

下表介绍了适用于各种 Exchange Server 版本的 Lync 2013 支持。 客户端计算机上必须安装 Outlook 才能处理扩展的 MAPI 呼叫，并且某些功能要求启用 Exchange Web 服务 (EWS)。

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
<td><p>与 Exchange Server 2010 支持相同，增加了统一联系人存储库、高分辨率图片以及存档集成。</p>
<div>

> [!NOTE]  
> 有关详细信息，请参阅<A href="lync-server-2013-integrating-with-microsoft-exchange-server-2013.md">Integrating Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</A>。


</div></td>
</tr>
<tr class="even">
<td><p>Exchange Server 2010</p></td>
<td><p>与 Exchange Server 2007 支持相同, 并且添加了 Exchange 联系人同步。</p></td>
</tr>
<tr class="odd">
<td><p>Exchange Server 2007 Service Pack 1 (SP1) (必需) 或最新服务包 (推荐)</p></td>
<td><p>只有通过 EWS 才能使用以下功能：</p>
<ul>
<li><p>读取或删除“对话历史记录”文件夹中的项</p></li>
<li><p>读取或删除语音邮件项</p></li>
<li><p>显示扩展的空闲/忙碌信息以及会议主题和位置</p></li>
</ul>
<p>公用文件夹在 Exchange Server 2007 中是可选的, Service Pack 1 (SP1) (必需) 或最新服务包或发布 (推荐)。</p></td>
</tr>
<tr class="even">
<td><p>Exchange Server 2003</p></td>
<td><p>仅限 Outlook MAPI。 仅 EWS 功能不可用 (请参阅上一行)。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="windows-and-lync-2013"></a>Windows 和 Lync 2013

有关 Lync 2013 和 Windows 可支持性的信息, 请参阅规划文档中[Lync Server 2013 中的 lync 客户端软件支持](lync-server-2013-lync-client-software-support.md)。

</div>

<div>

## <a name="macintosh-and-lync-2013"></a>Macintosh 和 Lync 2013

Lync Server 2013 支持运行 Macintosh 操作系统的计算机上的特定客户端。 有关详细信息, 请参阅规划文档中[Lync Server 2013 中的 Lync 客户端软件支持](lync-server-2013-lync-client-software-support.md)。

</div>

<div>

## <a name="public-instant-messaging-clients-and-lync-2013"></a>公共即时消息客户端和 Lync 2013

如果你已配置服务器用于公用 IM 连接, 则 Lync 支持使用公共 IM 网络的以下功能。 状态将筛选为公共 IM 客户端支持的状态。 有关详细信息, 请参阅在 Lync server 2013 中的 "规划文档" 和 "管理" 操作文档中[Lync server 2013 中的外部访问策略](lync-server-2013-manage-external-access-policy-for-your-organization.md)中的[公共即时消息连接](lync-server-2013-planning-for-public-instant-messaging-connectivity.md)。

此外, Lync Server 2013 的 XMPP 集成功能允许用户通过使用可扩展消息和状态协议 (如 Google 谈话) 的公共 IM 提供商的用户交换即时消息和状态信息。 有关详细信息, 请参阅规划文档中的[Lync Server 2013 中的 "规划可扩展消息和状态协议 (XMPP) 联盟](lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md)"。

### <a name="lync-2013-and-public-im-clients-compatibility"></a>Lync 2013 和公共 IM 客户端兼容性

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
<td><p>IM、基本状态、音频/视频 (A/V) *</p></td>
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
<td><p>Google 通话</p></td>
<td><p>IM 和基本状态</p></td>
</tr>
</tbody>
</table>


\*最新版本的 Windows Live Messenger 支持 A/V。 如果你要使用 Windows Live Messenger 实现音频/视频 (A/V) 联合, 则还必须修改服务器加密级别。 默认情况下，加密级别为“必需”。 您必须使用 Lync Server 命令行管理程序将此设置更改为 "支持"。

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>从2012年9月1日起, Microsoft Lync 公共 IM 连接用户订阅许可证 ("PIC USL") 不再可用于购买新的或续订协议。 具有活动许可证的客户将能够继续与 Yahoo! 进行联盟 Messenger, 直到服务关闭日期。 AOL 和 Yahoo! 的有效期结束日期为2014年6月 已宣布。 有关详细信息, 请参阅<A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Lync Server 2013 中的公共即时消息连接支持</A>。</P>
> <LI>
> <P>PIC USL 是 Lync Server 或 Office 通信服务器与 Yahoo! 联合所需的每个每个用户每月订阅许可证。 Messenger. Microsoft 提供此服务的能力已作为对 Yahoo! 的支持, 它的底层协议被向下缠绕。</P>
> <LI>
> <P>Lync 比以往更多, 是一种强大的工具, 用于跨组织和全球各地的人员进行连接。 与 Windows Live Messenger 的联盟不需要除 Lync 标准 CAL 之外的其他用户/设备许可证。</P></LI></UL>



</div>

</div>

<div>

## <a name="see-also"></a>另请参阅


[Lync 2013 中的客户端互操作性](lync-server-2013-client-interoperability-in-lync-2013.md)  
[Lync Server 2013 中的 Lync 客户端软件支持](lync-server-2013-lync-client-software-support.md)  
[Lync Web App 支持的 Lync Server 2013 平台](lync-server-2013-lync-web-app-supported-platforms.md)  
[Lync Server 2013 的 lync Windows 应用商店应用要求](lync-server-2013-lync-windows-store-app-requirements.md)  


[Lync Server 2013 的客户端系统要求](lync-server-2013-client-system-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

