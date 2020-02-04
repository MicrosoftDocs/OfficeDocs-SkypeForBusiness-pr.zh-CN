---
title: Lync Server 2013：集成托管 Exchange UM 的部署过程
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for integrating hosted Exchange UM with Lync Server
ms:assetid: dbec9c38-7f66-419d-b8c3-c61380052cac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398968(v=OCS.15)
ms:contentKeyID: 48185586
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b314ea3bd7a88264a72c804c7c67ed3baa819972
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762620"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-integrating-hosted-exchange-um-with-lync-server-2013"></a>集成托管 Exchange UM 与 Lync Server 2013 的部署过程

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-09-25_

将 Lync Server 2013 与托管 Exchange 统一消息（UM）集成的有效规划要求考虑以下事项：

  - 将 Lync Server 2013 与托管 Exchange UM 集成的先决条件

  - 集成过程中所需的步骤

<div>

## <a name="deployment-prerequisites-for-integrating-with-hosted-exchange-um"></a>与托管 Exchange UM 集成的部署先决条件

在开始集成过程之前，你必须已部署 Lync Server 2013 （至少是前端池或标准版服务器）、边缘服务器以及 Lync 2013 或 Lync 2010 客户端。

</div>

<div>

## <a name="integration-process"></a>集成过程

下表提供了托管 Exchange UM 集成过程的概述。 有关部署步骤的详细信息，请参阅在部署文档中向[Lync Server 2013 用户提供托管 EXCHANGE UM 上的语音邮件](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>阶段</th>
<th>步骤</th>
<th>权利和权限</th>
<th>部署文档</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>配置边缘服务器。</p></td>
<td><ol>
<li><p>配置边缘服务器以进行联盟。</p></li>
<li><p>手动将数据复制到边缘服务器。</p></li>
<li><p>在边缘服务器上配置托管提供商。</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-configure-the-edge-server-for-integration-with-hosted-exchange-um.md">配置边缘服务器以与托管 Exchange UM 集成</a></p></td>
</tr>
<tr class="even">
<td><p>配置托管语音邮件策略。</p></td>
<td><ol>
<li><p>修改全局托管语音邮件策略，或使用网站或每用户范围创建新的托管语音邮件策略。</p></li>
<li><p>对于具有每用户范围的策略，请将策略分配给用户或组。</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-manage-hosted-voice-mail-policies.md">在 Lync Server 2013 中管理托管的语音邮件策略</a></p></td>
</tr>
<tr class="odd">
<td><p>为用户启用托管语音邮件。</p></td>
<td><ul>
<li><p>为其邮箱位于托管 Exchange 服务上的用户配置用户帐户。</p></li>
</ul></td>
<td><p>RTCUniversalUserAdmins</p></td>
<td><p><a href="lync-server-2013-enable-users-for-hosted-voice-mail.md">在 Lync Server 2013 中为用户启用托管语音邮件</a></p></td>
</tr>
<tr class="even">
<td><p>配置托管联系人对象。</p></td>
<td><ol>
<li><p>为托管 Exchange UM 创建自动助理联系人对象。</p></li>
<li><p>创建订阅者访问托管 Exchange UM 的联系人对象。</p></li>
</ol></td>
<td><p>RTCUniversalUserAdmins</p>
<div>

> [!NOTE]  
> 若要创建、修改或删除联系人对象，运行 CsExUmContact、CsExUmContact 或 Remove CsExUmContact cmdlet 的用户必须对存储新联系人对象的 Active Directory 组织单位具有正确的权限。 可以通过运行 Grant-CsOUPermission cmdlet 授予此权限。 有关详细信息，请参阅 Lync Server Management Shell 文档。


</div></td>
<td><p><a href="lync-server-2013-create-contact-objects-for-hosted-exchange-um.md">在 Lync Server 2013 中为托管 Exchange UM 创建联系人对象</a></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

