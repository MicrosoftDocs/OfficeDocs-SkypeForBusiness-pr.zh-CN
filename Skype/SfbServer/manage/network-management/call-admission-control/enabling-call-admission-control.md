---
title: 启用呼叫允许控制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: " 配置呼叫允许控制 (CAC) 网络后，您必须启用 CAC 来强制实施的带宽限制。"
ms.openlocfilehash: a819f3a42078c094c0fc8bf10f788bbaf3361e20
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33888329"
---
# <a name="enabling-call-admission-control-in-skype-for-business-server"></a><span data-ttu-id="50908-103">在 Skype for Business Server 上启用呼叫允许控制</span><span class="sxs-lookup"><span data-stu-id="50908-103">Enabling call admission control in Skype for Business Server</span></span>

<span data-ttu-id="50908-104">呼叫允许控制 (CAC) 是区域、站点和子网的网络，通过它可基于可用带宽对音频和视频传输设置限制。</span><span class="sxs-lookup"><span data-stu-id="50908-104">Call admission control (CAC) is a network of regions, sites, and subnets that enable you to place restrictions on audio and video transmissions based on available bandwidth.</span></span> <span data-ttu-id="50908-105">配置 CAC 网络后，您必须启用 CAC 来强制实施的带宽限制。</span><span class="sxs-lookup"><span data-stu-id="50908-105">After you configure the CAC network, you must enable CAC to enforce the bandwidth limitations.</span></span> <span data-ttu-id="50908-106">您可以使用业务 Server Control Panel 的 Skype 执行此操作。</span><span class="sxs-lookup"><span data-stu-id="50908-106">You can use the Skype for Business Server Control Panel to do this.</span></span>


## <a name="to-enable-cac-from-the-skype-for-business-server-control-panel"></a><span data-ttu-id="50908-107">启用业务 Server Control Panel 从 Skype 的 CAC</span><span class="sxs-lookup"><span data-stu-id="50908-107">To enable CAC from the Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="50908-108">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="50908-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="50908-109">打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="50908-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="50908-110">在左侧的导航栏中，单击**网络配置**，然后单击**全局**。</span><span class="sxs-lookup"><span data-stu-id="50908-110">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="50908-111">在**全局**页上，单击**全局**配置。</span><span class="sxs-lookup"><span data-stu-id="50908-111">On the **Global** page, click the **Global** configuration.</span></span>
   
    > [!NOTE]  
    > <span data-ttu-id="50908-112">可以为任何 Skype 对于业务服务器部署，配置只有一个网络，以便不会在列表中的多个网络配置。</span><span class="sxs-lookup"><span data-stu-id="50908-112">Only one network can be configured for any Skype for Business Server deployment, so there will never be more than one network configuration in the list.</span></span> <span data-ttu-id="50908-113">无法重命名全局配置。</span><span class="sxs-lookup"><span data-stu-id="50908-113">You cannot rename the Global configuration.</span></span>

5.  <span data-ttu-id="50908-114">在“编辑”\*\*\*\* 菜单上，单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="50908-114">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="50908-115">在**编辑全局设置**页上，选择**启用呼叫允许控制**复选框，然后单击**提交**。</span><span class="sxs-lookup"><span data-stu-id="50908-115">On the **Edit Global Setting** page, select the **Enable call admission control** check box, and then click **Commit**.</span></span>

<span data-ttu-id="50908-116">单击**提交**，当您将运行测试的配置。</span><span class="sxs-lookup"><span data-stu-id="50908-116">When you click **Commit**, you run a test of the configuration.</span></span> <span data-ttu-id="50908-117">将关闭**编辑全局设置**对话框中，返回到**全局**页。</span><span class="sxs-lookup"><span data-stu-id="50908-117">The **Edit Global Settings** dialog box closes, returning you to the **Global** page.</span></span> <span data-ttu-id="50908-118">如果您将会阻止其正常工作 （例如，如果未连接到其他每个区域间路由通过每个区域） 的网络配置中发现的任何错误或不一致情况，您将收到一条警告。</span><span class="sxs-lookup"><span data-stu-id="50908-118">You will receive a warning if any errors or inconsistencies are discovered in your network configuration that will prevent it from working correctly (for example, if every region is not connected to every other region through an interregion route).</span></span>

<span data-ttu-id="50908-119">如果您对您的网络配置更改，您可以通过打开全局配置并单击**提交**运行再次验证检查。</span><span class="sxs-lookup"><span data-stu-id="50908-119">If you make changes to your network configuration, you can run the validation check again by opening the Global configuration and clicking **Commit**.</span></span> <span data-ttu-id="50908-120">不需要先禁用 CAC： 保留检查复选框，然后单击**提交**。</span><span class="sxs-lookup"><span data-stu-id="50908-120">You do not need to disable CAC first: leave the check box checked and click **Commit**.</span></span> <span data-ttu-id="50908-121">您可以这样做任何时候不进行任何配置更改。</span><span class="sxs-lookup"><span data-stu-id="50908-121">You can do this at any time without making any configuration changes.</span></span>

## <a name="see-also"></a><span data-ttu-id="50908-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="50908-122">See Also</span></span>

[<span data-ttu-id="50908-123">规划呼叫允许控制</span><span class="sxs-lookup"><span data-stu-id="50908-123">Plan for call admission control</span></span>](../../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md) 
 
[<span data-ttu-id="50908-124">部署呼叫允许控制</span><span class="sxs-lookup"><span data-stu-id="50908-124">Deploy call admission control</span></span>](../../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) 

[<span data-ttu-id="50908-125">Get-csnetworkconfiguration</span><span class="sxs-lookup"><span data-stu-id="50908-125">Get-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)  

[<span data-ttu-id="50908-126">Set-csnetworkconfiguration</span><span class="sxs-lookup"><span data-stu-id="50908-126">Set-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)  

[<span data-ttu-id="50908-127">删除 CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="50908-127">Remove-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)  
