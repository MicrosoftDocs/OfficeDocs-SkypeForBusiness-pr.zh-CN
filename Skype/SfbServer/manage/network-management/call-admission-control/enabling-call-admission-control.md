---
title: 启用呼叫许可控制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: " 配置呼叫许可控制 (CAC) 网络后, 必须启用 CAC 才能强制实施带宽限制。"
ms.openlocfilehash: cbe3ad690f7061611a91474ce6df1fe39d84b0fd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279548"
---
# <a name="enabling-call-admission-control-in-skype-for-business-server"></a><span data-ttu-id="39b38-103">在 Skype for Business Server 上启用呼叫允许控制</span><span class="sxs-lookup"><span data-stu-id="39b38-103">Enabling call admission control in Skype for Business Server</span></span>

<span data-ttu-id="39b38-104">呼叫允许控制 (CAC) 是区域、站点和子网的网络，通过它可基于可用带宽对音频和视频传输设置限制。</span><span class="sxs-lookup"><span data-stu-id="39b38-104">Call admission control (CAC) is a network of regions, sites, and subnets that enable you to place restrictions on audio and video transmissions based on available bandwidth.</span></span> <span data-ttu-id="39b38-105">配置 CAC 网络后, 必须启用 CAC 才能强制实施带宽限制。</span><span class="sxs-lookup"><span data-stu-id="39b38-105">After you configure the CAC network, you must enable CAC to enforce the bandwidth limitations.</span></span> <span data-ttu-id="39b38-106">您可以使用 Skype for Business 服务器控制面板执行此操作。</span><span class="sxs-lookup"><span data-stu-id="39b38-106">You can use the Skype for Business Server Control Panel to do this.</span></span>


## <a name="to-enable-cac-from-the-skype-for-business-server-control-panel"></a><span data-ttu-id="39b38-107">从 "Skype for Business 服务器" 控制面板启用 CAC</span><span class="sxs-lookup"><span data-stu-id="39b38-107">To enable CAC from the Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="39b38-108">使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="39b38-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="39b38-109">打开一个浏览器窗口, 然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。</span><span class="sxs-lookup"><span data-stu-id="39b38-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="39b38-110">在左侧导航栏中, 单击 "**网络配置**", 然后单击 "**全局**"。</span><span class="sxs-lookup"><span data-stu-id="39b38-110">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="39b38-111">在 "**全局**" 页面上, 单击 "**全局**配置"。</span><span class="sxs-lookup"><span data-stu-id="39b38-111">On the **Global** page, click the **Global** configuration.</span></span>
   
    > [!NOTE]  
    > <span data-ttu-id="39b38-112">仅可为任何 Skype for Business Server 部署配置一个网络, 因此列表中永远不会有多个网络配置。</span><span class="sxs-lookup"><span data-stu-id="39b38-112">Only one network can be configured for any Skype for Business Server deployment, so there will never be more than one network configuration in the list.</span></span> <span data-ttu-id="39b38-113">不能重命名全局配置。</span><span class="sxs-lookup"><span data-stu-id="39b38-113">You cannot rename the Global configuration.</span></span>

5.  <span data-ttu-id="39b38-114">在“编辑”\*\*\*\* 菜单上，单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="39b38-114">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="39b38-115">在 "**编辑全局设置**" 页面上, 选中 "**启用呼叫许可控制**" 复选框, 然后单击 "**提交**"。</span><span class="sxs-lookup"><span data-stu-id="39b38-115">On the **Edit Global Setting** page, select the **Enable call admission control** check box, and then click **Commit**.</span></span>

<span data-ttu-id="39b38-116">单击 "**提交**" 时, 将运行配置测试。</span><span class="sxs-lookup"><span data-stu-id="39b38-116">When you click **Commit**, you run a test of the configuration.</span></span> <span data-ttu-id="39b38-117">"**编辑全局设置**" 对话框将关闭, 返回到**全局**页。</span><span class="sxs-lookup"><span data-stu-id="39b38-117">The **Edit Global Settings** dialog box closes, returning you to the **Global** page.</span></span> <span data-ttu-id="39b38-118">如果你的网络配置中发现了任何错误或不一致 (例如, 如果每个区域未通过 interregion 路由连接到其他每个区域), 你将收到警告。</span><span class="sxs-lookup"><span data-stu-id="39b38-118">You will receive a warning if any errors or inconsistencies are discovered in your network configuration that will prevent it from working correctly (for example, if every region is not connected to every other region through an interregion route).</span></span>

<span data-ttu-id="39b38-119">如果你对网络配置进行了更改, 则可以通过打开全局配置并单击 "**提交**" 来再次运行验证检查。</span><span class="sxs-lookup"><span data-stu-id="39b38-119">If you make changes to your network configuration, you can run the validation check again by opening the Global configuration and clicking **Commit**.</span></span> <span data-ttu-id="39b38-120">无需首先禁用 CAC: 选中复选框, 然后单击 "**提交**"。</span><span class="sxs-lookup"><span data-stu-id="39b38-120">You do not need to disable CAC first: leave the check box checked and click **Commit**.</span></span> <span data-ttu-id="39b38-121">您可以随时执行此操作, 而无需进行任何配置更改。</span><span class="sxs-lookup"><span data-stu-id="39b38-121">You can do this at any time without making any configuration changes.</span></span>

## <a name="see-also"></a><span data-ttu-id="39b38-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="39b38-122">See Also</span></span>

[<span data-ttu-id="39b38-123">规划呼叫允许控制</span><span class="sxs-lookup"><span data-stu-id="39b38-123">Plan for call admission control</span></span>](../../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md) 
 
[<span data-ttu-id="39b38-124">部署呼叫允许控制</span><span class="sxs-lookup"><span data-stu-id="39b38-124">Deploy call admission control</span></span>](../../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) 

[<span data-ttu-id="39b38-125">Set-csnetworkconfiguration</span><span class="sxs-lookup"><span data-stu-id="39b38-125">Get-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)  

[<span data-ttu-id="39b38-126">Set-Set-csnetworkconfiguration</span><span class="sxs-lookup"><span data-stu-id="39b38-126">Set-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)  

[<span data-ttu-id="39b38-127">Remove-Set-csnetworkconfiguration</span><span class="sxs-lookup"><span data-stu-id="39b38-127">Remove-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)  
