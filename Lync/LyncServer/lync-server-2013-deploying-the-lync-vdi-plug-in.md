---
title: Lync Server 2013：部署 Lync VDI 插件
description: Lync Server 2013：部署 Lync VDI 插件。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying the Lync VDI plug-in
ms:assetid: 11d3bd5d-6dd3-471c-b842-b072fa197714
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204683(v=OCS.15)
ms:contentKeyID: 48183449
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3addecb07f269e4524f3da835f479439639935ad
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557798"
---
# <a name="deploying-the-lync-vdi-plug-in-in-lync-server-2013"></a><span data-ttu-id="16569-103">在 Lync Server 2013 中部署 Lync VDI 插件</span><span class="sxs-lookup"><span data-stu-id="16569-103">Deploying the Lync VDI plug-in in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="16569-104">_**上次修改的主题：** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="16569-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="16569-105">Lync 2013 客户端支持虚拟桌面基础结构中的音频和视频 (VDI) 环境。</span><span class="sxs-lookup"><span data-stu-id="16569-105">The Lync 2013 client supports audio and video in a Virtual Desktop Infrastructure (VDI) environment.</span></span> <span data-ttu-id="16569-106">用户可以将音频或视频设备（例如，耳机或网络摄像头）连接到本地计算机（例如，瘦客户端或已调整用途的计算机）。</span><span class="sxs-lookup"><span data-stu-id="16569-106">A user can connect an audio or video device (for example, a headset or a camera) to the local computer (for example, a thin client or repurposed computer).</span></span> <span data-ttu-id="16569-107">用户可以连接到虚拟机，登录到在虚拟机上运行的 Lync 2013 客户端，并参与实时音频和视频通信，如同客户端在本地运行一样。</span><span class="sxs-lookup"><span data-stu-id="16569-107">The user can connect to the virtual machine, sign in to the Lync 2013 client that is running on the virtual machine, and participate in real-time audio and video communications as though the client is running locally.</span></span>

<span data-ttu-id="16569-108">Lync VDI 插件是安装在本地计算机上的独立应用程序，允许将本地音频和视频设备与在虚拟机上运行的 Lync 2013 客户端结合使用。</span><span class="sxs-lookup"><span data-stu-id="16569-108">The Lync VDI Plug-in is a stand-alone application that installs on the local computer and allows the use of local audio and video devices with the Lync 2013 client running on the virtual machine.</span></span> <span data-ttu-id="16569-109">该插件不要求在本地计算机上安装 Lync。</span><span class="sxs-lookup"><span data-stu-id="16569-109">The plug-in does not require Lync to be installed on the local computer.</span></span> <span data-ttu-id="16569-110">用户登录到在虚拟机上运行的 Lync 2013 客户端后，Lync 会提示用户重新输入其凭据，以与本地计算机上运行的 Lync VDI 插件建立连接。</span><span class="sxs-lookup"><span data-stu-id="16569-110">After the user signs in to the Lync 2013 client that is running on the virtual machine, Lync prompts the user to re-enter his or her credentials to establish a connection with the Lync VDI Plug-in that is running on the local computer.</span></span> <span data-ttu-id="16569-111">建立此连接后，用户可以发出和接收音频和视频呼叫。</span><span class="sxs-lookup"><span data-stu-id="16569-111">After this connection is established, the user is ready to make and receive audio and video calls.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="16569-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="16569-112">In This Section</span></span>

  - [<span data-ttu-id="16569-113">Lync Server 2013 中的 lync VDI 插件先决条件</span><span class="sxs-lookup"><span data-stu-id="16569-113">Lync VDI plug-in prerequisites in Lync Server 2013</span></span>](lync-server-2013-lync-vdi-plug-in-prerequisites.md)

  - [<span data-ttu-id="16569-114">为 VDI 准备 Lync Server 2013 环境</span><span class="sxs-lookup"><span data-stu-id="16569-114">Preparing your Lync Server 2013 environment for VDI</span></span>](lync-server-2013-preparing-your-environment-for-vdi.md)

  - [<span data-ttu-id="16569-115">在虚拟机上登录和使用 Lync 2013</span><span class="sxs-lookup"><span data-stu-id="16569-115">Signing in and using Lync 2013 on the virtual machine</span></span>](lync-server-2013-signing-in-and-using-lync-2013-on-the-virtual-machine.md)

  - [<span data-ttu-id="16569-116">在 Lync Server 2013 中对 Lync VDI 插件进行故障排除</span><span class="sxs-lookup"><span data-stu-id="16569-116">Troubleshooting the Lync VDI plug-in in Lync Server 2013</span></span>](lync-server-2013-troubleshooting-the-lync-vdi-plug-in.md)

  - [<span data-ttu-id="16569-117">Lync Server 2013 中支持的虚拟化技术和已知限制</span><span class="sxs-lookup"><span data-stu-id="16569-117">Supported virtualization technologies and known limitations in Lync Server 2013</span></span>](lync-server-2013-supported-virtualization-technologies-and-known-limitations.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

