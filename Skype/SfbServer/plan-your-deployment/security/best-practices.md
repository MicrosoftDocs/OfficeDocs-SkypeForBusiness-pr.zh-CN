---
title: 核心基础结构中的业务服务器 Skype 的最佳实践
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 44aff88d-536c-4613-a81e-5398c9c6a648
description: 你可能已经着手设计系统容错能力，做法有：确保硬件冗余、防止断电、例行安装安全更新和防病毒措施，以及监控服务器活动等。 这些做法不仅您 Skype Business Server 基础结构，而且还使整个网络中受益。 如果还未实施这些做法，我们建议您这样做业务服务器部署 Skype 之前。
ms.openlocfilehash: 66725331c84e3f2d24e496489e0db8ef9866d0e8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33896352"
---
# <a name="best-practices-for-your-core-infrastructure-in-skype-for-business-server"></a><span data-ttu-id="15b18-105">核心基础结构中的业务服务器 Skype 的最佳实践</span><span class="sxs-lookup"><span data-stu-id="15b18-105">Best practices for your core infrastructure in Skype for Business Server</span></span>
 
<span data-ttu-id="15b18-106">你可能已经着手设计系统容错能力，做法有：确保硬件冗余、防止断电、例行安装安全更新和防病毒措施，以及监控服务器活动等。</span><span class="sxs-lookup"><span data-stu-id="15b18-106">You have probably already taken steps to design fault tolerance in your system, using practices such as ensuring hardware redundancy, guarding against power loss, routinely installing security updates and antivirus measures, and Monitoring Server activity.</span></span> <span data-ttu-id="15b18-107">这些做法不仅您 Skype Business Server 基础结构，而且还使整个网络中受益。</span><span class="sxs-lookup"><span data-stu-id="15b18-107">These practices benefit not only your Skype for Business Server infrastructure, but also your entire network.</span></span> <span data-ttu-id="15b18-108">如果还未实施这些做法，我们建议您这样做业务服务器部署 Skype 之前。</span><span class="sxs-lookup"><span data-stu-id="15b18-108">If you have not implemented these practices, we recommend that you do so before deploying Skype for Business Server.</span></span>
  
<span data-ttu-id="15b18-109">为了帮助防止受到无意或故意可能导致停机时间的危害您 Skype 业务服务器部署中的服务器，请采取以下防范措施：</span><span class="sxs-lookup"><span data-stu-id="15b18-109">To help protect the servers in your Skype for Business Server deployment from accidental or purposeful harm that might result in downtime, take the following precautions:</span></span>
  
- <span data-ttu-id="15b18-110">使用安全更新使服务器保持最新状态。</span><span class="sxs-lookup"><span data-stu-id="15b18-110">Keep your servers up-to-date with security updates.</span></span> <span data-ttu-id="15b18-111">订阅 Microsoft 安全性通知服务来帮助你确保收到关于任何 Microsoft 产品的安全公告发布的最新通知。</span><span class="sxs-lookup"><span data-stu-id="15b18-111">Subscribing to the Microsoft Security Notification Service helps ensure that you receive immediate notification of security bulletin releases for any Microsoft product.</span></span> <span data-ttu-id="15b18-112">若要订阅，请转到[Microsoft 技术安全性通知网站](https://go.microsoft.com/fwlink/p/?LinkId=145202)。</span><span class="sxs-lookup"><span data-stu-id="15b18-112">To subscribe, go to the [Microsoft Technical Security Notifications website](https://go.microsoft.com/fwlink/p/?LinkId=145202).</span></span>
    
- <span data-ttu-id="15b18-113">确保正确设置访问权限。</span><span class="sxs-lookup"><span data-stu-id="15b18-113">Ensure that access rights are set up correctly.</span></span>
    
- <span data-ttu-id="15b18-p104">将服务器部署在可阻止未经授权访问的物理环境中。确保在所有服务器上安装适当的防病毒软件。使用最新的病毒特征文件使软件保持最新。使用防病毒应用程序的自动更新功能使病毒特征保持最新。</span><span class="sxs-lookup"><span data-stu-id="15b18-p104">Keep your servers in a physical environment that prevents unauthorized access. Ensure that adequate antivirus software is installed on all your servers. Keep the software up-to-date with the latest virus signature files. Use the automatic update feature of your antivirus application to keep the virus signatures current.</span></span>
    
- <span data-ttu-id="15b18-118">我们建议您禁用不需要 Skype 业务服务器的安装位置的计算机的 Windows Server 操作系统服务。</span><span class="sxs-lookup"><span data-stu-id="15b18-118">We recommend that you disable the Windows Server operating system services that are not required on the computers where you install Skype for Business Server.</span></span>
    
- <span data-ttu-id="15b18-119">除非可以确保实现连续完整的服务器控制、完全物理隔离以及正确安全地停用更换的或有故障的磁盘驱动器，否则使用全卷加密系统对操作系统和存储数据的磁盘驱动器加密。</span><span class="sxs-lookup"><span data-stu-id="15b18-119">Encrypt operating systems and disk drives where data is stored with a full-volume encryption system, unless you can guarantee constant and complete control of the servers, total physical isolation, and proper and secure decommissioning of replaced or failed disk drives.</span></span>
    
- <span data-ttu-id="15b18-120">除非可以确保严格控制对服务器的物理访问，否则禁用服务器的所有外部直接内存访问 (DMA) 端口。</span><span class="sxs-lookup"><span data-stu-id="15b18-120">Disable all external Direct Memory Access (DMA) ports of the server, unless you can guarantee very tight control over the physical access to the servers.</span></span> <span data-ttu-id="15b18-121">很容易就能发起的基于 DMA 的攻击可能会公开非常敏感的信息，例如加密私钥。</span><span class="sxs-lookup"><span data-stu-id="15b18-121">DMA-based attacks, which can be initiated fairly easily, could expose very sensitive information, such as private encryption keys.</span></span>
    

