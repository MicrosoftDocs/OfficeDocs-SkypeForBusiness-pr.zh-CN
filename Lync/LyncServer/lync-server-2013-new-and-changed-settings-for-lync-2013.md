---
title: Lync Server 2013： Lync 2013 的新增和更改设置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New and changed settings for Lync 2013
ms:assetid: bb13789c-7eda-461c-a387-02ea8ca4dabe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205204(v=OCS.15)
ms:contentKeyID: 48185241
ms.date: 12/08/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45282476beac35df7248c4ef6bd04c6642a0f1e2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049033"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-and-changed-settings-for-lync-2013"></a>Lync 2013 的新增和更改设置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-12-05_

本主题讨论与直接与客户端管理相关的 Lync Server 命令行管理程序 cmdlet 的更改。 Lync Server 2013 引入了几个新参数，并为可以通过其他方式配置的功能 deprecates 参数。

<div>

## <a name="new-client-management-parameters"></a>新的客户端管理参数


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>New</th>
<th>Lync Server 命令行管理程序 Cmdlet</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TracingLevel</p></td>
<td><p>Set-csclientpolicy</p></td>
<td><p>如果设置为 True，将在 Lync 中启用软件跟踪;如果设置为 False，软件跟踪将被禁用。 软件跟踪涉及对程序执行的所有操作（包括跟踪 API 调用）的详细记录进行维护。 跟踪主要适用于开发人员和应用程序支持人员。此设置等效于通信服务器 2007 R2 组策略设置&quot;启用对 Communicator 的跟踪。&quot;设置如下所示：</p>
<ul>
<li><p>关闭 = 禁用跟踪，用户无法更改此设置。</p></li>
<li><p>简略 = 执行最低限度的跟踪，用户无法更改此设置。</p></li>
<li><p>开启 = 执行详细跟踪，用户无法更改此设置。</p></li>
</ul>
<p>默认情况下，TracingLevel 会设置为空值。这意味着将执行最低限度的跟踪，但是用户可以启用或禁用此最低限度的跟踪。</p></td>
</tr>
<tr class="even">
<td><p>EnableMediaRedirection</p></td>
<td><p>Set-csclientpolicy</p></td>
<td><p>设置为 True ($True) 时，允许音频流和视频流与其他网络流量分隔开。进而，允许客户端设备在本地对视频和音频执行编码和解码。与类似的技术（如设备远程处理或编解码器压缩）相比，媒体重定向通常带来较低的带宽使用率、较高的服务器可伸缩性，以及更佳的用户体验。</p></td>
</tr>
<tr class="odd">
<td><p>AllowLargeMeetings</p></td>
<td><p>CsConferencing</p></td>
<td><p>如果设置为 True，则所有 Lync 会议将被&quot;视为大型会议。&quot;在大型会议中，对发送给参与者的通知数以及默认情况下传输的会议名单的大小进行了限制。</p></td>
</tr>
<tr class="even">
<td><p>DisablePowerPointAnnotations</p></td>
<td><p>CsConferencing</p></td>
<td><p>设置为 True ($True) 时，用户无法向会议中使用的 PowerPoint 幻灯片添加注释。但是（根据 AllowAnnotations 属性的值），用户仍能访问其他白板功能。默认值为 False，表示允许 PowerPoint 注释。</p></td>
</tr>
<tr class="odd">
<td><p>AllowSharedNotes</p></td>
<td><p>CsConferencing</p></td>
<td><p>设置为 True（默认值）时，将使用诸如会议参与者之类的信息以及有关在会议过程中共享的内容的详细信息，自动更新链接到会议的任何打开的 OneNote 笔记本。</p></td>
</tr>
<tr class="even">
<td><p>EnableInviteCustomization</p></td>
<td><p>Get-csmeetingconfiguration</p></td>
<td><p>与其他新 Get-csmeetingconfiguration 参数一起使用，自定义由 Lync 2013 的联机会议外接程序生成的会议邀请。</p></td>
</tr>
<tr class="odd">
<td><p>LogoURL</p></td>
<td><p>Get-csmeetingconfiguration</p></td>
<td><p>将组织的徽标添加到由 Lync 2013 的联机会议外接程序生成的所有邀请中。 可以指定 GIF 或 JPG 图像的 URL。</p></td>
</tr>
<tr class="even">
<td><p>HelpURL</p></td>
<td><p>Get-csmeetingconfiguration</p></td>
<td><p>将组织的帮助或支持 URL 添加到由 Lync 2013 的联机会议外接程序生成的所有邀请中。</p></td>
</tr>
<tr class="odd">
<td><p>LegalURL</p></td>
<td><p>Get-csmeetingconfiguration</p></td>
<td><p>将法律文本或免责声明文本添加到由 Lync 2013 的联机会议外接程序生成的所有邀请中。 可以指定文本位置的 URL。</p></td>
</tr>
<tr class="even">
<td><p>CustomFooterText</p></td>
<td><p>Get-csmeetingconfiguration</p></td>
<td><p>将自定义页脚添加到由 Lync 2013 的联机会议外接程序生成的所有邀请中。 可以指定自定义页脚文本位置的 URL。</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="deprecated-client-management-parameters"></a>废弃的客户端管理参数


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>参数</th>
<th>Lync Server 命令行管理程序 Cmdlet</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CustomizedHelpUrl</p></td>
<td><p>Set-csclientpolicy</p></td>
<td><p>此参数已弃用，可用于 Lync Server 2013。 在与 EnableEnterpriseCustomizedHelp 结合使用时，此参数使组织能够指定 URL，以便在用户单击 Lync 中的 "帮助" 菜单时，自定义 "帮助" 将会显示。</p></td>
</tr>
<tr class="even">
<td><p>EnableEnterpriseCustomizedHelp</p></td>
<td><p>Set-csclientpolicy</p></td>
<td><p>此参数已弃用，可用于 Lync Server 2013。 在与 CustomizedHelpUrl 结合使用时，此参数启用组织以显示自定义帮助。</p></td>
</tr>
<tr class="odd">
<td><p>EnableSQMData</p></td>
<td><p>Set-csclientpolicy</p></td>
<td><p>已在 Lync Server 2013 中删除 Set-csclientpolicy cmdlet 的 EnableSQMData 参数。 可以改为使用软件质量管理 (SQM) 数据的共享组策略设置，来确定 Lync 客户端“常规选项”页面中“客户体验改善”选项的用户界面：</p>
<p>HKEY_CURRENT_USER \Software\Policies\Microsoft\Office\Common\QMEnable</p>
<p>值</p>
<p>1 = 显示并选中复选框（用户可以清除该复选框）</p>
<p>0 = 关闭并禁用复选框（用户无法覆盖）</p>
<p>Null = 该值由 Office 设置确定，并且会向用户显示该复选框，以按照他们的选择进行设置</p></td>
</tr>
<tr class="even">
<td><p>AllowExchangeContactStore</p></td>
<td><p>Set-csclientpolicy</p></td>
<td><p>已删除此参数。 相反，当您部署 Lync Server 2013 并发布拓扑时，默认情况下会为所有用户启用统一联系人存储。 这意味着用户的所有联系人均保留在 Exchange 中并且在 Lync、Outlook 和 Outlook Web Access 中可用。 您可以使用 Set-CsUserServicesPolicy cmdlet 来自定义哪些用户具有可用的统一联系人存储。 可以全局、依站点、依租户或依个人或个人组为用户启用。 有关详细信息，请参阅<a href="lync-server-2013-enable-users-for-unified-contact-store.md">在 Lync Server 2013 中为统一联系人存储启用用户</a>。</p></td>
</tr>
<tr class="odd">
<td><p>MAPIPollInterval</p></td>
<td><p>Set-csclientpolicy</p></td>
<td><p>Lync 2013 不使用此参数。 在以前的版本中，此参数指定客户端从 Exchange 公用文件夹中检索 MAPI 数据的频率</p></td>
</tr>
<tr class="even">
<td><p>DisableICE</p></td>
<td><p>Set-csclientpolicy</p></td>
<td><p>在 Lync 2013 中已弃用此参数。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

