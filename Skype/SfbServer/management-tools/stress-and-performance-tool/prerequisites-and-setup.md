---
title: Skype for Business 压力和性能工具的先决条件和设置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: 9389feedb21948604b1ea68319c5fc068a561679
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42005977"
---
# <a name="prerequisites-and-setup-for-the-skype-for-busines-stress-and-performance-tool"></a><span data-ttu-id="e9ce6-104">Skype for Business 压力和性能工具的先决条件和设置</span><span class="sxs-lookup"><span data-stu-id="e9ce6-104">Prerequisites and setup for the Skype for Busines Stress and Performance Tool</span></span>
 
<span data-ttu-id="e9ce6-105">Skype for Business Server 2015 压力和性能工具的要求或先决条件。</span><span class="sxs-lookup"><span data-stu-id="e9ce6-105">Requirements or prerequisites for the Skype for Business Server 2015 Stress and Performance Tool.</span></span> <span data-ttu-id="e9ce6-106">如何安装或设置压力和性能工具。</span><span class="sxs-lookup"><span data-stu-id="e9ce6-106">How to install or setup the Stress and Performance Tool.</span></span>
  
<span data-ttu-id="e9ce6-107">在运行压力和性能工具之前，我们有以下部分需要了解的硬件、软件和系统配置要求：</span><span class="sxs-lookup"><span data-stu-id="e9ce6-107">We have the following sections of hardware, software and system configuration requirements you'll need to be aware of prior to running the Stress and Performance Tool:</span></span>
  
- [<span data-ttu-id="e9ce6-108">客户端硬件要求</span><span class="sxs-lookup"><span data-stu-id="e9ce6-108">Client hardware requirements</span></span>](prerequisites-and-setup.md#ClientHardwareReqs)
    
- [<span data-ttu-id="e9ce6-109">客户端软件要求</span><span class="sxs-lookup"><span data-stu-id="e9ce6-109">Client software requirements</span></span>](prerequisites-and-setup.md#ClientSoftwareReqs)
    
- [<span data-ttu-id="e9ce6-110">配置要求</span><span class="sxs-lookup"><span data-stu-id="e9ce6-110">Configuration requirements</span></span>](prerequisites-and-setup.md#ConfigReqs)
    
<span data-ttu-id="e9ce6-111">此外，我们还提供了有关[安装 Skype For Business Server 2015 压力和性能工具](prerequisites-and-setup.md#Installing)的部分</span><span class="sxs-lookup"><span data-stu-id="e9ce6-111">Additionally, we also have a section below for [Installing the Skype for Business Server 2015 Stress and Performance Tool](prerequisites-and-setup.md#Installing)</span></span>
  
## <a name="client-hardware-requirements"></a><span data-ttu-id="e9ce6-112">客户端硬件要求</span><span class="sxs-lookup"><span data-stu-id="e9ce6-112">Client hardware requirements</span></span>
<span data-ttu-id="e9ce6-113"><a name="ClientHardwareReqs"> </a></span><span class="sxs-lookup"><span data-stu-id="e9ce6-113"><a name="ClientHardwareReqs"> </a></span></span>

<span data-ttu-id="e9ce6-114">在对 Skype for business Server 2015 部署运行压力和性能工具时，至少需要满足测试中的每个4500个用户的以下硬件要求：</span><span class="sxs-lookup"><span data-stu-id="e9ce6-114">When running the Stress and Performance Tool against your Skype for Business Server 2015 deployment, you'll, at a minimum, need these hardware requirements met for every 4500 users in your test:</span></span>
  
- <span data-ttu-id="e9ce6-115">1个千兆网络适配器</span><span class="sxs-lookup"><span data-stu-id="e9ce6-115">1 gigabit network adapter</span></span>
    
- <span data-ttu-id="e9ce6-116">8 GB RAM</span><span class="sxs-lookup"><span data-stu-id="e9ce6-116">8 GB RAM</span></span>
    
- <span data-ttu-id="e9ce6-117">2个双核 Cpu</span><span class="sxs-lookup"><span data-stu-id="e9ce6-117">2 dual-core CPUs</span></span>
    
## <a name="client-software-requirements"></a><span data-ttu-id="e9ce6-118">客户端软件要求</span><span class="sxs-lookup"><span data-stu-id="e9ce6-118">Client software requirements</span></span>
<span data-ttu-id="e9ce6-119"><a name="ClientSoftwareReqs"> </a></span><span class="sxs-lookup"><span data-stu-id="e9ce6-119"><a name="ClientSoftwareReqs"> </a></span></span>

<span data-ttu-id="e9ce6-120">压力和性能工具的受支持的操作系统是：</span><span class="sxs-lookup"><span data-stu-id="e9ce6-120">The supported operating systems for the Stress and Performance Tool are:</span></span>
  
- <span data-ttu-id="e9ce6-121">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="e9ce6-121">Windows Server 2012</span></span>
    
- <span data-ttu-id="e9ce6-122">Windows Server 2008 （64-位）</span><span class="sxs-lookup"><span data-stu-id="e9ce6-122">Windows Server 2008 (64-bit)</span></span>
    
<span data-ttu-id="e9ce6-123">此外，计算机需要满足以下软件要求：</span><span class="sxs-lookup"><span data-stu-id="e9ce6-123">Additionally, computers need to meet the following software requirements:</span></span>
  
- <span data-ttu-id="e9ce6-124">你将需要安装 Microsoft .NET 4.5 Framework。</span><span class="sxs-lookup"><span data-stu-id="e9ce6-124">You'll need the Microsoft .NET 4.5 Framework installed.</span></span> [<span data-ttu-id="e9ce6-125">在此处下载 .Net 4.5 框架。</span><span class="sxs-lookup"><span data-stu-id="e9ce6-125">Download the .Net 4.5 Framework here.</span></span>](https://www.microsoft.com/download/details.aspx?id=30653)
    
- <span data-ttu-id="e9ce6-126">你将需要在 Windows 中启用的 "桌面体验" 功能。</span><span class="sxs-lookup"><span data-stu-id="e9ce6-126">You'll need the Desktop Experience feature enabled in Windows.</span></span>
    
- <span data-ttu-id="e9ce6-127">你将需要安装 Microsoft Visual c + + 2013 （x64）。</span><span class="sxs-lookup"><span data-stu-id="e9ce6-127">You'll need Microsoft Visual C++ 2013 (x64) installed.</span></span> [<span data-ttu-id="e9ce6-128">在此处下载 Visual c + + 2013</span><span class="sxs-lookup"><span data-stu-id="e9ce6-128">Download Visual C++ 2013 here</span></span>](https://www.microsoft.com/download/details.aspx?id=40784)
    
- <span data-ttu-id="e9ce6-129">你需要成功部署 Skype for Business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="e9ce6-129">You're going to need Skype for Business Server 2015 successfully deployed.</span></span>
    
## <a name="configuration-requirements"></a><span data-ttu-id="e9ce6-130">配置要求</span><span class="sxs-lookup"><span data-stu-id="e9ce6-130">Configuration requirements</span></span>
<span data-ttu-id="e9ce6-131"><a name="ConfigReqs"> </a></span><span class="sxs-lookup"><span data-stu-id="e9ce6-131"><a name="ConfigReqs"> </a></span></span>

<span data-ttu-id="e9ce6-132">你将需要执行以下额外配置，以成功运行压力和性能工具：</span><span class="sxs-lookup"><span data-stu-id="e9ce6-132">You'll need these additional configurations done to run the Stress and Performance Tool successfully:</span></span>
  
- <span data-ttu-id="e9ce6-133">您需要以域或本地管理员组的成员身份登录到服务器。</span><span class="sxs-lookup"><span data-stu-id="e9ce6-133">You need to log into the server as a member of the Domain or Local Administrator's group.</span></span>
    
- <span data-ttu-id="e9ce6-134">您无法在用户帐户将驻留的任何前端服务器或 Standard Edition 服务器上安装 Skype for Business Server 2015 用户创建工具（UserProvisioningTool）。</span><span class="sxs-lookup"><span data-stu-id="e9ce6-134">You can't install the Skype for Business Server 2015 User Creation tool (UserProvisioningTool.exe) on any Front End Server or Standard Edition server where the user accounts will reside.</span></span>
    
- <span data-ttu-id="e9ce6-135">当用户创建工具运行多次时，为 Microsoft 统一通信启用的每个用户都需要具有唯一的电话号码。</span><span class="sxs-lookup"><span data-stu-id="e9ce6-135">When the User Creation tool is run multiple times, each user who's enabled for Microsoft Unified Communications needs to have a unique phone number.</span></span>
    
- <span data-ttu-id="e9ce6-136">页面文件大小应由系统管理，或者其他情况下必须至少为计算机系统中的 RAM 量的1.5 倍。</span><span class="sxs-lookup"><span data-stu-id="e9ce6-136">The page file size should be systems-managed, or otherwise needs to be at least 1.5 times the amount of RAM in the computer system.</span></span>
    
## <a name="installing-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="e9ce6-137">安装 Skype for Business Server 2015 压力和性能工具</span><span class="sxs-lookup"><span data-stu-id="e9ce6-137">Installing the Skype for Business Server 2015 Stress and Performance Tool</span></span>
<span data-ttu-id="e9ce6-138"><a name="Installing"> </a></span><span class="sxs-lookup"><span data-stu-id="e9ce6-138"><a name="Installing"> </a></span></span>

<span data-ttu-id="e9ce6-139">安装更为简单。</span><span class="sxs-lookup"><span data-stu-id="e9ce6-139">Installing couldn't be simpler.</span></span> <span data-ttu-id="e9ce6-140">您需要在要用于模拟用户通信的每台客户端计算机上运行 Windows Installer 文件**CapacityPlanningTool**，并在要创建用户和联系人的每个池中的前端服务器上运行。</span><span class="sxs-lookup"><span data-stu-id="e9ce6-140">You need to run the Windows Installer file, **CapacityPlanningTool.msi**, on each client computer you're going to use to simulate user traffic, and on a Front End Server in each pool where you'll create users and contacts.</span></span>
  
<span data-ttu-id="e9ce6-141">若要下载 .msi，以及我们其他文章中提到的示例脚本，请转到下载中心链接： [Skype For Business Server 2015、压力和性能工具](https://www.microsoft.com/download/details.aspx?id=50367)。</span><span class="sxs-lookup"><span data-stu-id="e9ce6-141">To download the .msi, along with the sample scripts mentioned in our other articles, go to the Download Center link: [Skype for Business Server 2015, Stress and Performance Tool](https://www.microsoft.com/download/details.aspx?id=50367).</span></span>
  

