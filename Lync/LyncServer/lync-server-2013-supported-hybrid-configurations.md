---
title: 'Lync Server 2013: 支持的混合配置'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Supported hybrid configurations
ms:assetid: 5d456d6c-ad71-420c-b6d8-4d9cd0324f86
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945633(v=OCS.15)
ms:contentKeyID: 51541482
ms.date: 05/10/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 142b86720e64fdfd071bc5cacb21e4891e3e7758
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845777"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-lync-server-2013-hybrid-configurations"></a>支持的 Lync Server 2013 混合配置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2016-05-10_

你可以将 Lync Server 2013 部署配置为与 Microsoft Exchange Server 2010 和 Microsoft Exchange Server 2013 和 SharePoint Server (本地和联机) 集成。 除非另行指定，否则所有客户端都支持下表中列出的功能。 有关客户端支持的详细信息, 请参阅[Lync Server 2013 的客户端比较表](lync-server-2013-desktop-client-comparison-tables.md)和 skype For business online 客户端比较客户端与[skype for](http://go.microsoft.com/fwlink/p/?linkid=281902)business online 的比较表。

<div>

## <a name="integration-with-exchange-server"></a>与 Exchange Server 集成

下表列出了与 Microsoft Exchange Server 集成时的混合部署中支持的功能。


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
<td><p><strong>Lync Server 2013 本地版</strong></p></td>
<td><ul>
<li><p>Outlook 中的 IM/状态</p>
<p>有关详细信息, 请参阅<a href="lync-server-2013-im-and-presence.md">Lync Server 2013 中的即时消息和状态</a></p></li>
<li><p>通过 Outlook 安排和加入联机会议</p>
<p>有关详细信息，请参阅 <a href="lync-server-2013-integrating-with-microsoft-exchange-server-2013.md">Integrating Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</a></p></li>
<li><p>Outlook Web App 中的 IM/状态</p>
<p>有关详细信息, 请参阅<a href="lync-server-2013-configuring-lync-server-in-a-cross-premises-environment.md">在跨平台环境下配置 Microsoft Lync Server 2013</a></p></li>
<li><p>通过 Outlook Web App 安排和加入联机会议</p></li>
<li><p>移动客户端中的 IM/状态</p></li>
<li><p>在移动客户端中加入联机会议</p>
<p>有关详细信息, 请参阅<a href="lync-server-2013-deploying-mobility.md">在 Lync Server 2013 中部署移动服务</a></p></li>
<li><p>根据 Outlook 日历闲/忙信息发布状态</p></li>
<li><p>联系人列表（通过统一联系人存储）</p>
<p>有关详细信息, 请参阅<a href="lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md">配置 Microsoft Lync Server 2013 以使用统一联系人存储</a></p>
<div>

> [!NOTE]  
> 需要 Exchange 2013。<BR>需要 Lync 2013 桌面客户端。


</div></li>
<li><p>Lync 2013 客户端和 Lync Web App 中的高分辨率联系人照片。</p>
<p>有关详细信息, 请参阅<a href="lync-server-2013-configuring-the-use-of-high-resolution-photos.md">在 Microsoft Lync Server 2013 中配置高分辨率照片的使用</a></p>
<div>

> [!NOTE]  
> 需要 Exchange 2013。


</div></li>
<li><p>会议委派</p>
<p>只有当两个用户联机驻留在相同林中或者驻留在内部部署中时才支持。</p></li>
<li><p>错过的对话历史记录和呼叫日志写入到用户的 Exchange 邮箱</p></li>
<li><p>在 Exchang 中存档内容（IM 和会议）</p>
<p>有关详细信息, 请参阅<a href="lync-server-2013-deployment-checklist-for-archiving.md">Lync Server 2013 中的存档部署清单</a></p>
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
<p>有关详细信息, 请参阅<a href="lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md">部署本地 EXCHANGE UM 以提供 Lync Server 2013 语音邮件</a></p></li>
</ul></td>
<td><ul>
<li><p>Outlook 中的 IM/状态</p>
<p>有关详细信息, 请参阅<a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">配置本地 Lync Server 2013 集成 Exchange Online</a></p></li>
<li><p>通过 Outlook 安排和加入联机会议</p></li>
<li><p>OWA 中的 IM/状态</p>
<p>有关详细信息, 请参阅<a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">配置本地 Lync Server 2013 集成 Exchange Online</a></p></li>
<li><p>从 Outlook Web App 安排和加入联机会议</p>
<p>有关详细信息, 请参阅<a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">配置本地 Lync Server 2013 集成 Exchange Online</a></p></li>
<li><p>移动客户端中的 IM/状态</p></li>
<li><p>在移动客户端中加入联机会议</p></li>
<li><p>根据 Outlook 日历闲/忙信息发布状态</p></li>
<li><p>联系人列表（通过统一联系人存储）。 有关详细信息, 请参阅<a href="lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md">配置 Microsoft Lync Server 2013 以使用统一联系人存储</a></p>
<div>

> [!NOTE]  
> 仅限 Lync Server 2013。 需要 Lync 2013 桌面客户端。


</div></li>
<li><p>Lync 2013 客户端和 Lync Web App 中的高分辨率联系人照片。</p>
<p>有关详细信息, 请参阅<a href="lync-server-2013-configuring-the-use-of-high-resolution-photos.md">在 Microsoft Lync Server 2013 中配置高分辨率照片的使用</a>。</p></li>
<li><p>会议委派</p>
<p>只有当两个用户联机驻留在相同林中或者驻留在内部部署中时才支持。</p></li>
<li><p>错过的对话历史记录和呼叫日志写入到用户的 Exchange 邮箱</p></li>
<li><p>在 Exchang 中存档内容（IM 和会议）。</p>
<p>有关详细信息, 请参阅<a href="lync-server-2013-deployment-checklist-for-archiving.md">Lync Server 2013 中的存档部署清单</a></p></li>
<li><p>搜索存档内容。 有关详细信息, 请参阅<a href="http://go.microsoft.com/fwlink/p/?linkid=285448">配置 SharePoint 电子数据展示中心的 Exchange</a></p></li>
<li><p>语音邮件。 有关详细信息, 请参阅向<a href="lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md">Lync Server 2013 用户提供托管 EXCHANGE UM 上的语音邮件</a></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Lync Online</strong></p></td>
<td><ul>
<li><p>Outlook 中的即时消息和状态</p></li>
<li><p>通过 Outlook 安排和加入联机会议</p></li>
<li><p>移动客户端中的 IM/状态</p></li>
<li><p>错过的对话历史记录和呼叫日志写入到用户的 Exchange 邮箱</p></li>
<li><p>Lync 2013 客户端中的高分辨率联系人照片。</p>
<div>

> [!NOTE]  
> 需要 Microsoft Exchange Server 2013。 当用户托管在 Skype for Business Online 上时, Lync Web App 不支持此功能。


</div></li>
<li><p>在移动客户端中加入联机会议</p></li>
<li><p>根据 Outlook 日历闲/忙信息发布状态</p></li>
<li><p>会议委派</p>
<p>只有当两个用户联机驻留在相同林中或者驻留在内部部署中时才支持。</p></li>
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
> Lync Server 2013 客户端必需


</div></li>
<li><p>Lync 2013 客户端和 Lync Web App 中的高分辨率联系人照片</p></li>
<li><p>会议委派</p>
<p>只有当两个用户联机驻留在相同林中或者驻留在内部部署中时才支持。</p></li>
<li><p>在 Exchang 中存档内容（IM 和会议）</p></li>
<li><p>搜索存档内容</p></li>
<li><p>语音邮件</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="integration-with-sharepoint"></a>与 SharePoint 集成

下表列出了与 SharePoint 集成时 Lync Server 2013 混合部署中支持的功能。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>SharePoint 本地版</th>
<th>SharePoint Online</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Lync Server 2013 本地版</strong></p></td>
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

