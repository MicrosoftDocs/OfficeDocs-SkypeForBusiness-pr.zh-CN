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
description: 了解 PSTN 呼叫的呼叫计划的已知问题，以及您可以如何解决这些问题。
ms.openlocfilehash: 9c660ee3b173f104e26816460db45c5bcf400837
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238018"
---
# <a name="calling-plans-known-issues"></a><span data-ttu-id="eb2d1-103">通话套餐已知问题</span><span class="sxs-lookup"><span data-stu-id="eb2d1-103">Calling Plans known issues</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="eb2d1-104">呼叫计划是联机通话中的Skype for Business功能。</span><span class="sxs-lookup"><span data-stu-id="eb2d1-104">Calling Plans are a new feature found in Skype for Business Online.</span></span> <span data-ttu-id="eb2d1-105">以下是当前正在跟踪并积极调查的问题。</span><span class="sxs-lookup"><span data-stu-id="eb2d1-105">The following are current issues that are being tracked and actively investigated.</span></span> <span data-ttu-id="eb2d1-106">在将来的生成中更新功能时，它们可能会得到解决。</span><span class="sxs-lookup"><span data-stu-id="eb2d1-106">They will be potentially resolved when the feature is updated in future builds.</span></span>
  
## <a name="calling-plans-known-issues"></a><span data-ttu-id="eb2d1-107">通话套餐已知问题</span><span class="sxs-lookup"><span data-stu-id="eb2d1-107">Calling Plans known issues</span></span>

|<span data-ttu-id="eb2d1-108">**已知问题**</span><span class="sxs-lookup"><span data-stu-id="eb2d1-108">**Known issue**</span></span>|<span data-ttu-id="eb2d1-109">**注释**</span><span class="sxs-lookup"><span data-stu-id="eb2d1-109">**Comments**</span></span>|
|:-----|:-----|
|<span data-ttu-id="eb2d1-110">从技术预览版许可证过渡到调用计划的生产许可证不会自动更新许可证。</span><span class="sxs-lookup"><span data-stu-id="eb2d1-110">Transitioning from Tech Preview licenses to production licenses for Calling Plans don't automatically update the license.</span></span>  <br/> |<span data-ttu-id="eb2d1-111">请首先购买新的许可证，以便准备好将它们分配给你的用户。</span><span class="sxs-lookup"><span data-stu-id="eb2d1-111">Purchase your new licenses first so they are ready to be assigned to your users.</span></span> <span data-ttu-id="eb2d1-112">从用户中删除 (技术预览版) 许可证，然后立即向该用户分配新的国内呼叫计划和/或国内和国际呼叫计划许可证。 </span><span class="sxs-lookup"><span data-stu-id="eb2d1-112">Remove the promo (Tech Preview) license from a user, and then **IMMEDIATELY** assign the new **Domestic Calling Plan** and/or **Domestic and International Calling Plan** licenses to the user.</span></span> <br/> <span data-ttu-id="eb2d1-113">如果要为多个用户删除和添加许可证，则应使用 Windows PowerShell 删除所有用户的许可证，然后再使用 Windows PowerShell **立即** 为所有用户分配许可证，这一点非常重要。</span><span class="sxs-lookup"><span data-stu-id="eb2d1-113">If you are removing and adding licenses for multiple users, it is extremely important that you remove the licenses from all of the users using Windows PowerShell and then **IMMEDIATELY** assign the licenses for all of the users also using Windows PowerShell.</span></span> <span data-ttu-id="eb2d1-114">这样做可确保在处理大量用户许可证分配时，服务不会中断。</span><span class="sxs-lookup"><span data-stu-id="eb2d1-114">Doing this will ensure that there is no disruption in service when handling large volumes of user license assignments.</span></span> <span data-ttu-id="eb2d1-115">有关示例 PowerShell 脚本，请参阅[分配Skype for Business和Microsoft Teams许可证](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="eb2d1-115">For sample PowerShell scripts, see [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>  <br/> <span data-ttu-id="eb2d1-116">**注意：** 如果为混合用户使用本地 PSTN *连接，则* 只需 **分配一个** 电话系统许可证。</span><span class="sxs-lookup"><span data-stu-id="eb2d1-116">**Note:** If you are using on-premises PSTN connectivity for hybrid users, you *only* need to assign a **Phone System** license.</span></span> <span data-ttu-id="eb2d1-117">你 **不应分配** 语音呼叫计划。</span><span class="sxs-lookup"><span data-stu-id="eb2d1-117">You should **NOT** also assign a voice Calling Plan.</span></span> <span data-ttu-id="eb2d1-118">但是，如果在 Microsoft 365 或 Office 365 中为 Microsoft 365 或 Office 365 中的用户启用呼叫计划，你仍然需要为这些用户分配国内呼叫计划或国内和国际呼叫计划许可证。 </span><span class="sxs-lookup"><span data-stu-id="eb2d1-118">However, if you are enabling Calling Plans in Microsoft 365 or Office 365 for users that are in Microsoft 365 or Office 365, you need to still assign a **Domestic Calling Plan** or a **Domestic and International Calling Plan** license for those users.</span></span> <span data-ttu-id="eb2d1-119">请参阅[分配Skype for Business许可证Microsoft Teams许可证](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="eb2d1-119">See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

> [!NOTE]
> <span data-ttu-id="eb2d1-120">如果需要获取的电话号码超过此数目，请联系商业产品支持 [人员 - 管理员帮助](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |</span><span class="sxs-lookup"><span data-stu-id="eb2d1-120">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |</span></span>
   
## <a name="related-topics"></a><span data-ttu-id="eb2d1-121">相关主题</span><span class="sxs-lookup"><span data-stu-id="eb2d1-121">Related topics</span></span>
[<span data-ttu-id="eb2d1-122">关于转移电话号码的常见问题</span><span class="sxs-lookup"><span data-stu-id="eb2d1-122">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="eb2d1-123">用于通话套餐的不同类型的电话号码</span><span class="sxs-lookup"><span data-stu-id="eb2d1-123">Different kinds of phone numbers used for Calling Plans</span></span>](/MicrosoftTeams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="eb2d1-124">管理你的组织的电话号码</span><span class="sxs-lookup"><span data-stu-id="eb2d1-124">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="eb2d1-125">紧急呼叫条款和条件</span><span class="sxs-lookup"><span data-stu-id="eb2d1-125">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="eb2d1-126">[Skype for Business Online：紧急呼叫免责声明标签](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="eb2d1-126">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 
