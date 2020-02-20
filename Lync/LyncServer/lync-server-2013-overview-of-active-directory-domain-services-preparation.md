---
title: Lync Server 2013： Active Directory 域服务准备概述
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Active Directory Domain Services preparation
ms:assetid: cdd2a652-6a0d-4728-9950-3fcaa7a80066
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398869(v=OCS.15)
ms:contentKeyID: 48185662
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4590a3aff21683b12d22a1253522d6c49f626957
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153302"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-active-directory-domain-services-preparation-in-lync-server-2013"></a>Lync Server 2013 中的 Active Directory 域服务准备概述

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-29_

若要为 Lync Server 2013 部署准备 Active Directory 域服务，必须按特定顺序执行三个步骤。

下表介绍为 Lync Server 准备 AD DS 所需的步骤。

### <a name="active-directory-preparation-steps"></a>Active Directory 准备步骤

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
<td><p>通过添加 Lync Server 使用的新类和属性扩展 Active Directory 架构。</p>
<p>对将在其中部署 Lync Server 的部署中的每个林运行一次。</p></td>
<td><p>对将在其中部署 Lync Server 的每个林的根域中的架构主机。</p>
<div>

> [!NOTE]  
> 如果在架构主机上具有权限，则无需在根域中执行此步骤，但必须是根域中 Schema Admins 组的成员，并且是架构主机上 Enterprise Admins 组的成员。在资源林拓扑中，仅在资源林中执行此步骤，而不必在任何用户林中执行。在中央林拓扑中，仅在中央林中执行此步骤，而不必在任何用户林中执行。


</div></td>
</tr>
<tr class="even">
<td><p>2.</p></td>
<td><p><a href="lync-server-2013-preparing-the-forest.md">准备 Lync Server 2013 的林</a></p></td>
<td><p>创建由 Lync Server 使用的全局设置和通用组。</p>
<p>对将在其中部署 Lync Server 的部署中的每个林运行一次。</p></td>
<td><p>在将在其中部署 Lync Server 的每个林的根域中。 您必须是 Enterprise Admins 组的成员才能执行此步骤。</p>
<div>

> [!NOTE]  
> 在资源林拓扑中，仅在资源林中执行此步骤，而不必在任何用户林中执行。在中央林拓扑中，仅在中央林中执行此步骤，而不必在任何用户林中执行。


</div></td>
</tr>
<tr class="odd">
<td><p>3.</p></td>
<td><p><a href="lync-server-2013-preparing-domains.md">准备 Lync Server 2013 的域</a></p></td>
<td><p>添加对通用组成员所要使用的对象的权限。</p>
<p>为每个用户域或服务器域运行一次。</p>
<div>

> [!NOTE]  
> 如果要从 Lync Server 2010 迁移到 Lync Server 2013，部署向导可能会指示已完成域准备工作。 无需再次运行域准备。 权限未从 Lync Server 2010 更改为 Lync Server 2013。


</div></td>
<td><p>在将部署 Lync Server 的每个域中的成员服务器上。 您必须是 Domain Admins 组的成员才能执行此步骤。</p></td>
</tr>
</tbody>
</table>


<div id="sectionSection0" class="section">

Lync Server 2013 （如 Lync Server 2010）将大部分配置信息存储在中央管理存储中，而不是在 Office 通信服务器 2007 R2 中，而不是在 AD DS 中。 但是，以下信息存储在 AD DS 中：

  - **架构扩展**：
    
      - 用户对象扩展
    
      - Office 通信服务器 2007 R2 类的扩展，以保持向后兼容性

<!-- end list -->

  - **数据**（存储在 Lync Server 扩展架构和现有架构类中）：
    
      - 用户 SIP 统一资源标识符 (URI) 和其他用户设置
    
      - 应用程序（如响应组和会议助理）的联系人对象
    
      - 指向中央管理存储的指针
    
      - Kerberos 身份验证帐户（可选计算机对象）

在 Lync Server 2013 中，通过向 RTCUniversalServerAdmins 通用组授予安装程序权限来委派安装和管理，以便该组的成员可以在本地服务器上安装和激活 Lync Server 2013 （在将服务器添加到拓扑、已发布和已启用）。 委派用户必须是安装和激活 Lync Server 2013 的计算机上的本地管理员，但不需要是 Domain Admins 组的成员。 您也可以授予对特定组织单位 (OU) 中的对象的权限，以便在林准备期间创建的通用组成员无需是 Domain Admins 组成员即可访问这些对象。

对于 Lync Server 2013 的新部署，全局设置必须存储在配置容器中。 如果您的组织从早期版本升级，但在系统容器中仍有全局设置，则系统容器仍受支持。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中准备 Active Directory 架构](lync-server-2013-preparing-the-active-directory-schema.md)  
[Lync Server 2013 使用的 Active Directory 架构扩展、类和属性](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md)  


[准备 Lync Server 2013 的林](lync-server-2013-preparing-the-forest.md)  
[准备 Lync Server 2013 的域](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

