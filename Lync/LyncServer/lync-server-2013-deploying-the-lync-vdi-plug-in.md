---
title: Lync Server 2013：部署 Lync VDI 插件
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
ms.openlocfilehash: d51b1858e3e1944d290d907ee14691786bf3cc53
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740772"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-the-lync-vdi-plug-in-in-lync-server-2013"></a><span data-ttu-id="175f0-102">在 Lync Server 2013 中部署 Lync VDI 插件</span><span class="sxs-lookup"><span data-stu-id="175f0-102">Deploying the Lync VDI plug-in in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="175f0-103">_**主题上次修改时间：** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="175f0-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="175f0-104">Lync 2013 客户端支持虚拟桌面基础结构（VDI）环境中的音频和视频。</span><span class="sxs-lookup"><span data-stu-id="175f0-104">The Lync 2013 client supports audio and video in a Virtual Desktop Infrastructure (VDI) environment.</span></span> <span data-ttu-id="175f0-105">用户可以将音频或视频设备（例如，耳机或相机）连接到本地计算机（例如，瘦客户端或重新使用用途的计算机）。</span><span class="sxs-lookup"><span data-stu-id="175f0-105">A user can connect an audio or video device (for example, a headset or a camera) to the local computer (for example, a thin client or repurposed computer).</span></span> <span data-ttu-id="175f0-106">用户可以连接到虚拟机，登录到在虚拟机上运行的 Lync 2013 客户端，并参与实时音频和视频通信，就像客户端在本地运行一样。</span><span class="sxs-lookup"><span data-stu-id="175f0-106">The user can connect to the virtual machine, sign in to the Lync 2013 client that is running on the virtual machine, and participate in real-time audio and video communications as though the client is running locally.</span></span>

<span data-ttu-id="175f0-107">Lync VDI 插件是一个独立的应用程序，可在本地计算机上安装，并允许将本地音频和视频设备与在虚拟机上运行的 Lync 2013 客户端配合使用。</span><span class="sxs-lookup"><span data-stu-id="175f0-107">The Lync VDI Plug-in is a stand-alone application that installs on the local computer and allows the use of local audio and video devices with the Lync 2013 client running on the virtual machine.</span></span> <span data-ttu-id="175f0-108">插件不需要在本地计算机上安装 Lync。</span><span class="sxs-lookup"><span data-stu-id="175f0-108">The plug-in does not require Lync to be installed on the local computer.</span></span> <span data-ttu-id="175f0-109">用户登录到在虚拟机上运行的 Lync 2013 客户端后，Lync 将提示用户重新输入其凭据，以便与在本地计算机上运行的 Lync VDI 插件建立连接。</span><span class="sxs-lookup"><span data-stu-id="175f0-109">After the user signs in to the Lync 2013 client that is running on the virtual machine, Lync prompts the user to re-enter his or her credentials to establish a connection with the Lync VDI Plug-in that is running on the local computer.</span></span> <span data-ttu-id="175f0-110">建立此连接后，用户即可开始进行音频和视频通话。</span><span class="sxs-lookup"><span data-stu-id="175f0-110">After this connection is established, the user is ready to make and receive audio and video calls.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="175f0-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="175f0-111">In This Section</span></span>

  - [<span data-ttu-id="175f0-112">Lync Server 2013 中的 Lync VDI 插件先决条件</span><span class="sxs-lookup"><span data-stu-id="175f0-112">Lync VDI plug-in prerequisites in Lync Server 2013</span></span>](lync-server-2013-lync-vdi-plug-in-prerequisites.md)

  - [<span data-ttu-id="175f0-113">针对 VDI 准备 Lync Server 2013 环境</span><span class="sxs-lookup"><span data-stu-id="175f0-113">Preparing your Lync Server 2013 environment for VDI</span></span>](lync-server-2013-preparing-your-environment-for-vdi.md)

  - [<span data-ttu-id="175f0-114">登录虚拟机并使用 Lync 2013</span><span class="sxs-lookup"><span data-stu-id="175f0-114">Signing in and using Lync 2013 on the virtual machine</span></span>](lync-server-2013-signing-in-and-using-lync-2013-on-the-virtual-machine.md)

  - [<span data-ttu-id="175f0-115">在 Lync Server 2013 中对 Lync VDI 插件进行故障排除</span><span class="sxs-lookup"><span data-stu-id="175f0-115">Troubleshooting the Lync VDI plug-in in Lync Server 2013</span></span>](lync-server-2013-troubleshooting-the-lync-vdi-plug-in.md)

  - [<span data-ttu-id="175f0-116">Lync Server 2013 中支持的虚拟化技术和已知限制</span><span class="sxs-lookup"><span data-stu-id="175f0-116">Supported virtualization technologies and known limitations in Lync Server 2013</span></span>](lync-server-2013-supported-virtualization-technologies-and-known-limitations.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

