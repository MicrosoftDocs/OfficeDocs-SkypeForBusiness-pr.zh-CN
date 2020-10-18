---
title: 前端池和 Standard Edition 服务器的 IIS 要求
description: 前端池和 Standard Edition 服务器的 IIS 要求。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IIS requirements for Front End pools and Standard Edition servers
ms:assetid: e8a6c7ac-b6d5-4c7e-abe9-d8ea5eedbc62
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399038(v=OCS.15)
ms:contentKeyID: 48185888
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f56452c7e47352333ac3ac5a51d649b0828a0ff9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573338"
---
# <a name="iis-requirements-for-front-end-pools-and-standard-edition-servers-in-lync-server-2013"></a>Lync Server 2013 中的前端池和 Standard Edition 服务器的 IIS 要求

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-06-19_

对于 Standard Edition 服务器和前端服务器以及控制器，Lync Server 2013 安装程序会在 Internet Information Services (IIS) 中创建虚拟目录，以实现以下目的：

  - 允许用户从通讯簿服务下载文件

  - 启用客户端以获取更新

  - 启用会议

  - 允许用户下载会议内容

  - 允许用户扩展通讯组

  - 启用电话会议

  - 启用响应组功能

此外，Lync Server 2010 的累积更新：11月2011安装程序将在 IIS 中创建虚拟目录，以实现以下目的：

  - 在前端服务器或 Standard Edition 服务器上，支持移动功能（如即时消息 (IM) 和状态）在移动设备上

  - 在前端服务器或 Standard Edition 服务器和控制器上，使移动设备能够自动发现移动资源



> [!NOTE]
> 如果要部署移动性，建议使用 IIS 7.5。 Lync Server 移动服务安装程序设置一些 ASP.NET 标志以提高性能。 默认情况下，IIS 7.5 安装在 Windows Server 2008 R2 上，并且 Mobility Service 安装程序会自动更改 ASP.NET 设置。 如果您在 Windows Server 2008 上使用 IIS 7.0，则需要手动更改这些设置。



Lync Server 要求安装以下 IIS 模块：


> [!IMPORTANT]
> 如果您的组织要求在除系统驱动器之外的驱动器上查找 IIS 和所有 Web 服务，则可以在 "安装程序" 对话框中更改 Lync Server 文件的安装位置路径。 如果将安装文件安装到此路径（包括 OCSCore.msi），则其余的 Lync Server 文件也将部署到此驱动器。 有关如何在安装 IIS 时重新定位由 Windows Server Manager 部署的 INETPUB 的详细信息，请参阅 <A href="https://go.microsoft.com/fwlink/p/?linkid=216888">https://go.microsoft.com/fwlink/p/?linkId=216888</A> 。


  - 静态内容

  - 默认文档

  - HTTP 错误

  - ASP.NET

  - .NET 扩展性

  - Internet Server API (ISAPI) 扩展

  - ISAPI 筛选器

  - HTTP 日志记录

  - 日志记录工具

  - 追踪

  - Windows 身份验证

  - 请求筛选

  - 静态内容压缩

  - 动态内容压缩

  - IIS 管理控制台

  - IIS 管理脚本和工具

  - 匿名身份验证（安装 IIS 时默认安装）

  - 客户端证书映射身份验证

下表列出了用于内部访问的虚拟目录的 URI 及其引用的文件系统资源。

### <a name="virtual-directories-for-internal-access"></a>用于内部访问的虚拟目录

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>功能</th>
<th>虚拟目录 URI</th>
<th>引用</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>通讯簿服务器</p></td>
<td><p>https:// &lt; 内部 FQDN &gt; /ABS/int/Handler</p></td>
<td><p>用于内部用户的通讯簿服务器下载文件的位置。</p></td>
</tr>
<tr class="even">
<td><p>自动发现服务</p></td>
<td><p>https:// &lt; 内部 FQDN &gt; /Autodiscover</p></td>
<td><p>为内部移动设备用户查找移动性资源的 Lync Server 自动发现服务的位置。</p></td>
</tr>
<tr class="odd">
<td><p>客户端更新</p></td>
<td><p>http:// &lt; 内部 FQDN &gt; /AutoUpdate/Int</p></td>
<td><p>用于内部基于计算机的客户端的更新文件的位置。</p></td>
</tr>
<tr class="even">
<td><p>会议</p></td>
<td><p>http:// &lt; 内部 FQDN &gt; /Conf/Int</p></td>
<td><p>用于内部用户的会议资源的位置。</p></td>
</tr>
<tr class="odd">
<td><p>设备更新</p></td>
<td><p>http:// &lt; 内部 FQDN &gt; /DeviceUpdateFiles_Int</p></td>
<td><p>用于内部 UC 设备的统一通信 (UC) 设备更新文件的位置。</p></td>
</tr>
<tr class="even">
<td><p>要求</p></td>
<td><p>http:// &lt; 内部 FQDN &gt; /etc/place/null</p></td>
<td><p>用于内部用户的会议内容的位置。</p></td>
</tr>
<tr class="odd">
<td><p>Mobility Service</p></td>
<td><p>https:// &lt; 内部 FQDN &gt; /Mcx</p></td>
<td><p>用于内部移动设备用户的 Mobility Service 资源的位置。</p></td>
</tr>
<tr class="even">
<td><p>组扩展和通讯簿 Web 查询服务</p></td>
<td><p>http:// &lt; 内部 FQDN &gt; /GroupExpansion/int/service.asmx</p></td>
<td><p>为内部用户启用组扩展的 Web 服务的位置。 此外，将全局地址列表信息提供给内部 Lync Mobile Microsoft Lync 2010 移动客户端的通讯簿 Web 查询服务的位置。</p></td>
</tr>
<tr class="odd">
<td><p>电话会议</p></td>
<td><p>http:// &lt; 内部 FQDN &gt; /PhoneConferencing/Int</p></td>
<td><p>用于内部用户的电话会议数据的位置。</p></td>
</tr>
<tr class="even">
<td><p>设备更新</p></td>
<td><p>http:// &lt; 内部 FQDN &gt; /RequestHandler</p></td>
<td><p>用于启用内部 UC 设备以便上载日志以及检查更新的设备更新 Web 服务请求处理程序的位置。</p></td>
</tr>
<tr class="odd">
<td><p>响应组应用程序</p></td>
<td><p>http:// &lt; 内部 FQDN &gt; /RgsConfig</p>
<p>http:// &lt; 内部 FQDN &gt; /RgsClients</p></td>
<td><p>响应组配置工具的位置。</p></td>
</tr>
</tbody>
</table>


> [!NOTE]
> 对于合并配置中的前端池，您必须先部署 IIS，然后才能将服务器添加到池。


<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="保护" alt="security" />安全说明：</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>必须使用 IIS 管理性管理单元分配由 IIS Web 组件服务器使用的证书。</td>
</tr>
</tbody>
</table>



</div>

<span> </span>

</div>

</div>

</div>

