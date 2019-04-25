---
title: 验证联盟和外部用户的远程访问
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 切换后联盟路由到 Skype 业务 Server 2019 边缘服务器，应执行一些功能测试，以确认联盟能够按预期方式。 外部用户访问测试应包括每种类型的外部用户的支持您的组织，包括任意或全部操作。
ms.openlocfilehash: 3a520b39d76ab93f4ec7fcaacd139b3f83a3326a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231348"
---
# <a name="verify-federation-and-remote-access-for-external-users"></a><span data-ttu-id="781a3-104">验证联盟和外部用户的远程访问</span><span class="sxs-lookup"><span data-stu-id="781a3-104">Verify federation and remote access for external users</span></span>

<span data-ttu-id="781a3-105">切换后联盟路由到 Skype 业务 Server 2019 边缘服务器，应执行一些功能测试，以确认联盟能够按预期方式。</span><span class="sxs-lookup"><span data-stu-id="781a3-105">After transitioning the federation route to the Skype for Business Server 2019 Edge Server, you should perform some functional tests to verify that federation performs as expected.</span></span> <span data-ttu-id="781a3-106">外部用户访问测试应包括每种类型的外部用户的支持您的组织，包括任意或全部操作。</span><span class="sxs-lookup"><span data-stu-id="781a3-106">Tests for external user access should include each type of external user that your organization supports, including any or all of the following.</span></span>
  
### <a name="test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="781a3-107">测试外部用户和外部访问的连接</span><span class="sxs-lookup"><span data-stu-id="781a3-107">Test connectivity of external users and external access</span></span>

- <span data-ttu-id="781a3-108">至少一个联盟的域、 业务服务器 2019年的 Skype 上的内部用户和旧上的用户的用户安装。</span><span class="sxs-lookup"><span data-stu-id="781a3-108">Users from at least one federated domain, an internal user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="781a3-109">测试即时消息 (IM)、 状态、 音频/视频 (A / V)，和桌面共享。</span><span class="sxs-lookup"><span data-stu-id="781a3-109">Test instant messaging (IM), presence, audio/video (A/V), and desktop sharing.</span></span>
    
- <span data-ttu-id="781a3-110">用户的每个公共 IM 服务提供商的组织支持 （为其设置已完成） 与 Skype 上的用户进行通信的业务服务器 2019年和旧安装上的用户。</span><span class="sxs-lookup"><span data-stu-id="781a3-110">Users of each public IM service provider that your organization supports (and for which provisioning has been completed) communicating with a user on Skype for Business Server 2019 and a user on the legacy install.</span></span> 
    
- <span data-ttu-id="781a3-111">验证匿名用户能够加入会议。</span><span class="sxs-lookup"><span data-stu-id="781a3-111">Verify that anonymous users are able to join conferences.</span></span>
    
- <span data-ttu-id="781a3-112">使用远程用户访问旧上承载用户安装 (日志记录 i 上 Lync Server/Skype for Business 从 intranet 外部但没有 VPN) 与旧安装上的用户和业务服务器 2019年的 Skype 上的用户。</span><span class="sxs-lookup"><span data-stu-id="781a3-112">A user hosted on the legacy install using remote user access (logging i nto Lync Server/Skype for Business from outside the intranet but without VPN) with a user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="781a3-113">测试 IM、 状态、 A / V 和桌面共享。</span><span class="sxs-lookup"><span data-stu-id="781a3-113">Test IM, presence, A/V, and desktop sharing.</span></span>
    
- <span data-ttu-id="781a3-114">为使用旧上的用户和业务服务器 2019年的 Skype 上的用户的远程用户访问 （登录到 Skype 的业务服务器 2019 从 intranet 外部但没有 VPN） 的业务服务器 2019 Skype 上承载用户安装。</span><span class="sxs-lookup"><span data-stu-id="781a3-114">A user hosted on Skype for Business Server 2019 using remote user access (logging in to Skype for Business Server 2019 from outside the intranet but without VPN) with a user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="781a3-115">测试 IM、 状态、 A / V 和桌面共享。</span><span class="sxs-lookup"><span data-stu-id="781a3-115">Test IM, presence, A/V, and desktop sharing.</span></span>
    

