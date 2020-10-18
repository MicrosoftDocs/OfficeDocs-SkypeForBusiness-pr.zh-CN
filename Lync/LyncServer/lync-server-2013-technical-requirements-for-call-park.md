---
title: Lync Server 2013：呼叫寄存的技术要求
description: Lync Server 2013：呼叫寄存的技术要求。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for Call Park
ms:assetid: 38bcf302-2b72-4492-9266-f6dc31b566e1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204818(v=OCS.15)
ms:contentKeyID: 48183897
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ddc17b40f78c42c090d1a87b4580ebdad0a07f6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577128"
---
# <a name="technical-requirements-for-call-park-in-lync-server-2013"></a><span data-ttu-id="dd828-103">Lync Server 2013 中呼叫寄存的技术要求</span><span class="sxs-lookup"><span data-stu-id="dd828-103">Technical requirements for Call Park in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dd828-104">_**上次修改的主题：** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="dd828-104">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="dd828-105">本部分介绍呼叫寄存的以下技术要求：</span><span class="sxs-lookup"><span data-stu-id="dd828-105">This section describes the following technical requirements for Call Park:</span></span>

  - <span data-ttu-id="dd828-106">硬件要求</span><span class="sxs-lookup"><span data-stu-id="dd828-106">Hardware requirements</span></span>

  - <span data-ttu-id="dd828-107">软件要求</span><span class="sxs-lookup"><span data-stu-id="dd828-107">Software requirements</span></span>

  - <span data-ttu-id="dd828-108">端口要求</span><span class="sxs-lookup"><span data-stu-id="dd828-108">Port requirements</span></span>

  - <span data-ttu-id="dd828-109">音频文件要求</span><span class="sxs-lookup"><span data-stu-id="dd828-109">Audio file requirements</span></span>

<div>

## <a name="hardware-requirements"></a><span data-ttu-id="dd828-110">硬件要求</span><span class="sxs-lookup"><span data-stu-id="dd828-110">Hardware Requirements</span></span>

<span data-ttu-id="dd828-111">呼叫寄存应用程序与前端服务器具有相同的硬件要求。</span><span class="sxs-lookup"><span data-stu-id="dd828-111">The Call Park application has the same hardware requirements as Front End Servers.</span></span> <span data-ttu-id="dd828-112">有关硬件要求的详细信息，请参阅可支持性文档中的 [Lync server 2013 的服务器硬件平台](lync-server-2013-server-hardware-platforms.md) 。</span><span class="sxs-lookup"><span data-stu-id="dd828-112">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="software-requirements"></a><span data-ttu-id="dd828-113">软件要求</span><span class="sxs-lookup"><span data-stu-id="dd828-113">Software Requirements</span></span>

<span data-ttu-id="dd828-114">呼叫寄存应用程序与前端服务器具有相同的操作系统要求和软件先决条件。</span><span class="sxs-lookup"><span data-stu-id="dd828-114">The Call Park application has the same operating system requirements and software prerequisites as Front End Servers.</span></span> <span data-ttu-id="dd828-115">有关软件要求的详细信息，请参阅可支持性文档中的 [Lync server 2013 中的服务器和工具操作系统支持](lync-server-2013-server-and-tools-operating-system-support.md) 。</span><span class="sxs-lookup"><span data-stu-id="dd828-115">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="dd828-116">在部署呼叫寄存应用程序的所有前端服务器和 Standard Edition 服务器上，必须为运行 windows Server 2008 R2 的服务器安装 Windows Media Format Runtime，或者为运行 Windows Server 2012 或 Windows Server 2012 R2 的服务器安装 Microsoft Media Foundation。</span><span class="sxs-lookup"><span data-stu-id="dd828-116">All Front End Servers and Standard Edition servers where the Call Park application is deployed must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="dd828-117">对于 Windows Server 2008 R2，Windows Media Format Runtime 将作为 Windows 桌面体验的一部分安装。</span><span class="sxs-lookup"><span data-stu-id="dd828-117">For Windows Server 2008 R2, Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span> <span data-ttu-id="dd828-118">Windows Media 音频需要 windows Media Format Runtime 或 Microsoft Media Foundation () 呼叫寄存的文件。在保留时播放的音乐。</span><span class="sxs-lookup"><span data-stu-id="dd828-118">Windows Media Format Runtime or Microsoft Media Foundation is required for Windows Media Audio (.wma) files that Call Park plays for music on hold.</span></span>

</div>

<div>

## <a name="port-requirements"></a><span data-ttu-id="dd828-119">端口要求</span><span class="sxs-lookup"><span data-stu-id="dd828-119">Port Requirements</span></span>

<span data-ttu-id="dd828-120">呼叫寄存应用程序使用以下端口：</span><span class="sxs-lookup"><span data-stu-id="dd828-120">The Call Park application uses the following port:</span></span>

  - <span data-ttu-id="dd828-121">**端口 5075**    用于 SIP 侦听请求。</span><span class="sxs-lookup"><span data-stu-id="dd828-121">**Port 5075**   Used for SIP listening requests.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="dd828-122">此端口是默认设置，您可以使用 <STRONG>Set-CsApplicationServer</STRONG> cmdlet 对其进行更改。</span><span class="sxs-lookup"><span data-stu-id="dd828-122">This port is a default setting that you can change by using the <STRONG>Set-CsApplicationServer</STRONG> cmdlet.</span></span> <span data-ttu-id="dd828-123">有关此 cmdlet 的详细信息，请参阅 Lync Server 命令行管理程序文档。</span><span class="sxs-lookup"><span data-stu-id="dd828-123">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>



</div>

</div>

<div>

## <a name="audio-file-requirements"></a><span data-ttu-id="dd828-124">音频文件要求</span><span class="sxs-lookup"><span data-stu-id="dd828-124">Audio File Requirements</span></span>

<span data-ttu-id="dd828-125">呼叫寄存应用程序仅支持对处于保留状态的音乐 ( .wma) 文件的 Windows Media 音频。</span><span class="sxs-lookup"><span data-stu-id="dd828-125">The Call Park application supports only Windows Media Audio (.wma) files for music on hold.</span></span> <span data-ttu-id="dd828-126">您可以使用 Microsoft Expression Encoder 4 来自定义用作保持音乐的文件。</span><span class="sxs-lookup"><span data-stu-id="dd828-126">You can use the Microsoft Expression Encoder 4 to customize files for music on hold.</span></span> <span data-ttu-id="dd828-127">若要下载表达式编码器4，请参阅中的 "Expression 编码器 4" [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkid=202843) 。</span><span class="sxs-lookup"><span data-stu-id="dd828-127">To download Expression Encoder 4, see "Expression Encoder 4" at [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkid=202843).</span></span> <span data-ttu-id="dd828-128">使用此工具将文件转换为 .wma 格式。</span><span class="sxs-lookup"><span data-stu-id="dd828-128">Use the tool to convert the file to a .wma format.</span></span> <span data-ttu-id="dd828-129">呼叫寄存保持音乐文件的建议格式为 Media Audio 9，44 kHz，16 位，单声道，CBR，32 kbps。</span><span class="sxs-lookup"><span data-stu-id="dd828-129">The recommended format for Call Park music-on-hold files is Media Audio 9, 44 kHz, 16 bits, Mono, CBR, 32 kbps.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="dd828-130">转换后的文件仅以 16 KHz 在电话上播放，即使录制时采用 44 KHz 也是如此。</span><span class="sxs-lookup"><span data-stu-id="dd828-130">The converted file plays over the phone only at 16 kHz, even if it was recorded at 44 kHz.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

