---
title: 'Lync Server 2013: Web 会议要求'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Web conferencing requirements
ms:assetid: 125f847c-58ab-450f-ae43-41219fd38477
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619171(v=OCS.15)
ms:contentKeyID: 49733559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dddfd7c2fdfe6cbcefcca7533e93c3c377cceea8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845255"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="web-conferencing-requirements-in-lync-server-2013"></a><span data-ttu-id="c6fd8-102">Lync Server 2013 中的网络会议要求</span><span class="sxs-lookup"><span data-stu-id="c6fd8-102">Web conferencing requirements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c6fd8-103">_**主题上次修改时间:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="c6fd8-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="c6fd8-104">如果您已选择启用 Web 会议，则需计划以下事项：</span><span class="sxs-lookup"><span data-stu-id="c6fd8-104">If you have chosen to enable web conferencing, you need to plan for the following:</span></span>

  - <span></span>  
    <span data-ttu-id="c6fd8-105">访问文件存储，文件存储用于存储 Web 会议内容。</span><span class="sxs-lookup"><span data-stu-id="c6fd8-105">Access to the file store, which is used for storing web conferencing content.</span></span>

  - <span></span>  
    <span data-ttu-id="c6fd8-106">与 Office Web Apps Server 集成，这是在会议期间共享 PowerPoint 文件所必需的。</span><span class="sxs-lookup"><span data-stu-id="c6fd8-106">Integration with Office Web Apps Server, which is necessary in order to share PowerPoint files during a conference.</span></span>

<div>

## <a name="file-store"></a><span data-ttu-id="c6fd8-107">文件存储</span><span class="sxs-lookup"><span data-stu-id="c6fd8-107">File Store</span></span>

<span data-ttu-id="c6fd8-108">Lync Server 2013 web 会议服务存储在文件存储中的会议期间共享的内容。</span><span class="sxs-lookup"><span data-stu-id="c6fd8-108">The Lync Server 2013 web conferencing service stores content shared during meetings in the file store.</span></span> <span data-ttu-id="c6fd8-109">作为部署的一部分, 你必须指定要用作标准版服务器或企业版前端池的文件存储的文件共享。</span><span class="sxs-lookup"><span data-stu-id="c6fd8-109">As part of deployment, you must specify a file share to be used as the file store for the either Standard Edition server or Enterprise Edition Front End pool.</span></span> <span data-ttu-id="c6fd8-110">可以将现有的文件共享用作文件存储，也可以通过指定文件共享所在的文件服务器的完全限定域名 (FQDN) 和新文件共享的文件夹名称来指定新的文件共享。</span><span class="sxs-lookup"><span data-stu-id="c6fd8-110">You can use an existing file share for the file store or you can specify a new file share by specifying the fully qualified domain name (FQDN) of the file server on which the file share is to be located and a folder name for the new file share.</span></span><span data-ttu-id="c6fd8-111">有关详细信息, 请参阅拓扑生成器-定义前端的文件存储。</span><span class="sxs-lookup"><span data-stu-id="c6fd8-111">  For more information, see Topology Builder – Define the File Store for the Front End.</span></span> <span data-ttu-id="c6fd8-112">Web 会议服务在将内容存储到文件存储中之前对内容进行加密。</span><span class="sxs-lookup"><span data-stu-id="c6fd8-112">The web conferencing service encrypts the content before it stores the content in the file store.</span></span>

<span data-ttu-id="c6fd8-113">Lync Server 2013 支持在直接连接的存储 (DAS) 或存储区域网络 (SAN) 上使用文件共享, 包括分布式文件系统 (DFS) 和文件存储的独立磁盘冗余阵列 (RAID)。</span><span class="sxs-lookup"><span data-stu-id="c6fd8-113">Lync Server 2013 supports using file shares on either direct attached storage (DAS) or a storage area network (SAN), including Distributed File System (DFS) and on a redundant array of independent disks (RAID) for file stores.</span></span> <span data-ttu-id="c6fd8-114">在 Lync Server 部署向导定义文件共享的位置后, Lync Server 将在文件共享中创建一个类似于以下内容的文件夹结构:</span><span class="sxs-lookup"><span data-stu-id="c6fd8-114">After the Lync Server Deployment Wizard has defined the location of the file share, Lync Server creates a folder structure within the file share similar to:</span></span>

  - <span data-ttu-id="c6fd8-115">1-ApplicationServer-1</span><span class="sxs-lookup"><span data-stu-id="c6fd8-115">1-ApplicationServer-1</span></span>

  - <span data-ttu-id="c6fd8-116">1-CentralMgmt-1</span><span class="sxs-lookup"><span data-stu-id="c6fd8-116">1-CentralMgmt-1</span></span>

  - <span data-ttu-id="c6fd8-117">1-WebServices-1</span><span class="sxs-lookup"><span data-stu-id="c6fd8-117">1-WebServices-1</span></span>
    
      - <span data-ttu-id="c6fd8-118">CollabContent</span><span class="sxs-lookup"><span data-stu-id="c6fd8-118">CollabContent</span></span>
    
      - <span data-ttu-id="c6fd8-119">CollabMetadata</span><span class="sxs-lookup"><span data-stu-id="c6fd8-119">CollabMetadata</span></span>
    
      - <span data-ttu-id="c6fd8-120">DataConf</span><span class="sxs-lookup"><span data-stu-id="c6fd8-120">DataConf</span></span>

<span data-ttu-id="c6fd8-121">然后，Web 会议服务在位于 WebServices 文件夹中的 CollabContent 和 CollabMetadata 文件夹中存储诸如 PowerPoint 幻灯片、白板、投票表决和附件之类的内容。</span><span class="sxs-lookup"><span data-stu-id="c6fd8-121">The web conferencing service then stores content such as PowerPoint slides, whiteboards, polls, and attachments in the CollabContent and CollabMetadata folders, located in the WebServices folder.</span></span>

<span data-ttu-id="c6fd8-122">管理员必须设置文件共享的权限, 以便 RTC 组具有必需的读写访问权限。</span><span class="sxs-lookup"><span data-stu-id="c6fd8-122">The administrator must set permissions on the file share so that RTC groups have the necessary read and write access.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="c6fd8-123">如果你遇到有关权限的任何错误, 请打开拓扑生成器, 下载并重新发布现有拓扑。</span><span class="sxs-lookup"><span data-stu-id="c6fd8-123">If you encounter any errors with the permissions, open Topology Builder, download and republish the existing topology.</span></span> <span data-ttu-id="c6fd8-124">发布拓扑将验证文件共享权限, 并根据需要对其进行重置。</span><span class="sxs-lookup"><span data-stu-id="c6fd8-124">Publishing the topology will verify the file share permissions and reset them if needed.</span></span>



</div>

<span data-ttu-id="c6fd8-125">可以使用以下设置管理会议内容的存储方式:</span><span class="sxs-lookup"><span data-stu-id="c6fd8-125">You can use the following settings to manage how content is stored for a meeting:</span></span>

  - <span data-ttu-id="c6fd8-126">**ContentGracePeriod**(位于[CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration)中) 设置会议结束后, web 会议内容将在服务器上保留多长时间。</span><span class="sxs-lookup"><span data-stu-id="c6fd8-126">**ContentGracePeriod**, located in [Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration), sets how long web conferencing content will remain on the server after the meeting has ended.</span></span>

  - <span data-ttu-id="c6fd8-127">**MaxContentStorageMb**(位于 "[设置" CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration)中) 设置单个会议期间允许用于存储内容的最大文件空间量。</span><span class="sxs-lookup"><span data-stu-id="c6fd8-127">**MaxContentStorageMb**, located in [Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration), sets the maximum amount of file space allowed for the storage of content during a single meeting.</span></span>

<span data-ttu-id="c6fd8-128">**MaxUploadFileSizeMb**不限制 Lync Web App 的文件上载设置。</span><span class="sxs-lookup"><span data-stu-id="c6fd8-128">**MaxUploadFileSizeMb** does not limit the file upload setting for Lync Web App.</span></span> <span data-ttu-id="c6fd8-129">Lync Web App 的文件大小上载限制设置为 "约 30MB", 由 IIS web.config 文件控制:/DataCollabWeb/Int\[Ext/Handler/web.config.\]要配置 Lync Web App 的文件大小上载限制, 请更新`maxRequestLength` , `maxAllowedContentLength`并在 web.config 文件中, 如下所示。</span><span class="sxs-lookup"><span data-stu-id="c6fd8-129">The file size upload limit for Lync Web App is set to approximately 30MB and is controlled by the IIS web.config file: /DataCollabWeb/Int\[Ext\]/Handler/web.config. To configure the file size upload limit for Lync Web App, update `maxRequestLength` and `maxAllowedContentLength` in the web.config file as shown below.</span></span>

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

<span data-ttu-id="c6fd8-130">必须更新每个前端服务器的 web.config 文件。</span><span class="sxs-lookup"><span data-stu-id="c6fd8-130">You must update the web.config file for each Front End Server.</span></span>

</div>

<div>

## <a name="office-web-apps-server"></a><span data-ttu-id="c6fd8-131">Office Web Apps Server</span><span class="sxs-lookup"><span data-stu-id="c6fd8-131">Office Web Apps Server</span></span>

<span data-ttu-id="c6fd8-132">若要使用这些新功能, 管理员必须安装 Office Web Apps 服务器, 并且必须将 Lync Server 2013 配置为与 Office Web Apps 服务器通信。</span><span class="sxs-lookup"><span data-stu-id="c6fd8-132">In order to use these new capabilities administrators must install Office Web Apps Server and they must configure Lync Server 2013 to communicate with Office Web Apps Server.</span></span> <span data-ttu-id="c6fd8-133">本文档提供有关如何将 Lync Server 2013 配置为使用 Office Web Apps 服务器的信息。</span><span class="sxs-lookup"><span data-stu-id="c6fd8-133">This documentation provides information on how to configure Lync Server 2013 to work with Office Web Apps Server.</span></span> <span data-ttu-id="c6fd8-134">本文档不提供的信息是有关如何安装 Office Web Apps 服务器的信息。</span><span class="sxs-lookup"><span data-stu-id="c6fd8-134">What this documentation does not provide is information about how to install Office Web Apps Server.</span></span> <span data-ttu-id="c6fd8-135">有关安装的详细信息, 请参阅中的 Microsoft Office Web <http://go.microsoft.com/fwlink/p/?linkid=257525>Apps 部署网站。</span><span class="sxs-lookup"><span data-stu-id="c6fd8-135">For installation details, see the Microsoft Office Web Apps Deployment website at <http://go.microsoft.com/fwlink/p/?linkid=257525>.</span></span> <span data-ttu-id="c6fd8-136">该指南包括 Office Web Apps 服务器的完整必备信息。</span><span class="sxs-lookup"><span data-stu-id="c6fd8-136">That guide includes complete prerequisite information for Office Web Apps Server.</span></span> <span data-ttu-id="c6fd8-137">请注意, Office Web Apps 服务器应安装在未运行 Lync Server、SQL Server 或任何其他服务器应用程序的独立计算机上。</span><span class="sxs-lookup"><span data-stu-id="c6fd8-137">Note that Office Web Apps Server should be installed on a stand-alone computer that is not running Lync Server, SQL Server, or any other server application.</span></span> <span data-ttu-id="c6fd8-138">(您不能在该计算机上安装任何版本的 Office。)任何用于运行 Office Web Apps 服务器的计算机还必须安装一组特定的软件 (包括 .NET Framework 4.5 和 Windows PowerShell 3.0)。</span><span class="sxs-lookup"><span data-stu-id="c6fd8-138">(You must not have any version of Office installed on that computer.) Any computer used to run Office Web Apps Server must also have a specific set of software installed (including .NET Framework 4.5 and Windows PowerShell 3.0).</span></span> <span data-ttu-id="c6fd8-139">有关配置证书和 Internet 信息服务 (IIS) 的这些要求以及有关配置证书和 Internet 信息服务 (IIS) 的信息, 请参阅 Microsoft <http://go.microsoft.com/fwlink/p/?linkid=257525>Office Web Apps 部署网站中的详细讨论。</span><span class="sxs-lookup"><span data-stu-id="c6fd8-139">These requirements, along with information about configuring certificates and Internet Information Services (IIS), are discussed in detail in the Microsoft Office Web Apps Deployment website at <http://go.microsoft.com/fwlink/p/?linkid=257525>.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c6fd8-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c6fd8-140">See Also</span></span>


[<span data-ttu-id="c6fd8-141">Lync Server 2013 中的网络会议概述</span><span class="sxs-lookup"><span data-stu-id="c6fd8-141">Overview of web conferencing in Lync Server 2013</span></span>](lync-server-2013-web-conferencing-overview.md)  
[<span data-ttu-id="c6fd8-142">Lync Server 2013 中的 web 会议的部署清单</span><span class="sxs-lookup"><span data-stu-id="c6fd8-142">Deployment checklist for web conferencing in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-web-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

