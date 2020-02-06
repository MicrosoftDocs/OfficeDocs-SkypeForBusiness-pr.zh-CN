---
title: 验证联盟和外部用户的远程访问
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 将联盟路由转换为 Skype for business Server 2019 Edge 服务器之后，你应该执行一些功能测试以验证联合身份验证是否按预期执行。 外部用户访问的测试应包括您的组织支持的每种类型的外部用户，包括以下任何或所有类型的外部用户。
ms.openlocfilehash: 7f27fa853c8af2ba5e97835ad1e0dd893c9128e0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812680"
---
# <a name="verify-federation-and-remote-access-for-external-users"></a><span data-ttu-id="56df2-104">验证联盟和外部用户的远程访问</span><span class="sxs-lookup"><span data-stu-id="56df2-104">Verify federation and remote access for external users</span></span>

<span data-ttu-id="56df2-105">将联盟路由转换为 Skype for business Server 2019 Edge 服务器之后，你应该执行一些功能测试以验证联合身份验证是否按预期执行。</span><span class="sxs-lookup"><span data-stu-id="56df2-105">After transitioning the federation route to the Skype for Business Server 2019 Edge Server, you should perform some functional tests to verify that federation performs as expected.</span></span> <span data-ttu-id="56df2-106">外部用户访问的测试应包括您的组织支持的每种类型的外部用户，包括以下任何或所有类型的外部用户。</span><span class="sxs-lookup"><span data-stu-id="56df2-106">Tests for external user access should include each type of external user that your organization supports, including any or all of the following.</span></span>
  
### <a name="test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="56df2-107">测试外部用户和外部访问的连接性</span><span class="sxs-lookup"><span data-stu-id="56df2-107">Test connectivity of external users and external access</span></span>

- <span data-ttu-id="56df2-108">至少一个联盟域中的用户、Skype for Business Server 2019 上的内部用户以及旧版安装中的用户。</span><span class="sxs-lookup"><span data-stu-id="56df2-108">Users from at least one federated domain, an internal user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="56df2-109">测试即时消息（IM）、状态、音频/视频（A/V）和桌面共享。</span><span class="sxs-lookup"><span data-stu-id="56df2-109">Test instant messaging (IM), presence, audio/video (A/V), and desktop sharing.</span></span>
    
- <span data-ttu-id="56df2-110">你的组织支持的每个公共 IM 服务提供商的用户（以及已完成的预配）与 Skype for Business Server 2019 上的用户和旧式安装中的用户进行通信。</span><span class="sxs-lookup"><span data-stu-id="56df2-110">Users of each public IM service provider that your organization supports (and for which provisioning has been completed) communicating with a user on Skype for Business Server 2019 and a user on the legacy install.</span></span> 
    
- <span data-ttu-id="56df2-111">验证匿名用户是否能够加入会议。</span><span class="sxs-lookup"><span data-stu-id="56df2-111">Verify that anonymous users are able to join conferences.</span></span>
    
- <span data-ttu-id="56df2-112">在旧版安装中使用远程用户访问托管的用户（通过 Skype for business Server 2019 上的用户（不使用 VPN）将 Lync Server/Skype for business 记录到 Skype for business Server 上的用户以及旧版安装中的用户。</span><span class="sxs-lookup"><span data-stu-id="56df2-112">A user hosted on the legacy install using remote user access (logging i nto Lync Server/Skype for Business from outside the intranet but without VPN) with a user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="56df2-113">测试即时消息、状态、A/V 和桌面共享。</span><span class="sxs-lookup"><span data-stu-id="56df2-113">Test IM, presence, A/V, and desktop sharing.</span></span>
    
- <span data-ttu-id="56df2-114">在 skype for business Server 2019 上托管的用户（使用远程用户访问权限登录到 intranet 外的 Skype for business Server 2019，但不使用 VPN）和 Skype for business Server 2019 上的用户以及旧版安装中的用户登录。</span><span class="sxs-lookup"><span data-stu-id="56df2-114">A user hosted on Skype for Business Server 2019 using remote user access (logging in to Skype for Business Server 2019 from outside the intranet but without VPN) with a user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="56df2-115">测试即时消息、状态、A/V 和桌面共享。</span><span class="sxs-lookup"><span data-stu-id="56df2-115">Test IM, presence, A/V, and desktop sharing.</span></span>
    

