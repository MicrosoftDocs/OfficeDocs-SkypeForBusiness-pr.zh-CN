---
title: Lync Server 2013：控制器的硬件和软件要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardware and software requirements for the Director
ms:assetid: 747b701e-7f97-46fe-91c5-1e8d9addf9f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398560(v=OCS.15)
ms:contentKeyID: 48184517
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ff5e28b21e06cc438c7eb092515443579f5c004
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42155024"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="hardware-and-software-requirements-for-the-director-in-lync-server-2013"></a>Lync Server 2013 中的控制器的硬件和软件要求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-20_

本部分详细介绍了控制器的硬件和软件要求，以及控制器支持的并置方案。

<div>

## <a name="hardware-requirements-for-the-director"></a>控制器的硬件要求

下表列出了控制器的硬件要求：

### <a name="hardware-requirements-for-the-director"></a>控制器的硬件要求

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>硬件组件</th>
<th>最低要求</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CPU</p></td>
<td><ul>
<li><p>64 位处理器、四核、2.0 GHz 或更快</p></li>
<li><p>64 位双处理器、双核、2.0 GHz 或更快</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>内存</p></td>
<td><p>4 GB</p></td>
</tr>
<tr class="odd">
<td><p>磁盘</p></td>
<td><ul>
<li><p>转速为 10K RPM 的硬盘驱动器 (HDD)</p></li>
<li><p>性能等于或高于 10K RPM HDD 的高性能固态驱动器 (SSD)</p></li>
<li><p>2 个 RAID 10（条带和镜像）、转速为 15K RPM 的硬盘，用于存储数据库数据文件</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>网络</p></td>
<td><ul>
<li><p>双 1 千兆位每秒 (Gbps) 网络适配器（推荐）</p></li>
<li><p>一个 1 Gbps 网络适配器（支持）</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="software-requirements-for-the-director"></a>控制器的软件要求

Director 角色只能部署在运行 Lync Server 2013 Enterprise Edition 的服务器上。

控制器需要以下64位操作系统之一：

  - Windows Server 2008 R2 Standard 操作系统 Service Pack 1

  - Windows Server 2008 R2 Enterprise 操作系统 Service Pack 1

  - Windows Server 2008 R2 Datacenter 操作系统 Service Pack 1

  - Windows Server 2012 标准操作系统

  - Windows Server 2012 Datacenter 操作系统

Lync Server 2013 还需要安装以下程序和更新在[Lync Server 2013 中的主题其他服务器支持和要求](lync-server-2013-additional-server-support-and-requirements.md)中详细介绍。

</div>

<div>

## <a name="supported-collocation"></a>支持的并置

在 Lync Server 2013 中，控制器服务器角色不能与任何其他服务器角色并置。 但是，如果不部署控制器，前端服务器将承担角色。

</div>

</div>

<span> </span>

</div>

</div>

</div>

