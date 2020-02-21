---
title: Lync Server 2013：其他软件要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Additional software requirements
ms:assetid: 87b318e3-03ae-41f7-af5e-29bb294f6af0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398686(v=OCS.15)
ms:contentKeyID: 48184731
ms.date: 12/09/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4565f91afeb703de967040edb8f6d437aedac9eb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196395"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="additional-software-requirements-for-lync-server-2013"></a>Lync Server 2013 的其他软件要求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2016-12-08_

除了服务器平台的硬件和操作系统要求之外，Lync Server 2013 还需要在部署的服务器上安装其他软件。

<div>


> [!NOTE]  
> 若要详细了解运行 Lync Server 的服务器的平台要求，请参阅 lync server 2013 中的 Lync Server 2013 和<A href="lync-server-2013-server-and-tools-operating-system-support.md">服务器和工具操作系统支持</A>的<A href="lync-server-2013-server-hardware-platforms.md">服务器硬件平台</A>。 有关客户端计算机和设备的系统要求的详细信息，请参阅规划文档中的在<A href="lync-server-2013-planning-for-clients-and-devices.md">Lync Server 2013 中规划客户端和设备</A>。 有关管理工具的软件要求的详细信息，请参阅<A href="lync-server-2013-administrative-tools-software-requirements.md">Lync Server 2013 中的管理工具软件要求</A>。



</div>

<div>

## <a name="additional-software-necessary-for-all-internal-server-roles"></a>所有内部服务器角色所需的其他软件

本节列出了所有内部服务器角色必需的软件，这些角色是除边缘服务器之外的所有 Lync Server 服务器角色。 边缘服务器和边缘池的要求在本主题后面的**其他软件的边缘服务器**下列出。

</div>

<div>

## <a name="windows-powershell-30"></a>Windows PowerShell 3.0

每台运行 Lync Server 2013 的服务器必须安装正确版本的 Windows PowerShell 3.0。 有关详细信息，请参阅[安装适用于 Lync Server 2013 的 Windows PowerShell 3.0](lync-server-2013-installing-windows-powershell-3-0.md)。

</div>

<div>

## <a name="microsoft-net-framework-45"></a>Microsoft .NET Framework 4.5

Lync Server 需要 Microsoft .NET Framework 4.5 在所有内部服务器角色上和运行 Lync Server 管理工具或 Microsoft Lync Server 2013 的任何计算机上，规划工具。 对于 Lync Server 2013，在安装 Lync Server 2013 之前，必须在服务器上手动安装64位版本的 Microsoft .NET Framework 4.5。 若要手动安装它，请从 Microsoft 下载中心下载 Microsoft .NET 4.5 Framework[https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)

<div>

## <a name="installing-microsoft-net-framework-45-on-servers-running-windows-server-2012"></a>在运行 Windows Server 2012 的服务器上安装 Microsoft .NET Framework 4。5

当您在将运行 Lync Server 2013 和 Windows Server 2012 的服务器上安装 Microsoft .NET Framework 4.5 时，您必须执行一个额外的步骤。 安装 .NET Framework 4.5 后，请使用服务器管理器安装 HTTP 激活。

**在 Windows Server 2012 上安装 .NET 4.5 HTTP 激活**

1.  从 "**开始**" 菜单中，单击 "**程序**"，再单击 "**管理工具**"，然后单击 "**服务器管理器**"。

2.  在服务器管理器中的 "**功能摘要**" 下，选择 "**添加功能**"。

3.  展开 **.Net Framework 4.5**。

4.  选择 " **WCF 激活**" （如果尚未选中）。 然后选择 " **HTTP 激活**"。

5.  单击 "**下一步**" 并按照提示完成安装。

</div>

</div>

<div>

## <a name="windows-identity-foundation"></a>Windows Identity Foundation

Lync Server 2013 中的**Windows Identity foundation**要求安装 Windows identity foundation，以便支持服务器到服务器身份验证方案。 Windows Server 2008 R2 和 Windows Server 2012 需要不同的过程来安装 Windows 识别基础。 从以下列表中选择您的服务器操作系统：

  - Windows server 2008 R2 For Windows Server 2008 R2，请检查是否已在您的计算机上安装了它。 若要执行此操作，请转到 "**添加/删除程序**"，**查看已安装的更新**，并查看**Windows** for THE entry **windows Identity Foundation （KB974405）**。 有关安装 Windows Identity Foundation 的详细信息， [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657)请参阅。

  - Windows Server 2012 For Windows Server 2012，可使用**服务器管理器**安装 Windows Identity Foundation。 在服务器管理器 "**添加角色和功能" 向导**中，选择 "**功能**"。 从列表中选择 " **Windows Identity Foundation 3.5** "。 单击 "**下一步**"，然后单击 "**安装**"。

</div>

<div>

## <a name="additional-software-for-all-front-end-servers-and-standard-edition-servers"></a>适用于所有前端服务器和 Standard Edition 服务器的其他软件

所有前端服务器和 Standard Edition 服务器还必须运行具有特定模块的 Internet 信息服务（IIS）。 此外，部署了会议、呼叫寄存应用程序、公告或响应组的所有前端服务器和 Standard Edition 服务器都必须运行 Windows Media Format Runtime。

<div>

## <a name="internet-information-services-iis"></a>Internet Information Services (IIS)

前端服务器和 Standard Edition 服务器必须运行 Internet Information Services （IIS），其中包含以下模块：

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

  - 匿名身份验证（安装 IIS 时，默认情况下会安装此身份验证。）

  - 客户端证书映射身份验证

</div>

<div>

## <a name="windows-media-format-runtime-and-windows-desktop-experience"></a>Windows Media Format Runtime 和 Windows 桌面体验

**Windows 桌面体验**将部署会议的所有前端服务器和 Standard Edition 服务器必须安装 Windows Media Format Runtime，除了 Windows Server 2012 安装在 Windows 桌面体验中之外。 Windows Server 2012 需要 Microsoft Media Foundation。 Windows Media Format Runtime 是运行呼叫寄存、通知和响应组应用程序播放通知和音乐时使用的 Windows Media 音频 (.wma) 文件所必需的软件。

建议您在安装 Lync Server 2013 之前安装 Windows 桌面体验。 如果 Lync Server 2013 在服务器上找不到此软件，它将提示您安装它，然后您必须重新启动服务器才能完成安装。

</div>

</div>

<div>

## <a name="additional-software-for-front-end-servers-and-standard-edition-servers-running-on-windows-server-2012"></a>在 Windows Server 2012 上运行的前端服务器和 Standard Edition 服务器的其他软件

前端服务器要求安装 .NET 3.5，这在 Windows Server 2012 中默认不会安装。 若要安装它，请将 Windows Server 2012 安装介质放在驱动器 D 中，并键入以下命令：

    Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client, BITS -Source D:\sources\sxs

有关在运行 Windows Server 2012 的服务器上安装 .NET 3.5 的详细信息，请参阅在<https://go.microsoft.com/fwlink/p/?linkid=275032>上的 "Microsoft .net Framework 3.5 部署注意事项"。

</div>

<div>

## <a name="additional-software-for-directors"></a>控制器的其他软件

控制器必须运行 Internet Information Services （IIS），其中包含以下模块：

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

  - IIS 管理控制台

  - IIS 管理脚本和工具

  - 匿名身份验证（安装 IIS 时默认安装。）

  - 客户端证书映射身份验证

</div>

<div>

## <a name="additional-software-for-persistent-chat-front-end-servers"></a>持久聊天前端服务器的其他软件

持久聊天前端服务器必须运行消息队列（也称为 MSMQ），这是 Windows Server 的组件。

若要了解如何启用 MSMQ，请[单击此处。](https://technet.microsoft.com/library/cc771474.aspx)

</div>

<div>

## <a name="additional-software-for-edge-servers"></a>其他适用于边缘服务器的软件

边缘服务器需要以下软件：

  - 每台运行 Lync Server 2013 的服务器必须安装正确版本的 Windows PowerShell 3.0。 有关详细信息，请参阅[安装适用于 Lync Server 2013 的 Windows PowerShell 3.0](lync-server-2013-installing-windows-powershell-3-0.md)。

  - Lync Server 要求安装 Microsoft .NET Framework 4.5。 对于安装在 Windows Server 2008 R2 上的 Lync Server 2013，必须先在服务器上手动安装64位版本的 Microsoft .NET Framework 4.5，然后再安装 Lync Server 2013。 若要手动安装它，请从 Microsoft 下载中心下载 Microsoft .NET 4.5 Framework[https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)

  - Lync Server 2013 中的**Windows Identity foundation**要求安装 Windows identity foundation，以便支持服务器到服务器身份验证方案。 Windows Server 2008 R2 和 Windows Server 2012 需要不同的过程来安装 Windows 识别基础。 从以下列表中选择您的服务器操作系统：
    
      - Windows server 2008 R2 For Windows Server 2008 R2，请检查是否已在您的计算机上安装了它。 若要执行此操作，请转到 "**添加/删除程序**"，**查看已安装的更新**，并查看**Windows** for THE entry **windows Identity Foundation （KB974405）**。 有关安装 Windows Identity Foundation 的详细信息， [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657)请参阅。
    
      - Windows Server 2012 For Windows Server 2012，可使用**服务器管理器**安装 Windows Identity Foundation。 在服务器管理器 "**添加角色和功能" 向导**中，选择 "**功能**"。 从列表中选择 " **Windows Identity Foundation 3.5** "。 单击 "**下一步**"，然后单击 "**安装**"。

</div>

<div>

## <a name="do-not-install-layered-socket-providers-on-media-servers"></a>不要在媒体服务器上安装分层套接字提供程序

请勿在任何前端服务器或独立中介服务器上安装任何 Microsoft Internet 安全性和加速（ISA）服务器客户端软件或任何其他 Winsock 分层服务提供程序（LSP）软件。 安装此软件可能会导致媒体流量下降。

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

