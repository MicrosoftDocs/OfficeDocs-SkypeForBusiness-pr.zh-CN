---
title: 先决条件
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Prerequisites
ms:assetid: 48016bea-be3b-4ba5-8df8-d8ad4d9243d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945592(v=OCS.15)
ms:contentKeyID: 51541417
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 394f73c83f1981e4c4ee1528c1623f6424d2a85a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743562"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prerequisites"></a><span data-ttu-id="4cc25-102">先决条件</span><span class="sxs-lookup"><span data-stu-id="4cc25-102">Prerequisites</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4cc25-103">_**主题上次修改时间：** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="4cc25-103">_**Topic Last Modified:** 2013-02-19_</span></span>

<span data-ttu-id="4cc25-104">需要运行 Lync Server 2013 应力和性能工具的各种硬件、软件和系统配置要求。</span><span class="sxs-lookup"><span data-stu-id="4cc25-104">There are various hardware, software, and system configuration requirements that you’ll need to run the Lync Server 2013 Stress and Performance Tool.</span></span>

<div>

## <a name="client-hardware-requirements"></a><span data-ttu-id="4cc25-105">客户端硬件要求</span><span class="sxs-lookup"><span data-stu-id="4cc25-105">Client Hardware Requirements</span></span>

<span data-ttu-id="4cc25-106">若要在 Lync Server 2013 部署上运行 Lync Server 2013 应力和性能工具，对于要模拟其负载的每个4500用户，您至少需要一台专用计算机，满足以下最低硬件要求：</span><span class="sxs-lookup"><span data-stu-id="4cc25-106">To run the Lync Server 2013 Stress and Performance Tool on your Lync Server 2013 deployment, for every 4,500 users whose load you want to simulate, you’ll need at least one dedicated computer that meets the following minimum hardware requirements:</span></span>

  - <span data-ttu-id="4cc25-107">1 GB 的网络适配器</span><span class="sxs-lookup"><span data-stu-id="4cc25-107">1 gigabit network adapter</span></span>

  - <span data-ttu-id="4cc25-108">8 GB ram</span><span class="sxs-lookup"><span data-stu-id="4cc25-108">8-GB ram</span></span>

  - <span data-ttu-id="4cc25-109">2个双核中央处理单元（Cpu）</span><span class="sxs-lookup"><span data-stu-id="4cc25-109">2 dual-core central processing units (CPUs)</span></span>

</div>

<div>

## <a name="client-software-requirements"></a><span data-ttu-id="4cc25-110">客户端软件要求</span><span class="sxs-lookup"><span data-stu-id="4cc25-110">Client Software Requirements</span></span>

<span data-ttu-id="4cc25-111">若要在 Lync Server 2013 部署上运行 Lync Server 2013 应力和性能工具，受支持的操作系统包括：</span><span class="sxs-lookup"><span data-stu-id="4cc25-111">To run the Lync Server 2013 Stress and Performance Tool on your Lync Server 2013 deployment, the supported operating systems are:</span></span>

  - <span data-ttu-id="4cc25-112">Windows Server 2012 操作系统</span><span class="sxs-lookup"><span data-stu-id="4cc25-112">Windows Server 2012 operating system</span></span>

  - <span data-ttu-id="4cc25-113">Windows Server 2008 操作系统（64位版）</span><span class="sxs-lookup"><span data-stu-id="4cc25-113">Windows Server 2008 operating system (64-bit edition)</span></span>

<span data-ttu-id="4cc25-114">客户端计算机必须满足以下软件要求：</span><span class="sxs-lookup"><span data-stu-id="4cc25-114">Your client computer must meet the following software requirements:</span></span>

  - <span data-ttu-id="4cc25-115">必须安装[Microsoft .Net Framework 4.5](http://go.microsoft.com/fwlink/?linkid=143212)运行时。</span><span class="sxs-lookup"><span data-stu-id="4cc25-115">You must have the [Microsoft .NET Framework 4.5](http://go.microsoft.com/fwlink/?linkid=143212) runtime installed.</span></span>

  - <span data-ttu-id="4cc25-116">在 Windows Server 2008/Windows Server 2012 上，必须启用 "桌面体验" 功能。</span><span class="sxs-lookup"><span data-stu-id="4cc25-116">On Windows Server 2008/Windows Server 2012, the Desktop Experience feature must be enabled.</span></span>

  - <span data-ttu-id="4cc25-117">必须已安装[Microsoft Visual c + + 2012 可再发行程序包](http://go.microsoft.com/fwlink/?linkid=143216)（x64）。</span><span class="sxs-lookup"><span data-stu-id="4cc25-117">You must have the [Microsoft Visual C++ 2012 redistributable package](http://go.microsoft.com/fwlink/?linkid=143216) (x64) installed.</span></span>

  - <span data-ttu-id="4cc25-118">已完全配置的 Lync Server 2013 部署。</span><span class="sxs-lookup"><span data-stu-id="4cc25-118">A fully configured Lync Server 2013 deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="4cc25-119">Microsoft 统一通信托管 API （UCMA）4.0 库包含在安装包中，因此 UCMA 不是必需的，也不应在客户端计算机上安装。</span><span class="sxs-lookup"><span data-stu-id="4cc25-119">Microsoft Unified Communications Managed API (UCMA) 4.0 libraries are included in the installation package, so UCMA is not required and should not be installed on client computers.</span></span>



</div>

</div>

<div>

## <a name="configuration-requirements"></a><span data-ttu-id="4cc25-120">配置要求</span><span class="sxs-lookup"><span data-stu-id="4cc25-120">Configuration Requirements</span></span>

<span data-ttu-id="4cc25-121">将运行 Lync Server 2013 应力和性能工具的计算机必须按照以下要求进行配置：</span><span class="sxs-lookup"><span data-stu-id="4cc25-121">The computers that will run the Lync Server 2013 Stress and Performance Tool must be configured according to the following requirements:</span></span>

1.  <span data-ttu-id="4cc25-122">您必须以 "域" 或 "本地管理员" 组的成员身份登录。</span><span class="sxs-lookup"><span data-stu-id="4cc25-122">You must be logged on as a member of the Domain or Local Admins group.</span></span>

2.  <span data-ttu-id="4cc25-123">Lync Server 2013 应力和性能工具（LyncPerfTool）无法在同时运行 Lync Server 2013 组件的计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="4cc25-123">Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe) cannot be run on a computer that is also running Lync Server 2013 components.</span></span>

3.  <span data-ttu-id="4cc25-124">必须在前端服务器或用户帐户所驻留的标准版服务器上运行 Lync Server 2013 用户创建工具（UserProvisioningTool）。</span><span class="sxs-lookup"><span data-stu-id="4cc25-124">You must run the Lync Server 2013 User Creation tool (UserProvisioningTool.exe) on the Front End Server or on the Standard Edition server where the user accounts will reside.</span></span> <span data-ttu-id="4cc25-125">当该工具运行多次时，已启用 Microsoft 统一通信的每个用户都必须具有唯一的电话号码。</span><span class="sxs-lookup"><span data-stu-id="4cc25-125">When the tool is run multiple times, each user who is enabled for Microsoft Unified Communications must have a unique phone number.</span></span>

4.  <span data-ttu-id="4cc25-126">页面文件大小应由系统管理，或者在系统上的 RAM 数量至少应为1.5 倍。</span><span class="sxs-lookup"><span data-stu-id="4cc25-126">The page file size should be system-managed, or should be at least 1.5 times the amount of RAM on the system.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

