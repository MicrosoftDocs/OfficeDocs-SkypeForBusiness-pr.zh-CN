---
title: Lync Server 2013： Lync 2013 的新增和更改的设置
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
ms.openlocfilehash: fb5366f7e3d4c2aba81b5b8b25873ea22d54c3a6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765843"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-and-changed-settings-for-lync-2013"></a>Lync 2013 的新增和更改的设置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2014-12-05_

本主题讨论直接与客户端管理相关的 Lync Server Management Shell cmdlet 的更改。 Lync Server 2013 引入了一些新参数，以及 deprecates 可通过其他方式配置的功能的参数。

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
<th>新增功能</th>
<th>Lync Server Management Shell Cmdlet</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TracingLevel</p></td>
<td><p>Set-csclientpolicy</p></td>
<td><p>当设置为 True 时，将在 Lync 中启用软件跟踪;当设置为 False 时，软件跟踪将被禁用。 软件跟踪包括对程序执行的所有操作（包括跟踪 API 调用）的详细记录。 跟踪主要适用于开发人员和应用程序支持人员。此设置等效于 "通信服务器 2007 R2 组策略" 设置&quot;"启用对 Communicator 的跟踪"。&quot;这些设置如下所示：</p>
<ul>
<li><p>关闭 = 禁用跟踪，用户无法更改此设置。</p></li>
<li><p>浅色 = 执行最短跟踪，用户无法更改此设置。</p></li>
<li><p>On = 执行详细跟踪，用户无法更改此设置。</p></li>
</ul>
<p>默认情况下，TracingLevel 设置为 null 值。 这意味着将执行最少的跟踪，但用户可以启用或禁用此最小跟踪。</p></td>
</tr>
<tr class="even">
<td><p>EnableMediaRedirection</p></td>
<td><p>Set-csclientpolicy</p></td>
<td><p>当设置为 True （$True）时，将音频和视频流与其他网络流量分开，从而允许客户端设备在本地对音频和视频进行编码和解码。 媒体重定向通常会导致带宽使用较低、服务器可伸缩性更高，以及与类似技术（如设备远程处理或编解码器压缩）相比的更为最佳的用户体验。</p></td>
</tr>
<tr class="odd">
<td><p>AllowLargeMeetings</p></td>
<td><p>CsConferencing</p></td>
<td><p>当设置为 True 时，所有 Lync 会议均被&quot;视为大型会议。&quot;使用较大的会议时，将对发送给参与者的通知的数量以及默认情况下传输的会议名单的大小进行限制。</p></td>
</tr>
<tr class="even">
<td><p>DisablePowerPointAnnotations</p></td>
<td><p>CsConferencing</p></td>
<td><p>当设置为 True （$True）时，用户将无法向会议中使用的 PowerPoint 幻灯片添加批注。 但是（根据 AllowAnnotations 属性的值），用户仍可访问其他 whiteboarding 功能。 默认值为 False，表示允许使用 PowerPoint 注释。</p></td>
</tr>
<tr class="odd">
<td><p>AllowSharedNotes</p></td>
<td><p>CsConferencing</p></td>
<td><p>设置为 True （默认值）时，将自动更新链接到会议的任何打开的 OneNote 笔记本，其中包含会议参与者和会议期间共享的内容的详细信息。</p></td>
</tr>
<tr class="even">
<td><p>EnableInviteCustomization</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>与其他新的 CsMeetingConfiguration 参数一起使用，自定义 Lync 2013 的联机会议加载项生成的会议邀请。</p></td>
</tr>
<tr class="odd">
<td><p>LogoURL</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>将组织的徽标添加到由 Lync 2013 的联机会议加载项生成的所有邀请。 指定 GIF 或 JPG 图像的 URL。</p></td>
</tr>
<tr class="even">
<td><p>HelpURL</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>将组织的帮助或支持 URL 添加到由 Lync 2013 的联机会议加载项生成的所有邀请。</p></td>
</tr>
<tr class="odd">
<td><p>LegalURL</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>将法律文本或免责声明文本添加到由 Lync 2013 的联机会议加载项生成的所有邀请中。 指定文本位置的 URL。</p></td>
</tr>
<tr class="even">
<td><p>CustomFooterText</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>将自定义页脚添加到由 Lync 2013 的联机会议加载项生成的所有邀请。 为自定义页脚文本的位置指定 URL。</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="deprecated-client-management-parameters"></a>已过时的客户端管理参数


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>参数</th>
<th>Lync Server Management Shell Cmdlet</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CustomizedHelpUrl</p></td>
<td><p>Set-csclientpolicy</p></td>
<td><p>此参数已弃用，无法用于 Lync Server 2013。 当与 EnableEnterpriseCustomizedHelp 结合使用时，此参数使组织可以指定 URL，以便在用户单击 Lync 中的 "帮助" 菜单时，将显示自定义帮助。</p></td>
</tr>
<tr class="even">
<td><p>EnableEnterpriseCustomizedHelp</p></td>
<td><p>Set-csclientpolicy</p></td>
<td><p>此参数已弃用，无法用于 Lync Server 2013。 当与 CustomizedHelpUrl 结合使用时，此参数允许组织显示自定义帮助。</p></td>
</tr>
<tr class="odd">
<td><p>EnableSQMData</p></td>
<td><p>Set-csclientpolicy</p></td>
<td><p>已将 Set-csclientpolicy cmdlet 的 EnableSQMData 参数从 Lync Server 2013 中删除。 相反，你可以使用软件质量管理（SQM）数据的共享组策略设置在 Lync 客户端 "常规选项" 页面中确定 "客户体验改善" 选项的用户界面：</p>
<p>HKEY_CURRENT_USER \Software\Policies\Microsoft\Office\Common\QMEnable</p>
<p>相对值</p>
<p>1 = 显示并选中复选框（用户可以清除该复选框）</p>
<p>0 = 关闭并禁用复选框（用户不能替代）</p>
<p>Null = 该值由 Office 安装程序确定，用户将显示复选框供用户选择</p></td>
</tr>
<tr class="even">
<td><p>AllowExchangeContactStore</p></td>
<td><p>Set-csclientpolicy</p></td>
<td><p>此参数已被删除。 当你部署 Lync Server 2013 并发布拓扑时，默认情况下为所有用户启用 "统一联系人存储"。 这意味着，所有用户的联系人都将保留在 Exchange 中，并且在 Lync、Outlook 和 Outlook Web Access 中可用。 你可以使用 CsUserServicesPolicy cmdlet 自定义哪些用户具有可用的统一联系人存储。 你可以按网站、租户、个人或个人组来启用用户。 有关详细信息，请参阅<a href="lync-server-2013-enable-users-for-unified-contact-store.md">在 Lync Server 2013 中为统一联系人存储启用用户</a>。</p></td>
</tr>
<tr class="odd">
<td><p>MAPIPollInterval</p></td>
<td><p>Set-csclientpolicy</p></td>
<td><p>Lync 2013 不使用此参数。 在以前的版本中，此参数指定客户端从 Exchange 公用文件夹检索 MAPI 数据的频率</p></td>
</tr>
<tr class="even">
<td><p>DisableICE</p></td>
<td><p>Set-csclientpolicy</p></td>
<td><p>此参数在 Lync 2013 中已弃用。</p></td>
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

