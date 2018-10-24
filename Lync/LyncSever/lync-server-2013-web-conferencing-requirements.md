---
title: Web 会议要求
TOCTitle: Web 会议要求
ms:assetid: 125f847c-58ab-450f-ae43-41219fd38477
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ619171(v=OCS.15)
ms:contentKeyID: 49312060
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Web 会议要求

 

_**上一次修改主题：** 2016-12-08_

如果您已选择启用 Web 会议，则需计划以下事项：

   访问文件存储，文件存储用于存储 Web 会议内容。

   与 Office Web Apps Server 集成，这是在会议期间共享 PowerPoint 文件所必需的。

## 文件存储

Lync Server 2013 Web 会议服务在文件存储中存储会议期间共享的内容。在部署过程中，必须指定要用作 标准版 服务器或 企业版前端池的文件存储的文件共享。可将现有的文件共享用于文件存储，或通过指定文件共享所在的文件服务器的完全限定域名 (FQDN) 以及新文件共享的文件夹名称来指定新文件共享。有关详细信息，请参阅“拓扑生成器 - 为前端定义文件存储”。Web 会议服务在将内容存储在文件存储中之前，会对该内容加密。

Lync Server 2013 支持在直接附加存储 (DAS) 或存储区域网络 (SAN)（包括分布式文件系统 (DFS)）以及文件存储的独立磁盘冗余阵列 (RAID) 上使用文件共享。在 Lync Server 部署向导已定义文件共享的位置后，Lync Server 会在该文件共享内创建一个类似如下的文件夹结构：

  - 1-ApplicationServer-1

  - 1-CentralMgmt-1

  - 1-WebServices-1
    
      - CollabContent
    
      - CollabMetadata
    
      - DataConf

然后，Web 会议服务在位于 WebServices 文件夹中的 CollabContent 和 CollabMetadata 文件夹中存储诸如 PowerPoint 幻灯片、白板、投票表决和附件之类的内容。

管理员必须设置对文件共享的权限，以使 RTC 组拥有必要的读和写访问权限。

> [!WARNING]
> 如果遇到与权限有关的任何错误，请打开拓扑生成器，下载并重新发布现有拓扑。发布拓扑将验证文件共享权限并在需要时重置这些权限。


可以使用以下设置管理如何存储会议内容：

  - **ContentGracePeriod**，位于 [Set-CsConferencingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsConferencingConfiguration) 中，设置 Web 会议内容在会议结束后将在服务器中保留的时间。

  - **MaxContentStorageMb**，位于 [Set-CsConferencingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsConferencingConfiguration) 中，设置在单个会议期间允许用于存储内容的最大文件空间量。

**MaxUploadFileSizeMb** 不限制用于 Lync Web App 的文件上载设置。Lync Web App 的文件大小上载限制设置为大约 30MB，并由以下 IIS web.config 文件控制：/DataCollabWeb/Int\[Ext\]/Handler/web.config。若要配置用于 Lync Web App 的文件大小上载限制，请更新 web.config 文件中的 `maxRequestLength` 和 `maxAllowedContentLength`，如下所示。

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

必须为每个前端服务器更新 web.config 文件。

## Office Web Apps Server

为了使用这些新功能，管理员必须安装 Office Web Apps Server 并且必须配置 Lync Server 2013 以与 Office Web Apps Server 通信。本文档提供了有关如何配置 Lync Server 2013 以与 Office Web Apps Server 结合使用的信息。本文档不提供有关如何安装 Office Web Apps Server 的信息。有关安装详细信息，请参阅位于 <http://go.microsoft.com/fwlink/?linkid=257525> 的 Microsoft Office Web Apps 部署网站。该指南包括用于 Office Web Apps Server 的完整的必备条件信息。请注意，应将 Office Web Apps Server 安装在未运行 Lync Server、SQL Server 或任何其他服务器应用程序的独立计算机上。（该计算机上不能安装任意版本的 Office。）用于运行 Office Web Apps Server 的任意计算机还必须安装一组特定软件（包括 .NET Framework 4.5 和 Windows PowerShell 3.0）。在位于 <http://go.microsoft.com/fwlink/?linkid=257525> 的 Microsoft Office Web Apps 部署网站中详细讨论了这些要求以及有关配置证书和 Internet Information Services (IIS) 的信息。

## 另请参阅

#### 概念

[Lync Server 2013 中的 Web 会议概述](lync-server-2013-web-conferencing-overview.md)  
[Web 会议的部署清单](lync-server-2013-deployment-checklist-for-web-conferencing.md)

