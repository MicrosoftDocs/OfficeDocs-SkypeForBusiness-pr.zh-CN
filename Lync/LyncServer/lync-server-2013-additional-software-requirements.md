---
title: Lync Server 2013：其他软件要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Additional software requirements
ms:assetid: 87b318e3-03ae-41f7-af5e-29bb294f6af0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398686(v=OCS.15)
ms:contentKeyID: 48184731
ms.date: 12/09/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2e21a375fecbd109e108806dc816a9fa3fce81a2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837921"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="additional-software-requirements-for-lync-server-2013"></a>Lync Server 2013 的其他软件要求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2016-12-08_

除了服务器平台的硬件和操作系统要求之外, Lync Server 2013 还需要在部署的服务器上安装其他软件。

<div>


> [!NOTE]  
> 有关运行 Lync Server 的服务器的平台要求的详细信息, 请参阅 Lync server <A href="lync-server-2013-server-hardware-platforms.md">2013 的服务器硬件平台</A>和<A href="lync-server-2013-server-and-tools-operating-system-support.md">lync server 2013 中的服务器和工具操作系统支持</A>。 有关客户端计算机和设备的系统要求的详细信息, 请参阅规划文档中<A href="lync-server-2013-planning-for-clients-and-devices.md">Lync Server 2013 中的客户端和设备规划</A>。 有关管理工具的软件要求的详细信息, 请参阅<A href="lync-server-2013-administrative-tools-software-requirements.md">Lync Server 2013 中的管理工具软件要求</A>。



</div>

<div>

## <a name="additional-software-necessary-for-all-internal-server-roles"></a>所有内部服务器角色所需的其他软件

本部分列出了所有内部服务器角色所必需的软件, 这些角色是除 Edge 服务器之外的所有 Lync Server 服务器角色。 有关 Edge 服务器和边缘池的要求将在本主题的 "**其他软件适用于边缘服务器**" 下列出。

</div>

<div>

## <a name="windows-powershell-30"></a>Windows PowerShell 3.0

运行 Lync Server 2013 的每台服务器必须安装正确版本的 Windows PowerShell 3.0。 有关详细信息, 请参阅[安装 Lync Server 2013 的 Windows PowerShell 3.0](lync-server-2013-installing-windows-powershell-3-0.md)。

</div>

<div>

## <a name="microsoft-net-framework-45"></a>Microsoft .NET Framework 4.5

Lync Server 要求 Microsoft .NET Framework 4.5 位于所有内部服务器角色和任何运行 Lync Server 管理工具或 Microsoft Lync Server 2013 的计算机上的 "规划工具"。 对于 Lync Server 2013, 必须先在服务器上手动安装64位版本的 Microsoft .NET Framework 4.5, 然后再安装 Lync Server 2013。 若要手动安装, 请从 Microsoft 下载中心下载 Microsoft .NET 4.5 Framework[https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)

<div>

## <a name="installing-microsoft-net-framework-45-on-servers-running-windows-server-2012"></a>在运行 Windows Server 2012 的服务器上安装 Microsoft .NET Framework 4。5

在将运行 Lync Server 2013 和 Windows Server 2012 的服务器上安装 Microsoft .NET Framework 4.5 时, 必须执行一个附加步骤。 安装 .NET Framework 4.5 后, 请使用服务器管理器安装 HTTP 激活。

**在 Windows Server 2012 上安装 .NET 4.5 HTTP 激活**

1.  从 "**开始**" 菜单中, 单击 "**程序**", 然后单击 "**管理工具**", 然后单击 "**服务器管理器**"。

2.  在服务器管理器中的 "**功能摘要**" 下, 选择 "**添加功能**"。

3.  展开 **.Net Framework 4.5**。

4.  选择 " **WCF 激活**" (如果尚未选中)。 然后选择 " **HTTP 激活**"。

5.  单击 "**下一步**" 并按照提示完成安装。

</div>

</div>

<div>

## <a name="windows-identity-foundation"></a>Windows Identity Foundation

Lync Server 2013 中的**Windows Identity foundation**需要安装 Windows identity foundation 才能支持服务器到服务器身份验证方案。 Windows Server 2008 R2 和 Windows Server 2012 需要不同的步骤来安装 Windows 识别基础。 从以下列表中选择服务器操作系统:

  - Windows server 2008 R2 For Windows Server 2008 R2, 请检查它是否已安装在你的计算机上。 若要执行此操作, 请转到 "**添加/删除程序**"、"**查看已安装的更新**", 然后在**Windows**中查看 "输入**windows Identity Foundation (KB974405)**"。 有关安装 Windows Identity Foundation 的详细信息, [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657)请参阅。

  - Windows server 2012 For Windows Server 2012, 可使用**服务器管理器**安装 Windows Identity Foundation。 在服务器管理器 "**添加角色和功能" 向导**中, 选择 "**功能**"。 从列表中选择**Windows Identity Foundation 3.5** 。 单击 "**下一步**", 然后单击 "**安装**"。

</div>

<div>

## <a name="additional-software-for-all-front-end-servers-and-standard-edition-servers"></a>适用于所有前端服务器和标准版服务器的其他软件

所有前端服务器和标准版服务器还必须运行具有特定模块的 Internet 信息服务 (IIS)。 此外, 所有前端服务器和标准版服务器 (可在其中部署会议、呼叫驻留应用程序、公告或响应组) 都必须运行 Windows Media 格式运行时。

<div>

## <a name="internet-information-services-iis"></a>Internet Information Services (IIS)

前端服务器和标准版服务器必须运行 Internet 信息服务 (IIS), 其中包含以下模块:

  - 静态内容

  - 默认文档

  - HTTP 错误

  - ASP.NET

  - .NET 扩展性

  - Internet 服务器 API (ISAPI) 扩展

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

  - 匿名身份验证 (在安装 IIS 时默认安装。)

  - 客户端证书映射身份验证

</div>

<div>

## <a name="windows-media-format-runtime-and-windows-desktop-experience"></a>Windows Media 格式运行时和 Windows 桌面体验

**Windows 桌面体验**部署会议的所有前端服务器和标准版服务器都必须安装 Windows Media 格式运行时, 但 Windows 桌面体验中安装的 windows Server 2012 除外。 Windows Server 2012 需要 Microsoft Media Foundation。 若要运行 windows Media 音频 (.wma) 文件, 需要 Windows Media Format Runtime 才能运行通知和音乐的 "呼叫寄存"、"通知" 和 "响应" 组应用程序。

我们建议你在安装 Lync Server 2013 之前安装 Windows 桌面体验。 如果 Lync Server 2013 在服务器上找不到此软件, 它将提示您安装它, 然后必须重新启动服务器才能完成安装。

</div>

</div>

<div>

## <a name="additional-software-for-front-end-servers-and-standard-edition-servers-running-on-windows-server-2012"></a>在 Windows Server 2012 上运行的前端服务器和标准版服务器的附加软件

前端服务器需要安装 .NET 3.5, 默认情况下不会在 Windows Server 2012 上安装。 若要安装, 请将 Windows Server 2012 安装媒体置于驱动器 D 中, 然后键入以下内容:

    Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client, BITS -Source D:\sources\sxs

有关在运行 Windows Server 2012 的服务器上安装 .NET 3.5 的详细信息, 请参阅 "Microsoft .NET Framework 3.5 <https://go.microsoft.com/fwlink/p/?linkid=275032>部署注意事项"。

</div>

<div>

## <a name="additional-software-for-directors"></a>适用于董事的其他软件

Director 必须运行 Internet Information Services (IIS), 其中包含以下模块:

  - 静态内容

  - 默认文档

  - HTTP 错误

  - ASP.NET

  - .NET 扩展性

  - Internet 服务器 API (ISAPI) 扩展

  - ISAPI 筛选器

  - HTTP 日志记录

  - 日志记录工具

  - 跟踪

  - Windows 身份验证

  - 请求筛选

  - 静态内容压缩

  - IIS 管理控制台

  - IIS 管理脚本和工具

  - 匿名身份验证 (在安装 IIS 时默认安装。)

  - 客户端证书映射身份验证

</div>

<div>

## <a name="additional-software-for-persistent-chat-front-end-servers"></a>适用于持久聊天前端服务器的其他软件

持久聊天前端服务器必须运行消息队列 (也称为 MSMQ), 它是 Windows Server 的一个组件。

有关启用 MSMQ 的信息, 请[单击此处。](https://technet.microsoft.com/en-us/library/cc771474.aspx)

</div>

<div>

## <a name="additional-software-for-edge-servers"></a>适用于边缘服务器的其他软件

边缘服务器需要以下软件:

  - 运行 Lync Server 2013 的每台服务器必须安装正确版本的 Windows PowerShell 3.0。 有关详细信息, 请参阅[安装 Lync Server 2013 的 Windows PowerShell 3.0](lync-server-2013-installing-windows-powershell-3-0.md)。

  - Lync 服务器需要 Microsoft .NET Framework 4.5。 对于安装在 Windows Server 2008 R2 上的 Lync Server 2013, 必须在安装 Lync Server 2013 之前在服务器上手动安装64位版本的 Microsoft .NET Framework 4.5。 若要手动安装, 请从 Microsoft 下载中心下载 Microsoft .NET 4.5 Framework[https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)

  - Lync Server 2013 中的**Windows Identity foundation**需要安装 Windows identity foundation 才能支持服务器到服务器身份验证方案。 Windows Server 2008 R2 和 Windows Server 2012 需要不同的步骤来安装 Windows 识别基础。 从以下列表中选择服务器操作系统:
    
      - Windows server 2008 R2 For Windows Server 2008 R2, 请检查它是否已安装在你的计算机上。 若要执行此操作, 请转到 "**添加/删除程序**"、"**查看已安装的更新**", 然后在**Windows**中查看 "输入**windows Identity Foundation (KB974405)**"。 有关安装 Windows Identity Foundation 的详细信息, [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657)请参阅。
    
      - Windows server 2012 For Windows Server 2012, 可使用**服务器管理器**安装 Windows Identity Foundation。 在服务器管理器 "**添加角色和功能" 向导**中, 选择 "**功能**"。 从列表中选择**Windows Identity Foundation 3.5** 。 单击 "**下一步**", 然后单击 "**安装**"。

</div>

<div>

## <a name="do-not-install-layered-socket-providers-on-media-servers"></a>不要在媒体服务器上安装分层套接字提供程序

不要在任何前端服务器或独立的中介服务器上安装任何 Microsoft Internet 安全和加速 (ISA) 服务器客户端软件或任何其他 Winsock 分层服务提供程序 (LSP) 软件。 安装此软件可能会导致媒体流量较差。

</div>

<div>

## <a name="see-also"></a>另请参阅


[Lync Server 2013 中的管理工具软件要求](lync-server-2013-administrative-tools-software-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

