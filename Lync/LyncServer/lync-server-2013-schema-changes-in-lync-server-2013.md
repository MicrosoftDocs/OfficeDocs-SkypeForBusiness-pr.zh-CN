---
title: Lync Server 2013： Lync Server 2013 中的架构更改
description: Lync Server 2013： Lync Server 2013 中的架构更改。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Schema changes in Lync Server 2013
ms:assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398944(v=OCS.15)
ms:contentKeyID: 48185575
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e914de48ace80fd2611f2d05b092894b11c534a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557148"
---
# <a name="schema-changes-in-lync-server-2013"></a>Lync Server 2013 中的架构更改

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-18_

在部署和操作 Lync Server 2013 之前，必须通过扩展架构来准备 Active Directory 域服务。 架构扩展添加了 Lync Server 2013 所需的类和属性。

Lync Server 2013 需要几个新的类和属性，并修改一些现有的类和属性。 此外，Lync Server 2013 的很多配置信息存储在中央管理存储中，而不是在 AD DS 中，就像在以前的版本中一样。 以下信息仍存储在 Lync Server 2013 中的 AD DS 中：

  - **架构扩展**：
    
      - 用户对象扩展
    
      - Office 通信服务器2007和 Office 通信服务器 2007 R2 类的扩展，以保持与受支持的早期版本的向后兼容

<!-- end list -->

  - 存储在 Lync Server 扩展架构和现有架构类中的**数据** () ：
    
      - 用户 SIP 统一资源标识符 (URI) 和其他用户设置
    
      - 应用程序（如响应组和会议助理）的联系人对象
    
      - 指向中央管理存储的指针
    
      - Kerberos 身份验证帐户（可选计算机对象）

本主题介绍 Lync Server 2013 所需的 Active Directory 架构更改。 它不会描述由早期版本的 Office 通信服务器引入的架构更改。 有关类及其说明的列表，请参阅 [Lync Server 2013 中的架构类和说明](lync-server-2013-schema-classes-and-descriptions.md)。 有关属性及其说明的列表，请参阅 [Lync Server 2013 中的架构属性和说明](lync-server-2013-schema-attributes-and-descriptions.md)。 有关它们可能包含的属性的类的列表，请参阅 [在 Lync Server 2013 中按类列出的架构属性](lync-server-2013-schema-attributes-by-class.md)。

MsRTCSIP 前缀标识特定于 Lync Server 的类和属性。

<div>

## <a name="new-active-directory-attributes"></a>新增 Active Directory 属性

下表介绍了由 Lync Server 2013 添加的 Active Directory 属性。

### <a name="attributes-added-by-lync-server-2013"></a>由 Lync Server 2013 添加的属性

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>属性</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>msExchUserHoldPolicies</p></td>
<td><p>此多值属性可保存应用于用户的保留策略的标识符。 保留策略会在保留持续时间内保留用户的邮箱项目。 此属性与 Exchange 2013 共享。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UserRoutingGroupId</p></td>
<td><p>这是 SIP 路由组 ID。同一组中的用户将注册到同一前端服务器。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MirrorBackEndServer</p></td>
<td><p>此属性用于存储前端池使用的镜像 SQL Server 后端。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="modified-active-directory-classes"></a>修改的 Active Directory 类

下表介绍了由 Lync Server 2013 修改的 Active Directory 类。

### <a name="classes-modified-by-lync-server-2013"></a>由 Lync Server 2013 修改的类

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Class</th>
<th>更改</th>
<th>类或属性</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>用户</p></td>
<td><p>add:mayContain</p>
<p>add:mayContain</p></td>
<td><p>ProxyAddresses</p>
<p>msRTCSIP-UserRoutingGroupId</p></td>
</tr>
<tr class="even">
<td><p>Contact</p></td>
<td><p>add:mayContain</p>
<p>add:mayContain</p></td>
<td><p>ProxyAddresses</p>
<p>msRTCSIP-UserRoutingGroupId</p></td>
</tr>
<tr class="odd">
<td><p>Mail-Recipient</p></td>
<td><p>add:mayContain</p></td>
<td><p>msExchUserHoldPolicies</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-GlobalTopologySetting</p></td>
<td><p>add:mayContain</p></td>
<td><p>msRTCSIP-MirrorBackEndServer</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

