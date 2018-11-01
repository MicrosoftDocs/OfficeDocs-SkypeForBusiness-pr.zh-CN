---
title: Lync Server 2013 中的架构更改
TOCTitle: Lync Server 2013 中的架构更改
ms:assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398944(v=OCS.15)
ms:contentKeyID: 49314410
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的架构更改

 

_**上一次修改主题：** 2015-03-09_

在部署和运行 Lync Server 2013 之前，必须通过扩展架构来准备 Active Directory 域服务。架构扩展将添加 Lync Server 2013 所需的类和属性。

Lync Server 2013 需要多个新的类和属性并修改某些现有的类和属性。此外，Lync Server 2013 的许多配置信息存储在中央管理存储中，而不是像以前的版本一样存储在 AD DS 中。Lync Server 2013 中的以下信息仍存储在 AD DS 中：

  - **架构扩展：**
    
      - 用户对象扩展
    
      - 用于维护与支持的早期版本向后兼容的 Office Communications Server 2007 和 Office Communications Server 2007 R2 类扩展

<!-- end list -->

  - **数据**（存储在 Lync Server 扩展架构和现有架构类中）：
    
      - 用户 SIP 统一资源标识符 (URI) 和其他用户设置
    
      - 应用程序（如响应组和会议助理）的联系人对象
    
      - 指向中央管理存储的指针
    
      - Kerberos 身份验证帐户（可选计算机对象）

本主题介绍 Lync Server 2013 所需的 Active Directory 架构更改。不介绍以前版本的 Office Communications Server 引入的架构更改。有关类及其说明的列表，请参阅[Lync Server 2013 中的架构类和说明](lync-server-2013-schema-classes-and-descriptions.md)。有关属性及其说明的列表，请参阅[Lync Server 2013 中的架构属性和说明](lync-server-2013-schema-attributes-and-descriptions.md)。有关带有可能包含的属性的类的列表，请参阅[Lync Server 2013 中的按类分组的架构属性](lync-server-2013-schema-attributes-by-class.md)。

msRTCSIP 前缀标识特定于 Lync Server 的类和属性。

## 新增 Active Directory 属性

下表介绍由 Lync Server 2013 添加的 Active Directory 属性。

### 由 Lync Server 2013 添加的属性

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
<td><p>此多值属性可保存应用于用户的保留策略的标识符。保留策略会在保持持续时间内保留用户的邮箱项目。与 Exchange 2013 共享此属性。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UserRoutingGroupId</p></td>
<td><p>这是 SIP 路由组 ID。同一组中的用户将注册到同一前端服务器。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MirrorBackEndServer</p></td>
<td><p>该属性用于存储前端池使用的镜像 SQL Server 后端。</p></td>
</tr>
</tbody>
</table>


## 修改的 Active Directory 类

下表介绍由 Lync Server 2013 修改的 Active Directory 类。

### 由 Lync Server 2013 修改的类

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>类</th>
<th>更改</th>
<th>类或属性</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>User</p></td>
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

