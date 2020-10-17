---
title: 先决条件
description: 组件.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Prerequisites
ms:assetid: 48016bea-be3b-4ba5-8df8-d8ad4d9243d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945592(v=OCS.15)
ms:contentKeyID: 51541417
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 936e52961539ed57fe1b610d42fb1c9cf35589b0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560098"
---
# <a name="prerequisites"></a><span data-ttu-id="30c11-103">先决条件</span><span class="sxs-lookup"><span data-stu-id="30c11-103">Prerequisites</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="30c11-104">_**上次修改的主题：** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="30c11-104">_**Topic Last Modified:** 2013-02-19_</span></span>

<span data-ttu-id="30c11-105">需要运行 Lync Server 2013 压力和性能工具的各种硬件、软件和系统配置要求。</span><span class="sxs-lookup"><span data-stu-id="30c11-105">There are various hardware, software, and system configuration requirements that you’ll need to run the Lync Server 2013 Stress and Performance Tool.</span></span>

<div>

## <a name="client-hardware-requirements"></a><span data-ttu-id="30c11-106">客户端硬件要求</span><span class="sxs-lookup"><span data-stu-id="30c11-106">Client Hardware Requirements</span></span>

<span data-ttu-id="30c11-107">若要在 Lync Server 2013 部署中运行 Lync Server 2013 压力和性能工具，请针对要模拟其负载的每个4500用户，至少需要一台满足以下最低硬件要求的专用计算机：</span><span class="sxs-lookup"><span data-stu-id="30c11-107">To run the Lync Server 2013 Stress and Performance Tool on your Lync Server 2013 deployment, for every 4,500 users whose load you want to simulate, you’ll need at least one dedicated computer that meets the following minimum hardware requirements:</span></span>

  - <span data-ttu-id="30c11-108">1个千兆网络适配器</span><span class="sxs-lookup"><span data-stu-id="30c11-108">1 gigabit network adapter</span></span>

  - <span data-ttu-id="30c11-109">8 GB ram</span><span class="sxs-lookup"><span data-stu-id="30c11-109">8-GB ram</span></span>

  - <span data-ttu-id="30c11-110">2 (Cpu 的核心中央处理单元) </span><span class="sxs-lookup"><span data-stu-id="30c11-110">2 dual-core central processing units (CPUs)</span></span>

</div>

<div>

## <a name="client-software-requirements"></a><span data-ttu-id="30c11-111">客户端软件要求</span><span class="sxs-lookup"><span data-stu-id="30c11-111">Client Software Requirements</span></span>

<span data-ttu-id="30c11-112">若要在 Lync Server 2013 部署上运行 Lync Server 2013 压力和性能工具，受支持的操作系统为：</span><span class="sxs-lookup"><span data-stu-id="30c11-112">To run the Lync Server 2013 Stress and Performance Tool on your Lync Server 2013 deployment, the supported operating systems are:</span></span>

  - <span data-ttu-id="30c11-113">Windows Server 2012 操作系统</span><span class="sxs-lookup"><span data-stu-id="30c11-113">Windows Server 2012 operating system</span></span>

  - <span data-ttu-id="30c11-114">Windows Server 2008 操作系统 (64-位版本) </span><span class="sxs-lookup"><span data-stu-id="30c11-114">Windows Server 2008 operating system (64-bit edition)</span></span>

<span data-ttu-id="30c11-115">您的客户端计算机必须满足以下软件要求：</span><span class="sxs-lookup"><span data-stu-id="30c11-115">Your client computer must meet the following software requirements:</span></span>

  - <span data-ttu-id="30c11-116">您必须已安装 [Microsoft .Net Framework 4.5](https://go.microsoft.com/fwlink/?linkid=143212) 运行时。</span><span class="sxs-lookup"><span data-stu-id="30c11-116">You must have the [Microsoft .NET Framework 4.5](https://go.microsoft.com/fwlink/?linkid=143212) runtime installed.</span></span>

  - <span data-ttu-id="30c11-117">在 Windows Server 2008/Windows Server 2012 中，必须启用 "桌面体验" 功能。</span><span class="sxs-lookup"><span data-stu-id="30c11-117">On Windows Server 2008/Windows Server 2012, the Desktop Experience feature must be enabled.</span></span>

  - <span data-ttu-id="30c11-118">您必须安装了 [Microsoft Visual c + + 2012 可再发行软件包](https://go.microsoft.com/fwlink/?linkid=143216) (x64) 。</span><span class="sxs-lookup"><span data-stu-id="30c11-118">You must have the [Microsoft Visual C++ 2012 redistributable package](https://go.microsoft.com/fwlink/?linkid=143216) (x64) installed.</span></span>

  - <span data-ttu-id="30c11-119">完全配置的 Lync Server 2013 部署。</span><span class="sxs-lookup"><span data-stu-id="30c11-119">A fully configured Lync Server 2013 deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="30c11-120">Microsoft 统一通信托管 API (UCMA) 4.0 库包含在安装程序包中，因此 UCMA 不是必需的，也不应安装在客户端计算机上。</span><span class="sxs-lookup"><span data-stu-id="30c11-120">Microsoft Unified Communications Managed API (UCMA) 4.0 libraries are included in the installation package, so UCMA is not required and should not be installed on client computers.</span></span>



</div>

</div>

<div>

## <a name="configuration-requirements"></a><span data-ttu-id="30c11-121">配置要求</span><span class="sxs-lookup"><span data-stu-id="30c11-121">Configuration Requirements</span></span>

<span data-ttu-id="30c11-122">将运行 Lync Server 2013 压力和性能工具的计算机必须按照以下要求进行配置：</span><span class="sxs-lookup"><span data-stu-id="30c11-122">The computers that will run the Lync Server 2013 Stress and Performance Tool must be configured according to the following requirements:</span></span>

1.  <span data-ttu-id="30c11-123">您必须以域或本地管理员组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="30c11-123">You must be logged on as a member of the Domain or Local Admins group.</span></span>

2.  <span data-ttu-id="30c11-124">Lync Server 2013 压力和性能工具 ( # A0) 不能在同时运行 Lync Server 2013 组件的计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="30c11-124">Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe) cannot be run on a computer that is also running Lync Server 2013 components.</span></span>

3.  <span data-ttu-id="30c11-125">必须在前端服务器上或用户帐户将驻留的 Standard Edition 服务器上运行 Lync Server 2013 用户创建工具 ( # A0) 。</span><span class="sxs-lookup"><span data-stu-id="30c11-125">You must run the Lync Server 2013 User Creation tool (UserProvisioningTool.exe) on the Front End Server or on the Standard Edition server where the user accounts will reside.</span></span> <span data-ttu-id="30c11-126">当该工具运行多次时，为 Microsoft 统一通信启用的每个用户都必须具有唯一的电话号码。</span><span class="sxs-lookup"><span data-stu-id="30c11-126">When the tool is run multiple times, each user who is enabled for Microsoft Unified Communications must have a unique phone number.</span></span>

4.  <span data-ttu-id="30c11-127">页面文件大小应由系统管理，或者应至少为系统上的 RAM 量的1.5 倍。</span><span class="sxs-lookup"><span data-stu-id="30c11-127">The page file size should be system-managed, or should be at least 1.5 times the amount of RAM on the system.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

