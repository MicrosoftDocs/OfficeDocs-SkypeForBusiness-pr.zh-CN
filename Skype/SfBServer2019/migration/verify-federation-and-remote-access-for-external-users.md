---
title: 验证联盟和外部用户的远程访问
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 将联合身份验证路由转换为 Skype for business Server 2019 边缘服务器后，应执行一些功能测试，以验证联合身份验证是否按预期执行。 外部用户访问测试应包括贵组织支持的每种类型的外部用户，包括下列任意部分或全部用户。
ms.openlocfilehash: b2567f4e46bd39d2748e3a4a3ba6cc5d6c197b11
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751664"
---
# <a name="verify-federation-and-remote-access-for-external-users"></a><span data-ttu-id="a1aed-104">验证联盟和外部用户的远程访问</span><span class="sxs-lookup"><span data-stu-id="a1aed-104">Verify federation and remote access for external users</span></span>

<span data-ttu-id="a1aed-105">将联合身份验证路由转换为 Skype for business Server 2019 边缘服务器后，应执行一些功能测试，以验证联合身份验证是否按预期执行。</span><span class="sxs-lookup"><span data-stu-id="a1aed-105">After transitioning the federation route to the Skype for Business Server 2019 Edge Server, you should perform some functional tests to verify that federation performs as expected.</span></span> <span data-ttu-id="a1aed-106">外部用户访问测试应包括贵组织支持的每种类型的外部用户，包括下列任意部分或全部用户。</span><span class="sxs-lookup"><span data-stu-id="a1aed-106">Tests for external user access should include each type of external user that your organization supports, including any or all of the following.</span></span>
  
### <a name="test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="a1aed-107">测试外部用户和外部访问的连接</span><span class="sxs-lookup"><span data-stu-id="a1aed-107">Test connectivity of external users and external access</span></span>

- <span data-ttu-id="a1aed-108">至少一个联盟域中的用户、Skype for business Server 2019 上的内部用户以及旧安装中的用户。</span><span class="sxs-lookup"><span data-stu-id="a1aed-108">Users from at least one federated domain, an internal user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="a1aed-109">测试即时消息 (IM)、状态、音频/视频 (A/V) 和桌面共享。</span><span class="sxs-lookup"><span data-stu-id="a1aed-109">Test instant messaging (IM), presence, audio/video (A/V), and desktop sharing.</span></span>
    
- <span data-ttu-id="a1aed-110">您的组织支持的每个公共 IM 服务提供商的用户（以及已完成的设置）与 Skype for Business Server 2019 上的用户以及旧安装中的用户进行通信。</span><span class="sxs-lookup"><span data-stu-id="a1aed-110">Users of each public IM service provider that your organization supports (and for which provisioning has been completed) communicating with a user on Skype for Business Server 2019 and a user on the legacy install.</span></span> 
    
- <span data-ttu-id="a1aed-111">验证匿名用户是否能够加入会议。</span><span class="sxs-lookup"><span data-stu-id="a1aed-111">Verify that anonymous users are able to join conferences.</span></span>
    
- <span data-ttu-id="a1aed-112">在旧版安装中使用远程用户访问（通过远程用户访问而不是 VPN 登录到 intranet 上的 Lync Server/Skype for Business）与 Skype for Business Server 2019 上的用户以及旧版安装中的用户进行了托管。</span><span class="sxs-lookup"><span data-stu-id="a1aed-112">A user hosted on the legacy install using remote user access (logging i nto Lync Server/Skype for Business from outside the intranet but without VPN) with a user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="a1aed-113">测试 IM、状态、A/V 和桌面共享。</span><span class="sxs-lookup"><span data-stu-id="a1aed-113">Test IM, presence, A/V, and desktop sharing.</span></span>
    
- <span data-ttu-id="a1aed-114">在 Skype for business Server 2019 上托管的用户使用远程用户访问（从 intranet 外部（但不使用 VPN 登录到 Skype for Business Server 2019）与 Skype for business Server 2019 上的用户以及旧安装中的用户。</span><span class="sxs-lookup"><span data-stu-id="a1aed-114">A user hosted on Skype for Business Server 2019 using remote user access (logging in to Skype for Business Server 2019 from outside the intranet but without VPN) with a user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="a1aed-115">测试 IM、状态、A/V 和桌面共享。</span><span class="sxs-lookup"><span data-stu-id="a1aed-115">Test IM, presence, A/V, and desktop sharing.</span></span>
    

