---
title: 在 Skype for Business 2015 中查看 PSTN 用法记录
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
ms.assetid: 65025c78-c263-472c-9ff9-e170588f10b5
description: 摘要： 了解如何通过使用 Skype 业务服务器的控制面板或 Skype 业务服务器管理外壳程序查看 PSTN 使用记录。
ms.openlocfilehash: 63e35879f9530d56ef770584de45a169c20ea057
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="view-pstn-usage-records-in-skype-for-business-2015"></a><span data-ttu-id="fe109-103">在 Skype for Business 2015 中查看 PSTN 用法记录</span><span class="sxs-lookup"><span data-stu-id="fe109-103">View PSTN usage records in Skype for Business 2015</span></span>
 
<span data-ttu-id="fe109-104">**摘要：**了解如何通过使用 Skype 业务服务器的控制面板或 Skype 业务服务器管理外壳程序查看 PSTN 使用记录。</span><span class="sxs-lookup"><span data-stu-id="fe109-104">**Summary:** Learn how to view PSTN usage records by using the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.</span></span>
  
<span data-ttu-id="fe109-105">公用电话交换网 (PSTN) 用法记录指定组织中各个用户或用户组所能发出的呼叫类别（如内部、本地或长途）。</span><span class="sxs-lookup"><span data-stu-id="fe109-105">A Public Switched Telephone Network (PSTN) usage record specifies a class of call (such as internal, local, or long distance) that can be made by various users or groups of users in an organization.</span></span> <span data-ttu-id="fe109-106">有关详细信息，请参阅规划文档中的[PSTN 使用记录](http://technet.microsoft.com/library/b5f624aa-abe8-455b-a8e3-c228be230463.aspx)。</span><span class="sxs-lookup"><span data-stu-id="fe109-106">For details, see [PSTN Usage Records](http://technet.microsoft.com/library/b5f624aa-abe8-455b-a8e3-c228be230463.aspx) in the Planning documentation.</span></span>
  
### <a name="to-view-a-pstn-usage-record-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="fe109-107">若要查看通过 Skype 业务服务器控件面板 PSTN 使用记录</span><span class="sxs-lookup"><span data-stu-id="fe109-107">To view a PSTN usage record by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="fe109-108">打开 Skype 业务服务器的控制面板。</span><span class="sxs-lookup"><span data-stu-id="fe109-108">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="fe109-109">在左侧导航栏中，单击“语音路由”****，然后单击“PSTN 用法”****。</span><span class="sxs-lookup"><span data-stu-id="fe109-109">In the left navigation bar, click **Voice Routing** and then click **PSTN Usage**.</span></span>
    
3. <span data-ttu-id="fe109-110">在“PSTN 用法”****页上，突出显示要查看的 PSTN 用法记录，单击“编辑”****，然后单击“显示详细信息”****。</span><span class="sxs-lookup"><span data-stu-id="fe109-110">On the **PSTN Usage** page, highlight the PSTN usage record you want to view, click **Edit** and then click **Show details**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="fe109-111">所选 PSTN 用法记录的只读页面会显示关联的路由和关联的语音策略。</span><span class="sxs-lookup"><span data-stu-id="fe109-111">A read-only page of the selected PSTN usage record shows the associated routes and associated voice policies.</span></span> 
  
### <a name="to-view-pstn-usage-information-by-using-skype-for-business-server-management-shell-cmdlets"></a><span data-ttu-id="fe109-112">若要查看通过 Skype 业务服务器管理外壳 cmdlet PSTN 使用信息</span><span class="sxs-lookup"><span data-stu-id="fe109-112">To view PSTN usage information by using Skype for Business Server Management Shell cmdlets</span></span>

- <span data-ttu-id="fe109-113">若要查看有关所有 PSTN 用法的信息，为业务服务器管理外壳，Skype 中键入下面的命令，然后按 enter 键：</span><span class="sxs-lookup"><span data-stu-id="fe109-113">To view information about all of your PSTN usages, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
  ```
  Get-CsPstnUsage
  ```

    <span data-ttu-id="fe109-114">此命令会返回类似下列信息：</span><span class="sxs-lookup"><span data-stu-id="fe109-114">This command returns information similar to the following:</span></span>
    
  ```
  Identity : Global
  Usage    : {Internal, Local, Long Distance}
  ```

## <a name="see-also"></a><span data-ttu-id="fe109-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fe109-115">See also</span></span>

#### 

[<span data-ttu-id="fe109-116">创建或修改语音策略和业务 2015年的 Skype 在配置 PSTN 使用记录</span><span class="sxs-lookup"><span data-stu-id="fe109-116">Create or modify a voice policy and configure PSTN usage records in Skype for Business 2015</span></span>](voice-policy-and-pstn-usage-records.md)

