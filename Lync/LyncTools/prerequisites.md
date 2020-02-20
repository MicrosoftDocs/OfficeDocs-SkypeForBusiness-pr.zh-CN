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
ms.openlocfilehash: 3c5ffc74e80547df1dd451cd86d681e85befe334
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146295"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="prerequisites"></a><span data-ttu-id="e1ccd-102">先决条件</span><span class="sxs-lookup"><span data-stu-id="e1ccd-102">Prerequisites</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e1ccd-103">_**上次修改的主题：** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="e1ccd-103">_**Topic Last Modified:** 2013-02-19_</span></span>

<span data-ttu-id="e1ccd-104">需要运行 Lync Server 2013 压力和性能工具的各种硬件、软件和系统配置要求。</span><span class="sxs-lookup"><span data-stu-id="e1ccd-104">There are various hardware, software, and system configuration requirements that you’ll need to run the Lync Server 2013 Stress and Performance Tool.</span></span>

<div>

## <a name="client-hardware-requirements"></a><span data-ttu-id="e1ccd-105">客户端硬件要求</span><span class="sxs-lookup"><span data-stu-id="e1ccd-105">Client Hardware Requirements</span></span>

<span data-ttu-id="e1ccd-106">若要在 Lync Server 2013 部署中运行 Lync Server 2013 压力和性能工具，请针对要模拟其负载的每个4500用户，至少需要一台满足以下最低硬件要求的专用计算机：</span><span class="sxs-lookup"><span data-stu-id="e1ccd-106">To run the Lync Server 2013 Stress and Performance Tool on your Lync Server 2013 deployment, for every 4,500 users whose load you want to simulate, you’ll need at least one dedicated computer that meets the following minimum hardware requirements:</span></span>

  - <span data-ttu-id="e1ccd-107">1个千兆网络适配器</span><span class="sxs-lookup"><span data-stu-id="e1ccd-107">1 gigabit network adapter</span></span>

  - <span data-ttu-id="e1ccd-108">8 GB ram</span><span class="sxs-lookup"><span data-stu-id="e1ccd-108">8-GB ram</span></span>

  - <span data-ttu-id="e1ccd-109">2个双核中央处理单元（Cpu）</span><span class="sxs-lookup"><span data-stu-id="e1ccd-109">2 dual-core central processing units (CPUs)</span></span>

</div>

<div>

## <a name="client-software-requirements"></a><span data-ttu-id="e1ccd-110">客户端软件要求</span><span class="sxs-lookup"><span data-stu-id="e1ccd-110">Client Software Requirements</span></span>

<span data-ttu-id="e1ccd-111">若要在 Lync Server 2013 部署上运行 Lync Server 2013 压力和性能工具，受支持的操作系统为：</span><span class="sxs-lookup"><span data-stu-id="e1ccd-111">To run the Lync Server 2013 Stress and Performance Tool on your Lync Server 2013 deployment, the supported operating systems are:</span></span>

  - <span data-ttu-id="e1ccd-112">Windows Server 2012 操作系统</span><span class="sxs-lookup"><span data-stu-id="e1ccd-112">Windows Server 2012 operating system</span></span>

  - <span data-ttu-id="e1ccd-113">Windows Server 2008 操作系统（64-位版本）</span><span class="sxs-lookup"><span data-stu-id="e1ccd-113">Windows Server 2008 operating system (64-bit edition)</span></span>

<span data-ttu-id="e1ccd-114">您的客户端计算机必须满足以下软件要求：</span><span class="sxs-lookup"><span data-stu-id="e1ccd-114">Your client computer must meet the following software requirements:</span></span>

  - <span data-ttu-id="e1ccd-115">您必须已安装[Microsoft .Net Framework 4.5](https://go.microsoft.com/fwlink/?linkid=143212)运行时。</span><span class="sxs-lookup"><span data-stu-id="e1ccd-115">You must have the [Microsoft .NET Framework 4.5](https://go.microsoft.com/fwlink/?linkid=143212) runtime installed.</span></span>

  - <span data-ttu-id="e1ccd-116">在 Windows Server 2008/Windows Server 2012 中，必须启用 "桌面体验" 功能。</span><span class="sxs-lookup"><span data-stu-id="e1ccd-116">On Windows Server 2008/Windows Server 2012, the Desktop Experience feature must be enabled.</span></span>

  - <span data-ttu-id="e1ccd-117">您必须已安装[Microsoft Visual c + + 2012 可再发行组件包](https://go.microsoft.com/fwlink/?linkid=143216)（x64）。</span><span class="sxs-lookup"><span data-stu-id="e1ccd-117">You must have the [Microsoft Visual C++ 2012 redistributable package](https://go.microsoft.com/fwlink/?linkid=143216) (x64) installed.</span></span>

  - <span data-ttu-id="e1ccd-118">完全配置的 Lync Server 2013 部署。</span><span class="sxs-lookup"><span data-stu-id="e1ccd-118">A fully configured Lync Server 2013 deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e1ccd-119">Microsoft 统一通信托管 API （UCMA）4.0 库包含在安装包中，因此 UCMA 不是必需的，也不应安装在客户端计算机上。</span><span class="sxs-lookup"><span data-stu-id="e1ccd-119">Microsoft Unified Communications Managed API (UCMA) 4.0 libraries are included in the installation package, so UCMA is not required and should not be installed on client computers.</span></span>



</div>

</div>

<div>

## <a name="configuration-requirements"></a><span data-ttu-id="e1ccd-120">配置要求</span><span class="sxs-lookup"><span data-stu-id="e1ccd-120">Configuration Requirements</span></span>

<span data-ttu-id="e1ccd-121">将运行 Lync Server 2013 压力和性能工具的计算机必须按照以下要求进行配置：</span><span class="sxs-lookup"><span data-stu-id="e1ccd-121">The computers that will run the Lync Server 2013 Stress and Performance Tool must be configured according to the following requirements:</span></span>

1.  <span data-ttu-id="e1ccd-122">您必须以域或本地管理员组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="e1ccd-122">You must be logged on as a member of the Domain or Local Admins group.</span></span>

2.  <span data-ttu-id="e1ccd-123">Lync Server 2013 压力和性能工具（LyncPerfTool）无法在同时运行 Lync Server 2013 组件的计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="e1ccd-123">Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe) cannot be run on a computer that is also running Lync Server 2013 components.</span></span>

3.  <span data-ttu-id="e1ccd-124">必须在前端服务器上或用户帐户将驻留的 Standard Edition 服务器上运行 Lync Server 2013 用户创建工具（UserProvisioningTool）。</span><span class="sxs-lookup"><span data-stu-id="e1ccd-124">You must run the Lync Server 2013 User Creation tool (UserProvisioningTool.exe) on the Front End Server or on the Standard Edition server where the user accounts will reside.</span></span> <span data-ttu-id="e1ccd-125">当该工具运行多次时，为 Microsoft 统一通信启用的每个用户都必须具有唯一的电话号码。</span><span class="sxs-lookup"><span data-stu-id="e1ccd-125">When the tool is run multiple times, each user who is enabled for Microsoft Unified Communications must have a unique phone number.</span></span>

4.  <span data-ttu-id="e1ccd-126">页面文件大小应由系统管理，或者应至少为系统上的 RAM 量的1.5 倍。</span><span class="sxs-lookup"><span data-stu-id="e1ccd-126">The page file size should be system-managed, or should be at least 1.5 times the amount of RAM on the system.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

