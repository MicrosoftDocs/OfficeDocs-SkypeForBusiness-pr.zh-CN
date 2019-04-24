---
title: 测试 SIP 中继配置设置中 Skype 业务服务器
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'SIP 中继配置设置定义的关系和中介服务器和公用电话交换网 (pstn) 网关、 IP 公用交换机 (PBX) 或服务提供商会话边界控制器 (SBC) 之间的功能。 '
ms.openlocfilehash: 3f251ea720ab220ccda0cfe9882d4a8396085aa0
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214622"
---
# <a name="test-sip-trunk-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="f783f-103">测试 SIP 中继配置设置中 Skype 业务服务器</span><span class="sxs-lookup"><span data-stu-id="f783f-103">Test SIP trunk configuration settings in Skype for Business Server</span></span>

<span data-ttu-id="f783f-104">SIP 中继配置设置定义的关系和中介服务器和公用电话交换网 (pstn) 网关、 IP 公用交换机 (PBX) 或服务提供商会话边界控制器 (SBC) 之间的功能。</span><span class="sxs-lookup"><span data-stu-id="f783f-104">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span> <span data-ttu-id="f783f-105">这些设置可执行如下所指定内容的操作：</span><span class="sxs-lookup"><span data-stu-id="f783f-105">These settings do such things as specify:</span></span>

- <span data-ttu-id="f783f-106">是否在中继上启用媒体旁路功能。</span><span class="sxs-lookup"><span data-stu-id="f783f-106">Whether media bypass should be enabled on the trunks.</span></span>
- <span data-ttu-id="f783f-107">在其下发送实时传输控制协议 (RTCP) 数据包的条件。</span><span class="sxs-lookup"><span data-stu-id="f783f-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>
- <span data-ttu-id="f783f-108">是否每个中继上是否需要安全实时协议 (SRTP) 加密。</span><span class="sxs-lookup"><span data-stu-id="f783f-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="f783f-109">在安装 Skype 业务服务器时，会为您创建 SIP 中继配置设置的全局集合。</span><span class="sxs-lookup"><span data-stu-id="f783f-109">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="f783f-110">此外，管理员可以在站点作用域或服务作用域创建自定义设置集合（仅适用于 PSTN 网关服务）。</span><span class="sxs-lookup"><span data-stu-id="f783f-110">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span> <span data-ttu-id="f783f-111">管理员还可以使用[测试 CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsTrunkConfiguration) cmdlet 来验证中继，可以将用户可以处理由网关的号码拨打的号码的转换。</span><span class="sxs-lookup"><span data-stu-id="f783f-111">Administrators can also use the [Test-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsTrunkConfiguration) cmdlet to verify that a trunk can convert a number as dialed by a user to a number that can be handled by the gateway.</span></span>

<span data-ttu-id="f783f-112">只能使用 Windows PowerShell 和 Test-CsTrunkConfiguration cmdlet 测试中继配置设置。</span><span class="sxs-lookup"><span data-stu-id="f783f-112">Trunk configuration settings can only be tested by using Windows PowerShell and the Test-CsTrunkConfiguration cmdlet.</span></span> <span data-ttu-id="f783f-113">从业务 Server 命令行管理程序 Skype 或 Windows PowerShell 远程会话，则可以运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f783f-113">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

<span data-ttu-id="f783f-114">**测试 SIP 中继配置设置**</span><span class="sxs-lookup"><span data-stu-id="f783f-114">**To test SIP trunk configuration settings**</span></span>

<span data-ttu-id="f783f-115">以下命令可验证 Redmond 站点的中继配置设置是否能正确转换拨号号码 4255551212。</span><span class="sxs-lookup"><span data-stu-id="f783f-115">This command verifies that the trunk configuration settings for the Redmond site can correctly convert the dialed number 4255551212.</span></span>

```
$trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk
```
