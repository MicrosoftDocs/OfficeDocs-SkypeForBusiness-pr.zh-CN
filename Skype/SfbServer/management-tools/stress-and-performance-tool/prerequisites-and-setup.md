---
title: Skype for Business Stress and Performance Tool 的先决条件和设置
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
description: Skype for Business Server 2015 Stress and Performance Tool 的要求或先决条件。 如何安装或设置 Stress and Performance Tool。
ms.openlocfilehash: f52d92022e09314a8f9467cd939f67b2827cc153
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816171"
---
# <a name="prerequisites-and-setup-for-the-skype-for-busines-stress-and-performance-tool"></a><span data-ttu-id="83376-104">Skype for Business Stress and Performance Tool 的先决条件和设置</span><span class="sxs-lookup"><span data-stu-id="83376-104">Prerequisites and setup for the Skype for Busines Stress and Performance Tool</span></span>
 
<span data-ttu-id="83376-p102">Skype for Business Server 2015 Stress and Performance Tool 的要求或先决条件。 如何安装或设置 Stress and Performance Tool。</span><span class="sxs-lookup"><span data-stu-id="83376-p102">Requirements or prerequisites for the Skype for Business Server 2015 Stress and Performance Tool. How to install or setup the Stress and Performance Tool.</span></span>
  
<span data-ttu-id="83376-107">在运行 Stress and Performance Tool 之前，你需要了解下面的硬件、软件和系统配置要求：</span><span class="sxs-lookup"><span data-stu-id="83376-107">We have the following sections of hardware, software and system configuration requirements you'll need to be aware of prior to running the Stress and Performance Tool:</span></span>
  
- [<span data-ttu-id="83376-108">客户端硬件要求</span><span class="sxs-lookup"><span data-stu-id="83376-108">Client hardware requirements</span></span>](prerequisites-and-setup.md#ClientHardwareReqs)
    
- [<span data-ttu-id="83376-109">客户端软件要求</span><span class="sxs-lookup"><span data-stu-id="83376-109">Client software requirements</span></span>](prerequisites-and-setup.md#ClientSoftwareReqs)
    
- [<span data-ttu-id="83376-110">配置要求</span><span class="sxs-lookup"><span data-stu-id="83376-110">Configuration requirements</span></span>](prerequisites-and-setup.md#ConfigReqs)
    
<span data-ttu-id="83376-111">此外，还有下面的部分[安装 Skype for Business Server 2015 Stress and Performance Tool](prerequisites-and-setup.md#Installing)</span><span class="sxs-lookup"><span data-stu-id="83376-111">Additionally, we also have a section below for [Installing the Skype for Business Server 2015 Stress and Performance Tool](prerequisites-and-setup.md#Installing)</span></span>
  
## <a name="client-hardware-requirements"></a><span data-ttu-id="83376-112">客户端硬件要求</span><span class="sxs-lookup"><span data-stu-id="83376-112">Client hardware requirements</span></span>
<span data-ttu-id="83376-113"><a name="ClientHardwareReqs"> </a></span><span class="sxs-lookup"><span data-stu-id="83376-113"><a name="ClientHardwareReqs"> </a></span></span>

<span data-ttu-id="83376-114">在对 Skype for Business Server 2015 部署运行 Stress and Performance Tool 时，至少需对测试中的每 4500 个用户满足以下硬件要求：</span><span class="sxs-lookup"><span data-stu-id="83376-114">When running the Stress and Performance Tool against your Skype for Business Server 2015 deployment, you'll, at a minimum, need these hardware requirements met for every 4500 users in your test:</span></span>
  
- <span data-ttu-id="83376-115">1 GB 的网络适配器</span><span class="sxs-lookup"><span data-stu-id="83376-115">1 gigabit network adapter</span></span>
    
- <span data-ttu-id="83376-116">8 GB RAM</span><span class="sxs-lookup"><span data-stu-id="83376-116">8 GB RAM</span></span>
    
- <span data-ttu-id="83376-117">2 个双核 CPU</span><span class="sxs-lookup"><span data-stu-id="83376-117">2 dual-core CPUs</span></span>
    
## <a name="client-software-requirements"></a><span data-ttu-id="83376-118">客户端软件要求</span><span class="sxs-lookup"><span data-stu-id="83376-118">Client software requirements</span></span>
<span data-ttu-id="83376-119"><a name="ClientSoftwareReqs"> </a></span><span class="sxs-lookup"><span data-stu-id="83376-119"><a name="ClientSoftwareReqs"> </a></span></span>

<span data-ttu-id="83376-120">Stress and Performance Tool 支持的操作系统有：</span><span class="sxs-lookup"><span data-stu-id="83376-120">The supported operating systems for the Stress and Performance Tool are:</span></span>
  
- <span data-ttu-id="83376-121">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="83376-121">Windows Server 2012</span></span>
    
- <span data-ttu-id="83376-122">Windows Server 2008（64 位）</span><span class="sxs-lookup"><span data-stu-id="83376-122">Windows Server 2008 (64-bit)</span></span>
    
<span data-ttu-id="83376-123">此外，计算机还需满足以下软件要求：</span><span class="sxs-lookup"><span data-stu-id="83376-123">Additionally, computers need to meet the following software requirements:</span></span>
  
- <span data-ttu-id="83376-124">需要安装 Microsoft .NET 4.5 Framework。</span><span class="sxs-lookup"><span data-stu-id="83376-124">You'll need the Microsoft .NET 4.5 Framework installed.</span></span> [<span data-ttu-id="83376-125">在此处下载 .Net 4.5 框架。</span><span class="sxs-lookup"><span data-stu-id="83376-125">Download the .Net 4.5 Framework here.</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=30653)
    
- <span data-ttu-id="83376-126">需要在 Windows 中启用桌面体验功能。</span><span class="sxs-lookup"><span data-stu-id="83376-126">You'll need the Desktop Experience feature enabled in Windows.</span></span>
    
- <span data-ttu-id="83376-127">需要安装 Microsoft Visual C++ 2013 (x64)。</span><span class="sxs-lookup"><span data-stu-id="83376-127">You'll need Microsoft Visual C++ 2013 (x64) installed.</span></span> [<span data-ttu-id="83376-128">在此处下载 Visual c + + 2013</span><span class="sxs-lookup"><span data-stu-id="83376-128">Download Visual C++ 2013 here</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=40784)
    
- <span data-ttu-id="83376-129">需要成功部署 Skype for Business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="83376-129">You're going to need Skype for Business Server 2015 successfully deployed.</span></span>
    
## <a name="configuration-requirements"></a><span data-ttu-id="83376-130">配置要求</span><span class="sxs-lookup"><span data-stu-id="83376-130">Configuration requirements</span></span>
<span data-ttu-id="83376-131"><a name="ConfigReqs"> </a></span><span class="sxs-lookup"><span data-stu-id="83376-131"><a name="ConfigReqs"> </a></span></span>

<span data-ttu-id="83376-132">需要先完成这些附加配置，才能成功运行 Stress and Performance Tool：</span><span class="sxs-lookup"><span data-stu-id="83376-132">You'll need these additional configurations done to run the Stress and Performance Tool successfully:</span></span>
  
- <span data-ttu-id="83376-133">你需要以域或本地管理员组成员的身份登录服务器。</span><span class="sxs-lookup"><span data-stu-id="83376-133">You need to log into the server as a member of the Domain or Local Administrator's group.</span></span>
    
- <span data-ttu-id="83376-134">你无法在用户帐户所在的任何前端服务器或 Standard Edition 服务器上安装 Skype for Business Server 2015 User Creation 工具 (UserProvisioningTool.exe)。</span><span class="sxs-lookup"><span data-stu-id="83376-134">You can't install the Skype for Business Server 2015 User Creation tool (UserProvisioningTool.exe) on any Front End Server or Standard Edition server where the user accounts will reside.</span></span>
    
- <span data-ttu-id="83376-135">多次运行 User Creation 工具时，为 Microsoft 统一通信启用的每个用户都需要有一个唯一电话号码。</span><span class="sxs-lookup"><span data-stu-id="83376-135">When the User Creation tool is run multiple times, each user who's enabled for Microsoft Unified Communications needs to have a unique phone number.</span></span>
    
- <span data-ttu-id="83376-136">页面文件大小应由系统管理，或至少为计算机系统中 RAM 量的 1.5 倍。</span><span class="sxs-lookup"><span data-stu-id="83376-136">The page file size should be systems-managed, or otherwise needs to be at least 1.5 times the amount of RAM in the computer system.</span></span>
    
## <a name="installing-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="83376-137">安装 Skype for Business Server 2015 Stress and Performance Tool</span><span class="sxs-lookup"><span data-stu-id="83376-137">Installing the Skype for Business Server 2015 Stress and Performance Tool</span></span>
<span data-ttu-id="83376-138"><a name="Installing"> </a></span><span class="sxs-lookup"><span data-stu-id="83376-138"><a name="Installing"> </a></span></span>

<span data-ttu-id="83376-p105">安装非常简单。 你需要在要用来模拟用户流量的每台客户端计算机上以及要创建用户和联系人的每个池中的前端服务器上运行 Windows 安装程序文件 **CapacityPlanningTool.msi**。</span><span class="sxs-lookup"><span data-stu-id="83376-p105">Installing couldn't be simpler. You need to run the Windows Installer file, **CapacityPlanningTool.msi**, on each client computer you're going to use to simulate user traffic, and on a Front End Server in each pool where you'll create users and contacts.</span></span>
  
<span data-ttu-id="83376-141">若要下载 .msi，以及其他文章中提及的示例脚本，请转到下载中心链接： Skype for business [Server 2015、应力和性能工具](https://www.microsoft.com/download/details.aspx?id=50367)。</span><span class="sxs-lookup"><span data-stu-id="83376-141">To download the .msi, along with the sample scripts mentioned in our other articles, go to the Download Center link: [Skype for Business Server 2015, Stress and Performance Tool](https://www.microsoft.com/download/details.aspx?id=50367).</span></span>
  

