---
title: Lync Server 2013：IIS 配置
TOCTitle: IIS 配置
ms:assetid: b458babf-bf64-43f0-8a8e-612f5096b63c
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412871(v=OCS.15)
ms:contentKeyID: 49313984
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 IIS 配置

 

_**上一次修改主题：** 2016-12-08_

要成功完成此过程，应至少以本地管理员身份和域用户身份登录服务器。

为 Lync Server 2013、 标准版 或池中第一台 前端服务器配置和安装 前端服务器之前，必须为 Internet Information Services (IIS) 安装和配置服务器角色和 Web 服务。

> [!IMPORTANT]
> 如果组织需要您将 IIS 和所有 Web 服务定位到非系统驱动器上，您可以在最初安装 Lync Server 2013 管理工具时在“安装”对话框中更改 Lync Server 2013 文件的安装位置路径。安装 IIS 前，需要安装管理工具。如果您将安装文件（包括 OCSCore.msi）安装到此路径，则其余的 Lync Server 2013 文件也将部署到该驱动器。有关详细信息，请参阅<a href="lync-server-2013-install-lync-server-administrative-tools.md">安装 Lync Server 2013 管理工具</a>。有关如何在安装 IIS 时重新定位 Windows Server Manager 部署的 INETPUB 的详细信息，请参阅 <a href="http://go.microsoft.com/fwlink/?linkid=216888" class="uri">http://go.microsoft.com/fwlink/?linkid=216888</a>。


下表指出了所需的 IIS 7.5 角色服务。

### IIS 7.5 角色服务

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>角色标题</th>
<th>角色服务</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>已安装的常见 HTTP 功能</p></td>
<td><p>静态内容</p></td>
</tr>
<tr class="even">
<td><p>已安装的常见 HTTP 功能</p></td>
<td><p>默认文档</p></td>
</tr>
<tr class="odd">
<td><p>已安装的常见 HTTP 功能</p></td>
<td><p>HTTP 错误</p></td>
</tr>
<tr class="even">
<td><p>应用程序开发</p></td>
<td><p>ASP.NET</p>
<p>Windows Server 2012 还需要 ASP.NET4.5</p></td>
</tr>
<tr class="odd">
<td><p>应用程序开发</p></td>
<td><p>.NET 扩展性</p></td>
</tr>
<tr class="even">
<td><p>应用程序开发</p></td>
<td><p>Internet Server API (ISAPI) 扩展</p></td>
</tr>
<tr class="odd">
<td><p>应用程序开发</p></td>
<td><p>ISAPI 筛选器</p></td>
</tr>
<tr class="even">
<td><p>运行状况和诊断</p></td>
<td><p>HTTP 日志记录</p></td>
</tr>
<tr class="odd">
<td><p>运行状况和诊断</p></td>
<td><p>日志记录工具</p></td>
</tr>
<tr class="even">
<td><p>运行状况和诊断</p></td>
<td><p>跟踪</p></td>
</tr>
<tr class="odd">
<td><p>安全性</p></td>
<td><p>匿名身份验证（默认情况下已安装并处于启用状态）</p></td>
</tr>
<tr class="even">
<td><p>安全性</p></td>
<td><p>Windows 身份验证</p></td>
</tr>
<tr class="odd">
<td><p>安全性</p></td>
<td><p>客户端证书映射身份验证</p></td>
</tr>
<tr class="even">
<td><p>安全性</p></td>
<td><p>请求筛选</p></td>
</tr>
<tr class="odd">
<td><p>性能</p></td>
<td><p>静态内容压缩</p>
<p>动态内容压缩</p></td>
</tr>
<tr class="even">
<td><p>管理工具</p></td>
<td><p>IIS 管理控制台</p></td>
</tr>
<tr class="odd">
<td><p>管理工具</p></td>
<td><p>IIS 管理脚本和工具</p></td>
</tr>
</tbody>
</table>


在 Windows Server 2008 R2 SP1 x64 操作系统上，您可以使用 Windows PowerShell 2.0。必须先导入 ServerManager 模块，然后才能安装 IIS 7.5 角色和角色服务。

    Import-Module ServerManager

   &nbsp;

    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Scripting-Tools, Web-Windows-Auth, Web-Asp-Net, Web-Log-Libraries, Web-Http-Tracing, Web-Stat-Compression, Web-Dyn-Compression, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Errors, Web-Http-Logging, Web-Net-Ext, Web-Client-Auth, Web-Filtering, Web-Mgmt-Console

> [!NOTE]  
> 默认情况下，匿名身份验证会随 IIS 服务器角色一起安装。安装 IIS 后，您可以管理匿名身份验证。有关详细信息，请参阅“启用匿名身份验证 (IIS 7)”，网址为 <a href="http://go.microsoft.com/fwlink/?linkid=203935" class="uri">http://go.microsoft.com/fwlink/?linkid=203935</a>。



下表指明 Windows Server 2012 和 Windows Server 2012 R2 所需的 IIS 8.0 和 IIS 8.5 角色服务。

> [!NOTE]  
> 对于 Windows Server 2012 和 Windows Server 2012 R2，Add-WindowsFeature cmdlet 已替换为 Install-WindowsFeature cmdlet。有关详细信息，请参阅 <a href="http://go.microsoft.com/fwlink/p/?linkid=392274">Install-WindowsFeature</a>。



### IIS 8.0 和 IIS 8.5 角色服务

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>角色标题</th>
<th>角色服务</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Web 服务器 (IIS)</p></td>
<td><p>Web 服务器</p></td>
</tr>
<tr class="even">
<td><p>常见的 HTTP 功能</p></td>
<td><p>默认文档</p></td>
</tr>
<tr class="odd">
<td><p>常见的 HTTP 功能</p></td>
<td><p>目录浏览</p></td>
</tr>
<tr class="even">
<td><p>常见的 HTTP 功能</p></td>
<td><p>HTTP 错误</p></td>
</tr>
<tr class="odd">
<td><p>常见的 HTTP 功能</p></td>
<td><p>静态内容</p></td>
</tr>
<tr class="even">
<td><p>常见的 HTTP 功能</p></td>
<td><p>HTTP 重定向</p></td>
</tr>
<tr class="odd">
<td><p>运行状况和诊断</p></td>
<td><p>HTTP 日志记录</p></td>
</tr>
<tr class="even">
<td><p>运行状况和诊断</p></td>
<td><p>日志记录工具</p></td>
</tr>
<tr class="odd">
<td><p>运行状况和诊断</p></td>
<td><p>请求监视器</p></td>
</tr>
<tr class="even">
<td><p>运行状况和诊断</p></td>
<td><p>跟踪</p></td>
</tr>
<tr class="odd">
<td><p>安全性</p></td>
<td><p>请求筛选</p></td>
</tr>
<tr class="even">
<td><p>安全性</p></td>
<td><p>基本身份验证</p></td>
</tr>
<tr class="odd">
<td><p>安全性</p></td>
<td><p>客户端证书映射身份验证</p></td>
</tr>
<tr class="even">
<td><p>安全性</p></td>
<td><p>Windows 身份验证</p></td>
</tr>
<tr class="odd">
<td><p>应用程序开发</p></td>
<td><p>.Net Extensibility 3.5</p></td>
</tr>
<tr class="even">
<td><p>应用程序开发</p></td>
<td><p>.Net Extensibility 4.5</p></td>
</tr>
<tr class="odd">
<td><p>应用程序开发</p></td>
<td><p>ASP.Net 3.5</p></td>
</tr>
<tr class="even">
<td><p>应用程序开发</p></td>
<td><p>ASP.Net 4.5</p></td>
</tr>
<tr class="odd">
<td><p>应用程序开发</p></td>
<td><p>ISAPI 扩展</p></td>
</tr>
<tr class="even">
<td><p>应用程序开发</p></td>
<td><p>ISAPI 筛选器</p></td>
</tr>
<tr class="odd">
<td><p>应用程序开发</p></td>
<td><p>服务器端包含</p></td>
</tr>
<tr class="even">
<td><p>管理工具</p></td>
<td><p>IIS 管理控制台</p></td>
</tr>
<tr class="odd">
<td><p>管理工具</p></td>
<td><p>IIS 6 元数据库兼容性</p></td>
</tr>
<tr class="even">
<td><p>管理工具</p></td>
<td><p>IIS 管理脚本和工具</p></td>
</tr>
<tr class="odd">
<td><p>.Net 3.5 Framework 功能</p></td>
<td><p>.Net 3.5 Framework</p></td>
</tr>
<tr class="even">
<td><p>.Net 4.5 Framework 功能</p></td>
<td><p>.Net Framework 4.5</p></td>
</tr>
<tr class="odd">
<td><p>.Net 4.5 Framework 功能</p></td>
<td><p>ASP.Net 4.5</p></td>
</tr>
<tr class="even">
<td><p>.Net 4.5 Framework 功能</p></td>
<td><p>HTTP 激活</p></td>
</tr>
<tr class="odd">
<td><p>.Net 4.5 Framework 功能</p></td>
<td><p>TCP 端口共享</p></td>
</tr>
<tr class="even">
<td><p>后台智能传输服务</p></td>
<td><p>IIS 服务器扩展</p></td>
</tr>
<tr class="odd">
<td><p>墨迹和手写服务</p></td>
<td><p>墨迹和手写服务</p></td>
</tr>
<tr class="even">
<td><p>媒体基础</p></td>
<td><p>媒体基础</p></td>
</tr>
<tr class="odd">
<td><p>用户界面和基础结构</p></td>
<td><p>图形管理工具和基础结构</p></td>
</tr>
<tr class="even">
<td><p>用户界面和基础结构</p></td>
<td><p>桌面体验</p></td>
</tr>
<tr class="odd">
<td><p>用户界面和基础结构</p></td>
<td><p>服务器图形 Shell</p></td>
</tr>
<tr class="even">
<td><p>Windows Identity Foundation 3.5</p></td>
<td><p>Windows Identity Foundation 3.5</p></td>
</tr>
<tr class="odd">
<td><p>Windows Process Activation Service</p></td>
<td><p>进程模型</p></td>
</tr>
<tr class="even">
<td><p>Windows Process Activation Service</p></td>
<td><p>配置 API</p></td>
</tr>
</tbody>
</table>


在 Windows Server 2012 和 Windows Server 2012 R2 中，您可以使用 Windows PowerShell 3.0 安装 IIS 要求。使用 Windows PowerShell 3.0 中的 ServerManager 模块时，请键入：

    Import-Module ServerManager

   &nbsp;

    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-Framework-45-Core, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Console, Web-Mgmt-Compat, Windows-Identity-Foundation, Server-Media-Foundation, BITS -Source D:\sources\sxs

> [!IMPORTANT]
> Windows Server 2012 的新增内容是 –Source 参数，该参数用来定义可找到 Windows Server 2012 源媒体的位置。该媒体可以定义为 DVD 驱动器（例如，D:\Sources\Sxs）或已复制媒体文件的网络共享（例如，\\fileserver\windows2012\sources\Sxs）。


## 另请参阅

#### 概念

[Lync Server 2013 中前端池和 Standard Edition 服务器的 IIS 要求](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)

