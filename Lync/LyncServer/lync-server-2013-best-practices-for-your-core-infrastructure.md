---
title: Lync Server 2013：核心基础结构的最佳做法
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Best practices for your core infrastructure in Lync Server 2013
ms:assetid: 44aff88d-536c-4613-a81e-5398c9c6a648
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518328(v=OCS.15)
ms:contentKeyID: 61071242
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 087cfed02e3b28df88508446c57e451f42ef067c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512999"
---
# <a name="best-practices-for-your-core-infrastructure-in-lync-server-2013"></a><span data-ttu-id="82dde-102">Lync Server 2013 中核心基础结构的最佳做法</span><span class="sxs-lookup"><span data-stu-id="82dde-102">Best practices for your core infrastructure in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="82dde-103">_**上次修改的主题：** 2014-01-27_</span><span class="sxs-lookup"><span data-stu-id="82dde-103">_**Topic Last Modified:** 2014-01-27_</span></span>

<span data-ttu-id="82dde-104">您可能已经着手设计系统容错能力了，做法有：确保硬件冗余，防止断电，例行安装安全更新和防病毒措施，以及监控服务器活动等。</span><span class="sxs-lookup"><span data-stu-id="82dde-104">You have probably already taken steps to design fault tolerance in your system, using practices such as ensuring hardware redundancy, guarding against power loss, routinely installing security updates and antivirus measures, and Monitoring Server activity.</span></span> <span data-ttu-id="82dde-105">这些做法不仅受益于 Microsoft Lync Server 2013 基础结构，还受益于整个网络。</span><span class="sxs-lookup"><span data-stu-id="82dde-105">These practices benefit not only your Microsoft Lync Server 2013 infrastructure, but also your entire network.</span></span> <span data-ttu-id="82dde-106">如果尚未实施这些做法，我们建议您在部署 Lync Server 2013 之前执行此操作。</span><span class="sxs-lookup"><span data-stu-id="82dde-106">If you have not implemented these practices, we recommend that you do so before deploying Lync Server 2013.</span></span>

<span data-ttu-id="82dde-107">为了帮助保护 Lync Server 2013 部署中的服务器，避免因意外或故意损害可能导致停机的情况，请采取以下预防措施：</span><span class="sxs-lookup"><span data-stu-id="82dde-107">To help protect the servers in your Lync Server 2013 deployment from accidental or purposeful harm that might result in downtime, take the following precautions:</span></span>

  - <span data-ttu-id="82dde-108">使用安全更新使服务器保持最新状态。</span><span class="sxs-lookup"><span data-stu-id="82dde-108">Keep your servers up-to-date with security updates.</span></span> <span data-ttu-id="82dde-109">订阅 Microsoft 安全性通知服务有助于确保您收到任何 Microsoft 产品的安全公告发布的最新通知。</span><span class="sxs-lookup"><span data-stu-id="82dde-109">Subscribing to the Microsoft Security Notification Service helps ensure that you receive immediate notification of security bulletin releases for any Microsoft product.</span></span> <span data-ttu-id="82dde-110">若要订阅，请访问 Microsoft 技术安全通知网站，网址为 [https://go.microsoft.com/fwlink/p/?LinkId=145202](https://go.microsoft.com/fwlink/p/?linkid=145202) 。</span><span class="sxs-lookup"><span data-stu-id="82dde-110">To subscribe, go to the Microsoft Technical Security Notifications website at [https://go.microsoft.com/fwlink/p/?LinkId=145202](https://go.microsoft.com/fwlink/p/?linkid=145202).</span></span>

  - <span data-ttu-id="82dde-111">确保正确设置访问权限。</span><span class="sxs-lookup"><span data-stu-id="82dde-111">Ensure that access rights are set up correctly.</span></span>

  - <span data-ttu-id="82dde-p103">将服务器部署在可防止未授权访问的物理环境中。确保在所有服务器上安装适当的防病毒软件。使用最新的病毒特征文件使软件保持最新。使用防病毒应用程序的自动更新功能使病毒特征保持最新。</span><span class="sxs-lookup"><span data-stu-id="82dde-p103">Keep your servers in a physical environment that prevents unauthorized access. Ensure that adequate antivirus software is installed on all your servers. Keep the software up-to-date with the latest virus signature files. Use the automatic update feature of your antivirus application to keep the virus signatures current.</span></span>

  - <span data-ttu-id="82dde-116">建议您在安装 Lync Server 2013 的计算机上禁用不需要的 Windows Server 操作系统服务。</span><span class="sxs-lookup"><span data-stu-id="82dde-116">We recommend that you disable the Windows Server operating system services that are not required on the computers where you install Lync Server 2013.</span></span>

  - <span data-ttu-id="82dde-117">除非可以确保实现连续完整的服务器控制、完全物理隔离以及正确安全地停用更换的或有故障的磁盘驱动器，否则使用全卷加密系统对操作系统和存储数据的磁盘驱动器加密。</span><span class="sxs-lookup"><span data-stu-id="82dde-117">Encrypt operating systems and disk drives where data is stored with a full-volume encryption system, unless you can guarantee constant and complete control of the servers, total physical isolation, and proper and secure decommissioning of replaced or failed disk drives.</span></span>

  - <span data-ttu-id="82dde-118">除非可以确保严格控制对服务器的物理访问，否则禁用服务器的所有外部直接内存访问 (DMA) 端口。</span><span class="sxs-lookup"><span data-stu-id="82dde-118">Disable all external Direct Memory Access (DMA) ports of the server, unless you can guarantee very tight control over the physical access to the servers.</span></span> <span data-ttu-id="82dde-119">可以轻松发起的基于 DMA 的攻击可能会公开非常敏感的信息，例如加密私钥。</span><span class="sxs-lookup"><span data-stu-id="82dde-119">DMA-based attacks, which can be initiated fairly easily, could expose very sensitive information, such as private encryption keys.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

