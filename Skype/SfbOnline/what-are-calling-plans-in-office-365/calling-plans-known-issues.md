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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: 'Learn known issues with the calling plan for Office 365 (PSTN Calling) and what you can do about them. '
ms.openlocfilehash: 01a49749f472b6a3e591295cff7184dc26fd564a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32233222"
---
# <a name="calling-plans-known-issues"></a><span data-ttu-id="6b04b-103">通话套餐已知问题</span><span class="sxs-lookup"><span data-stu-id="6b04b-103">Calling Plans known issues</span></span>

<span data-ttu-id="6b04b-104">Office 365 中的呼叫计划是业务 online Skype 中找到的新增功能。</span><span class="sxs-lookup"><span data-stu-id="6b04b-104">Calling Plans in Office 365 are a new feature found in Skype for Business Online.</span></span> <span data-ttu-id="6b04b-105">以下是当前问题正在跟踪，主动调查。</span><span class="sxs-lookup"><span data-stu-id="6b04b-105">The following are current issues that are being tracked and actively investigated.</span></span> <span data-ttu-id="6b04b-106">它们将可能解析功能在 Office 365 和 Skype 中的将来版本中更新业务 online 时。</span><span class="sxs-lookup"><span data-stu-id="6b04b-106">They will be potentially resolved when the feature is updated in future builds in Office 365 and Skype for Business Online.</span></span>
  
## <a name="calling-plans-known-issues"></a><span data-ttu-id="6b04b-107">通话套餐已知问题</span><span class="sxs-lookup"><span data-stu-id="6b04b-107">Calling Plans known issues</span></span>

|<span data-ttu-id="6b04b-108">**已知问题**</span><span class="sxs-lookup"><span data-stu-id="6b04b-108">**Known issue**</span></span>|<span data-ttu-id="6b04b-109">**注释**</span><span class="sxs-lookup"><span data-stu-id="6b04b-109">**Comments**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6b04b-110">从技术预览版转换到调用计划生产许可证的许可证不自动更新许可证。</span><span class="sxs-lookup"><span data-stu-id="6b04b-110">Transitioning from Tech Preview licenses to production licenses for Calling Plans don't automatically update the license.</span></span>  <br/> |<span data-ttu-id="6b04b-111">请首先购买新的许可证，以便准备好将它们分配给你的用户。</span><span class="sxs-lookup"><span data-stu-id="6b04b-111">Purchase your new licenses first so they are ready to be assigned to your users.</span></span> <span data-ttu-id="6b04b-112">升级 （技术预览） 许可证删除用户，然后**立即**将新的**国内调用规划**和/或**国内和国际呼叫规划**许可证分配给用户。</span><span class="sxs-lookup"><span data-stu-id="6b04b-112">Remove the promo (Tech Preview) license from a user, and then **IMMEDIATELY** assign the new **Domestic Calling Plan** and/or **Domestic and International Calling Plan** licenses to the user.</span></span> <br/> <span data-ttu-id="6b04b-113">如果要为多个用户删除和添加许可证，则应使用 Windows PowerShell 删除所有用户的许可证，然后再使用 Windows PowerShell **立即** 为所有用户分配许可证，这一点非常重要。</span><span class="sxs-lookup"><span data-stu-id="6b04b-113">If you are removing and adding licenses for multiple users, it is extremely important that you remove the licenses from all of the users using Windows PowerShell and then **IMMEDIATELY** assign the licenses for all of the users also using Windows PowerShell.</span></span> <span data-ttu-id="6b04b-114">此操作将确保有服务不会中断时处理大量用户许可证分配。</span><span class="sxs-lookup"><span data-stu-id="6b04b-114">Doing this will ensure that there is no disruption in service when handling large volumes of user license assignments.</span></span> <span data-ttu-id="6b04b-115">示例 PowerShell 脚本，请参阅[业务和 Microsoft 团队许可证分配 Skype](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="6b04b-115">For sample PowerShell scripts, see [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>  <br/> <span data-ttu-id="6b04b-116">**注意：** 如果您的混合用户使用内部部署 PSTN 连接，您*只*需将**电话系统**许可证分配。</span><span class="sxs-lookup"><span data-stu-id="6b04b-116">**Note:** If you are using on-premises PSTN connectivity for hybrid users, you  *only*  need to assign a **Phone System** license.</span></span> <span data-ttu-id="6b04b-117">**不**应还分配调用规划语音。</span><span class="sxs-lookup"><span data-stu-id="6b04b-117">You should **NOT** also assign a voice Calling Plan.</span></span> <span data-ttu-id="6b04b-118">但是，如果要为 Office 365 中的用户启用调用计划在 Office 365 中，您需要仍分配**国内调用规划**或**国内和国际呼叫规划**许可证，这些用户。</span><span class="sxs-lookup"><span data-stu-id="6b04b-118">However, if you are enabling Calling Plans in Office 365 for users that are in Office 365, you need to still assign a **Domestic Calling Plan** or a **Domestic and International Calling Plan** license for those users.</span></span> <span data-ttu-id="6b04b-119">请参阅[业务和 Microsoft 团队许可证分配 Skype](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="6b04b-119">See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

> [!NOTE]
> <span data-ttu-id="6b04b-120">如果您需要获取比这的多个电话号码，请[与业务产品的管理员技术支持部门联系](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |</span><span class="sxs-lookup"><span data-stu-id="6b04b-120">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |</span></span>
   
## <a name="related-topics"></a><span data-ttu-id="6b04b-121">相关主题</span><span class="sxs-lookup"><span data-stu-id="6b04b-121">Related topics</span></span>
[<span data-ttu-id="6b04b-122">关于转移电话号码的常见问题</span><span class="sxs-lookup"><span data-stu-id="6b04b-122">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="6b04b-123">用于通话套餐的不同类型的电话号码</span><span class="sxs-lookup"><span data-stu-id="6b04b-123">Different kinds of phone numbers used for Calling Plans</span></span>](/MicrosoftTeams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="6b04b-124">管理你的组织的电话号码</span><span class="sxs-lookup"><span data-stu-id="6b04b-124">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="6b04b-125">紧急呼叫条款和条件</span><span class="sxs-lookup"><span data-stu-id="6b04b-125">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="6b04b-126">[Skype for Business Online：紧急呼叫免责声明标签](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="6b04b-126">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 