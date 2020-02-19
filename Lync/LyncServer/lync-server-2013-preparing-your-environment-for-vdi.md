---
title: Lync Server 2013：为 VDI 准备环境
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing your environment for VDI
ms:assetid: a3ec2e13-1a73-4b1c-a54a-8db7d4cd50f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205154(v=OCS.15)
ms:contentKeyID: 48185052
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6d3d017709937a58ff93fe3827b571992235873a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139093"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="preparing-your-lync-server-2013-environment-for-vdi"></a><span data-ttu-id="3a013-102">为 VDI 准备 Lync Server 2013 环境</span><span class="sxs-lookup"><span data-stu-id="3a013-102">Preparing your Lync Server 2013 environment for VDI</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3a013-103">_**上次修改的主题：** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="3a013-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="3a013-104">若要为 Lync VDI 插件准备环境，管理员必须执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="3a013-104">To prepare the environment for the Lync VDI plug-in, the administrator must perform the following steps.</span></span>

1.  <span data-ttu-id="3a013-105">在 Lync Server 2013 中，确保所有 VDI 用户的 EnableMediaRedirection 设置为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="3a013-105">In Lync Server 2013, ensure that EnableMediaRedirection is set to TRUE for all VDI users.</span></span> <span data-ttu-id="3a013-106">有关详细信息，请参阅[set-csclientpolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) Cmdlet 和[Set-csclientpolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="3a013-106">For details, see the Help topics for the [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) cmdlet and the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) cmdlet.</span></span>

2.  <span data-ttu-id="3a013-107">在数据中心计算机上，在所有虚拟机上安装 Lync 2013 客户端。</span><span class="sxs-lookup"><span data-stu-id="3a013-107">On the data center computer, install the Lync 2013 client on all virtual machines.</span></span>

3.  <span data-ttu-id="3a013-108">在本地计算机上，安装 Lync VDI 插件。</span><span class="sxs-lookup"><span data-stu-id="3a013-108">On the local computers, install the Lync VDI plug-in.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

