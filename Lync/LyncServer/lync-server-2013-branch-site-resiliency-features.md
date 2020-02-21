---
title: Lync Server 2013：分支站点恢复功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Branch-site resiliency features
ms:assetid: 8e3feda5-9a38-4e3c-b808-af29f19c5eb9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398715(v=OCS.15)
ms:contentKeyID: 48184765
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa8e54578ba2e81f7e2e847994e92e13bb8010ca
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207148"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="branch-site-resiliency-features-in-lync-server-2013"></a>Lync Server 2013 中的分支站点恢复功能

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-02-10_

如果提供分支站点恢复能力，当分支站点到中央站点的 WAN 连接出现故障，或者当中央站点无法访问时，以下语音功能应该仍然可用：

<div>


  - 入站和出站公用电话交换网 (PSTN) 呼叫

  - 同一站点的用户间和两个不同站点的用户间的企业呼叫

  - 基本呼叫处理功能（包括呼叫保持、取回和转接）

  - 双方即时消息

  - 呼叫转接、终结点同时响铃、呼叫委派和团队呼叫服务，但前提是在同一站点配置代理程序和代理人（例如，经理和经理的管理员）或所有团队成员

  - 呼叫详细信息记录 (CDR)

  - 使用会议自动助理的 PSTN 电话拨入式会议

  - 语音邮件功能（如果配置了语音邮件重新路由设置）。 （有关详细信息，请参阅[Lync Server 2013 的分支站点恢复要求](lync-server-2013-branch-site-resiliency-requirements.md)。）

  - 用户身份验证和授权

仅当您的恢复解决方案是分支站点的完全规模的 Lync 服务器部署时，以下功能才可用：

  - IM、Web 会议和 A/V 会议

  - 基于状态和请勿打扰 (DND) 的路由（其中将阻止呼叫在已激活 DND 的分机上响铃）

  - 更新呼叫转接设置

  - 响应组应用程序和呼叫寄存应用程序

  - 设置新的电话和客户端，但仅在分支站点上存在 Active Directory 域服务时。

  - 增强型 9-1-1 (E9-1-1)
    
    如果已部署 E9-1-1，并且中心站点上的 SIP 中继因 WAN 链路断开而不可用，则 Survivable 分支设备会将 E9-1-1 呼叫路由到本地分支网关。 要启用该功能，分支站点用户的语音策略应在 WAN 出现故障时将呼叫路由到本地网关。

<div>


> [!NOTE]  
> XMPP 不支持 SBA （survivable branch office）。 驻留在 SBA 配置中的用户将无法使用 XMPP 联系人发送即时消息或查看状态。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

