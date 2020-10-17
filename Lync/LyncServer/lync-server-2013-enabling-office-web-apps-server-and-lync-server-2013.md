---
title: Lync Server 2013：启用 Office Web Apps Server 和 Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling Office Web Apps Server and Lync Server 2013
ms:assetid: 3370ab55-9949-4f32-b88b-5cffed6aaad8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204792(v=OCS.15)
ms:contentKeyID: 48183790
ms.date: 08/19/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 89ec4337bd4bc728f9737ecb75bb29075831bc09
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528539"
---
# <a name="configuring-integration-with-office-web-apps-server-and-lync-server-2013"></a><span data-ttu-id="0be92-102">配置与 Office Web Apps Server 和 Lync Server 2013 的集成</span><span class="sxs-lookup"><span data-stu-id="0be92-102">Configuring integration with Office Web Apps Server and Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0be92-103">_**上次修改的主题：** 2016-08-19_</span><span class="sxs-lookup"><span data-stu-id="0be92-103">_**Topic Last Modified:** 2016-08-19_</span></span>

<span data-ttu-id="0be92-104">Lync Server 2013 采用 Office Web Apps Server 来处理 PowerPoint 演示文稿。</span><span class="sxs-lookup"><span data-stu-id="0be92-104">Lync Server 2013 employs Office Web Apps Server to handle PowerPoint presentations.</span></span> <span data-ttu-id="0be92-105">有关此方法的优势的信息，请参阅 [Lync Server 2013 中的 web 会议概述](lync-server-2013-web-conferencing-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="0be92-105">For information about the advantages to this approach, see [Overview of web conferencing in Lync Server 2013](lync-server-2013-web-conferencing-overview.md).</span></span>

<span data-ttu-id="0be92-106">为了使用这些新功能，管理员必须安装 Office Web Apps Server，并且必须配置 Lync Server 2013 以与 Office Web Apps Server 进行通信。</span><span class="sxs-lookup"><span data-stu-id="0be92-106">In order to use these new capabilities administrators must install Office Web Apps Server and they must configure Lync Server 2013 to communicate with Office Web Apps Server.</span></span> <span data-ttu-id="0be92-107">本文档提供了有关如何配置 Lync Server 2013 以与 Office Web Apps Server 配合使用的信息。</span><span class="sxs-lookup"><span data-stu-id="0be92-107">This documentation provides information on how to configure Lync Server 2013 to work with Office Web Apps Server.</span></span> <span data-ttu-id="0be92-108">本文档不提供的内容是有关如何安装 Office Web Apps Server 本身的信息。有关此信息，请参阅中的 Microsoft Office Web Apps 部署网站 <https://go.microsoft.com/fwlink/p/?linkid=257525> 。</span><span class="sxs-lookup"><span data-stu-id="0be92-108">What this documentation does not provide is information on how to install Office Web Apps Server itself; for that information, see the Microsoft Office Web Apps Deployment website at <https://go.microsoft.com/fwlink/p/?linkid=257525>.</span></span> <span data-ttu-id="0be92-109">该指南包括 Office Web Apps Server 的完整必备信息;请注意，Office Web Apps Server 应安装在未运行 Lync Server、Microsoft SQL Server 或任何其他服务器应用程序的独立计算机上。</span><span class="sxs-lookup"><span data-stu-id="0be92-109">That guide includes complete prerequisite information for Office Web Apps Server; note that Office Web Apps Server should be installed on a stand-alone computer that is not running Lync Server, Microsoft SQL Server, or any other server application.</span></span> <span data-ttu-id="0be92-110"> (不得在该计算机上安装任何版本的 Microsoft Office。 ) 用于运行 Office Web Apps Server 的任何计算机还必须安装一组特定的软件 (包括 .NET Framework 4.5 和 Windows PowerShell 3.0) ;下面的 Microsoft Office Web Apps 部署网站中详细介绍了有关配置证书和 Internet 信息服务 (IIS) 的相关要求 <https://go.microsoft.com/fwlink/p/?linkid=257525> 。</span><span class="sxs-lookup"><span data-stu-id="0be92-110">(You must not have any version of Microsoft Office installed on that computer.) Any computer used to run Office Web Apps Server must also have a specific set of software installed (including .NET Framework 4.5 and Windows PowerShell 3.0); these requirements, along with information on configuring certificates and Internet Information Services (IIS), are discussed in detail in the Microsoft Office Web Apps Deployment website at <https://go.microsoft.com/fwlink/p/?linkid=257525>.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0be92-111">Office Web Apps Server 的最新小版本命名为 Office Online Server，这是由 Lync Server 2013 支持的。</span><span class="sxs-lookup"><span data-stu-id="0be92-111">The latest iteration of Office Web Apps Server is named Office Online Server, which is supported by Lync Server 2013.</span></span> <span data-ttu-id="0be92-112">有关更多详细信息，请参阅 <A href="https://technet.microsoft.com/library/jj219456(v=office.16).aspx">Office Online Server 文档</A>。</span><span class="sxs-lookup"><span data-stu-id="0be92-112">For more detail, refer to the <A href="https://technet.microsoft.com/library/jj219456(v=office.16).aspx">Office Online Server documentation</A>.</span></span>



</div>

<span data-ttu-id="0be92-113">本文档包含以下主题领域：</span><span class="sxs-lookup"><span data-stu-id="0be92-113">This document covers the following topic areas:</span></span>

  - [<span data-ttu-id="0be92-114">配置 Lync Server 2013 以与 Office Web Apps Server 配合使用</span><span class="sxs-lookup"><span data-stu-id="0be92-114">Configuring Lync Server 2013 to work with Office Web Apps Server</span></span>](lync-server-2013-configuring-lync-server-2013-to-work-with-office-web-apps-server.md)

  - [<span data-ttu-id="0be92-115">使用反向代理服务器在 Lync Server 2013 中发布 Office Web Apps Server</span><span class="sxs-lookup"><span data-stu-id="0be92-115">Publishing Office Web Apps Server in Lync Server 2013 using a reverse proxy server</span></span>](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md)

  - [<span data-ttu-id="0be92-116">在 Lync Server 2013 中验证 Office Web Apps Server 的配置</span><span class="sxs-lookup"><span data-stu-id="0be92-116">Validating the configuration of Office Web Apps Server in Lync Server 2013</span></span>](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md)

  - [<span data-ttu-id="0be92-117">配置用于 Office Web Apps Server 的 Lync Server 2013 客户端</span><span class="sxs-lookup"><span data-stu-id="0be92-117">Configuring clients of Lync Server 2013 for use with Office Web Apps Server</span></span>](lync-server-2013-configuring-clients-for-use-with-office-web-apps-server.md)

</div>

<span> </span>

</div>

</div>

</div>

