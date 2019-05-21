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
f1keywords: None
ms.custom:
- Calling Plans
description: 'Learn known issues with the calling plan for Office 365 (PSTN Calling) and what you can do about them. '
ms.openlocfilehash: 9a6f97a93aa6c7b4e847ba1cb3280a21c473db0c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299521"
---
# <a name="calling-plans-known-issues"></a><span data-ttu-id="bafee-103">通话套餐已知问题</span><span class="sxs-lookup"><span data-stu-id="bafee-103">Calling Plans known issues</span></span>

<span data-ttu-id="bafee-104">Office 365 中的通话计划是在 Skype for Business Online 中找到的一项新功能。</span><span class="sxs-lookup"><span data-stu-id="bafee-104">Calling Plans in Office 365 are a new feature found in Skype for Business Online.</span></span> <span data-ttu-id="bafee-105">以下是当前正在跟踪和主动调查的问题。</span><span class="sxs-lookup"><span data-stu-id="bafee-105">The following are current issues that are being tracked and actively investigated.</span></span> <span data-ttu-id="bafee-106">如果在 Office 365 和 Skype for business Online 中的未来版本中更新该功能, 则可能会解决这些功能。</span><span class="sxs-lookup"><span data-stu-id="bafee-106">They will be potentially resolved when the feature is updated in future builds in Office 365 and Skype for Business Online.</span></span>
  
## <a name="calling-plans-known-issues"></a><span data-ttu-id="bafee-107">通话套餐已知问题</span><span class="sxs-lookup"><span data-stu-id="bafee-107">Calling Plans known issues</span></span>

|<span data-ttu-id="bafee-108">**已知问题**</span><span class="sxs-lookup"><span data-stu-id="bafee-108">**Known issue**</span></span>|<span data-ttu-id="bafee-109">**注释**</span><span class="sxs-lookup"><span data-stu-id="bafee-109">**Comments**</span></span>|
|:-----|:-----|
|<span data-ttu-id="bafee-110">从技术预览许可证转换到用于通话计划的生产许可证不会自动更新许可证。</span><span class="sxs-lookup"><span data-stu-id="bafee-110">Transitioning from Tech Preview licenses to production licenses for Calling Plans don't automatically update the license.</span></span>  <br/> |<span data-ttu-id="bafee-111">请首先购买新的许可证，以便准备好将它们分配给你的用户。</span><span class="sxs-lookup"><span data-stu-id="bafee-111">Purchase your new licenses first so they are ready to be assigned to your users.</span></span> <span data-ttu-id="bafee-112">删除用户的促销 (技术预览版) 许可证, 然后**立即**将新的**国内呼叫计划**和/或**国内和国际呼叫计划**许可证分配给用户。</span><span class="sxs-lookup"><span data-stu-id="bafee-112">Remove the promo (Tech Preview) license from a user, and then **IMMEDIATELY** assign the new **Domestic Calling Plan** and/or **Domestic and International Calling Plan** licenses to the user.</span></span> <br/> <span data-ttu-id="bafee-113">如果要为多个用户删除和添加许可证，则应使用 Windows PowerShell 删除所有用户的许可证，然后再使用 Windows PowerShell **立即** 为所有用户分配许可证，这一点非常重要。</span><span class="sxs-lookup"><span data-stu-id="bafee-113">If you are removing and adding licenses for multiple users, it is extremely important that you remove the licenses from all of the users using Windows PowerShell and then **IMMEDIATELY** assign the licenses for all of the users also using Windows PowerShell.</span></span> <span data-ttu-id="bafee-114">这样做可确保在处理大量用户许可证分配时, 服务不会中断。</span><span class="sxs-lookup"><span data-stu-id="bafee-114">Doing this will ensure that there is no disruption in service when handling large volumes of user license assignments.</span></span> <span data-ttu-id="bafee-115">有关 PowerShell 脚本示例, 请参阅[分配 Skype For business 和 Microsoft 团队许可证](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="bafee-115">For sample PowerShell scripts, see [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>  <br/> <span data-ttu-id="bafee-116">**注意:** 如果您使用的是混合用户的本地 PSTN 连接, 则*只*需分配**电话系统**许可证。</span><span class="sxs-lookup"><span data-stu-id="bafee-116">**Note:** If you are using on-premises PSTN connectivity for hybrid users, you  *only*  need to assign a **Phone System** license.</span></span> <span data-ttu-id="bafee-117">您还**不**应分配语音呼叫计划。</span><span class="sxs-lookup"><span data-stu-id="bafee-117">You should **NOT** also assign a voice Calling Plan.</span></span> <span data-ttu-id="bafee-118">但是, 如果在 Office 365 中为 Office 365 中的用户启用呼叫计划, 则仍需为这些用户分配**国内呼叫计划**或**国内和国际呼叫计划**许可证。</span><span class="sxs-lookup"><span data-stu-id="bafee-118">However, if you are enabling Calling Plans in Office 365 for users that are in Office 365, you need to still assign a **Domestic Calling Plan** or a **Domestic and International Calling Plan** license for those users.</span></span> <span data-ttu-id="bafee-119">请参阅[分配 Skype For business 和 Microsoft 团队许可证](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="bafee-119">See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

> [!NOTE]
> <span data-ttu-id="bafee-120">如果您需要获得比这更多的电话号码, 请[联系客户支持部门-管理员帮助](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |</span><span class="sxs-lookup"><span data-stu-id="bafee-120">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |</span></span>
   
## <a name="related-topics"></a><span data-ttu-id="bafee-121">相关主题</span><span class="sxs-lookup"><span data-stu-id="bafee-121">Related topics</span></span>
[<span data-ttu-id="bafee-122">关于转移电话号码的常见问题</span><span class="sxs-lookup"><span data-stu-id="bafee-122">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="bafee-123">用于通话套餐的不同类型的电话号码</span><span class="sxs-lookup"><span data-stu-id="bafee-123">Different kinds of phone numbers used for Calling Plans</span></span>](/MicrosoftTeams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="bafee-124">管理你的组织的电话号码</span><span class="sxs-lookup"><span data-stu-id="bafee-124">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="bafee-125">紧急呼叫条款和条件</span><span class="sxs-lookup"><span data-stu-id="bafee-125">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="bafee-126">[Skype for Business Online：紧急呼叫免责声明标签](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="bafee-126">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 