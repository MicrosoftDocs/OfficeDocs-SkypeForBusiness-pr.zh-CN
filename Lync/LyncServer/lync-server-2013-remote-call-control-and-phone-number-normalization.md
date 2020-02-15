---
title: Lync Server 2013：远程呼叫控制和电话号码规范化
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remote call control and phone number normalization
ms:assetid: 291d9e87-4c65-4ea2-888f-517741391de5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558630(v=OCS.15)
ms:contentKeyID: 48183696
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 76d7ffb386f6b565fc00b866072bfab6390bc8d9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048733"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remote-call-control-and-phone-number-normalization-in-lync-server-2013"></a>Lync Server 2013 中的远程呼叫控制和电话号码规范化

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-22_

Lync 客户端在通讯簿服务（ABS）文件下载过程中下载电话号码规范化规则。 在远程呼叫控制方案中，通讯簿服务电话号码规范化规则同时适用于传入和传出远程呼叫控制呼叫。 对于对启用了远程呼叫控制的用户的传入呼叫，呼叫者的电话号码首先通过 SIP/CSTA 网关或专用交换机 (PBX) 规范化为 E.164 格式。 当 Lync Server 2013 从网关接收呼叫时，将对呼叫者的电话号码执行反向号码查找（RNL），对被呼叫者的 Microsoft Office Outlook 联系人列表中的规范化号码或存储在中的全局地址列表（GAL）。通讯簿服务。 如果反向号码查找成功找到了匹配项，则通过传入呼叫通知中的名称来识别呼叫者。

对于传出远程呼叫控制呼叫，Lync 会在将呼叫路由到 SIP/CSTA 网关之前，将通讯簿服务电话号码规范化规则应用于所拨打的号码。

有关为远程呼叫控制创建电话号码规范化规则的详细信息，请参阅规划文档中的[Lync Server 2013 中的拨号计划和规范化规则](lync-server-2013-dial-plans-and-normalization-rules.md)。

<div>

## <a name="migrating-phone-number-normalization-rules"></a>迁移电话号码规范化规则

如果要迁移以前启用了远程呼叫控制的用户，请参阅迁移文档中的以下主题：

  - 对于 Lync Server 2010，请参阅迁移文档中的[迁移通讯簿](migrate-address-book.md)。

  - 有关通信服务器 2007 R2 的详细说明，请参阅迁移文档中的[迁移通讯簿](migrate-address-book_1.md)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

