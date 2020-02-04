---
title: Lync Server 2013：控制器的软硬件要求
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
ms.openlocfilehash: 52d91a739935b2e42bb925d5645350c5875e5b43
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762190"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardware-and-software-requirements-for-the-director-in-lync-server-2013"></a>Lync Server 2013 中控制器的软硬件要求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-20_

本部分详细介绍了 Director 的硬件和软件要求，以及 Director 支持的 collocation 方案。

<div>

## <a name="hardware-requirements-for-the-director"></a>控制器的硬件要求

下表列出了 Director 的硬件要求：

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
<li><p>64位处理器、四核、2.0 GHz 或更高版本</p></li>
<li><p>64位双处理器、双核、2.0 GHz 或更高版本</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>内存</p></td>
<td><p>4千兆字节（GB）</p></td>
</tr>
<tr class="odd">
<td><p>磁盘</p></td>
<td><ul>
<li><p>10K RPM 硬盘（HDD）</p></li>
<li><p>高性能稳定状态驱动器（SSD），性能等于或优于 10K RPM HDD</p></li>
<li><p>2倍的 RAID 10 （条带化和镜像）数据库数据文件的 15K RPM 磁盘</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>网络</p></td>
<td><ul>
<li><p>双核1千兆位/秒（Gbps）网络适配器（推荐）</p></li>
<li><p>单个 1 Gbps 网络适配器（支持）</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="software-requirements-for-the-director"></a>董事的软件要求

Director 角色只能部署在运行 Lync Server 2013 企业版的服务器上。

控制器需要以下64位操作系统之一：

  - Windows Server 2008 R2 标准操作系统，Service Pack 1

  - Windows Server 2008 R2 企业版操作系统 Service Pack 1

  - Windows Server 2008 R2 Datacenter 操作系统 Service Pack 1

  - Windows Server 2012 标准操作系统

  - Windows Server 2012 Datacenter 操作系统

Lync Server 2013 还要求安装以下程序和更新，详细信息请参阅[Lync Server 2013 中的其他服务器支持和要求](lync-server-2013-additional-server-support-and-requirements.md)主题。

</div>

<div>

## <a name="supported-collocation"></a>支持的 Collocation

Director 服务器角色不能与 Lync Server 2013 中的任何其他服务器角色 collocated。 但是，如果您不部署 Director，前端服务器将承担该角色。

</div>

</div>

<span> </span>

</div>

</div>

</div>

