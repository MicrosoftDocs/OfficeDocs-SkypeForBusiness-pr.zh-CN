---
title: Lync Server 2013： Web 会议要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Web conferencing requirements
ms:assetid: 125f847c-58ab-450f-ae43-41219fd38477
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619171(v=OCS.15)
ms:contentKeyID: 49733559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 56a030329f9d69a3748b2b76179c7a783b13cb0f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42210975"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="web-conferencing-requirements-in-lync-server-2013"></a>Lync Server 2013 中的 Web 会议要求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-01-30_

如果您已选择启用 Web 会议，则需计划以下事项：

  - <span></span>  
    访问文件存储，文件存储用于存储 Web 会议内容。

  - <span></span>  
    与 Office Web Apps Server 集成，这是在会议期间共享 PowerPoint 文件所必需的。

<div>

## <a name="file-store"></a>文件存储

Lync Server 2013 web 会议服务在文件存储中存储会议期间共享的内容。 作为部署的一部分，您必须指定要用作 Standard Edition server 或 Enterprise Edition 前端池的文件存储的文件共享。 可以将现有的文件共享用作文件存储，也可以通过指定文件共享所在的文件服务器的完全限定域名 (FQDN) 和新文件共享的文件夹名称来指定新的文件共享。有关详细信息，请参阅拓扑生成器–为前端定义文件存储。 Web 会议服务在将内容存储在文件存储中之前对内容进行加密。

Lync Server 2013 支持在直接连接存储（DAS）或存储区域网络（SAN）上使用文件共享，包括分布式文件系统（DFS）和文件存储的独立磁盘冗余阵列（RAID）。 在 Lync Server 部署向导定义文件共享的位置之后，Lync Server 会在文件共享中创建一个类似于以下内容的文件夹结构：

  - 1-ApplicationServer-1

  - 1-CentralMgmt-1

  - 1-WebServices-1
    
      - CollabContent
    
      - CollabMetadata
    
      - DataConf

然后，Web 会议服务在位于 WebServices 文件夹中的 CollabContent 和 CollabMetadata 文件夹中存储诸如 PowerPoint 幻灯片、白板、投票表决和附件之类的内容。

管理员必须设置对文件共享的权限，以使 RTC 组拥有必要的读和写访问权限。

<div>


> [!WARNING]  
> 如果遇到与权限有关的任何错误，请打开拓扑生成器，下载并重新发布现有拓扑。发布拓扑将验证文件共享权限并在需要时重置这些权限。



</div>

可以使用以下设置管理如何存储会议内容：

  - **ContentGracePeriod**（位于[CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration)中）设置了会议结束后 web 会议内容将在服务器上保留多长时间。

  - **MaxContentStorageMb**（位于[CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration)中）设置了单个会议期间允许用于存储内容的最大文件空间量。

**MaxUploadFileSizeMb**不限制 Lync Web App 的文件上载设置。 将 Lync Web App 的文件大小上载限制设置为约30MB，由 IIS web.config 文件控制：/DataCollabWeb/Int\[Ext/Handler/web.config.\]若要配置 Lync Web App 的文件大小上载限制，请`maxRequestLength` `maxAllowedContentLength`在 web.config 文件中进行更新，如下所示。

    <system.web>
        <!-- 
            Since this handler is used to upload files to DMCU the request size (in kilobytes) 
            has to fit max allowed file size uploaded by Lync Web App client.
            The timeout has to reflect the min client bandwidth. Timeout of 600 secs 
            and 512 Kbits of *client* bandwidth would result into aproximately 30 Mbytes 
            for Lync Web App upload size limit.
        -->
          <httpRuntime maxRequestLength="500000" executionTimeout="600" />
    
    
    
                    <security>
                    <requestFiltering>
                               <requestLimits maxAllowedContentLength="524288000" />
                    </requestFiltering>
                    </security>

您必须为每台前端服务器更新 web.config 文件。

</div>

<div>

## <a name="office-web-apps-server"></a>Office Web Apps Server

为了使用这些新功能，管理员必须安装 Office Web Apps Server，并且必须配置 Lync Server 2013 以与 Office Web Apps Server 进行通信。 本文档提供了有关如何配置 Lync Server 2013 以与 Office Web Apps Server 配合使用的信息。 本文档不提供的内容是有关如何安装 Office Web Apps Server 的信息。 有关安装的详细信息，请参阅 Microsoft Office Web Apps 部署<https://go.microsoft.com/fwlink/p/?linkid=257525>网站。 该指南包括 Office Web Apps Server 的完整必备信息。 请注意，Office Web Apps Server 应安装在未运行 Lync Server、SQL Server 或任何其他服务器应用程序的独立计算机上。 （您不得在该计算机上安装任何版本的 Office。）用于运行 Office Web Apps Server 的任何计算机还必须安装一组特定的软件（包括 .NET Framework 4.5 和 Windows PowerShell 3.0）。 中的 Microsoft Office Web Apps 部署网站详细讨论了这些要求以及有关配置证书和 Internet 信息服务（IIS）的信息<https://go.microsoft.com/fwlink/p/?linkid=257525>。

</div>

<div>

## <a name="see-also"></a>另请参阅


[Lync Server 2013 中的 web 会议概述](lync-server-2013-web-conferencing-overview.md)  
[Lync Server 2013 中的 web 会议的部署清单](lync-server-2013-deployment-checklist-for-web-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

