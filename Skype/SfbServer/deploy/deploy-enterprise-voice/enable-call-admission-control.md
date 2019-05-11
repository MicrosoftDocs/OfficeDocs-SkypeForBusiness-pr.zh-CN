---
title: 启用 Business Server Skype 中的呼叫允许控制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 80201105-18f7-4c02-9c71-8df5a952f6c7
description: 启用业务 Server 企业语音中 Skype 的呼叫允许控制。
ms.openlocfilehash: ce50e11d5d8536dba6038a918a9242ad2cfd6f1d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33892494"
---
# <a name="enable-call-admission-control-in-skype-for-business-server"></a><span data-ttu-id="929b4-103">启用 Business Server Skype 中的呼叫允许控制</span><span class="sxs-lookup"><span data-stu-id="929b4-103">Enable call admission control in Skype for Business Server</span></span>
 
<span data-ttu-id="929b4-104">启用业务 Server 企业语音中 Skype 的呼叫允许控制。</span><span class="sxs-lookup"><span data-stu-id="929b4-104">Enable call admission control in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="929b4-105">配置完呼叫允许控制部署的网络设置后，必须启用 CAC 来使带宽策略生效。</span><span class="sxs-lookup"><span data-stu-id="929b4-105">After you have configured your network settings for call admission control deployment, you must enable CAC to put your bandwidth policies into effect.</span></span>
  
### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="929b4-106">若要使用 Skype 业务 Server 命令行管理程序启用呼叫允许控制</span><span class="sxs-lookup"><span data-stu-id="929b4-106">To enable call admission control by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="929b4-107">启动 Skype for Business Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\* 和“Skype for Business 2015”\*\*\*\*，然后单击“Skype for Business Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="929b4-107">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="929b4-p101">运行 Set-CsNetworkConfiguration cmdlet 以在网络中启用 CAC。例如，运行：</span><span class="sxs-lookup"><span data-stu-id="929b4-p101">Run the Set-CsNetworkConfiguration cmdlet to enable CAC in your network. For example, run:</span></span>
    
   ```
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 1
   ```

    <span data-ttu-id="929b4-110">如果要在网络中禁用 CAC，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="929b4-110">If you want to disable CAC in your network, run the following:</span></span>
    
   ```
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 0
   ```

### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="929b4-111">使用适用于业务 Server Control Panel Skype 启用呼叫允许控制</span><span class="sxs-lookup"><span data-stu-id="929b4-111">To enable call admission control by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="929b4-112">打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="929b4-112">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="929b4-113">在左侧导航栏中，单击“网络配置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="929b4-113">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="929b4-114">单击“全局”\*\*\*\* 导航按钮。</span><span class="sxs-lookup"><span data-stu-id="929b4-114">Click the **Global** navigation button.</span></span>
    
4. <span data-ttu-id="929b4-115">单击列表中的“全局”\*\*\*\*，然后在“编辑”\*\*\*\* 菜单中选择“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="929b4-115">Click **Global** in the list, and then select **Show Details** on the **Edit** menu.</span></span>
    
5. <span data-ttu-id="929b4-116">在“编辑全局设置”\*\*\*\* 页上，选中“启用呼叫允许控制”\*\*\*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="929b4-116">On the **Edit Global Settings** page, select the **Enable call admission control** check box.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="929b4-117">如果要在整个部署中禁用呼叫允许控制，请清除此复选框。</span><span class="sxs-lookup"><span data-stu-id="929b4-117">If you want to disable call admission control throughout your deployment, clear this check box.</span></span> 
  
6. <span data-ttu-id="929b4-118">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="929b4-118">Click **Commit**.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="929b4-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="929b4-119">See also</span></span>

[<span data-ttu-id="929b4-120">Get-csnetworkconfiguration</span><span class="sxs-lookup"><span data-stu-id="929b4-120">Get-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkconfiguration?view=skype-ps)
  
[<span data-ttu-id="929b4-121">Set-csnetworkconfiguration</span><span class="sxs-lookup"><span data-stu-id="929b4-121">Set-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkconfiguration?view=skype-ps)
  
[<span data-ttu-id="929b4-122">删除 CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="929b4-122">Remove-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkconfiguration?view=skype-ps)
