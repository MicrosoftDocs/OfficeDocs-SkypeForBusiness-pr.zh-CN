---
title: 在 Skype for Business Server 2015 中启用呼叫允许控制
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
ms.assetid: 80201105-18f7-4c02-9c71-8df5a952f6c7
description: 启用业务服务器企业语音在 Skype 呼叫许可控制。
ms.openlocfilehash: 52425dffc788ab2d1e6822957f30b67e00cb7a9c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="enable-call-admission-control-in-skype-for-business-server-2015"></a><span data-ttu-id="bc3b5-103">在 Skype for Business Server 2015 中启用呼叫允许控制</span><span class="sxs-lookup"><span data-stu-id="bc3b5-103">Enable call admission control in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="bc3b5-104">启用业务服务器企业语音在 Skype 呼叫许可控制。</span><span class="sxs-lookup"><span data-stu-id="bc3b5-104">Enable call admission control in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="bc3b5-105">配置完呼叫允许控制部署的网络设置后，必须启用 CAC 来使带宽策略生效。</span><span class="sxs-lookup"><span data-stu-id="bc3b5-105">After you have configured your network settings for call admission control deployment, you must enable CAC to put your bandwidth policies into effect.</span></span>
  
### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="bc3b5-106">若要启用通过 Skype 业务服务器管理外壳程序调用许可控制</span><span class="sxs-lookup"><span data-stu-id="bc3b5-106">To enable call admission control by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="bc3b5-107">启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。</span><span class="sxs-lookup"><span data-stu-id="bc3b5-107">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="bc3b5-p101">运行 Set-CsNetworkConfiguration cmdlet 以在网络中启用 CAC。例如，运行：</span><span class="sxs-lookup"><span data-stu-id="bc3b5-p101">Run the Set-CsNetworkConfiguration cmdlet to enable CAC in your network. For example, run:</span></span>
    
   ```
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 1
   ```

    <span data-ttu-id="bc3b5-110">如果要在网络中禁用 CAC，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="bc3b5-110">If you want to disable CAC in your network, run the following:</span></span>
    
   ```
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 0
   ```

### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="bc3b5-111">通过 Skype 业务服务器控制面板启用呼叫许可控制</span><span class="sxs-lookup"><span data-stu-id="bc3b5-111">To enable call admission control by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="bc3b5-112">打开 Skype 业务服务器的控制面板。</span><span class="sxs-lookup"><span data-stu-id="bc3b5-112">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="bc3b5-113">在左侧导航栏中，单击“网络配置”****。</span><span class="sxs-lookup"><span data-stu-id="bc3b5-113">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="bc3b5-114">单击“全局”****导航按钮。</span><span class="sxs-lookup"><span data-stu-id="bc3b5-114">Click the **Global** navigation button.</span></span>
    
4. <span data-ttu-id="bc3b5-115">单击列表中的“全局”****，然后在“编辑”****菜单中选择“显示详细信息”****。</span><span class="sxs-lookup"><span data-stu-id="bc3b5-115">Click **Global** in the list, and then select **Show Details** on the **Edit** menu.</span></span>
    
5. <span data-ttu-id="bc3b5-116">在“编辑全局设置”****页上，选中“启用呼叫允许控制”****复选框。</span><span class="sxs-lookup"><span data-stu-id="bc3b5-116">On the **Edit Global Settings** page, select the **Enable call admission control** check box.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="bc3b5-117">如果要在整个部署中禁用呼叫允许控制，请清除此复选框。</span><span class="sxs-lookup"><span data-stu-id="bc3b5-117">If you want to disable call admission control throughout your deployment, clear this check box.</span></span> 
  
6. <span data-ttu-id="bc3b5-118">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="bc3b5-118">Click **Commit**.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="bc3b5-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bc3b5-119">See also</span></span>

#### 

[<span data-ttu-id="bc3b5-120">获得 CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="bc3b5-120">Get-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkconfiguration?view=skype-ps)
  
[<span data-ttu-id="bc3b5-121">一组 CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="bc3b5-121">Set-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkconfiguration?view=skype-ps)
  
[<span data-ttu-id="bc3b5-122">删除 CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="bc3b5-122">Remove-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkconfiguration?view=skype-ps)

