---
title: Lync Server 2013：集成托管 Exchange UM 的部署过程
TOCTitle: 集成托管 Exchange UM 与 Lync Server 的部署过程
ms:assetid: dbec9c38-7f66-419d-b8c3-c61380052cac
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398968(v=OCS.15)
ms:contentKeyID: 49314460
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 集成托管 Exchange UM 与 Lync Server 2013 的部署过程

 

_**上一次修改主题：** 2015-03-09_

要有效地规划 Lync Server 2013 与托管的 Exchange 统一消息 (UM) 的集成，您需要考虑以下内容：

  - 将 Lync Server 2013 与托管 Exchange UM 集成的先决条件

  - 集成过程中所需的步骤

## 与托管 Exchange UM 集成的部署先决条件

必须已部署 Lync Server 2013（至少是前端池或 Standard Edition Server）、边缘服务器和 Lync 2013 或 Lync 2010 客户端，然后才能开始集成过程。

## 集成过程

下表概述了托管 Exchange UM 集成过程。有关部署步骤的详细信息，请参阅部署文档中的 [在托管 Exchange UM 上提供 Lync Server 2013 用户语音邮件](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)。


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
<th>权限</th>
<th>部署文档</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>配置边缘服务器。</p></td>
<td><ol>
<li><p>配置边缘服务器以进行联盟。</p></li>
<li><p>手动将数据复制到边缘服务器。</p></li>
<li><p>在边缘服务器上配置托管服务提供商。</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-configure-the-edge-server-for-integration-with-hosted-exchange-um.md">配置边缘服务器以与托管 Exchange UM 集成</a></p></td>
</tr>
<tr class="even">
<td><p>配置托管语音邮件策略。</p></td>
<td><ol>
<li><p>修改全局托管语音邮件策略或创建具有 Site 作用域或每用户作用域的新托管语音邮件策略。</p></li>
<li><p>对于具有每用户作用域的策略，请将策略分配给用户或组。</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-manage-hosted-voice-mail-policies.md">在 Lync Server 2013 中管理托管的语音邮件策略</a></p></td>
</tr>
<tr class="odd">
<td><p>为用户启用托管语音邮件。</p></td>
<td><ul>
<li><p>为邮箱位于托管的 Exchange 服务的用户配置用户帐户。</p></li>
</ul></td>
<td><p>RTCUniversalUserAdmins</p></td>
<td><p><a href="lync-server-2013-enable-users-for-hosted-voice-mail.md">在 Lync Server 2013 中为用户启用托管语音邮件</a></p></td>
</tr>
<tr class="even">
<td><p>配置托管联系人对象。</p></td>
<td><ol>
<li><p>为托管 Exchange UM 创建自动助理联系人对象。</p></li>
<li><p>为托管 Exchange UM 创建订阅者访问联系人对象。</p></li>
</ol></td>
<td><p>RTCUniversalUserAdmins</p>
<div>

> [!NOTE]  
> 要创建、修改或删除联系人对象，运行 New-CsExUmContact、Set-CsExUmContact 或 Remove-CsExUmContact cmdlet 的用户必须对存储新联系人对象的 Active Directory 组织单位具有相应的权限。可以通过运行 Grant-CsOUPermission cmdlet 授予此权限。有关详细信息，请参阅 Lync Server 命令行管理程序文档。


</div></td>
<td><p><a href="lync-server-2013-create-contact-objects-for-hosted-exchange-um.md">在 Lync Server 2013 中为托管 Exchange UM 创建联系人对象</a></p></td>
</tr>
</tbody>
</table>

