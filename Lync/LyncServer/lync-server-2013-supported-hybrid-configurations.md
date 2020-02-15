---
title: Lync Server 2013：支持的混合配置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported hybrid configurations
ms:assetid: 5d456d6c-ad71-420c-b6d8-4d9cd0324f86
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945633(v=OCS.15)
ms:contentKeyID: 51541482
ms.date: 05/10/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f268d76c33e3a76c909d164eb63d6ad3c1eb29c8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029803"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-lync-server-2013-hybrid-configurations"></a>支持的 Lync Server 2013 混合配置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2016-05-10_

你可以将 Lync Server 2013 部署配置为与 Microsoft Exchange Server 2010 和 Microsoft Exchange server 2013 和 SharePoint Server （本地和联机）集成。 除非另行指定，否则所有客户端都支持下表中列出的功能。 有关客户端支持的详细信息，请参阅适用[于 skype For Business Online 客户](http://go.microsoft.com/fwlink/p/?linkid=281902)端的 Lync Server 2013 和 Skype For business online 客户端比较表[的客户端比较表](lync-server-2013-desktop-client-comparison-tables.md)。

<div>

## <a name="integration-with-exchange-server"></a>与 Exchange Server 集成

下表列出了在与 Microsoft Exchange Server 集成时的混合部署中支持的功能。


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
<td><p><strong>Lync Server 2013 本地</strong></p></td>
<td><ul>
<li><p>Outlook 中的 IM/状态</p>
<p>有关详细信息，请参阅<a href="lync-server-2013-im-and-presence.md">Lync Server 2013 中的 IM 和状态</a></p></li>
<li><p>通过 Outlook 安排和加入联机会议</p>
<p>有关详细信息，请参阅<a href="lync-server-2013-integrating-with-microsoft-exchange-server-2013.md">集成 Microsoft Lync Server 2013 和 Microsoft Exchange Server 2013</a></p></li>
<li><p>Outlook Web App 中的 IM/状态</p>
<p>有关详细信息，请参阅<a href="lync-server-2013-configuring-lync-server-in-a-cross-premises-environment.md">在跨界环境中配置 Microsoft Lync Server 2013</a></p></li>
<li><p>通过 Outlook Web App 安排和加入联机会议</p></li>
<li><p>移动客户端中的 IM/状态</p></li>
<li><p>在移动客户端中加入联机会议</p>
<p>有关详细信息，请参阅<a href="lync-server-2013-deploying-mobility.md">在 Lync Server 2013 中部署移动</a>功能</p></li>
<li><p>基于 Outlook 日历的忙/闲信息发布状态</p></li>
<li><p>联系人列表（通过统一联系人存储区）</p>
<p>有关详细信息，请参阅<a href="lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md">配置 Microsoft Lync Server 2013 以使用统一的联系人存储库</a></p>
<div>

> [!NOTE]  
> 需要 Exchange 2013。<BR>Lync 2013 桌面客户端是必需的。


</div></li>
<li><p>Lync 2013 客户端和 Lync Web App 中的高分辨率联系人照片。</p>
<p>有关详细信息，请参阅<a href="lync-server-2013-configuring-the-use-of-high-resolution-photos.md">在 Microsoft Lync Server 2013 中配置高分辨率照片的使用</a></p>
<div>

> [!NOTE]  
> 需要 Exchange 2013。


</div></li>
<li><p>会议委派</p>
<p>仅当两个用户在同一个林中托管联机，或者两者都驻留在本地时受支持。</p></li>
<li><p>错过的对话历史记录和呼叫日志将写入用户的 exchange 邮箱</p></li>
<li><p>在 Exchange 中存档内容（IM 和会议）</p>
<p>有关详细信息，请参阅<a href="lync-server-2013-deployment-checklist-for-archiving.md">Lync Server 2013 中存档的部署清单</a></p>
<div>

> [!NOTE]  
> 需要 Exchange 2013。


</div></li>
<li><p>搜索存档的内容</p>
<div>

> [!NOTE]  
> 需要 Exchange 2013。


</div></li>
<li><p>语音邮件</p>
<p>有关详细信息，请参阅<a href="lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md">部署本地 EXCHANGE UM 以提供 Lync Server 2013 语音邮件</a></p></li>
</ul></td>
<td><ul>
<li><p>Outlook 中的 IM/状态</p>
<p>有关详细信息，请参阅<a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">配置本地 Lync Server 2013 与 Exchange Online 集成</a></p></li>
<li><p>通过 Outlook 安排和加入联机会议</p></li>
<li><p>OWA 中的 IM/状态</p>
<p>有关详细信息，请参阅<a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">配置本地 Lync Server 2013 与 Exchange Online 集成</a></p></li>
<li><p>从 Outlook Web App 安排和加入联机会议</p>
<p>有关详细信息，请参阅<a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">配置本地 Lync Server 2013 与 Exchange Online 集成</a></p></li>
<li><p>移动客户端中的 IM/状态</p></li>
<li><p>在移动客户端中加入联机会议</p></li>
<li><p>基于 Outlook 日历的忙/闲信息发布状态</p></li>
<li><p>联系人列表（通过统一联系人存储区）。 有关详细信息，请参阅<a href="lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md">配置 Microsoft Lync Server 2013 以使用统一的联系人存储库</a></p>
<div>

> [!NOTE]  
> 仅限 Lync Server 2013。 Lync 2013 桌面客户端是必需的。


</div></li>
<li><p>Lync 2013 客户端和 Lync Web App 中的高分辨率联系人照片。</p>
<p>有关详细信息，请参阅<a href="lync-server-2013-configuring-the-use-of-high-resolution-photos.md">在 Microsoft Lync Server 2013 中配置高分辨率照片的使用</a>。</p></li>
<li><p>会议委派</p>
<p>仅当两个用户在同一个林中托管联机，或者两者都驻留在本地时受支持。</p></li>
<li><p>错过的对话历史记录和呼叫日志将写入用户的 exchange 邮箱</p></li>
<li><p>在 Exchange 中存档内容（IM 和会议）。</p>
<p>有关详细信息，请参阅<a href="lync-server-2013-deployment-checklist-for-archiving.md">Lync Server 2013 中存档的部署清单</a></p></li>
<li><p>搜索存档的内容。 有关详细信息，请参阅<a href="http://go.microsoft.com/fwlink/p/?linkid=285448">Configure Exchange For SharePoint 电子数据展示中心</a></p></li>
<li><p>语音邮件。 有关详细信息，请参阅<a href="lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md">在托管 EXCHANGE UM 上提供 Lync Server 2013 用户语音邮件</a></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Lync Online</strong></p></td>
<td><ul>
<li><p>Outlook 中的 IM 和状态</p></li>
<li><p>通过 Outlook 安排和加入联机会议</p></li>
<li><p>移动客户端中的 IM/状态</p></li>
<li><p>错过的对话历史记录和呼叫日志将写入用户的 exchange 邮箱</p></li>
<li><p>Lync 2013 客户端中的高分辨率联系人照片。</p>
<div>

> [!NOTE]  
> 需要 Microsoft Exchange Server 2013。 当用户托管在 Skype for Business Online 中时，Lync Web App 不支持此项。


</div></li>
<li><p>在移动客户端中加入联机会议</p></li>
<li><p>基于 Outlook 日历的忙/闲信息发布状态</p></li>
<li><p>会议委派</p>
<p>仅当两个用户在同一个林中托管联机，或者两者都驻留在本地时受支持。</p></li>
</ul></td>
<td><ul>
<li><p>Outlook 中的 IM/状态</p></li>
<li><p>通过 Outlook 安排和加入联机会议</p></li>
<li><p>Outlook Web App 中的 IM/状态</p></li>
<li><p>从 Outlook Web App 安排和加入联机会议</p></li>
<li><p>移动客户端中的 IM/状态</p></li>
<li><p>在移动客户端中加入联机会议</p></li>
<li><p>基于 Outlook 日历的忙/闲信息发布状态</p></li>
<li><p>错过的对话历史记录和呼叫日志将写入用户的 exchange 邮箱</p></li>
<li><p>联系人列表（通过统一联系人存储区）</p>
<div>

> [!NOTE]  
> Lync Server 2013 客户端必需


</div></li>
<li><p>Lync 2013 客户端和 Lync Web App 中的高分辨率联系人照片</p></li>
<li><p>会议委派</p>
<p>仅当两个用户在同一个林中托管联机，或者两者都驻留在本地时受支持。</p></li>
<li><p>在 Exchange 中存档内容（IM 和会议）</p></li>
<li><p>搜索存档的内容</p></li>
<li><p>Voicemail</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="integration-with-sharepoint"></a>与 SharePoint 集成

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
<th>SharePoint 本地部署</th>
<th>SharePoint Online</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Lync Server 2013 本地</strong></p></td>
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


</div>

</div>

<span> </span>

</div>

</div>

</div>

