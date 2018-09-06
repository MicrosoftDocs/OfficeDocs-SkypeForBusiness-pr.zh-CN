---
title: 查看 PSTN 用法记录中的业务的 Skype
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 65025c78-c263-472c-9ff9-e170588f10b5
description: 摘要： 了解如何使用 Skype 业务 Server Control Panel 或 Skype for Business Server 命令行管理程序查看 PSTN 用法记录。
ms.openlocfilehash: 7e0cf091c1fd6afbfde6fc4a35ba049e75deaf4f
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/28/2018
ms.locfileid: "23250264"
---
# <a name="view-pstn-usage-records-in-skype-for-business"></a><span data-ttu-id="41eb1-103">查看 PSTN 用法记录中的业务的 Skype</span><span class="sxs-lookup"><span data-stu-id="41eb1-103">View PSTN usage records in Skype for Business</span></span>

<span data-ttu-id="41eb1-104">**摘要：** 了解如何使用 Skype 业务 Server Control Panel 或 Skype for Business Server 命令行管理程序查看 PSTN 用法记录。</span><span class="sxs-lookup"><span data-stu-id="41eb1-104">**Summary:** Learn how to view PSTN usage records by using the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.</span></span>

<span data-ttu-id="41eb1-105">公用电话交换网 (PSTN) 用法记录指定组织中各个用户或用户组所能发出的呼叫类别（如内部、本地或长途）。</span><span class="sxs-lookup"><span data-stu-id="41eb1-105">A Public Switched Telephone Network (PSTN) usage record specifies a class of call (such as internal, local, or long distance) that can be made by various users or groups of users in an organization.</span></span> <span data-ttu-id="41eb1-106">有关详细信息，请参阅规划文档中的[PSTN 用法记录](https://technet.microsoft.com/library/b5f624aa-abe8-455b-a8e3-c228be230463.aspx)。</span><span class="sxs-lookup"><span data-stu-id="41eb1-106">For details, see [PSTN Usage Records](https://technet.microsoft.com/library/b5f624aa-abe8-455b-a8e3-c228be230463.aspx) in the Planning documentation.</span></span>

### <a name="to-view-a-pstn-usage-record-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="41eb1-107">使用适用于业务 Server Control Panel Skype 查看 PSTN 用法记录</span><span class="sxs-lookup"><span data-stu-id="41eb1-107">To view a PSTN usage record by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="41eb1-108">打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="41eb1-108">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="41eb1-109">在左侧导航栏中，单击“语音路由”\*\*\*\*，然后单击“PSTN 用法”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="41eb1-109">In the left navigation bar, click **Voice Routing** and then click **PSTN Usage**.</span></span>

3. <span data-ttu-id="41eb1-110">在“PSTN 用法”\*\*\*\* 页上，突出显示要查看的 PSTN 用法记录，单击“编辑”\*\*\*\*，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="41eb1-110">On the **PSTN Usage** page, highlight the PSTN usage record you want to view, click **Edit** and then click **Show details**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="41eb1-111">所选 PSTN 用法记录的只读页面会显示关联的路由和关联的语音策略。</span><span class="sxs-lookup"><span data-stu-id="41eb1-111">A read-only page of the selected PSTN usage record shows the associated routes and associated voice policies.</span></span>

### <a name="to-view-pstn-usage-information-by-using-skype-for-business-server-management-shell-cmdlets"></a><span data-ttu-id="41eb1-112">若要使用 Skype 业务 Server Management Shell cmdlet 查看 PSTN 用法信息</span><span class="sxs-lookup"><span data-stu-id="41eb1-112">To view PSTN usage information by using Skype for Business Server Management Shell cmdlets</span></span>

- <span data-ttu-id="41eb1-113">若要查看有关所有 PSTN 用法的信息，业务 Server Management Shell，Skype 中键入以下命令，然后按 ENTER:</span><span class="sxs-lookup"><span data-stu-id="41eb1-113">To view information about all of your PSTN usages, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>

  ```
  Get-CsPstnUsage
  ```

    <span data-ttu-id="41eb1-114">此命令会返回类似下列信息：</span><span class="sxs-lookup"><span data-stu-id="41eb1-114">This command returns information similar to the following:</span></span>

<pre>
  Identity : Global
  Usage    : {Internal, Local, Long Distance}
</pre>

## <a name="see-also"></a><span data-ttu-id="41eb1-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="41eb1-115">See also</span></span>

[<span data-ttu-id="41eb1-116">创建或修改语音策略和配置 PSTN 用法记录中的业务的 Skype</span><span class="sxs-lookup"><span data-stu-id="41eb1-116">Create or modify a voice policy and configure PSTN usage records in Skype for Business</span></span>](voice-policy-and-pstn-usage-records.md)

