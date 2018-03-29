---
title: 在 Skype for Business Server 2015 中测试 SIP 中继配置设置
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: c8712308-0e2d-4e39-8f90-d1a250487a94
description: 摘要： 了解如何通过 Skype 业务服务器管理外壳程序测试 SIP 中继配置设置。
ms.openlocfilehash: 4e4c0c7ce117143f743dd40536bc49bfce92d978
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server-2015"></a><span data-ttu-id="041d0-103">在 Skype for Business Server 2015 中测试 SIP 中继配置设置</span><span class="sxs-lookup"><span data-stu-id="041d0-103">Test SIP trunk configuration settings in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="041d0-104">**摘要：**了解如何通过 Skype 业务服务器管理外壳程序测试 SIP 中继配置设置。</span><span class="sxs-lookup"><span data-stu-id="041d0-104">**Summary:** Learn how to test SIP trunk configuration settings by using the Skype for Business Server Management Shell.</span></span>
  
<span data-ttu-id="041d0-p101">SIP 中继配置设置可定义中介服务器与服务提供商的公用电话交换网 (PSTN) 网关、IP 公用交换机 (PBX) 或会话边界控制器 (SBC) 之间的关系和功能。这些设置可执行如下所指定内容的操作：</span><span class="sxs-lookup"><span data-stu-id="041d0-p101">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the Public Switched Telephone Network (PSTN) gateway, an IP-Public Branch eXchange (PBX), or a Session Border Controller (SBC) at the service provider. These settings do such things as specify:</span></span>
  
- <span data-ttu-id="041d0-107">是否在中继上启用媒体旁路功能。</span><span class="sxs-lookup"><span data-stu-id="041d0-107">Whether media bypass should be enabled on the trunks.</span></span>
    
- <span data-ttu-id="041d0-108">发送实时传输控制协议 (RTCP) 数据包所依据的条件。</span><span class="sxs-lookup"><span data-stu-id="041d0-108">The conditions under which Realtime Transport Control Protocol (RTCP) packets are sent.</span></span>
    
- <span data-ttu-id="041d0-109">在每个中继上是否需要安全实时传输协议 (SRTP) 加密。</span><span class="sxs-lookup"><span data-stu-id="041d0-109">Whether or not Secure Realtime Transport Protocol (SRTP) encryption is required on each trunk.</span></span>
    
<span data-ttu-id="041d0-110">为业务服务器安装 Skype 时，为您创建的 SIP 中继配置设置一个全局集合。</span><span class="sxs-lookup"><span data-stu-id="041d0-110">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="041d0-111">此外，管理员还可以在站点作用域或服务作用域（仅针对 PSTN 网关服务）内创建自定义设置集合。</span><span class="sxs-lookup"><span data-stu-id="041d0-111">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span> <span data-ttu-id="041d0-112">管理员还可以使用 Test-CsTrunkConfiguration cmdlet 验证中继是否可以将用户拨打的号码转换为网关可处理的号码。</span><span class="sxs-lookup"><span data-stu-id="041d0-112">Administrators can also use the Test-CsTrunkConfiguration cmdlet to verify that a trunk can convert a number as dialed by a user to a number that can be handled by the gateway.</span></span>
  
<span data-ttu-id="041d0-113">仅可以使用 Windows PowerShell 和[测试 CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/test-cstrunkconfiguration?view=skype-ps) cmdlet 测试中继的配置设置。</span><span class="sxs-lookup"><span data-stu-id="041d0-113">Trunk configuration settings can only be tested by using Windows PowerShell and the [Test-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/test-cstrunkconfiguration?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="041d0-114">从业务服务器管理外壳的 Skype 或业务服务器管理外壳的 Skype 远程会话，则可以运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="041d0-114">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Skype for Business Server Management Shell.</span></span>
  
### <a name="to-test-sip-trunk-configuration-settings"></a><span data-ttu-id="041d0-115">测试 SIP 中继配置设置</span><span class="sxs-lookup"><span data-stu-id="041d0-115">To test SIP trunk configuration settings</span></span>

- <span data-ttu-id="041d0-116">以下命令可验证 Redmond 站点的中继配置设置是否能正确转换拨号号码 4255551212。</span><span class="sxs-lookup"><span data-stu-id="041d0-116">This command verifies that the trunk configuration settings for the Redmond site can correctly convert the dialed number 4255551212.</span></span>
    
  ```
  $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
  Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
  ```


