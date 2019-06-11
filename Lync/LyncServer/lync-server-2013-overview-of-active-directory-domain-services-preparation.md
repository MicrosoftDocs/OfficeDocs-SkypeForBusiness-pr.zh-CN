---
title: Lync Server 2013：Active Directory 域服务准备概述
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of Active Directory Domain Services preparation
ms:assetid: cdd2a652-6a0d-4728-9950-3fcaa7a80066
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398869(v=OCS.15)
ms:contentKeyID: 48185662
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26636846ce7b985a33af3175d51798c4c12c5ea7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825819"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-active-directory-domain-services-preparation-in-lync-server-2013"></a>Lync Server 2013 中的 Active Directory 域服务准备概述

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-29_

若要为 Lync Server 2013 部署准备 Active Directory 域服务, 必须按特定顺序执行三个步骤。

下表介绍了为 Lync Server 准备 AD DS 所需的步骤。

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
<td><p>通过添加 Lync Server 使用的新类和属性, 扩展 Active Directory 架构。</p>
<p>对将在其中部署 Lync Server 的部署中的每个林运行一次。</p></td>
<td><p>对于将在其中部署 Lync Server 的每个林的根域中的架构主机。</p>
<div>

> [!NOTE]  
> 如果你拥有架构主机的权限, 则无需在根域中运行此步骤, 但你必须是根域中的架构管理员组的成员, 以及架构主机上企业管理员组的成员。 在资源林拓扑中, 仅在资源目录林中运行此步骤, 而不是在任何用户林中运行。 在中央林拓扑中, 仅在中央林中 (而不是在任何用户林中) 运行此步骤。


</div></td>
</tr>
<tr class="even">
<td><p>2.</p></td>
<td><p><a href="lync-server-2013-preparing-the-forest.md">为 Lync Server 2013 准备林</a></p></td>
<td><p>创建由 Lync Server 使用的全局设置和通用组。</p>
<p>对将在其中部署 Lync Server 的部署中的每个林运行一次。</p></td>
<td><p>在将在其中部署 Lync Server 的每个林的根域中。 若要运行此步骤, 您必须是企业管理员组的成员。</p>
<div>

> [!NOTE]  
> 在资源林拓扑中, 仅在资源目录林中运行此步骤, 而不是在任何用户林中运行。 在中央林拓扑中, 仅在中央林中 (而不是在任何用户林中) 运行此步骤。


</div></td>
</tr>
<tr class="odd">
<td><p>3.</p></td>
<td><p><a href="lync-server-2013-preparing-domains.md">为 Lync Server 2013 准备域</a></p></td>
<td><p>在要由通用组成员使用的对象上添加权限。</p>
<p>每个用户域或服务器域运行一次。</p>
<div>

> [!NOTE]  
> 如果要从 Lync Server 2010 迁移到 Lync Server 2013, 则部署向导可能会指示域准备已完成。 无需再次运行域准备。 权限未从 Lync Server 2010 更改为 Lync Server 2013。


</div></td>
<td><p>在将部署 Lync Server 的每个域中的成员服务器上。 若要运行此步骤, 您必须是域管理员组的成员。</p></td>
</tr>
</tbody>
</table>


<div id="sectionSection0" class="section">

Lync Server 2013 (如 Lync Server 2010) 将大部分配置信息存储在中央管理存储中, 而不是在 Office 通信服务器 2007 R2 中的情况下, 而不是在 AD DS 中。 但是, 以下信息存储在 AD DS 中:

  - **架构扩展**:
    
      - 用户对象扩展
    
      - 用于维护向后兼容性的 Office 通信服务器 2007 R2 类的扩展

<!-- end list -->

  - **数据**(存储在 Lync Server 扩展架构和现有架构类中):
    
      - 用户 SIP 统一资源标识符 (URI) 和其他用户设置
    
      - 响应组和会议助理等应用程序的联系人对象
    
      - 指向中央管理存储的指针
    
      - Kerberos 身份验证帐户 (可选的计算机对象)

在 Lync Server 2013 中, 你可以通过向 RTCUniversalServerAdmins 通用组授予设置权限来委派设置和管理, 以便该组的成员可以在本地服务器上安装和激活 Lync Server 2013 (在将服务器添加到拓扑、已发布和已启用)。 委派用户必须是安装和激活 Lync Server 2013 的计算机上的本地管理员, 但不需要是域管理员组的成员。 你还可以为指定组织单位 (Ou) 中的对象授予权限, 以便在林准备期间创建的通用组的成员可以访问这些对象, 而不是域管理员组的成员。

对于 Lync Server 2013 的新部署, 全局设置必须存储在配置容器中。 如果你的组织从早期版本升级, 并且在系统容器中仍具有全局设置, 则系统容器仍受支持。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中准备 Active Directory 架构](lync-server-2013-preparing-the-active-directory-schema.md)  
[Lync Server 2013 使用的 Active Directory 架构扩展、类和属性](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md)  


[为 Lync Server 2013 准备林](lync-server-2013-preparing-the-forest.md)  
[为 Lync Server 2013 准备域](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

