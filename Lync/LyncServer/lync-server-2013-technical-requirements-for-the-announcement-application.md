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
ms.openlocfilehash: 6a1a752159f27cf2d1bdadc149c2f26131c5ab06
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141768"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-the-announcement-application-in-lync-server-2013"></a><span data-ttu-id="74b0f-102">Lync Server 2013 中通知应用程序的技术要求</span><span class="sxs-lookup"><span data-stu-id="74b0f-102">Technical requirements for the Announcement application in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74b0f-103">_**上次修改的主题：** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="74b0f-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="74b0f-104">本部分介绍了通知应用程序的以下技术要求：</span><span class="sxs-lookup"><span data-stu-id="74b0f-104">This section describes the following technical requirements for the Announcement application:</span></span>

  - <span data-ttu-id="74b0f-105">硬件要求</span><span class="sxs-lookup"><span data-stu-id="74b0f-105">Hardware requirements</span></span>

  - <span data-ttu-id="74b0f-106">软件要求</span><span class="sxs-lookup"><span data-stu-id="74b0f-106">Software requirements</span></span>

  - <span data-ttu-id="74b0f-107">端口要求</span><span class="sxs-lookup"><span data-stu-id="74b0f-107">Port requirements</span></span>

  - <span data-ttu-id="74b0f-108">音频文件要求</span><span class="sxs-lookup"><span data-stu-id="74b0f-108">Audio file requirements</span></span>

<div>

## <a name="hardware-requirements"></a><span data-ttu-id="74b0f-109">硬件要求</span><span class="sxs-lookup"><span data-stu-id="74b0f-109">Hardware Requirements</span></span>

<span data-ttu-id="74b0f-110">通知应用程序与前端服务器具有相同的硬件要求。</span><span class="sxs-lookup"><span data-stu-id="74b0f-110">The Announcement application has the same hardware requirements as Front End Servers.</span></span> <span data-ttu-id="74b0f-111">有关硬件要求的详细信息，请参阅可支持性文档中的[Lync server 2013 的服务器硬件平台](lync-server-2013-server-hardware-platforms.md)。</span><span class="sxs-lookup"><span data-stu-id="74b0f-111">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="software-requirements"></a><span data-ttu-id="74b0f-112">软件要求</span><span class="sxs-lookup"><span data-stu-id="74b0f-112">Software Requirements</span></span>

<span data-ttu-id="74b0f-113">通知应用程序与前端服务器具有相同的操作系统要求和软件先决条件。</span><span class="sxs-lookup"><span data-stu-id="74b0f-113">The Announcement application has the same operating system requirements and software prerequisites as Front End Servers.</span></span> <span data-ttu-id="74b0f-114">有关软件要求的详细信息，请参阅可支持性文档中的[Lync server 2013 中的服务器和工具操作系统支持](lync-server-2013-server-and-tools-operating-system-support.md)。</span><span class="sxs-lookup"><span data-stu-id="74b0f-114">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="74b0f-115">运行通知应用程序的所有前端服务器或 Standard Edition 服务器必须为运行 Windows Server 2008 R2 的服务器安装 Windows Media Format Runtime，或者为运行 Windows Server 2012 的服务器安装 Microsoft Media Foundation。Windows Server 2012 R2。</span><span class="sxs-lookup"><span data-stu-id="74b0f-115">All Front End Servers or Standard Edition servers that run the Announcement application must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="74b0f-116">对于 Windows Server 2008 R2，Windows Media Format Runtime 将作为 Windows 桌面体验的一部分安装。</span><span class="sxs-lookup"><span data-stu-id="74b0f-116">For Windows Server 2008 R2, the Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span> <span data-ttu-id="74b0f-117">对于通知和音乐，通知应用程序播放的 Windows Media 音频（.wma）文件需要 windows Media Format Runtime 或 Microsoft Media Foundation。</span><span class="sxs-lookup"><span data-stu-id="74b0f-117">Windows Media Format Runtime or Microsoft Media Foundation is required for Windows Media Audio (.wma) files that the Announcement application plays for announcements and music.</span></span>

</div>

<div>

## <a name="port-requirements"></a><span data-ttu-id="74b0f-118">端口要求</span><span class="sxs-lookup"><span data-stu-id="74b0f-118">Port Requirements</span></span>

<span data-ttu-id="74b0f-119">通知应用程序使用以下端口：</span><span class="sxs-lookup"><span data-stu-id="74b0f-119">The Announcement application uses the following port:</span></span>

  - <span data-ttu-id="74b0f-120">\*\*\*\*   用于 SIP 侦听请求的端口5071</span><span class="sxs-lookup"><span data-stu-id="74b0f-120">**Port 5071**   Used for SIP listening requests</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="74b0f-121">此端口是默认设置，可以通过使用 <STRONG>Set-CsApplicationServer</STRONG> cmdlet 进行更改。</span><span class="sxs-lookup"><span data-stu-id="74b0f-121">This port is the default setting, which you can change by using the <STRONG>Set-CsApplicationServer</STRONG> cmdlet.</span></span> <span data-ttu-id="74b0f-122">有关此 cmdlet 的详细信息，请参阅 Lync Server 命令行管理程序文档。</span><span class="sxs-lookup"><span data-stu-id="74b0f-122">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>



</div>

</div>

<div>

## <a name="audio-file-requirements"></a><span data-ttu-id="74b0f-123">音频文件要求</span><span class="sxs-lookup"><span data-stu-id="74b0f-123">Audio File Requirements</span></span>

<span data-ttu-id="74b0f-124">通知应用程序支持波形（.wav）文件格式和 Windows Media 音频（.wma）文件格式的音乐和公告。</span><span class="sxs-lookup"><span data-stu-id="74b0f-124">The Announcement application supports Wave (.wav) file format and Windows Media audio (.wma) file format for music and announcements.</span></span> <span data-ttu-id="74b0f-125">通知应用程序的音频文件要求与响应组应用程序的音频文件要求相同。</span><span class="sxs-lookup"><span data-stu-id="74b0f-125">Audio file requirements for the Announcement application are the same as for the Response Group application.</span></span> <span data-ttu-id="74b0f-126">有关详细信息，请参阅[Lync Server 2013 中响应组的技术要求](lync-server-2013-technical-requirements-for-response-group.md)。</span><span class="sxs-lookup"><span data-stu-id="74b0f-126">For details, see [Technical requirements for Response Group in Lync Server 2013](lync-server-2013-technical-requirements-for-response-group.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

