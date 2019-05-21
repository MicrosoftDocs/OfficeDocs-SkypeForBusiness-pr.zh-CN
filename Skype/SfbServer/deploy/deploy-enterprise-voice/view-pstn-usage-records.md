---
title: 查看 Skype for Business 中的 PSTN 使用记录
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 65025c78-c263-472c-9ff9-e170588f10b5
description: '摘要: 了解如何使用 Skype for business 服务器控制面板或 Skype for business Server 命令行管理程序查看 PSTN 使用情况记录。'
ms.openlocfilehash: d00fcab8c7f5ad9b8f47d5aecb6c6169e8d43574
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34300921"
---
# <a name="view-pstn-usage-records-in-skype-for-business"></a><span data-ttu-id="f889a-103">查看 Skype for Business 中的 PSTN 使用记录</span><span class="sxs-lookup"><span data-stu-id="f889a-103">View PSTN usage records in Skype for Business</span></span>

<span data-ttu-id="f889a-104">**摘要:** 了解如何使用 Skype for business 服务器控制面板或 Skype for business Server 命令行管理程序查看 PSTN 使用情况记录。</span><span class="sxs-lookup"><span data-stu-id="f889a-104">**Summary:** Learn how to view PSTN usage records by using the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.</span></span>

<span data-ttu-id="f889a-p101">公用电话交换网 (PSTN) 用法记录指定组织中各个用户或用户组所能发出的呼叫类别（如内部、本地或长途）。有关详细信息，请参阅规划文档中的 [PSTN Usage Records](https://technet.microsoft.com/library/b5f624aa-abe8-455b-a8e3-c228be230463.aspx)。</span><span class="sxs-lookup"><span data-stu-id="f889a-p101">A Public Switched Telephone Network (PSTN) usage record specifies a class of call (such as internal, local, or long distance) that can be made by various users or groups of users in an organization. For details, see [PSTN Usage Records](https://technet.microsoft.com/library/b5f624aa-abe8-455b-a8e3-c228be230463.aspx) in the Planning documentation.</span></span>

### <a name="to-view-a-pstn-usage-record-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="f889a-107">使用 "Skype for Business 服务器" 控制面板查看 PSTN 使用记录</span><span class="sxs-lookup"><span data-stu-id="f889a-107">To view a PSTN usage record by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="f889a-108">打开 "Skype for Business 服务器" 控制面板。</span><span class="sxs-lookup"><span data-stu-id="f889a-108">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="f889a-109">在左侧导航栏中，单击“语音路由”\*\*\*\*，然后单击“PSTN 用法”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f889a-109">In the left navigation bar, click **Voice Routing** and then click **PSTN Usage**.</span></span>

3. <span data-ttu-id="f889a-110">在“PSTN 用法”\*\*\*\* 页上，突出显示要查看的 PSTN 用法记录，单击“编辑”\*\*\*\*，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f889a-110">On the **PSTN Usage** page, highlight the PSTN usage record you want to view, click **Edit** and then click **Show details**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f889a-111">所选 PSTN 用法记录的只读页面会显示关联的路由和关联的语音策略。</span><span class="sxs-lookup"><span data-stu-id="f889a-111">A read-only page of the selected PSTN usage record shows the associated routes and associated voice policies.</span></span>

### <a name="to-view-pstn-usage-information-by-using-skype-for-business-server-management-shell-cmdlets"></a><span data-ttu-id="f889a-112">使用 Skype for Business Server Management Shell cmdlet 查看 PSTN 使用信息</span><span class="sxs-lookup"><span data-stu-id="f889a-112">To view PSTN usage information by using Skype for Business Server Management Shell cmdlets</span></span>

- <span data-ttu-id="f889a-113">若要查看有关所有 PSTN 用法的信息, 请在 Skype for Business Server 命令行管理程序中键入以下命令, 然后按 ENTER:</span><span class="sxs-lookup"><span data-stu-id="f889a-113">To view information about all of your PSTN usages, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>

  ```
  Get-CsPstnUsage
  ```

    <span data-ttu-id="f889a-114">此命令会返回类似下列信息：</span><span class="sxs-lookup"><span data-stu-id="f889a-114">This command returns information similar to the following:</span></span>

<pre>
  Identity : Global
  Usage    : {Internal, Local, Long Distance}
</pre>

## <a name="see-also"></a><span data-ttu-id="f889a-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f889a-115">See also</span></span>

[<span data-ttu-id="f889a-116">在 Skype for Business 中创建或修改语音策略和配置 PSTN 使用记录</span><span class="sxs-lookup"><span data-stu-id="f889a-116">Create or modify a voice policy and configure PSTN usage records in Skype for Business</span></span>](voice-policy-and-pstn-usage-records.md)

