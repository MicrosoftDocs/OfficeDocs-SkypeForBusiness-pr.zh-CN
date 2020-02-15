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
ms.openlocfilehash: 914fee9d2ddf0a7e6d6867879a197b55380d35c9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041271"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="web-conferencing-requirements-in-lync-server-2013"></a><span data-ttu-id="72e43-102">Lync Server 2013 中的 Web 会议要求</span><span class="sxs-lookup"><span data-stu-id="72e43-102">Web conferencing requirements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="72e43-103">_**上次修改的主题：** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="72e43-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="72e43-104">如果您已选择启用 Web 会议，则需计划以下事项：</span><span class="sxs-lookup"><span data-stu-id="72e43-104">If you have chosen to enable web conferencing, you need to plan for the following:</span></span>

  - <span></span>  
    <span data-ttu-id="72e43-105">访问文件存储，文件存储用于存储 Web 会议内容。</span><span class="sxs-lookup"><span data-stu-id="72e43-105">Access to the file store, which is used for storing web conferencing content.</span></span>

  - <span></span>  
    <span data-ttu-id="72e43-106">与 Office Web Apps Server 集成，这是在会议期间共享 PowerPoint 文件所必需的。</span><span class="sxs-lookup"><span data-stu-id="72e43-106">Integration with Office Web Apps Server, which is necessary in order to share PowerPoint files during a conference.</span></span>

<div>

## <a name="file-store"></a><span data-ttu-id="72e43-107">文件存储</span><span class="sxs-lookup"><span data-stu-id="72e43-107">File Store</span></span>

<span data-ttu-id="72e43-108">Lync Server 2013 web 会议服务在文件存储中存储会议期间共享的内容。</span><span class="sxs-lookup"><span data-stu-id="72e43-108">The Lync Server 2013 web conferencing service stores content shared during meetings in the file store.</span></span> <span data-ttu-id="72e43-109">作为部署的一部分，您必须指定要用作 Standard Edition server 或 Enterprise Edition 前端池的文件存储的文件共享。</span><span class="sxs-lookup"><span data-stu-id="72e43-109">As part of deployment, you must specify a file share to be used as the file store for the either Standard Edition server or Enterprise Edition Front End pool.</span></span> <span data-ttu-id="72e43-110">可以将现有的文件共享用作文件存储，也可以通过指定文件共享所在的文件服务器的完全限定域名 (FQDN) 和新文件共享的文件夹名称来指定新的文件共享。</span><span class="sxs-lookup"><span data-stu-id="72e43-110">You can use an existing file share for the file store or you can specify a new file share by specifying the fully qualified domain name (FQDN) of the file server on which the file share is to be located and a folder name for the new file share.</span></span><span data-ttu-id="72e43-111">有关详细信息，请参阅拓扑生成器–为前端定义文件存储。</span><span class="sxs-lookup"><span data-stu-id="72e43-111">  For more information, see Topology Builder – Define the File Store for the Front End.</span></span> <span data-ttu-id="72e43-112">Web 会议服务在将内容存储在文件存储中之前对内容进行加密。</span><span class="sxs-lookup"><span data-stu-id="72e43-112">The web conferencing service encrypts the content before it stores the content in the file store.</span></span>

<span data-ttu-id="72e43-113">Lync Server 2013 支持在直接连接存储（DAS）或存储区域网络（SAN）上使用文件共享，包括分布式文件系统（DFS）和文件存储的独立磁盘冗余阵列（RAID）。</span><span class="sxs-lookup"><span data-stu-id="72e43-113">Lync Server 2013 supports using file shares on either direct attached storage (DAS) or a storage area network (SAN), including Distributed File System (DFS) and on a redundant array of independent disks (RAID) for file stores.</span></span> <span data-ttu-id="72e43-114">在 Lync Server 部署向导定义文件共享的位置之后，Lync Server 会在文件共享中创建一个类似于以下内容的文件夹结构：</span><span class="sxs-lookup"><span data-stu-id="72e43-114">After the Lync Server Deployment Wizard has defined the location of the file share, Lync Server creates a folder structure within the file share similar to:</span></span>

  - <span data-ttu-id="72e43-115">1-ApplicationServer-1</span><span class="sxs-lookup"><span data-stu-id="72e43-115">1-ApplicationServer-1</span></span>

  - <span data-ttu-id="72e43-116">1-CentralMgmt-1</span><span class="sxs-lookup"><span data-stu-id="72e43-116">1-CentralMgmt-1</span></span>

  - <span data-ttu-id="72e43-117">1-WebServices-1</span><span class="sxs-lookup"><span data-stu-id="72e43-117">1-WebServices-1</span></span>
    
      - <span data-ttu-id="72e43-118">CollabContent</span><span class="sxs-lookup"><span data-stu-id="72e43-118">CollabContent</span></span>
    
      - <span data-ttu-id="72e43-119">CollabMetadata</span><span class="sxs-lookup"><span data-stu-id="72e43-119">CollabMetadata</span></span>
    
      - <span data-ttu-id="72e43-120">DataConf</span><span class="sxs-lookup"><span data-stu-id="72e43-120">DataConf</span></span>

<span data-ttu-id="72e43-121">然后，Web 会议服务在位于 WebServices 文件夹中的 CollabContent 和 CollabMetadata 文件夹中存储诸如 PowerPoint 幻灯片、白板、投票表决和附件之类的内容。</span><span class="sxs-lookup"><span data-stu-id="72e43-121">The web conferencing service then stores content such as PowerPoint slides, whiteboards, polls, and attachments in the CollabContent and CollabMetadata folders, located in the WebServices folder.</span></span>

<span data-ttu-id="72e43-122">管理员必须设置对文件共享的权限，以使 RTC 组拥有必要的读和写访问权限。</span><span class="sxs-lookup"><span data-stu-id="72e43-122">The administrator must set permissions on the file share so that RTC groups have the necessary read and write access.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="72e43-p103">如果遇到与权限有关的任何错误，请打开拓扑生成器，下载并重新发布现有拓扑。发布拓扑将验证文件共享权限并在需要时重置这些权限。</span><span class="sxs-lookup"><span data-stu-id="72e43-p103">If you encounter any errors with the permissions, open Topology Builder, download and republish the existing topology. Publishing the topology will verify the file share permissions and reset them if needed.</span></span>



</div>

<span data-ttu-id="72e43-125">可以使用以下设置管理如何存储会议内容：</span><span class="sxs-lookup"><span data-stu-id="72e43-125">You can use the following settings to manage how content is stored for a meeting:</span></span>

  - <span data-ttu-id="72e43-126">**ContentGracePeriod**（位于[CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration)中）设置了会议结束后 web 会议内容将在服务器上保留多长时间。</span><span class="sxs-lookup"><span data-stu-id="72e43-126">**ContentGracePeriod**, located in [Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration), sets how long web conferencing content will remain on the server after the meeting has ended.</span></span>

  - <span data-ttu-id="72e43-127">**MaxContentStorageMb**（位于[CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration)中）设置了单个会议期间允许用于存储内容的最大文件空间量。</span><span class="sxs-lookup"><span data-stu-id="72e43-127">**MaxContentStorageMb**, located in [Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration), sets the maximum amount of file space allowed for the storage of content during a single meeting.</span></span>

<span data-ttu-id="72e43-128">**MaxUploadFileSizeMb**不限制 Lync Web App 的文件上载设置。</span><span class="sxs-lookup"><span data-stu-id="72e43-128">**MaxUploadFileSizeMb** does not limit the file upload setting for Lync Web App.</span></span> <span data-ttu-id="72e43-129">将 Lync Web App 的文件大小上载限制设置为约30MB，由 IIS web.config 文件控制：/DataCollabWeb/Int\[Ext/Handler/web.config.\]若要配置 Lync Web App 的文件大小上载限制，请`maxRequestLength` `maxAllowedContentLength`在 web.config 文件中进行更新，如下所示。</span><span class="sxs-lookup"><span data-stu-id="72e43-129">The file size upload limit for Lync Web App is set to approximately 30MB and is controlled by the IIS web.config file: /DataCollabWeb/Int\[Ext\]/Handler/web.config. To configure the file size upload limit for Lync Web App, update `maxRequestLength` and `maxAllowedContentLength` in the web.config file as shown below.</span></span>

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

<span data-ttu-id="72e43-130">您必须为每台前端服务器更新 web.config 文件。</span><span class="sxs-lookup"><span data-stu-id="72e43-130">You must update the web.config file for each Front End Server.</span></span>

</div>

<div>

## <a name="office-web-apps-server"></a><span data-ttu-id="72e43-131">Office Web Apps Server</span><span class="sxs-lookup"><span data-stu-id="72e43-131">Office Web Apps Server</span></span>

<span data-ttu-id="72e43-132">为了使用这些新功能，管理员必须安装 Office Web Apps Server，并且必须配置 Lync Server 2013 以与 Office Web Apps Server 进行通信。</span><span class="sxs-lookup"><span data-stu-id="72e43-132">In order to use these new capabilities administrators must install Office Web Apps Server and they must configure Lync Server 2013 to communicate with Office Web Apps Server.</span></span> <span data-ttu-id="72e43-133">本文档提供了有关如何配置 Lync Server 2013 以与 Office Web Apps Server 配合使用的信息。</span><span class="sxs-lookup"><span data-stu-id="72e43-133">This documentation provides information on how to configure Lync Server 2013 to work with Office Web Apps Server.</span></span> <span data-ttu-id="72e43-134">本文档不提供的内容是有关如何安装 Office Web Apps Server 的信息。</span><span class="sxs-lookup"><span data-stu-id="72e43-134">What this documentation does not provide is information about how to install Office Web Apps Server.</span></span> <span data-ttu-id="72e43-135">有关安装的详细信息，请参阅 Microsoft Office Web Apps 部署<http://go.microsoft.com/fwlink/p/?linkid=257525>网站。</span><span class="sxs-lookup"><span data-stu-id="72e43-135">For installation details, see the Microsoft Office Web Apps Deployment website at <http://go.microsoft.com/fwlink/p/?linkid=257525>.</span></span> <span data-ttu-id="72e43-136">该指南包括 Office Web Apps Server 的完整必备信息。</span><span class="sxs-lookup"><span data-stu-id="72e43-136">That guide includes complete prerequisite information for Office Web Apps Server.</span></span> <span data-ttu-id="72e43-137">请注意，Office Web Apps Server 应安装在未运行 Lync Server、SQL Server 或任何其他服务器应用程序的独立计算机上。</span><span class="sxs-lookup"><span data-stu-id="72e43-137">Note that Office Web Apps Server should be installed on a stand-alone computer that is not running Lync Server, SQL Server, or any other server application.</span></span> <span data-ttu-id="72e43-138">（您不得在该计算机上安装任何版本的 Office。）用于运行 Office Web Apps Server 的任何计算机还必须安装一组特定的软件（包括 .NET Framework 4.5 和 Windows PowerShell 3.0）。</span><span class="sxs-lookup"><span data-stu-id="72e43-138">(You must not have any version of Office installed on that computer.) Any computer used to run Office Web Apps Server must also have a specific set of software installed (including .NET Framework 4.5 and Windows PowerShell 3.0).</span></span> <span data-ttu-id="72e43-139">中的 Microsoft Office Web Apps 部署网站详细讨论了这些要求以及有关配置证书和 Internet 信息服务（IIS）的信息<http://go.microsoft.com/fwlink/p/?linkid=257525>。</span><span class="sxs-lookup"><span data-stu-id="72e43-139">These requirements, along with information about configuring certificates and Internet Information Services (IIS), are discussed in detail in the Microsoft Office Web Apps Deployment website at <http://go.microsoft.com/fwlink/p/?linkid=257525>.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="72e43-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="72e43-140">See Also</span></span>


[<span data-ttu-id="72e43-141">Lync Server 2013 中的 web 会议概述</span><span class="sxs-lookup"><span data-stu-id="72e43-141">Overview of web conferencing in Lync Server 2013</span></span>](lync-server-2013-web-conferencing-overview.md)  
[<span data-ttu-id="72e43-142">Lync Server 2013 中的 web 会议的部署清单</span><span class="sxs-lookup"><span data-stu-id="72e43-142">Deployment checklist for web conferencing in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-web-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

