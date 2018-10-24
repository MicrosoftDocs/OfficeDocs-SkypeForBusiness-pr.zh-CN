---
title: Lync Server 2013：Active Directory 域服务准备概述
TOCTitle: Active Directory 域服务准备概述
ms:assetid: cdd2a652-6a0d-4728-9950-3fcaa7a80066
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398869(v=OCS.15)
ms:contentKeyID: 49314281
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 Active Directory 域服务准备概述

 

_**上一次修改主题：** 2015-03-09_

要为 Lync Server 2013 部署准备 Active Directory 域服务，必须按照特定顺序执行三个步骤。

下表介绍了为 Lync Server 准备 AD DS 所需的步骤。

### Active Directory 准备步骤

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>步骤</th>
<th>说明</th>
<th>运行位置</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1.</p></td>
<td><p><a href="lync-server-2013-preparing-the-active-directory-schema.md">在 Lync Server 2013 中准备 Active Directory 架构</a></p></td>
<td><p>通过添加 Lync Server 所使用的新类和属性，扩展 Active Directory 架构。</p>
<p>为部署中将部署 Lync Server 的每个林运行一次。</p></td>
<td><p>针对将部署 Lync Server 的每个林的根域中的架构主机。</p>
<div>

> [!NOTE]  
> 如果在架构主机上具有权限，则无需在根域中执行此步骤，但必须是根域中 Schema Admins 组的成员，并且是架构主机上 Enterprise Admins 组的成员。在资源林拓扑中，仅在资源林中执行此步骤，而不必在任何用户林中执行。在中央林拓扑中，仅在中央林中执行此步骤，而不必在任何用户林中执行。


</div></td>
</tr>
<tr class="even">
<td><p>2.</p></td>
<td><p><a href="lync-server-2013-preparing-the-forest.md">为 Lync Server 2013 准备林</a></p></td>
<td><p>创建 Lync Server 所使用的全局设置和通用组。</p>
<p>为部署中将部署 Lync Server 的每个林运行一次。</p></td>
<td><p>在将部署 Lync Server 的每个林的根域中。您必须是 Enterprise Admins 组的成员才能执行此步骤。</p>
<div>

> [!NOTE]  
> 在资源林拓扑中，仅在资源林中执行此步骤，而不必在任何用户林中执行。在中央林拓扑中，仅在中央林中执行此步骤，而不必在任何用户林中执行。


</div></td>
</tr>
<tr class="odd">
<td><p>3.</p></td>
<td><p><a href="lync-server-2013-preparing-domains.md">为 Lync Server 2013 准备域</a></p></td>
<td><p>添加对通用组成员所要使用的对象的权限。</p>
<p>为每个用户域或服务器域运行一次。</p>
<div>

> [!NOTE]  
> 如果是从 Lync Server 2010 迁移到 Lync Server 2013，部署向导可能指示域准备已经完成。无需再次运行域准备。未将 Lync Server 2010 权限更改为 Lync Server 2013。


</div></td>
<td><p>在将部署 Lync Server 的每个域中的成员服务器上。您必须是 Domain Admins 组的成员才能执行此步骤。</p></td>
</tr>
</tbody>
</table>


Lync Server 2013 与 Lync Server 2010 类似，将许多配置信息存储在 中央管理存储中，而不是像 Office Communications Server 2007 R2 一样存储在 AD DS 中。但是，以下信息存储在 AD DS 中：

  - **架构扩展 ：**
    
      - 用户对象扩展
    
      - 用于保持向后兼容性的 Office Communications Server 2007 R2 类的扩展

<!-- end list -->

  - **数据**（存储在 Lync Server 扩展架构和现有架构类中）：
    
      - 用户 SIP 统一资源标识符 (URI) 和其他用户设置
    
      - 应用程序（如响应组和会议助理）的联系人对象
    
      - 指向 中央管理存储的指针
    
      - Kerberos 身份验证帐户（可选计算机对象）

在 Lync Server 2013 中，通过向 RTCUniversalServerAdmins 通用组授予安装权限来委派安装和管理，以便该组中的成员可以在本地服务器上安装并激活 Lync Server 2013（当服务器添加到拓扑、发布并启用以后）。委派的用户必须是要安装并激活 Lync Server 2013 的计算机上的本地管理员，但是无需是 Domain Admins 组的成员。您也可以授予对指定组织单位 (OU) 中的对象的权限，以便在林准备期间创建的通用组成员无需是 Domain Admins 组成员即可访问这些对象。

对于 Lync Server 2013 的新部署，全局设置必须存储在“配置”容器中。如果组织是从早期版本升级的，而您在“系统”容器中还有全局设置，则“系统”容器仍然受支持。

## 另请参阅

#### 概念

[在 Lync Server 2013 中准备 Active Directory 架构](lync-server-2013-preparing-the-active-directory-schema.md)  
[Lync Server 2013 使用的 Active Directory 架构扩展、类和属性](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md)  

#### 其他资源

[为 Lync Server 2013 准备林](lync-server-2013-preparing-the-forest.md)  
[为 Lync Server 2013 准备域](lync-server-2013-preparing-domains.md)

