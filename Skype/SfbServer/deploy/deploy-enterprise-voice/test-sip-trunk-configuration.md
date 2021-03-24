---
title: 在 Skype for Business Server 中测试 SIP 中继配置设置
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c8712308-0e2d-4e39-8f90-d1a250487a94
description: 摘要：了解如何使用 Skype for Business Server 命令行管理程序测试 SIP 中继配置设置。
ms.openlocfilehash: 6f569c7e397e7902cb347e13b4077acb5a9b34fb
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103368"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="7a7b1-103">在 Skype for Business Server 中测试 SIP 中继配置设置</span><span class="sxs-lookup"><span data-stu-id="7a7b1-103">Test SIP trunk configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="7a7b1-104">**摘要：** 了解如何使用 Skype for Business Server 命令行管理程序测试 SIP 中继配置设置。</span><span class="sxs-lookup"><span data-stu-id="7a7b1-104">**Summary:** Learn how to test SIP trunk configuration settings by using the Skype for Business Server Management Shell.</span></span>
  
<span data-ttu-id="7a7b1-105">SIP 中继配置设置定义中介服务器与服务提供商的公用电话交换网 (PSTN) 网关、IP-Public 交换机 (PBX) 或会话边界控制器 (SBC) 之间的关系和功能。</span><span class="sxs-lookup"><span data-stu-id="7a7b1-105">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the Public Switched Telephone Network (PSTN) gateway, an IP-Public Branch eXchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span> <span data-ttu-id="7a7b1-106">这些设置按下面的指示执行此类操作：</span><span class="sxs-lookup"><span data-stu-id="7a7b1-106">These settings do such things as specify:</span></span>
  
- <span data-ttu-id="7a7b1-107">是否应对中继启用媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="7a7b1-107">Whether media bypass should be enabled on the trunks.</span></span>
    
- <span data-ttu-id="7a7b1-108">发送实时传输控制协议 (RTCP) 的条件。</span><span class="sxs-lookup"><span data-stu-id="7a7b1-108">The conditions under which Realtime Transport Control Protocol (RTCP) packets are sent.</span></span>
    
- <span data-ttu-id="7a7b1-109">每个中继上是否需要安全实时传输 (SRTP) 加密。</span><span class="sxs-lookup"><span data-stu-id="7a7b1-109">Whether or not Secure Realtime Transport Protocol (SRTP) encryption is required on each trunk.</span></span>
    
<span data-ttu-id="7a7b1-110">安装 Skype for Business Server 时，将创建 SIP 中继配置设置的全局集合。</span><span class="sxs-lookup"><span data-stu-id="7a7b1-110">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="7a7b1-111">此外，管理员还可以在站点作用域或服务作用域（仅针对 PSTN 网关服务）内创建自定义设置集合。</span><span class="sxs-lookup"><span data-stu-id="7a7b1-111">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span> <span data-ttu-id="7a7b1-112">管理员还可以使用 Test-CsTrunkConfiguration cmdlet 验证中继是否可以将用户拨打的号码转换为网关可处理的号码。</span><span class="sxs-lookup"><span data-stu-id="7a7b1-112">Administrators can also use the Test-CsTrunkConfiguration cmdlet to verify that a trunk can convert a number as dialed by a user to a number that can be handled by the gateway.</span></span>
  
<span data-ttu-id="7a7b1-113">只能使用 Windows PowerShell 和 [Test-CsTrunkConfiguration](/powershell/module/skype/test-cstrunkconfiguration?view=skype-ps) cmdlet 测试中继配置设置。</span><span class="sxs-lookup"><span data-stu-id="7a7b1-113">Trunk configuration settings can only be tested by using Windows PowerShell and the [Test-CsTrunkConfiguration](/powershell/module/skype/test-cstrunkconfiguration?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="7a7b1-114">此 cmdlet 可以从 Skype for Business Server 命令行管理程序运行，也可以从 Skype for Business Server 命令行管理程序 的远程会话中运行。</span><span class="sxs-lookup"><span data-stu-id="7a7b1-114">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Skype for Business Server Management Shell.</span></span>
  
### <a name="to-test-sip-trunk-configuration-settings"></a><span data-ttu-id="7a7b1-115">测试 SIP 中继配置设置</span><span class="sxs-lookup"><span data-stu-id="7a7b1-115">To test SIP trunk configuration settings</span></span>

- <span data-ttu-id="7a7b1-116">以下命令可验证 Redmond 站点的中继配置设置是否能正确转换拨号号码 4255551212。</span><span class="sxs-lookup"><span data-stu-id="7a7b1-116">This command verifies that the trunk configuration settings for the Redmond site can correctly convert the dialed number 4255551212.</span></span>
    
  ```powershell
  $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
  Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
  ```