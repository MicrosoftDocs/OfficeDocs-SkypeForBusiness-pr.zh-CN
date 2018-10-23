---
title: Lync Server 2013：其他软件要求
TOCTitle: 其他软件要求
ms:assetid: 87b318e3-03ae-41f7-af5e-29bb294f6af0
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398686(v=OCS.15)
ms:contentKeyID: 49313505
ms.date: 07/21/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 的其他软件要求

 

_**上一次修改主题：** 2016-12-08_

除了服务器平台的硬件和操作系统要求外， Lync Server 2013 还要求在部署的服务器上安装其他软件。

> [!NOTE]  
> 有关运行 Lync Server 的服务器的平台要求的详细信息，请参阅 <a href="lync-server-2013-server-hardware-platforms.md">适用于 Lync Server 2013 的服务器硬件平台</a>和 <a href="lync-server-2013-server-and-tools-operating-system-support.md">Lync Server 2013 中的服务器和工具操作系统支持</a>。有关客户端计算机和设备的系统要求的详细信息，请参阅规划文档中的 <a href="lync-server-2013-planning-for-clients-and-devices.md">规划 Lync Server 2013 中的客户端和设备</a>。有关管理工具的软件要求的详细信息，请参阅 <a href="lync-server-2013-administrative-tools-software-requirements.md">Lync Server 2013 中的管理工具软件要求</a>。



## 所有内部服务器角色所需的其他软件

此部分列出所有内部服务器角色（除边缘服务器以外的所有 Lync Server 服务器角色）上必要的软件。在本主题后面的**边缘服务器所需的其他软件**下列出了边缘服务器和边缘池的要求。

## Windows PowerShell 3.0

每台运行 Lync Server 2013 的服务器上必须安装正确的版本 Windows PowerShell 3.0。有关详细信息，请参阅 [为 Lync Server 2013 安装 Windows PowerShell 3.0](lync-server-2013-installing-windows-powershell-3-0.md)。

## Microsoft .NET Framework 4.5

Lync Server 在所有内部服务器角色和您将运行 Lync Server 管理工具或 Microsoft Lync Server 2013 规划工具 的任何计算机上都需要 Microsoft .NET Framework 4.5。对于 Lync Server 2013，您必须先在服务器上手动安装 64 位版本的 Microsoft .NET Framework 4.5，然后才能安装 Lync Server 2013。若要手动安装，请从 Microsoft 下载中心下载 Microsoft .NET 4.5 Framework，网址为 [http://go.microsoft.com/fwlink/p/?LinkId=268529](http://go.microsoft.com/fwlink/p/?linkid=268529)

## 在运行 Windows Server 2012 的服务器上安装 Microsoft .NET Framework 4.5

在将运行 Lync Server 2013 和 Windows Server 2012 的服务器上安装 Microsoft .NET Framework 4.5 时，您必须执行一个额外步骤。安装 .NET Framework 4.5 之后，请使用服务器管理器安装 HTTP 激活。

**在 Windows Server 2012 上安装 .NET 4.5 HTTP 激活**

1.  从“开始”菜单中，依次单击“程序”、“管理工具”和“服务器管理器”。

2.  在服务器管理器的“功能摘要”下，选择“添加功能”。

3.  展开“.NET Framework 4.5”。

4.  选择“WCF 激活”（如果尚未选择它）。然后选择“HTTP 激活”。

5.  单击“下一步”，然后按照提示完成安装。

## Windows Identity Foundation

Lync Server 2013 中的 **Windows Identity Foundation** 要求安装 Windows Identity Foundation，以便支持服务器到服务器身份验证方案。 Windows Server 2008 R2 和 Windows Server 2012 需要不同的 Windows Identify Foundation 安装过程。请从以下列表中选择您的服务器操作系统：

  - Windows Server 2008 R2   对于 Windows Server 2008 R2，检查它是否已安装在您的计算机上。为此，请转至“添加/删除程序”，“查看已安装的更新”，检查“Windows”下有无“Windows Identity Foundation (KB974405)”条目。有关安装 Windows Identity Foundation 的详细信息，请参阅 [http://go.microsoft.com/fwlink/p/?linkId=204657](http://go.microsoft.com/fwlink/p/?linkid=204657)。

  - Windows Server 2012   对于 Windows Server 2012，请使用“服务器管理器”安装 Windows Identity Foundation。在服务器管理器的“添加角色和功能向导”中，选择“功能”。从列表中选择“Windows Identity Foundation 3.5”。单击“下一步”，然后单击“安装”。

## 所有前端服务器和 Standard Edition Server 的其他软件

所有前端服务器和 Standard Edition Server 还必须运行 Internet Information Services (IIS) 的某些模块。此外，要部署会议、 呼叫寄存应用程序、通知或响应组的所有前端服务器和 Standard Edition Server 必须运行 Windows Media Format Runtime。

## Internet 信息服务 (IIS)

前端服务器和 Standard Edition Server 必须运行 Internet Information Services (IIS) 的以下模块：

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

  - 匿名身份验证（安装 IIS 时默认安装。）

  - 客户端证书映射身份验证

## Windows Media Format Runtime 和 Windows 桌面体验

**Windows 桌面体验** 要部署会议的所有前端服务器和 Standard Edition Server 必须安装 Windows Media Format Runtime，这对于将 Windows Server 2012 作为 Windows 桌面体验的一部分进行安装例外。 Windows Server 2012 需要 Microsoft Media Foundation。Windows Media Format Runtime 是运行 呼叫寄存、通知和响应组应用程序播放通知和音乐时使用的 Windows Media 音频 (.wma) 文件所必需的软件。

建议在安装 Lync Server 2013 之前先安装 Windows 桌面体验。如果 Lync Server 2013 在服务器上找不到此软件，它将提示您安装它，然后您必须重新启动服务器才能完成安装。

## 运行 Windows Server 2012 的前端服务器和 Standard Edition Server 的其他软件

前端服务器需要 .NET 3.5，后者在默认情况下不会安装在 Windows Server 2012 上。若要安装，请将您的 Windows Server 2012 安装媒体放在驱动器 D 中，然后键入以下命令：

    Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client, BITS -Source D:\sources\sxs

有关在运行 Windows Server 2012 的服务器上安装 .NET 3.5 的详细信息，请参阅 <http://go.microsoft.com/fwlink/?linkid=275032> 上的“Microsoft .NET Framework 3.5 部署注意事项”。

## 控制器的其他软件

控制器必须运行 Internet Information Services (IIS) 的以下模块：

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

  - IIS 管理控制台

  - IIS 管理脚本和工具

  - 匿名身份验证（安装 IIS 时默认安装。）

  - 客户端证书映射身份验证

## 持久聊天前端服务器的其他软件

持久聊天前端服务器必须运行消息队列（也称为“MSMQ”），后者是 Windows Server 的一个组件。

有关启用 MSMQ 的信息，[请单击此处。](http://technet.microsoft.com/en-us/library/cc771474.aspx)

## 边缘服务器所需的其他软件

边缘服务器需要以下软件：

  - 每台运行 Lync Server 2013 的服务器上必须安装正确的版本 Windows PowerShell 3.0。有关详细信息，请参阅 [为 Lync Server 2013 安装 Windows PowerShell 3.0](lync-server-2013-installing-windows-powershell-3-0.md)。

  - Lync Server 需要 Microsoft .NET Framework 4.5。要在 Windows Server 2008 R2 上安装 Lync Server 2013，您必须先在该服务器上手动安装 64 位版本的 Microsoft .NET Framework 4.5，然后才能安装 Lync Server 2013。若要手动安装，请从 Microsoft 下载中心下载 Microsoft .NET 4.5 Framework，网址为 <http://go.microsoft.com/fwlink/?linkid=268529>

  - Lync Server 2013 中的 **Windows Identity Foundation** 要求安装 Windows Identity Foundation，以便支持服务器到服务器身份验证方案。 Windows Server 2008 R2 和 Windows Server 2012 需要不同的 Windows Identify Foundation 安装过程。请从以下列表中选择您的服务器操作系统：
    
      - Windows Server 2008 R2   对于 Windows Server 2008 R2，检查它是否已安装在您的计算机上。为此，请转至“添加/删除程序”，“查看已安装的更新”，检查“Windows”下有无“Windows Identity Foundation (KB974405)”条目。有关安装 Windows Identity Foundation 的详细信息，请参阅 [http://go.microsoft.com/fwlink/p/?linkId=204657](http://go.microsoft.com/fwlink/p/?linkid=204657)。
    
      - Windows Server 2012   对于 Windows Server 2012，请使用“服务器管理器”安装 Windows Identity Foundation。在服务器管理器的“添加角色和功能向导”中，选择“功能”。从列表中选择“Windows Identity Foundation 3.5”。单击“下一步”，然后单击“安装”。

## 不要在媒体服务器上安装分层套接字提供程序

请不要在任何前端服务器或独立中介服务器上安装任何 Microsoft Internet Security and Acceleration (ISA) 服务器 客户端软件，或其他任何 Winsock 分层服务提供程序 (LSP) 软件。安装此软件可能导致媒体流量性能下降。

## 另请参阅

#### 概念

[Lync Server 2013 中的管理工具软件要求](lync-server-2013-administrative-tools-software-requirements.md)

