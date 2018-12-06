---
title: Lync 2013 的新增和更改的设置
TOCTitle: Lync 2013 的新增和更改的设置
ms:assetid: bb13789c-7eda-461c-a387-02ea8ca4dabe
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205204(v=OCS.15)
ms:contentKeyID: 49314051
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync 2013 的新增和更改的设置

 

_**上一次修改主题：** 2015-03-09_

本主题讨论对直接与客户端管理相关的 Lync Server 命令行管理程序 cmdlet 的更改。Lync Server 2013 引入了几个新参数，并废弃可通过其他方式配置的功能的参数。

## 新的客户端管理参数


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>新</th>
<th>Lync Server 命令行管理程序 Cmdlet</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TracingLevel</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>设置为 True 时，在 Lync 中将启用软件跟踪；设置为 False 时，将禁用软件跟踪。软件跟踪包括对程序进行的所有操作（包括跟踪 API 调用）进行详细地记录。对于开发人员和应用程序支持人员，此类跟踪极为有用。此设置等同于 Communications Server 2007 R2 组策略设置“打开 Communicator 的跟踪功能”。设置如下：</p>
<ul>
<li><p>关闭 = 禁用跟踪，用户无法更改此设置。</p></li>
<li><p>简略 = 执行最低限度的跟踪，用户无法更改此设置。</p></li>
<li><p>开启 = 执行详细跟踪，用户无法更改此设置。</p></li>
</ul>
<p>默认情况下，TracingLevel 会设置为空值。这意味着将执行最低限度的跟踪，但是用户可以启用或禁用此最低限度的跟踪。</p></td>
</tr>
<tr class="even">
<td><p>EnableMediaRedirection</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>设置为 True ($True) 时，允许音频流和视频流与其他网络流量分隔开。进而，允许客户端设备在本地对视频和音频执行编码和解码。与类似的技术（如设备远程处理或编解码器压缩）相比，媒体重定向通常带来较低的带宽使用率、较高的服务器可伸缩性，以及更佳的用户体验。</p></td>
</tr>
<tr class="odd">
<td><p>AllowLargeMeetings</p></td>
<td><p>CsConferencing</p></td>
<td><p>设置为 True 时，所有 Lync 会议均被视为“大型会议”。对于大型会议而言，除了默认情况下传输的会议规模名单以外，还会对发送给参与者的通知数施加限制。</p></td>
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
<td><p>CsMeetingConfiguration</p></td>
<td><p>与其他新的 CsMeetingConfiguration 参数一起使用，以自定义由 Lync 2013 联机会议外接程序生成的会议邀请。</p></td>
</tr>
<tr class="odd">
<td><p>LogoURL</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>将您的组织的徽标添加到由 Lync 2013 联机会议外接程序生成的所有邀请。可以指定 GIF 或 JPG 图像的 URL。</p></td>
</tr>
<tr class="even">
<td><p>HelpURL</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>将您的组织的帮助或支持 URL 添加到由 Lync 2013 联机会议外接程序生成的所有邀请。</p></td>
</tr>
<tr class="odd">
<td><p>LegalURL</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>将法律文本或免责声明文本添加到由 Lync 2013 联机会议外接程序生成的所有邀请。可以指定文本位置的 URL。</p></td>
</tr>
<tr class="even">
<td><p>CustomFooterText</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>将自定义页脚添加到由 Lync 2013 联机会议外接程序生成的所有邀请。可以指定自定义页脚文本位置的 URL。</p></td>
</tr>
<tr class="odd">
<td><p>IsPublicDisclosureAllowed</p></td>
<td><p>CsWebServiceConfiguration</p></td>
<td><p>启用新的 Lync Web App 2013 版。Lync Web App 的新版本在默认情况下不会启用，并且必须由管理员启用。</p></td>
</tr>
</tbody>
</table>


## 废弃的客户端管理参数


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
<td><p>EnableSQMData</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Set-CSClientPolicy cmdlet 的 EnableSQMData 参数已在 Lync Server 2013 中删除。可以改为使用软件质量管理 (SQM) 数据的共享组策略设置，来确定 Lync 客户端“常规选项”页面中“客户体验改善”选项的用户界面：</p>
<p>HKEY_CURRENT_USER\Software\Policies\Microsoft\Office\Common\QMEnable</p>
<p>值：</p>
<p>1 = 显示并选中复选框（用户可以清除该复选框）</p>
<p>0 = 关闭并禁用复选框（用户无法覆盖）</p>
<p>Null = 该值由 Office 设置确定，并且会向用户显示该复选框，以按照他们的选择进行设置</p></td>
</tr>
<tr class="even">
<td><p>AllowExchangeContactStore</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>已删除此参数。部署 Lync Server 2013 并发布拓扑时，默认情况下会针对所有用户启用统一联系人存储。这意味着用户的所有联系人均保留在 Exchange 中并且在 Lync、Outlook 和 Outlook Web Access 中可用。您可以使用 Set-CsUserServicesPolicy cmdlet 来自定义哪些用户具有可用的统一联系人存储。可以全局、依站点、依租户或依个人或个人组为用户启用。有关详细信息，请参阅<a href="lync-server-2013-enable-users-for-unified-contact-store.md">在 Lync Server 2013 中为用户启用统一联系人存储</a>。</p></td>
</tr>
<tr class="odd">
<td><p>MAPIPollInterval</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>此参数未被 Lync 2013 使用。在以前的版本中，此参数指定客户端从 Exchange 公用文件夹中检索 MAPI 数据的频率</p></td>
</tr>
</tbody>
</table>

