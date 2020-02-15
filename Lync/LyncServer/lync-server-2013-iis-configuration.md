---
title: Lync Server 2013： IIS 配置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IIS configuration
ms:assetid: b458babf-bf64-43f0-8a8e-612f5096b63c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412871(v=OCS.15)
ms:contentKeyID: 48185169
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65d9d4f61fabdca7a3f9cb4808efe952ec7ce3b2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037874"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="iis-configuration-in-lync-server-2013"></a>Lync Server 2013 中的 IIS 配置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-02-17_

若要成功完成此过程，您应至少以本地管理员和域用户的身份登录到服务器。

在为 Lync Server 2013、Standard Edition 或第一台前端服务器配置和安装前端服务器之前，请为 Internet Information Services （IIS）安装和配置服务器角色和 Web 服务。

<div class=" ">


> [!IMPORTANT]  
> 如果您的组织要求在除系统驱动器之外的驱动器上查找 IIS 和所有 Web 服务，则在最初安装 Lync Server 2013 时，可以在 "安装程序" 对话框中更改 Lync Server 2013 文件的安装位置路径。管理工具。 安装 IIS 之前安装管理工具。 如果将安装文件安装到此路径（包括 OCSCore），则其余的 Lync Server 2013 文件也将部署到此驱动器。 有关 dtails，请参阅<A href="lync-server-2013-install-lync-server-administrative-tools.md">Install Lync Server 2013 管理工具</A>。 有关如何在安装 IIS 时重新定位由 Windows Server Manager 部署的 INETPUB 的详细信息<A href="http://go.microsoft.com/fwlink/p/?linkid=216888">http://go.microsoft.com/fwlink/p/?linkId=216888</A>，请参阅。



</div>

下表指示必需的 IIS 7.5 角色服务。

### <a name="iis-75-role-services"></a>IIS 7.5 角色服务

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
<td><p>已安装常见 HTTP 功能</p></td>
<td><p>静态内容</p></td>
</tr>
<tr class="even">
<td><p>已安装常见 HTTP 功能</p></td>
<td><p>默认文档</p></td>
</tr>
<tr class="odd">
<td><p>已安装常见 HTTP 功能</p></td>
<td><p>HTTP 错误</p></td>
</tr>
<tr class="even">
<td><p>应用程序开发</p></td>
<td><p>ASP.NET</p>
<p>Windows Server 2012 还需要安装 ASP. NET 4。5</p></td>
</tr>
<tr class="odd">
<td><p>应用程序开发</p></td>
<td><p>.NET 扩展性</p></td>
</tr>
<tr class="even">
<td><p>应用程序开发</p></td>
<td><p>Internet Server API （ISAPI）扩展</p></td>
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
<td><p>追踪</p></td>
</tr>
<tr class="odd">
<td><p>安全性</p></td>
<td><p>匿名身份验证（默认情况下已安装并启用）</p></td>
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


在 Windows Server 2008 R2 SP1 x64 操作系统上，您可以使用 Windows PowerShell 2.0。 必须先导入 ServerManager 模块，然后再安装 IIS 7.5 角色和角色服务。

   ```PowerShell
    Import-Module ServerManager
   ```

   ```PowerShell
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Scripting-Tools, Web-Windows-Auth, Web-Asp-Net, Web-Log-Libraries, Web-Http-Tracing, Web-Stat-Compression, Web-Dyn-Compression, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Errors, Web-Http-Logging, Web-Net-Ext, Web-Client-Auth, Web-Filtering, Web-Mgmt-Console
   ```

<div class=" ">


> [!NOTE]  
> 默认情况下，将使用 IIS 服务器角色安装匿名身份验证。 您可以在安装 IIS 之后管理匿名身份验证。 有关详细信息，请参阅处<A href="http://go.microsoft.com/fwlink/p/?linkid=203935">http://go.microsoft.com/fwlink/p/?linkId=203935</A>的 "启用匿名身份验证（IIS 7）"。



</div>

下表指示 Windows Server 2012 和 Windows Server 2012 R2 所需的 IIS 8.0 和 IIS 8.5 角色服务。

<div class=" ">


> [!NOTE]  
> 对于 Windows Server 2012 和 Windows Server 2012 R2，已将 add-windowsfeature cmdlet 替换为 Install cmdlet。 有关详细信息，请参阅<A href="http://go.microsoft.com/fwlink/p/?linkid=392274">Install-add-windowsfeature</A>。



</div>

### <a name="iis-80-and-iis-85-role-services"></a>IIS 8.0 和 IIS 8.5 角色服务

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
<td><p>追踪</p></td>
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
<td><p>.Net 扩展性3。5</p></td>
</tr>
<tr class="even">
<td><p>应用程序开发</p></td>
<td><p>.Net 扩展性4。5</p></td>
</tr>
<tr class="odd">
<td><p>应用程序开发</p></td>
<td><p>ASP.Net 3。5</p></td>
</tr>
<tr class="even">
<td><p>应用程序开发</p></td>
<td><p>ASP.Net 4。5</p></td>
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
<td><p>服务器端包括</p></td>
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
<td><p>.Net Framework 4。5</p></td>
</tr>
<tr class="odd">
<td><p>.Net 4.5 Framework 功能</p></td>
<td><p>ASP.Net 4。5</p></td>
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
<td><p>服务器图形命令行管理程序</p></td>
</tr>
<tr class="even">
<td><p>Windows Identity Foundation 3。5</p></td>
<td><p>Windows Identity Foundation 3。5</p></td>
</tr>
<tr class="odd">
<td><p>Windows Process Activation Service</p></td>
<td><p>进程模型</p></td>
</tr>
<tr class="even">
<td><p>Windows Process Activation Service</p></td>
<td><p>配置 Api</p></td>
</tr>
</tbody>
</table>


在 Windows Server 2012 和 Windows Server 2012 R2 中，可以使用 Windows PowerShell 3.0 安装 IIS 要求。 使用 Windows PowerShell 3.0 中的 ServerManager 模块，请键入：

   ```PowerShell
    Import-Module ServerManager
   ```

   ```PowerShell
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-Framework-45-Core, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Console, Web-Mgmt-Compat, Windows-Identity-Foundation, Server-Media-Foundation, BITS -Source D:\sources\sxs
   ```

<div class=" ">


> [!IMPORTANT]  
> Windows Server 2012 的新版本是用于定义可在何处找到 Windows Server 2012 源媒体的– Source 参数。 可以将媒体定义为 DVD 驱动器（例如，D:\Sources\Sxs），也可以定义为网络共享媒体文件已复制（例如， \\fileserver\windows2012\sources\Sxs）。



</div>

<div>

## <a name="see-also"></a>另请参阅


[Lync Server 2013 中的前端池和 Standard Edition 服务器的 IIS 要求](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

