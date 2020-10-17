---
title: Lync Server 2013：持久聊天服务器的 DNS 要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for Persistent Chat Servers
ms:assetid: f7531374-d7ed-4b63-ae81-02294cb4496a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205391(v=OCS.15)
ms:contentKeyID: 48185857
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 055a55498247cdde540ceca44cc33187e2b9baca
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501379"
---
# <a name="dns-requirements-for-persistent-chat-servers-in-lync-server-2013"></a>Lync Server 2013 中持久聊天服务器的 DNS 要求

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-06-28_

本节介绍部署持久聊天服务器所需的 (DNS) 记录的域名系统。

<div>

## <a name="dns-records-for-persistent-chat-servers"></a>持久聊天服务器的 DNS 记录

下表指定持久聊天服务器部署的 DNS 要求。

### <a name="dns-requirements-for-a-persistent-chat-server"></a>持久聊天服务器的 DNS 要求

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>部署方案</th>
<th>DNS 要求</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>一台持久聊天服务器</p></td>
<td><p>将服务器的完全限定的域名 (FQDN) 解析为其 IP 地址的内部 A 记录。</p></td>
</tr>
<tr class="even">
<td><p>持久聊天池</p></td>
<td><p>将服务器的完全限定的域名 (FQDN) 解析为其 IP 地址的内部 A 记录。</p>
<p><strong>示例</strong></p>
<p>PersistentChatServer01.contoso.com 10.10.10。1</p>
<p>PersistentChatServer02.contoso.com 10.10.10。2</p>
<p>将服务器的完全限定的域名 (FQDN) 解析为其 IP 地址的内部 A 记录。</p>
<p><strong>示例</strong></p>
<p>PersistentChatPool.contoso.com 10.10.10。1</p>
<p>PersistentChatPool.contoso.com 10.10.10。2</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

