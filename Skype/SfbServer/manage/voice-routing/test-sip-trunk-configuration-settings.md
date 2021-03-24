---
title: 在 Skype for Business Server 中测试 SIP 中继配置设置
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'SIP 中继配置设置定义了中介服务器和服务提供商的公用电话交换网 (PSTN) 网关、IP 公用交换机 (PBX) 或会话边界控制器 (SBC) 之间的关系和功能。 '
ms.openlocfilehash: 87f5b8aa07a7545f30f1d0e8b81b33197ea704c1
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103018"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="e3aa6-103">在 Skype for Business Server 中测试 SIP 中继配置设置</span><span class="sxs-lookup"><span data-stu-id="e3aa6-103">Test SIP trunk configuration settings in Skype for Business Server</span></span>

<span data-ttu-id="e3aa6-p101">SIP 中继配置设置定义了中介服务器和服务提供商的公用电话交换网 (PSTN) 网关、IP 公用交换机 (PBX) 或会话边界控制器 (SBC) 之间的关系和功能。这些设置按下面的指示执行此类操作：</span><span class="sxs-lookup"><span data-stu-id="e3aa6-p101">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider. These settings do such things as specify:</span></span>

- <span data-ttu-id="e3aa6-106">是否应对中继启用媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="e3aa6-106">Whether media bypass should be enabled on the trunks.</span></span>
- <span data-ttu-id="e3aa6-107">发送实时传输控制协议 (RTCP) 数据包的条件。</span><span class="sxs-lookup"><span data-stu-id="e3aa6-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>
- <span data-ttu-id="e3aa6-108">每个中继上是否需要安全实时协议 (SRTP) 加密。</span><span class="sxs-lookup"><span data-stu-id="e3aa6-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="e3aa6-109">安装 Skype for Business Server 时，将创建 SIP 中继配置设置的全局集合。</span><span class="sxs-lookup"><span data-stu-id="e3aa6-109">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="e3aa6-110">此外，管理员还可以在站点作用域或服务作用域（仅针对 PSTN 网关服务）内创建自定义设置集合。</span><span class="sxs-lookup"><span data-stu-id="e3aa6-110">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span> <span data-ttu-id="e3aa6-111">管理员还可使用 [Test-CsTrunkConfiguration](/powershell/module/skype/Test-CsTrunkConfiguration) cmdlet 验证中继能否将用户拨打的号码转换为网关可以处理的号码。</span><span class="sxs-lookup"><span data-stu-id="e3aa6-111">Administrators can also use the [Test-CsTrunkConfiguration](/powershell/module/skype/Test-CsTrunkConfiguration) cmdlet to verify that a trunk can convert a number as dialed by a user to a number that can be handled by the gateway.</span></span>

<span data-ttu-id="e3aa6-112">只能使用 Windows PowerShell 和 Test-CsTrunkConfiguration cmdlet 测试中继配置设置。</span><span class="sxs-lookup"><span data-stu-id="e3aa6-112">Trunk configuration settings can only be tested by using Windows PowerShell and the Test-CsTrunkConfiguration cmdlet.</span></span> <span data-ttu-id="e3aa6-113">可以从 Skype for Business Server 命令行管理程序或远程会话运行此 cmdlet Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="e3aa6-113">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

<span data-ttu-id="e3aa6-114">**测试 SIP 中继配置设置**</span><span class="sxs-lookup"><span data-stu-id="e3aa6-114">**To test SIP trunk configuration settings**</span></span>

<span data-ttu-id="e3aa6-115">以下命令可验证 Redmond 站点的中继配置设置是否能正确转换拨号号码 4255551212。</span><span class="sxs-lookup"><span data-stu-id="e3aa6-115">This command verifies that the trunk configuration settings for the Redmond site can correctly convert the dialed number 4255551212.</span></span>

```PowerShell
$trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
```