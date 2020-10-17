---
title: Lync Server 2013：响应组的技术要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for Response Group
ms:assetid: 477488bd-124f-437b-9327-732a0d7271ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204863(v=OCS.15)
ms:contentKeyID: 48184044
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0b06176a033c90ff915fccb145dac3b3ed6fe87
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536119"
---
# <a name="technical-requirements-for-response-group-in-lync-server-2013"></a><span data-ttu-id="9bbc5-102">Lync Server 2013 中响应组的技术要求</span><span class="sxs-lookup"><span data-stu-id="9bbc5-102">Technical requirements for Response Group in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9bbc5-103">_**上次修改的主题：** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="9bbc5-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="9bbc5-104">本节介绍响应组应用程序的以下技术要求：</span><span class="sxs-lookup"><span data-stu-id="9bbc5-104">This section describes the following technical requirements for the Response Group application:</span></span>

  - <span data-ttu-id="9bbc5-105">硬件要求</span><span class="sxs-lookup"><span data-stu-id="9bbc5-105">Hardware requirements</span></span>

  - <span data-ttu-id="9bbc5-106">软件要求</span><span class="sxs-lookup"><span data-stu-id="9bbc5-106">Software requirements</span></span>

  - <span data-ttu-id="9bbc5-107">端口要求</span><span class="sxs-lookup"><span data-stu-id="9bbc5-107">Port requirements</span></span>

  - <span data-ttu-id="9bbc5-108">音频文件要求</span><span class="sxs-lookup"><span data-stu-id="9bbc5-108">Audio file requirements</span></span>

  - <span data-ttu-id="9bbc5-109">响应组配置工具要求</span><span class="sxs-lookup"><span data-stu-id="9bbc5-109">Response Group configuration tool requirements</span></span>

<div>

## <a name="hardware-requirements"></a><span data-ttu-id="9bbc5-110">硬件要求</span><span class="sxs-lookup"><span data-stu-id="9bbc5-110">Hardware Requirements</span></span>

<span data-ttu-id="9bbc5-111">响应组应用程序与前端服务器具有相同的硬件要求。</span><span class="sxs-lookup"><span data-stu-id="9bbc5-111">The Response Group application has the same hardware requirements as Front End Servers.</span></span> <span data-ttu-id="9bbc5-112">有关硬件要求的详细信息，请参阅可支持性文档中的 [Lync server 2013 的服务器硬件平台](lync-server-2013-server-hardware-platforms.md) 。</span><span class="sxs-lookup"><span data-stu-id="9bbc5-112">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="software-requirements"></a><span data-ttu-id="9bbc5-113">软件要求</span><span class="sxs-lookup"><span data-stu-id="9bbc5-113">Software Requirements</span></span>

<span data-ttu-id="9bbc5-114">响应组应用程序与前端服务器具有相同的操作系统要求和软件先决条件。</span><span class="sxs-lookup"><span data-stu-id="9bbc5-114">The Response Group application has the same operating system requirements and software prerequisites as Front End Servers.</span></span> <span data-ttu-id="9bbc5-115">有关软件要求的详细信息，请参阅可支持性文档中的 [Lync server 2013 中的服务器和工具操作系统支持](lync-server-2013-server-and-tools-operating-system-support.md) 。</span><span class="sxs-lookup"><span data-stu-id="9bbc5-115">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="9bbc5-116">如果使用 Windows Media Audio)  ( 响应组音乐和公告的文件，则所有前端服务器或运行响应组应用程序的标准版服务器必须为运行 windows server 2008 R2 的服务器安装 windows Media Format Runtime，或为运行 Windows Server 2012 或 Windows Server 2012 R2 的服务器安装 Microsoft Media Foundation。</span><span class="sxs-lookup"><span data-stu-id="9bbc5-116">If you use Windows Media Audio (.wma) files for Response Group music and announcements, all Front End Servers or Standard Editions servers that run the Response Group application must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="9bbc5-117">对于 Windows Server 2008 R2，Windows Media Format Runtime 将作为 Windows 桌面体验的一部分安装。</span><span class="sxs-lookup"><span data-stu-id="9bbc5-117">For Windows Server 2008 R2, Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span>

<span data-ttu-id="9bbc5-118">有关音频要求的更多详细信息，请参阅本节后面的 "音频文件要求"。</span><span class="sxs-lookup"><span data-stu-id="9bbc5-118">For more details about audio requirements, see "Audio File Requirements" later in this section.</span></span>

</div>

<div>

## <a name="port-requirements"></a><span data-ttu-id="9bbc5-119">端口要求</span><span class="sxs-lookup"><span data-stu-id="9bbc5-119">Port Requirements</span></span>

<span data-ttu-id="9bbc5-120">响应组应用程序使用以下端口：</span><span class="sxs-lookup"><span data-stu-id="9bbc5-120">The Response Group application uses the following ports:</span></span>

  - <span data-ttu-id="9bbc5-121">**端口 5071**    用于 SIP 侦听请求</span><span class="sxs-lookup"><span data-stu-id="9bbc5-121">**Port 5071**   Used for SIP listening requests</span></span>

  - <span data-ttu-id="9bbc5-122">**端口 8404**    用于服务器间通信</span><span class="sxs-lookup"><span data-stu-id="9bbc5-122">**Port 8404**   Used for interserver communications</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9bbc5-123">此端口用于 Match service，并且当响应组应用程序部署在具有多个前端服务器的池中时，此端口是必需的。</span><span class="sxs-lookup"><span data-stu-id="9bbc5-123">This port is used for the Match Making service and is required when the Response Group application is deployed in a pool that has more than one Front End Server.</span></span>

    
    </div>

<div>


> [!NOTE]  
> <span data-ttu-id="9bbc5-124">这些端口是默认设置，您可以使用 <STRONG>Set-CsApplicationServer</STRONG> cmdlet 更改。</span><span class="sxs-lookup"><span data-stu-id="9bbc5-124">These ports are default settings that you can change by using the <STRONG>Set-CsApplicationServer</STRONG> cmdlet.</span></span> <span data-ttu-id="9bbc5-125">有关此 cmdlet 的详细信息，请参阅 Lync Server 命令行管理程序文档。</span><span class="sxs-lookup"><span data-stu-id="9bbc5-125">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>



</div>

</div>

<div>

## <a name="audio-file-requirements"></a><span data-ttu-id="9bbc5-126">音频文件要求</span><span class="sxs-lookup"><span data-stu-id="9bbc5-126">Audio File Requirements</span></span>

<span data-ttu-id="9bbc5-127">响应组应用程序支持 wave ( .wav) 文件格式和 Windows Media ( 音频) 响应组邮件的文件格式、保留音乐或交互语音响应 (IVR) 问题。</span><span class="sxs-lookup"><span data-stu-id="9bbc5-127">The Response Group application supports wave (.wav) file format and Windows Media audio (.wma) file format for Response Group messages, on-hold music, or interactive voice response (IVR) questions.</span></span>

<span data-ttu-id="9bbc5-128">Windows Media 音频文件格式要求在运行 Windows Server 2008 R2 和 Windows Server 2008 的前端服务器上安装 Windows Media Format Runtime。</span><span class="sxs-lookup"><span data-stu-id="9bbc5-128">The Windows Media audio file format requires that the Windows Media Format Runtime is installed on Front End Servers running Windows Server 2008 R2 and Windows Server 2008.</span></span> <span data-ttu-id="9bbc5-129">有关更多详细信息，请参阅本节前面的 "软件要求"。</span><span class="sxs-lookup"><span data-stu-id="9bbc5-129">For more details, see "Software Requirements" earlier in this section.</span></span>

<div>

## <a name="supported-wave-file-formats"></a><span data-ttu-id="9bbc5-130">支持的 Wave 文件格式</span><span class="sxs-lookup"><span data-stu-id="9bbc5-130">Supported Wave File Formats</span></span>

<span data-ttu-id="9bbc5-131">所有 wave 文件必须符合以下要求：</span><span class="sxs-lookup"><span data-stu-id="9bbc5-131">All wave files must meet the following requirements:</span></span>

  - <span data-ttu-id="9bbc5-132">8 位或 16 位文件</span><span class="sxs-lookup"><span data-stu-id="9bbc5-132">8-bit or 16-bit file</span></span>

  - <span data-ttu-id="9bbc5-133">线性脉冲编码调制 (LPCM)，A-Law 或 mu-Law 格式</span><span class="sxs-lookup"><span data-stu-id="9bbc5-133">Linear pulse code modulation (LPCM), A-Law, or mu-Law format</span></span>

  - <span data-ttu-id="9bbc5-134">单声道或立体声</span><span class="sxs-lookup"><span data-stu-id="9bbc5-134">Mono or stereo</span></span>

  - <span data-ttu-id="9bbc5-135">4 MB 或更小</span><span class="sxs-lookup"><span data-stu-id="9bbc5-135">4MB or less</span></span>

<span data-ttu-id="9bbc5-136">为获得 wave 文件的最佳性能，建议使用 16 kHz、单声道、16 位的 wave 文件。</span><span class="sxs-lookup"><span data-stu-id="9bbc5-136">For the best performance of wave files, a 16 kHz, mono, 16-bit Wave file is recommended.</span></span>

</div>

<div>

## <a name="supported-windows-media-audio-file-formats"></a><span data-ttu-id="9bbc5-137">支持的 Windows Media 音频文件格式</span><span class="sxs-lookup"><span data-stu-id="9bbc5-137">Supported Windows Media Audio File Formats</span></span>

<span data-ttu-id="9bbc5-138">如果使用的是 Windows Media 音频文件，请考虑使用低比特率，并在 "负载" 下验证系统的性能。</span><span class="sxs-lookup"><span data-stu-id="9bbc5-138">If you use a Windows Media audio file, consider using low bit rates, and verify the performance of your system under load.</span></span>

<span data-ttu-id="9bbc5-139">您可以使用 Microsoft Expression Encoder 4 将文件转换为 Windows Media 音频格式。</span><span class="sxs-lookup"><span data-stu-id="9bbc5-139">You can use the Microsoft Expression Encoder 4 to convert a file to the Windows Media Audio format.</span></span> <span data-ttu-id="9bbc5-140">若要下载表达式编码器4，请参阅 [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkid=202843) 。</span><span class="sxs-lookup"><span data-stu-id="9bbc5-140">To download Expression Encoder 4, see [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkid=202843).</span></span>

</div>

</div>

<div>

## <a name="response-group-configuration-tool-requirements"></a><span data-ttu-id="9bbc5-141">响应组配置工具要求</span><span class="sxs-lookup"><span data-stu-id="9bbc5-141">Response Group Configuration Tool Requirements</span></span>

<span data-ttu-id="9bbc5-142">响应组配置工具支持下表中所述的操作系统和 web 浏览器的组合。</span><span class="sxs-lookup"><span data-stu-id="9bbc5-142">The Response Group Configuration Tool supports the combinations of operating systems and web browsers described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9bbc5-143">支持32位或64位版本的操作系统。</span><span class="sxs-lookup"><span data-stu-id="9bbc5-143">32-bit or 64-bit versions of the operating systems are supported.</span></span> <span data-ttu-id="9bbc5-144">仅支持32位版本的 Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="9bbc5-144">Only 32-bit versions of Internet Explorer are supported.</span></span>



</div>

### <a name="supported-operating-systems-and-web-browsers"></a><span data-ttu-id="9bbc5-145">支持的操作系统和 Web 浏览器</span><span class="sxs-lookup"><span data-stu-id="9bbc5-145">Supported Operating Systems and Web Browsers</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9bbc5-146">操作系统</span><span class="sxs-lookup"><span data-stu-id="9bbc5-146">Operating system</span></span></th>
<th><span data-ttu-id="9bbc5-147">Web 浏览器</span><span class="sxs-lookup"><span data-stu-id="9bbc5-147">Web browser</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9bbc5-148">Windows Vista Service Pack (SP) 2</span><span class="sxs-lookup"><span data-stu-id="9bbc5-148">Windows Vista with Service Pack (SP) 2</span></span></p></td>
<td><p><span data-ttu-id="9bbc5-149">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="9bbc5-149">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="9bbc5-150">Internet Explorer 8 (本机模式) </span><span class="sxs-lookup"><span data-stu-id="9bbc5-150">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="9bbc5-151">Internet Explorer 9 (本机模式) </span><span class="sxs-lookup"><span data-stu-id="9bbc5-151">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9bbc5-152">Windows 7</span><span class="sxs-lookup"><span data-stu-id="9bbc5-152">Windows 7</span></span></p>
<p><span data-ttu-id="9bbc5-153">Windows 7 Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="9bbc5-153">Windows 7 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="9bbc5-154">Internet Explorer 8 (本机模式) </span><span class="sxs-lookup"><span data-stu-id="9bbc5-154">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="9bbc5-155">Internet Explorer 9 (本机模式) </span><span class="sxs-lookup"><span data-stu-id="9bbc5-155">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9bbc5-156">Windows Server 2008 Service Pack 2</span><span class="sxs-lookup"><span data-stu-id="9bbc5-156">Windows Server 2008 with Service Pack 2</span></span></p></td>
<td><p><span data-ttu-id="9bbc5-157">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="9bbc5-157">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="9bbc5-158">Internet Explorer 8 (本机模式) </span><span class="sxs-lookup"><span data-stu-id="9bbc5-158">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="9bbc5-159">Internet Explorer 9 (本机模式) </span><span class="sxs-lookup"><span data-stu-id="9bbc5-159">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9bbc5-160">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="9bbc5-160">Windows Server 2008 R2</span></span></p>
<p><span data-ttu-id="9bbc5-161">Windows Server 2008 R2 Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="9bbc5-161">Windows Server 2008 R2 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="9bbc5-162">Internet Explorer 8 (本机模式) </span><span class="sxs-lookup"><span data-stu-id="9bbc5-162">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="9bbc5-163">Internet Explorer 9 (本机模式) </span><span class="sxs-lookup"><span data-stu-id="9bbc5-163">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="response-group-agent-console"></a><span data-ttu-id="9bbc5-164">响应组代理控制台</span><span class="sxs-lookup"><span data-stu-id="9bbc5-164">Response Group Agent Console</span></span>

<span data-ttu-id="9bbc5-165">代理控制台支持下表中所述的操作系统和 web 浏览器的组合。</span><span class="sxs-lookup"><span data-stu-id="9bbc5-165">The agent console supports the combinations of operating systems and web browsers described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9bbc5-166">支持32位或64位版本的操作系统。</span><span class="sxs-lookup"><span data-stu-id="9bbc5-166">32-bit or 64-bit versions of the operating systems are supported.</span></span> <span data-ttu-id="9bbc5-167">仅支持32位版本的 Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="9bbc5-167">Only 32-bit versions of Internet Explorer are supported.</span></span>



</div>

### <a name="supported-operating-systems-and-web-browsers"></a><span data-ttu-id="9bbc5-168">支持的操作系统和 Web 浏览器</span><span class="sxs-lookup"><span data-stu-id="9bbc5-168">Supported Operating Systems and Web Browsers</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9bbc5-169">操作系统</span><span class="sxs-lookup"><span data-stu-id="9bbc5-169">Operating system</span></span></th>
<th><span data-ttu-id="9bbc5-170">Web 浏览器</span><span class="sxs-lookup"><span data-stu-id="9bbc5-170">Web browser</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9bbc5-171">Windows Vista Service Pack (SP) 2</span><span class="sxs-lookup"><span data-stu-id="9bbc5-171">Windows Vista with Service Pack (SP) 2</span></span></p></td>
<td><p><span data-ttu-id="9bbc5-172">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="9bbc5-172">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="9bbc5-173">Internet Explorer 8 (本机模式) </span><span class="sxs-lookup"><span data-stu-id="9bbc5-173">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="9bbc5-174">Internet Explorer 9 (本机模式) </span><span class="sxs-lookup"><span data-stu-id="9bbc5-174">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9bbc5-175">Windows 7</span><span class="sxs-lookup"><span data-stu-id="9bbc5-175">Windows 7</span></span></p>
<p><span data-ttu-id="9bbc5-176">Windows 7 Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="9bbc5-176">Windows 7 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="9bbc5-177">Internet Explorer 8 (本机模式) </span><span class="sxs-lookup"><span data-stu-id="9bbc5-177">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="9bbc5-178">Internet Explorer 9 (本机模式) </span><span class="sxs-lookup"><span data-stu-id="9bbc5-178">Internet Explorer 9 (native mode)</span></span></p>
<p><span data-ttu-id="9bbc5-179">Firefox 10。0</span><span class="sxs-lookup"><span data-stu-id="9bbc5-179">Firefox 10.0</span></span></p>
<p><span data-ttu-id="9bbc5-180">Chrome 18。0</span><span class="sxs-lookup"><span data-stu-id="9bbc5-180">Chrome 18.0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9bbc5-181">Windows Server 2008 Service Pack 2</span><span class="sxs-lookup"><span data-stu-id="9bbc5-181">Windows Server 2008 with Service Pack 2</span></span></p></td>
<td><p><span data-ttu-id="9bbc5-182">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="9bbc5-182">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="9bbc5-183">Internet Explorer 8 (本机模式) </span><span class="sxs-lookup"><span data-stu-id="9bbc5-183">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="9bbc5-184">Internet Explorer 9 (本机模式) </span><span class="sxs-lookup"><span data-stu-id="9bbc5-184">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9bbc5-185">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="9bbc5-185">Windows Server 2008 R2</span></span></p>
<p><span data-ttu-id="9bbc5-186">Windows Server 2008 R2 Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="9bbc5-186">Windows Server 2008 R2 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="9bbc5-187">Internet Explorer 8 (本机模式) </span><span class="sxs-lookup"><span data-stu-id="9bbc5-187">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="9bbc5-188">Internet Explorer 9 (本机模式) </span><span class="sxs-lookup"><span data-stu-id="9bbc5-188">Internet Explorer 9 (native mode)</span></span></p>
<p><span data-ttu-id="9bbc5-189">Firefox 10。0</span><span class="sxs-lookup"><span data-stu-id="9bbc5-189">Firefox 10.0</span></span></p>
<p><span data-ttu-id="9bbc5-190">Chrome 18。0</span><span class="sxs-lookup"><span data-stu-id="9bbc5-190">Chrome 18.0</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

