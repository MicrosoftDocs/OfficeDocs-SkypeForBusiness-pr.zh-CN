---
title: Skype for Busines 压力和性能工具的先决条件和设置
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 12/20/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 948c176c-75ce-418d-891a-a68427d61e40
description: Skype for Business Server 2015 压力和性能工具的要求或先决条件。 如何安装或设置压力和性能工具。
ms.openlocfilehash: a58eb5e291878bea74365cd1b9519983c7a77a84
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814952"
---
# <a name="prerequisites-and-setup-for-the-skype-for-busines-stress-and-performance-tool"></a><span data-ttu-id="30dff-104">Skype for Busines 压力和性能工具的先决条件和设置</span><span class="sxs-lookup"><span data-stu-id="30dff-104">Prerequisites and setup for the Skype for Busines Stress and Performance Tool</span></span>
 
<span data-ttu-id="30dff-105">Skype for Business Server 2015 压力和性能工具的要求或先决条件。</span><span class="sxs-lookup"><span data-stu-id="30dff-105">Requirements or prerequisites for the Skype for Business Server 2015 Stress and Performance Tool.</span></span> <span data-ttu-id="30dff-106">如何安装或设置压力和性能工具。</span><span class="sxs-lookup"><span data-stu-id="30dff-106">How to install or setup the Stress and Performance Tool.</span></span>
  
<span data-ttu-id="30dff-107">我们在运行压力和性能工具之前，需要了解以下硬件、软件和系统配置要求：</span><span class="sxs-lookup"><span data-stu-id="30dff-107">We have the following sections of hardware, software and system configuration requirements you'll need to be aware of prior to running the Stress and Performance Tool:</span></span>
  
- [<span data-ttu-id="30dff-108">客户端硬件要求</span><span class="sxs-lookup"><span data-stu-id="30dff-108">Client hardware requirements</span></span>](prerequisites-and-setup.md#ClientHardwareReqs)
    
- [<span data-ttu-id="30dff-109">客户端软件要求</span><span class="sxs-lookup"><span data-stu-id="30dff-109">Client software requirements</span></span>](prerequisites-and-setup.md#ClientSoftwareReqs)
    
- [<span data-ttu-id="30dff-110">配置要求</span><span class="sxs-lookup"><span data-stu-id="30dff-110">Configuration requirements</span></span>](prerequisites-and-setup.md#ConfigReqs)
    
<span data-ttu-id="30dff-111">此外，我们在下面还有一个有关安装 [Skype for Business Server 2015 压力和性能工具的部分](prerequisites-and-setup.md#Installing)</span><span class="sxs-lookup"><span data-stu-id="30dff-111">Additionally, we also have a section below for [Installing the Skype for Business Server 2015 Stress and Performance Tool](prerequisites-and-setup.md#Installing)</span></span>
  
## <a name="client-hardware-requirements"></a><span data-ttu-id="30dff-112">客户端硬件要求</span><span class="sxs-lookup"><span data-stu-id="30dff-112">Client hardware requirements</span></span>
<span data-ttu-id="30dff-113"><a name="ClientHardwareReqs"> </a></span><span class="sxs-lookup"><span data-stu-id="30dff-113"><a name="ClientHardwareReqs"> </a></span></span>

<span data-ttu-id="30dff-114">针对 Skype for Business Server 2015 部署运行压力和性能工具时，至少需要满足测试中每 4500 个用户以下硬件要求：</span><span class="sxs-lookup"><span data-stu-id="30dff-114">When running the Stress and Performance Tool against your Skype for Business Server 2015 deployment, you'll, at a minimum, need these hardware requirements met for every 4500 users in your test:</span></span>
  
- <span data-ttu-id="30dff-115">1 GB 网络适配器</span><span class="sxs-lookup"><span data-stu-id="30dff-115">1 gigabit network adapter</span></span>
    
- <span data-ttu-id="30dff-116">8 GB RAM</span><span class="sxs-lookup"><span data-stu-id="30dff-116">8 GB RAM</span></span>
    
- <span data-ttu-id="30dff-117">2 个双核 CPU</span><span class="sxs-lookup"><span data-stu-id="30dff-117">2 dual-core CPUs</span></span>
    
## <a name="client-software-requirements"></a><span data-ttu-id="30dff-118">客户端软件要求</span><span class="sxs-lookup"><span data-stu-id="30dff-118">Client software requirements</span></span>
<span data-ttu-id="30dff-119"><a name="ClientSoftwareReqs"> </a></span><span class="sxs-lookup"><span data-stu-id="30dff-119"><a name="ClientSoftwareReqs"> </a></span></span>

<span data-ttu-id="30dff-120">压力和性能工具支持的操作系统包括：</span><span class="sxs-lookup"><span data-stu-id="30dff-120">The supported operating systems for the Stress and Performance Tool are:</span></span>
  
- <span data-ttu-id="30dff-121">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="30dff-121">Windows Server 2012</span></span>
    
- <span data-ttu-id="30dff-122">Windows Server 2008 (64 位) </span><span class="sxs-lookup"><span data-stu-id="30dff-122">Windows Server 2008 (64-bit)</span></span>
    
<span data-ttu-id="30dff-123">此外，计算机需要满足以下软件要求：</span><span class="sxs-lookup"><span data-stu-id="30dff-123">Additionally, computers need to meet the following software requirements:</span></span>
  
- <span data-ttu-id="30dff-124">你需要安装 Microsoft .NET 4.5 Framework。</span><span class="sxs-lookup"><span data-stu-id="30dff-124">You'll need the Microsoft .NET 4.5 Framework installed.</span></span> [<span data-ttu-id="30dff-125">在此处下载 .Net 4.5 Framework。</span><span class="sxs-lookup"><span data-stu-id="30dff-125">Download the .Net 4.5 Framework here.</span></span>](https://www.microsoft.com/download/details.aspx?id=30653)
    
- <span data-ttu-id="30dff-126">你需要在 Windows 中启用桌面体验功能。</span><span class="sxs-lookup"><span data-stu-id="30dff-126">You'll need the Desktop Experience feature enabled in Windows.</span></span>
    
- <span data-ttu-id="30dff-127">你需要安装 Microsoft Visual C++ 2013 (x64) 。</span><span class="sxs-lookup"><span data-stu-id="30dff-127">You'll need Microsoft Visual C++ 2013 (x64) installed.</span></span> [<span data-ttu-id="30dff-128">在此处下载 Visual C++ 2013</span><span class="sxs-lookup"><span data-stu-id="30dff-128">Download Visual C++ 2013 here</span></span>](https://www.microsoft.com/download/details.aspx?id=40784)
    
- <span data-ttu-id="30dff-129">你需要成功部署 Skype for Business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="30dff-129">You're going to need Skype for Business Server 2015 successfully deployed.</span></span>
    
## <a name="configuration-requirements"></a><span data-ttu-id="30dff-130">配置要求</span><span class="sxs-lookup"><span data-stu-id="30dff-130">Configuration requirements</span></span>
<span data-ttu-id="30dff-131"><a name="ConfigReqs"> </a></span><span class="sxs-lookup"><span data-stu-id="30dff-131"><a name="ConfigReqs"> </a></span></span>

<span data-ttu-id="30dff-132">需要完成以下其他配置，以成功运行压力和性能工具：</span><span class="sxs-lookup"><span data-stu-id="30dff-132">You'll need these additional configurations done to run the Stress and Performance Tool successfully:</span></span>
  
- <span data-ttu-id="30dff-133">您需要以 Domain 或 Local Administrator 组的成员登录服务器。</span><span class="sxs-lookup"><span data-stu-id="30dff-133">You need to log into the server as a member of the Domain or Local Administrator's group.</span></span>
    
- <span data-ttu-id="30dff-134">不能将 Skype for Business Server 2015 用户创建工具 (UserProvisioningTool.exe) 安装在用户帐户将驻留的任何前端服务器或 Standard Edition 服务器上。</span><span class="sxs-lookup"><span data-stu-id="30dff-134">You can't install the Skype for Business Server 2015 User Creation tool (UserProvisioningTool.exe) on any Front End Server or Standard Edition server where the user accounts will reside.</span></span>
    
- <span data-ttu-id="30dff-135">多次运行用户创建工具时，启用了 Microsoft 统一通信的每个用户都需要有唯一的电话号码。</span><span class="sxs-lookup"><span data-stu-id="30dff-135">When the User Creation tool is run multiple times, each user who's enabled for Microsoft Unified Communications needs to have a unique phone number.</span></span>
    
- <span data-ttu-id="30dff-136">页面文件大小应进行系统管理，否则需要至少是计算机系统中 RAM 大小的 1.5 倍。</span><span class="sxs-lookup"><span data-stu-id="30dff-136">The page file size should be systems-managed, or otherwise needs to be at least 1.5 times the amount of RAM in the computer system.</span></span>
    
## <a name="installing-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="30dff-137">安装 Skype for Business Server 2015 压力和性能工具</span><span class="sxs-lookup"><span data-stu-id="30dff-137">Installing the Skype for Business Server 2015 Stress and Performance Tool</span></span>
<span data-ttu-id="30dff-138"><a name="Installing"> </a></span><span class="sxs-lookup"><span data-stu-id="30dff-138"><a name="Installing"> </a></span></span>

<span data-ttu-id="30dff-139">安装非常简单。</span><span class="sxs-lookup"><span data-stu-id="30dff-139">Installing couldn't be simpler.</span></span> <span data-ttu-id="30dff-140">你需要在要用于模拟用户流量的每个客户端计算机上运行 Windows Installer 文件 **CapacityPlanningTool.msi，** 在将创建用户和联系人的每个池中的前端服务器上运行该文件。</span><span class="sxs-lookup"><span data-stu-id="30dff-140">You need to run the Windows Installer file, **CapacityPlanningTool.msi**, on each client computer you're going to use to simulate user traffic, and on a Front End Server in each pool where you'll create users and contacts.</span></span>
  
<span data-ttu-id="30dff-141">若要下载 .msi 以及我们其他文章中提及的示例脚本，请转到下载中心链接 [：Skype for Business Server 2015](https://www.microsoft.com/download/details.aspx?id=50367)压力和性能工具。</span><span class="sxs-lookup"><span data-stu-id="30dff-141">To download the .msi, along with the sample scripts mentioned in our other articles, go to the Download Center link: [Skype for Business Server 2015, Stress and Performance Tool](https://www.microsoft.com/download/details.aspx?id=50367).</span></span>
  

