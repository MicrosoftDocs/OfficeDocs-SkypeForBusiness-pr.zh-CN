---
title: Lync Server 2013：通知应用程序的技术要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for the Announcement application
ms:assetid: fbd8c204-3765-4b22-a0c9-a781b5126366
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205413(v=OCS.15)
ms:contentKeyID: 48185944
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 54371acb29bcc7d9b6581cbfd26199888dcfe893
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536099"
---
# <a name="technical-requirements-for-the-announcement-application-in-lync-server-2013"></a><span data-ttu-id="d9eda-102">Lync Server 2013 中通知应用程序的技术要求</span><span class="sxs-lookup"><span data-stu-id="d9eda-102">Technical requirements for the Announcement application in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d9eda-103">_**上次修改的主题：** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="d9eda-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="d9eda-104">本部分介绍了通知应用程序的以下技术要求：</span><span class="sxs-lookup"><span data-stu-id="d9eda-104">This section describes the following technical requirements for the Announcement application:</span></span>

  - <span data-ttu-id="d9eda-105">硬件要求</span><span class="sxs-lookup"><span data-stu-id="d9eda-105">Hardware requirements</span></span>

  - <span data-ttu-id="d9eda-106">软件要求</span><span class="sxs-lookup"><span data-stu-id="d9eda-106">Software requirements</span></span>

  - <span data-ttu-id="d9eda-107">端口要求</span><span class="sxs-lookup"><span data-stu-id="d9eda-107">Port requirements</span></span>

  - <span data-ttu-id="d9eda-108">音频文件要求</span><span class="sxs-lookup"><span data-stu-id="d9eda-108">Audio file requirements</span></span>

<div>

## <a name="hardware-requirements"></a><span data-ttu-id="d9eda-109">硬件要求</span><span class="sxs-lookup"><span data-stu-id="d9eda-109">Hardware Requirements</span></span>

<span data-ttu-id="d9eda-110">通知应用程序与前端服务器具有相同的硬件要求。</span><span class="sxs-lookup"><span data-stu-id="d9eda-110">The Announcement application has the same hardware requirements as Front End Servers.</span></span> <span data-ttu-id="d9eda-111">有关硬件要求的详细信息，请参阅可支持性文档中的 [Lync server 2013 的服务器硬件平台](lync-server-2013-server-hardware-platforms.md) 。</span><span class="sxs-lookup"><span data-stu-id="d9eda-111">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="software-requirements"></a><span data-ttu-id="d9eda-112">软件要求</span><span class="sxs-lookup"><span data-stu-id="d9eda-112">Software Requirements</span></span>

<span data-ttu-id="d9eda-113">通知应用程序与前端服务器具有相同的操作系统要求和软件先决条件。</span><span class="sxs-lookup"><span data-stu-id="d9eda-113">The Announcement application has the same operating system requirements and software prerequisites as Front End Servers.</span></span> <span data-ttu-id="d9eda-114">有关软件要求的详细信息，请参阅可支持性文档中的 [Lync server 2013 中的服务器和工具操作系统支持](lync-server-2013-server-and-tools-operating-system-support.md) 。</span><span class="sxs-lookup"><span data-stu-id="d9eda-114">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="d9eda-115">运行通知应用程序的所有前端服务器或 Standard Edition 服务器都必须为运行 windows Server 2008 R2 的服务器安装 Windows Media Format Runtime，或者为运行 Windows Server 2012 或 Windows Server 2012 R2 的服务器安装 Microsoft Media Foundation。</span><span class="sxs-lookup"><span data-stu-id="d9eda-115">All Front End Servers or Standard Edition servers that run the Announcement application must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="d9eda-116">对于 Windows Server 2008 R2，Windows Media Format Runtime 将作为 Windows 桌面体验的一部分安装。</span><span class="sxs-lookup"><span data-stu-id="d9eda-116">For Windows Server 2008 R2, the Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span> <span data-ttu-id="d9eda-117">Windows media 音频 ( 的 wma) 文件（通知应用程序对通知和音乐播放）需要 windows Media Format Runtime 或 Microsoft 媒体基础。</span><span class="sxs-lookup"><span data-stu-id="d9eda-117">Windows Media Format Runtime or Microsoft Media Foundation is required for Windows Media Audio (.wma) files that the Announcement application plays for announcements and music.</span></span>

</div>

<div>

## <a name="port-requirements"></a><span data-ttu-id="d9eda-118">端口要求</span><span class="sxs-lookup"><span data-stu-id="d9eda-118">Port Requirements</span></span>

<span data-ttu-id="d9eda-119">通知应用程序使用以下端口：</span><span class="sxs-lookup"><span data-stu-id="d9eda-119">The Announcement application uses the following port:</span></span>

  - <span data-ttu-id="d9eda-120">**端口 5071**    用于 SIP 侦听请求</span><span class="sxs-lookup"><span data-stu-id="d9eda-120">**Port 5071**   Used for SIP listening requests</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d9eda-121">此端口是默认设置，可以通过使用 <STRONG>Set-CsApplicationServer</STRONG> cmdlet 进行更改。</span><span class="sxs-lookup"><span data-stu-id="d9eda-121">This port is the default setting, which you can change by using the <STRONG>Set-CsApplicationServer</STRONG> cmdlet.</span></span> <span data-ttu-id="d9eda-122">有关此 cmdlet 的详细信息，请参阅 Lync Server 命令行管理程序文档。</span><span class="sxs-lookup"><span data-stu-id="d9eda-122">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>



</div>

</div>

<div>

## <a name="audio-file-requirements"></a><span data-ttu-id="d9eda-123">音频文件要求</span><span class="sxs-lookup"><span data-stu-id="d9eda-123">Audio File Requirements</span></span>

<span data-ttu-id="d9eda-124">通知应用程序支持 Wave ( .wav) 文件格式和 Windows Media ( 音频) 音乐和公告的文件格式。</span><span class="sxs-lookup"><span data-stu-id="d9eda-124">The Announcement application supports Wave (.wav) file format and Windows Media audio (.wma) file format for music and announcements.</span></span> <span data-ttu-id="d9eda-125">通知应用程序的音频文件要求与响应组应用程序的音频文件要求相同。</span><span class="sxs-lookup"><span data-stu-id="d9eda-125">Audio file requirements for the Announcement application are the same as for the Response Group application.</span></span> <span data-ttu-id="d9eda-126">有关详细信息，请参阅 [Lync Server 2013 中响应组的技术要求](lync-server-2013-technical-requirements-for-response-group.md)。</span><span class="sxs-lookup"><span data-stu-id="d9eda-126">For details, see [Technical requirements for Response Group in Lync Server 2013](lync-server-2013-technical-requirements-for-response-group.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

