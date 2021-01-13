---
title: 启用呼叫允许控制
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
description: " 在将呼叫允许控制 (CAC) 网络后，必须启用 CAC 才能强制实施带宽限制。"
ms.openlocfilehash: 8e996b4d2272144a35f667a5d6987b2cb91af708
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816502"
---
# <a name="enabling-call-admission-control-in-skype-for-business-server"></a><span data-ttu-id="221cb-103">在 Skype for Business Server 上启用呼叫允许控制</span><span class="sxs-lookup"><span data-stu-id="221cb-103">Enabling call admission control in Skype for Business Server</span></span>

<span data-ttu-id="221cb-104">呼叫允许控制 (CAC) 是区域、站点和子网的网络，通过它可基于可用带宽对音频和视频传输设置限制。</span><span class="sxs-lookup"><span data-stu-id="221cb-104">Call admission control (CAC) is a network of regions, sites, and subnets that enable you to place restrictions on audio and video transmissions based on available bandwidth.</span></span> <span data-ttu-id="221cb-105">配置 CAC 网络后，必须启用 CAC 以强制实施带宽限制。</span><span class="sxs-lookup"><span data-stu-id="221cb-105">After you configure the CAC network, you must enable CAC to enforce the bandwidth limitations.</span></span> <span data-ttu-id="221cb-106">可以使用 Skype for Business Server 控制面板来这样做。</span><span class="sxs-lookup"><span data-stu-id="221cb-106">You can use the Skype for Business Server Control Panel to do this.</span></span>


## <a name="to-enable-cac-from-the-skype-for-business-server-control-panel"></a><span data-ttu-id="221cb-107">从 Skype for Business Server 控制面板启用 CAC</span><span class="sxs-lookup"><span data-stu-id="221cb-107">To enable CAC from the Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="221cb-108">从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或已分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。</span><span class="sxs-lookup"><span data-stu-id="221cb-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="221cb-109">打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="221cb-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="221cb-110">在左侧导航栏中，单击 **"网络配置**"，然后单击"**全局"。**</span><span class="sxs-lookup"><span data-stu-id="221cb-110">In the left navigation bar, click **Network Configuration**, and then click **Global**.</span></span>

4.  <span data-ttu-id="221cb-111">在“全局”页上，单击“全局”配置。</span><span class="sxs-lookup"><span data-stu-id="221cb-111">On the **Global** page, click the **Global** configuration.</span></span>
   
    > [!NOTE]  
    > <span data-ttu-id="221cb-112">只能为任何 Skype for Business Server 部署配置一个网络，因此列表中绝不会存在多个网络配置。</span><span class="sxs-lookup"><span data-stu-id="221cb-112">Only one network can be configured for any Skype for Business Server deployment, so there will never be more than one network configuration in the list.</span></span> <span data-ttu-id="221cb-113">无法重命名“全局”配置。</span><span class="sxs-lookup"><span data-stu-id="221cb-113">You cannot rename the Global configuration.</span></span>

5.  <span data-ttu-id="221cb-114">在“编辑”菜单上，单击“显示详细信息”。</span><span class="sxs-lookup"><span data-stu-id="221cb-114">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="221cb-115">在“编辑全局设置”页上，选中“启用呼叫允许控制”复选框，然后单击“提交”。</span><span class="sxs-lookup"><span data-stu-id="221cb-115">On the **Edit Global Setting** page, select the **Enable call admission control** check box, and then click **Commit**.</span></span>

<span data-ttu-id="221cb-p103">单击“提交”时，运行配置测试。此时将关闭“编辑全局设置”对话框，并返回到“全局”页。如果在网络配置中发现任何阻止其正常工作的错误或不一致问题（例如，如果每个区域未通过区域间路由连接到其他每个区域），则会收到警告。</span><span class="sxs-lookup"><span data-stu-id="221cb-p103">When you click **Commit**, you run a test of the configuration. The **Edit Global Settings** dialog box closes, returning you to the **Global** page. You will receive a warning if any errors or inconsistencies are discovered in your network configuration that will prevent it from working correctly (for example, if every region is not connected to every other region through an interregion route).</span></span>

<span data-ttu-id="221cb-p104">如果更改网络配置，则可通过打开“全局”配置并单击“提交”再次运行验证检查。无需先禁用 CAC：保留此复选框的选中状态，并单击“提交”。在未对配置进行任何更改的情况下可随时执行此操作。</span><span class="sxs-lookup"><span data-stu-id="221cb-p104">If you make changes to your network configuration, you can run the validation check again by opening the Global configuration and clicking **Commit**. You do not need to disable CAC first: leave the check box checked and click **Commit**. You can do this at any time without making any configuration changes.</span></span>

## <a name="see-also"></a><span data-ttu-id="221cb-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="221cb-122">See Also</span></span>

[<span data-ttu-id="221cb-123">规划呼叫允许控制</span><span class="sxs-lookup"><span data-stu-id="221cb-123">Plan for call admission control</span></span>](../../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md) 
 
[<span data-ttu-id="221cb-124">部署呼叫允许控制</span><span class="sxs-lookup"><span data-stu-id="221cb-124">Deploy call admission control</span></span>](../../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) 

[<span data-ttu-id="221cb-125">Get-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="221cb-125">Get-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)  

[<span data-ttu-id="221cb-126">Set-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="221cb-126">Set-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)  

[<span data-ttu-id="221cb-127">Remove-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="221cb-127">Remove-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)  
