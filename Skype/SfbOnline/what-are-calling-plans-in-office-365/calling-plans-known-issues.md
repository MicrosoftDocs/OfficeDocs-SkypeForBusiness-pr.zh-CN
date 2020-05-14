---
title: 通话套餐已知问题
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: baa3645a-0518-472e-942e-971c63ba4ca0
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Calling Plans
description: 了解 PSTN 呼叫的通话计划的已知问题以及你可以执行的操作。
ms.openlocfilehash: 3a97057f61c154ded83b85becbfcf53dc2b4bc78
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220732"
---
# <a name="calling-plans-known-issues"></a><span data-ttu-id="534ae-103">通话套餐已知问题</span><span class="sxs-lookup"><span data-stu-id="534ae-103">Calling Plans known issues</span></span>

<span data-ttu-id="534ae-p101">通话计划是 Skype for Business Online 中发现的一项新功能。以下是当前正在跟踪和主动调查的问题。在将来的内部版本中更新该功能时，它们可能会得到解决。</span><span class="sxs-lookup"><span data-stu-id="534ae-p101">Calling Plans are a new feature found in Skype for Business Online. The following are current issues that are being tracked and actively investigated. They will be potentially resolved when the feature is updated in future builds.</span></span>
  
## <a name="calling-plans-known-issues"></a><span data-ttu-id="534ae-107">通话套餐已知问题</span><span class="sxs-lookup"><span data-stu-id="534ae-107">Calling Plans known issues</span></span>

|<span data-ttu-id="534ae-108">**已知问题**</span><span class="sxs-lookup"><span data-stu-id="534ae-108">**Known issue**</span></span>|<span data-ttu-id="534ae-109">**注释**</span><span class="sxs-lookup"><span data-stu-id="534ae-109">**Comments**</span></span>|
|:-----|:-----|
|<span data-ttu-id="534ae-110">从技术预览许可证转换到用于通话计划的生产许可证不会自动更新许可证。</span><span class="sxs-lookup"><span data-stu-id="534ae-110">Transitioning from Tech Preview licenses to production licenses for Calling Plans don't automatically update the license.</span></span>  <br/> |<span data-ttu-id="534ae-111">请首先购买新的许可证，以便准备好将它们分配给你的用户。</span><span class="sxs-lookup"><span data-stu-id="534ae-111">Purchase your new licenses first so they are ready to be assigned to your users.</span></span> <span data-ttu-id="534ae-112">删除用户的促销（技术预览版）许可证，然后**立即**将新的**国内呼叫计划**和/或**国内和国际呼叫计划**许可证分配给用户。</span><span class="sxs-lookup"><span data-stu-id="534ae-112">Remove the promo (Tech Preview) license from a user, and then **IMMEDIATELY** assign the new **Domestic Calling Plan** and/or **Domestic and International Calling Plan** licenses to the user.</span></span> <br/> <span data-ttu-id="534ae-113">如果要为多个用户删除和添加许可证，则应使用 Windows PowerShell 删除所有用户的许可证，然后再使用 Windows PowerShell **立即** 为所有用户分配许可证，这一点非常重要。</span><span class="sxs-lookup"><span data-stu-id="534ae-113">If you are removing and adding licenses for multiple users, it is extremely important that you remove the licenses from all of the users using Windows PowerShell and then **IMMEDIATELY** assign the licenses for all of the users also using Windows PowerShell.</span></span> <span data-ttu-id="534ae-114">这样做可确保在处理大量用户许可证分配时，服务不会中断。</span><span class="sxs-lookup"><span data-stu-id="534ae-114">Doing this will ensure that there is no disruption in service when handling large volumes of user license assignments.</span></span> <span data-ttu-id="534ae-115">有关 PowerShell 脚本示例，请参阅[分配 Skype For business 和 Microsoft 团队许可证](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="534ae-115">For sample PowerShell scripts, see [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>  <br/> <span data-ttu-id="534ae-116">**注意：** 如果您使用的是混合用户的本地 PSTN 连接，则*只*需分配**电话系统**许可证。</span><span class="sxs-lookup"><span data-stu-id="534ae-116">**Note:** If you are using on-premises PSTN connectivity for hybrid users, you *only* need to assign a **Phone System** license.</span></span> <span data-ttu-id="534ae-117">您还**不**应分配语音呼叫计划。</span><span class="sxs-lookup"><span data-stu-id="534ae-117">You should **NOT** also assign a voice Calling Plan.</span></span> <span data-ttu-id="534ae-118">但是，如果在 Microsoft 365 或 Office 365 中为 Microsoft 365 或 Office 365 中的用户启用呼叫计划，则仍需为这些用户分配**国内呼叫计划**或**国内和国际呼叫计划**许可证。</span><span class="sxs-lookup"><span data-stu-id="534ae-118">However, if you are enabling Calling Plans in Microsoft 365 or Office 365 for users that are in Microsoft 365 or Office 365, you need to still assign a **Domestic Calling Plan** or a **Domestic and International Calling Plan** license for those users.</span></span> <span data-ttu-id="534ae-119">请参阅[分配 Skype For business 和 Microsoft 团队许可证](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="534ae-119">See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

> [!NOTE]
> <span data-ttu-id="534ae-120">如果您需要获得比这更多的电话号码，请[联系客户支持部门-管理员帮助](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |</span><span class="sxs-lookup"><span data-stu-id="534ae-120">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |</span></span>
   
## <a name="related-topics"></a><span data-ttu-id="534ae-121">相关主题</span><span class="sxs-lookup"><span data-stu-id="534ae-121">Related topics</span></span>
[<span data-ttu-id="534ae-122">关于转移电话号码的常见问题</span><span class="sxs-lookup"><span data-stu-id="534ae-122">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="534ae-123">用于通话套餐的不同类型的电话号码</span><span class="sxs-lookup"><span data-stu-id="534ae-123">Different kinds of phone numbers used for Calling Plans</span></span>](/MicrosoftTeams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="534ae-124">管理你的组织的电话号码</span><span class="sxs-lookup"><span data-stu-id="534ae-124">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="534ae-125">紧急呼叫条款和条件</span><span class="sxs-lookup"><span data-stu-id="534ae-125">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="534ae-126">[Skype for Business Online：紧急呼叫免责声明标签](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="534ae-126">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 
