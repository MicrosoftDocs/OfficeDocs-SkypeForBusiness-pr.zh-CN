---
title: Lync Server 2013：前端池和 Standard Edition 服务器的 IIS 要求
TOCTitle: 前端池和 Standard Edition 服务器的 IIS 要求
ms:assetid: e8a6c7ac-b6d5-4c7e-abe9-d8ea5eedbc62
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg399038(v=OCS.15)
ms:contentKeyID: 49314603
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中前端池和 Standard Edition 服务器的 IIS 要求

 

_**上一次修改主题：** 2016-12-08_

对于 Standard Edition Server、前端服务器和控制器，Lync Server 2013 安装程序会出于以下目的在 Internet Information Services (IIS) 中创建虚拟目录：

  - 允许用户从通讯簿服务下载文件

  - 允许客户端获取更新

  - 启用会议

  - 允许用户下载会议内容

  - 允许用户扩展通讯组

  - 启用电话会议

  - 启用响应组功能

此外，2011 年 11 月版的 Lync Server 2010 累积更新安装程序会出于以下目的在 IIS 中创建虚拟目录：

  - 在 前端服务器或 Standard Edition Server 上支持移动设备上的移动功能，如即时消息 (IM) 和状态

  - 在 前端服务器或 Standard Edition Server 和控制器上允许移动设备自动发现移动资源

> [!NOTE]  
> 如果您要部署移动功能，则建议您使用 IIS 7.5。 Lync Server Mobility Service 安装程序设置了一些 ASP.NET 标志以提高性能。默认情况下，IIS 7.5 安装在 Windows Server 2008 R2 上，并且 Mobility Service 安装程序会自动更改 ASP.NET 设置。如果您在 Windows Server 2008 上使用 IIS 7.0，则需要手动更改这些设置。



Lync Server 要求安装以下 IIS 模块：

> [!IMPORTANT]
> 如果组织要求您在系统驱动器之外的某个驱动器上定位 IIS 和所有 Web Services，您可以在“安装”对话框中更改 Lync Server 文件的安装位置路径。如果您将安装文件（包括 OCSCore.msi）安装到此路径，则其余的 Lync Server 文件也将部署到该驱动器。有关如何在安装 IIS 时重新定位 Windows Server Manager 部署的 INETPUB 的详细信息，请参阅 <a href="http://go.microsoft.com/fwlink/p/?linkid=216888">http://go.microsoft.com/fwlink/p/?linkId=216888</a>。


  - 静态内容

  - 默认文档

  - HTTP 错误

  - ASP.NET

  - .NET 扩展性

  - Internet Server API (ISAPI) 扩展

  - ISAPI 筛选器

  - HTTP 日志记录

  - 日志记录工具

  - 跟踪

  - Windows 身份验证

  - 请求筛选

  - 静态内容压缩

  - 动态内容压缩

  - IIS 管理控制台

  - IIS 管理脚本和工具

  - 匿名身份验证（安装 IIS 时默认安装）

  - 客户端证书映射身份验证

下表列出了用于内部访问的虚拟目录的 URI 及其引用的文件系统资源。

### 用于内部访问的虚拟目录

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
<td><p>https://<em>&lt;Internal FQDN&gt;</em>/ABS/int/Handler</p></td>
<td><p>用于内部用户的通讯簿服务器下载文件的位置。</p></td>
</tr>
<tr class="even">
<td><p>自动发现服务</p></td>
<td><p>https://<em>&lt;Internal FQDN&gt;</em>/Autodiscover</p></td>
<td><p>用于内部移动设备用户的定位移动资源的 Lync Server 自动发现服务的位置。</p></td>
</tr>
<tr class="odd">
<td><p>客户端更新</p></td>
<td><p>http://<em>&lt;Internal FQDN&gt;</em>/AutoUpdate/Int</p></td>
<td><p>用于内部基于计算机的客户端的更新文件的位置。</p></td>
</tr>
<tr class="even">
<td><p>会议</p></td>
<td><p>http://<em>&lt;Internal FQDN&gt;</em>/Conf/Int</p></td>
<td><p>用于内部用户的会议资源的位置。</p></td>
</tr>
<tr class="odd">
<td><p>设备更新</p></td>
<td><p>http://<em>&lt;Internal FQDN&gt;</em>/DeviceUpdateFiles_Int</p></td>
<td><p>用于内部 UC 设备的统一通信 (UC) 设备更新文件的位置。</p></td>
</tr>
<tr class="even">
<td><p>会议</p></td>
<td><p>http://<em>&lt;Internal FQDN&gt;</em>/etc/place/null</p></td>
<td><p>用于内部用户的会议内容的位置。</p></td>
</tr>
<tr class="odd">
<td><p>Mobility Service</p></td>
<td><p>https://<em>&lt;Internal FQDN&gt;</em>/Mcx</p></td>
<td><p>用于内部移动设备用户的 Mobility Service 资源的位置。</p></td>
</tr>
<tr class="even">
<td><p>组扩展和通讯簿 Web 查询服务</p></td>
<td><p>http://<em>&lt;Internal FQDN&gt;</em>/GroupExpansion/int/service.asmx</p></td>
<td><p>为内部用户启用组扩展的 Web 服务的位置。以及向内部 Lync MobileMicrosoft Lync 2010 Mobile 客户端提供全局地址列表信息的通讯簿 Web 查询服务的位置。</p></td>
</tr>
<tr class="odd">
<td><p>电话会议</p></td>
<td><p>http://<em>&lt;Internal FQDN&gt;</em>/PhoneConferencing/Int</p></td>
<td><p>用于内部用户的电话会议数据的位置。</p></td>
</tr>
<tr class="even">
<td><p>设备更新</p></td>
<td><p>http://<em>&lt;Internal FQDN&gt;</em>/RequestHandler</p></td>
<td><p>用于启用内部 UC 设备以便上载日志以及检查更新的设备更新 Web 服务请求处理程序的位置。</p></td>
</tr>
<tr class="odd">
<td><p>响应组应用程序</p></td>
<td><p>http://<em>&lt;Internal FQDN&gt;</em>/RgsConfig</p>
<p>http://<em>&lt;Internal FQDN&gt;</em>/RgsClients</p></td>
<td><p>响应组配置工具的位置。</p></td>
</tr>
</tbody>
</table>


> [!NOTE]  
> 对于采用合并配置的 前端池，必须先部署 IIS，然后才能向池中添加服务器。



> [!NOTE]  
> 必须使用 IIS 管理性管理单元分配由 IIS Web 组件服务器使用的证书。

