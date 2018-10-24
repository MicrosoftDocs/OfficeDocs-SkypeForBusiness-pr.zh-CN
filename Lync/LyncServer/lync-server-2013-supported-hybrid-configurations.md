---
title: Lync Server 2013：支持的混合配置
TOCTitle: 支持的混合配置
ms:assetid: 5d456d6c-ad71-420c-b6d8-4d9cd0324f86
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ945633(v=OCS.15)
ms:contentKeyID: 52061028
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 支持的 Lync Server 2013 混合配置

 

_**上一次修改主题：** 2016-12-08_

您可以在本地或联机配置 Lync Server 2013 部署以与 Microsoft Exchange Server 2010、Microsoft Exchange Server 2013 和 SharePoint Server 集成。除非另行指定，否则所有客户端都支持下表中列出的功能。有关客户端支持的详细信息，请参阅 [Lync Server 2013 的客户端比较表](lync-server-2013-desktop-client-comparison-tables.md) 和位于 [Lync Online 客户端](http://go.microsoft.com/fwlink/p/?linkid=281902)上的“Lync Online 客户端比较表”。

## 与 Exchange Server 集成

下表列出了在与 Microsoft Exchange Server 集成时混合部署中支持的功能。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>本地 Exchange</th>
<th>Exchange Online</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>本地 Lync Server 2013</strong></p></td>
<td><ul>
<li><p>Outlook 中的 IM/状态</p>
<p>有关详细信息，请参阅 <a href="lync-server-2013-im-and-presence.md">Lync Server 2013 中的 IM 和状态</a></p></li>
<li><p>通过 Outlook 安排和加入联机会议</p>
<p>有关详细信息，请参阅<a href="lync-server-2013-integrating-with-microsoft-exchange-server-2013.md">集成 Microsoft Lync Server 2013 和 Microsoft Exchange Server 2013</a></p></li>
<li><p>Outlook Web App 中的 IM/状态</p>
<p>有关详细信息，请参阅 <a href="lync-server-2013-configuring-lync-server-in-a-cross-premises-environment.md">在交叉部署环境中配置 Microsoft Lync Server 2013</a></p></li>
<li><p>通过 Outlook Web App 安排和加入联机会议</p></li>
<li><p>移动客户端中的 IM/状态</p></li>
<li><p>在移动客户端中加入联机会议</p>
<p>有关详细信息，请参阅<a href="lync-server-2013-deploying-mobility.md">在 Lync Server 2013 中部署移动功能</a></p></li>
<li><p>根据 Outlook 日历闲/忙信息发布状态</p></li>
<li><p>联系人列表（通过统一联系人存储）</p>
<p>有关详细信息，请参阅<a href="lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md">将 Microsoft Lync Server 2013 配置为使用统一联系人存储</a></p>
<div>

> [!NOTE]
> 需要 Exchange 2013。<br />
> 需要 Lync 2013 桌面客户端。

</div></li>
<li><p>Lync 2013 客户端和 Lync Web App 中的高分辨率联系人照片。</p>
<p>有关详细信息，请参阅<a href="lync-server-2013-configuring-the-use-of-high-resolution-photos.md">在 Microsoft Lync Server 2013 中配置使用高分辨率照片</a></p>
<div>

> [!NOTE]  
> 需要 Exchange 2013。

</div></li>
<li><p>会议委派</p>
<p>只有当两个用户驻留在相同林中或者驻留在内部部署中时才支持。</p></li>
<li><p>错过的对话历史记录和呼叫日志写入到用户的 Exchange 邮箱</p></li>
<li><p>在 Exchang 中存档内容（IM 和会议）</p>
<p>有关详细信息，请参阅<a href="lync-server-2013-deployment-checklist-for-archiving.md">Lync Server 2013 中存档的部署清单</a></p>
<div>

> [!NOTE]  
> 需要 Exchange 2013。

</div></li>
<li><p>搜索存档内容</p>
<div>

> [!NOTE]  
> 需要 Exchange 2013。

</div></li>
<li><p>语音邮件</p>
<p>有关详细信息，请参阅<a href="lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md">部署本地 Exchange UM 以提供 Lync Server 2013 语音邮件</a></p></li>
</ul></td>
<td><ul>
<li><p>Outlook 中的 IM/状态</p>
<p>有关详细信息，请参阅<a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">配置本地 Lync Server 2013 与 Exchange Online 的集成</a></p></li>
<li><p>通过 Outlook 安排和加入联机会议</p></li>
<li><p>OWA 中的 IM/状态</p>
<p>有关详细信息，请参阅<a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">配置本地 Lync Server 2013 与 Exchange Online 的集成</a></p></li>
<li><p>从 Outlook Web App 安排和加入联机会议</p>
<p>有关详细信息，请参阅<a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">配置本地 Lync Server 2013 与 Exchange Online 的集成</a></p></li>
<li><p>移动客户端中的 IM/状态</p></li>
<li><p>在移动客户端中加入联机会议</p></li>
<li><p>根据 Outlook 日历闲/忙信息发布状态</p></li>
<li><p>联系人列表（通过统一联系人存储）。有关详细信息，请参阅 <a href="lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md">将 Microsoft Lync Server 2013 配置为使用统一联系人存储</a></p>
<div>

> [!NOTE]  
> 仅 Lync Server 2013。需要 Lync 2013 桌面客户端。

</div></li>
<li><p>Lync 2013 客户端和 Lync Web App 中的高分辨率联系人照片。</p>
<p>有关详细信息，请参阅<a href="lync-server-2013-configuring-the-use-of-high-resolution-photos.md">在 Microsoft Lync Server 2013 中配置使用高分辨率照片</a>。</p></li>
<li><p>会议委派</p>
<p>只有当两个用户驻留在相同林中或者驻留在内部部署中时才支持。</p></li>
<li><p>错过的对话历史记录和呼叫日志写入到用户的 Exchange 邮箱</p></li>
<li><p>在 Exchang 中存档内容（IM 和会议）。</p>
<p>有关详细信息，请参阅<a href="lync-server-2013-deployment-checklist-for-archiving.md">Lync Server 2013 中存档的部署清单</a></p></li>
<li><p>搜索存档内容。有关详细信息，请参阅<a href="http://go.microsoft.com/fwlink/p/?linkid=285448">针对 SharePoint 电子数据展示中心配置 Exchange</a></p></li>
<li><p>语音邮件。有关详细信息，请参阅 <a href="lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md">在托管 Exchange UM 上提供 Lync Server 2013 用户语音邮件</a></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Lync Online</strong></p></td>
<td><ul>
<li><p>Outlook 中的 IM 和状态</p></li>
<li><p>通过 Outlook 安排和加入联机会议</p></li>
<li><p>移动客户端中的 IM/状态</p></li>
<li><p>错过的对话历史记录和呼叫日志写入到用户的 Exchange 邮箱</p></li>
<li><p>Lync 2013 客户端中的高分辨率联系人照片。</p>
<div>

> [!NOTE]  
> 需要 Microsoft Exchange Server 2013。当用户驻留在 Skype for Business Online 上时， Lync Web App 中不支持。

</div></li>
<li><p>在移动客户端中加入联机会议</p></li>
<li><p>根据 Outlook 日历闲/忙信息发布状态</p></li>
<li><p>会议委派</p>
<p>只有当两个用户驻留在相同林中或者驻留在内部部署中时才支持。</p></li>
</ul></td>
<td><ul>
<li><p>Outlook 中的 IM/状态</p></li>
<li><p>通过 Outlook 安排和加入联机会议</p></li>
<li><p>Outlook Web App 中的 IM/状态</p></li>
<li><p>从 Outlook Web App 安排和加入联机会议</p></li>
<li><p>移动客户端中的 IM/状态</p></li>
<li><p>在移动客户端中加入联机会议</p></li>
<li><p>根据 Outlook 日历闲/忙信息发布状态</p></li>
<li><p>错过的对话历史记录和呼叫日志写入到用户的 Exchange 邮箱</p></li>
<li><p>联系人列表（通过统一联系人存储）</p>
<div>

> [!NOTE]  
> 需要 Lync Server 2013 客户端

</div></li>
<li><p>Lync 2013 客户端和 Lync Web App 中的高分辨率联系人照片</p></li>
<li><p>会议委派</p>
<p>只有当两个用户驻留在相同林中或者驻留在内部部署中时才支持。</p></li>
<li><p>在 Exchang 中存档内容（IM 和会议）</p></li>
<li><p>搜索存档内容</p></li>
<li><p>语音邮件</p></li>
</ul></td>
</tr>
</tbody>
</table>


## 与 SharePoint 集成

下表列出了在与 SharePoint 集成时 Lync Server 2013 混合部署中支持的功能。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>本地 SharePoint</th>
<th>SharePoint联机</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>本地 Lync Server 2013</strong></p></td>
<td><ul>
<li><p>技能搜索</p></li>
<li><p>SharePoint 中的状态</p></li>
</ul></td>
<td><ul>
<li><p>SharePoint 中的状态</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Lync Online</strong></p></td>
<td><ul>
<li><p>SharePoint 中的状态</p></li>
</ul></td>
<td><ul>
<li><p>SharePoint 中的状态</p></li>
</ul></td>
</tr>
</tbody>
</table>

