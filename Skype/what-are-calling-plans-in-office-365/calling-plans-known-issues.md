---
title: "调用计划的已知的问题"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: baa3645a-0518-472e-942e-971c63ba4ca0
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: Calling Plans
description: 'Learn known issues with the calling plan for Office 365 (PSTN Calling) and what you can do about them. '
ms.openlocfilehash: 42b282bce7ba65dc4e053020970a02e71c98b5bd
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/15/2017
---
# <a name="calling-plans-known-issues"></a><span data-ttu-id="bd173-103">调用计划的已知的问题</span><span class="sxs-lookup"><span data-stu-id="bd173-103">Calling Plans known issues</span></span>

<span data-ttu-id="bd173-104">Office 365 中的通话方案是找到在 Skype 的在线业务的新增功能。</span><span class="sxs-lookup"><span data-stu-id="bd173-104">Calling Plans in Office 365 are a new feature found in Skype for Business Online.</span></span> <span data-ttu-id="bd173-105">以下是当前的问题正在跟踪，主动调查。</span><span class="sxs-lookup"><span data-stu-id="bd173-105">The following are current issues that are being tracked and actively investigated.</span></span> <span data-ttu-id="bd173-106">他们将有可能解决该功能在 Office 365 和 Skype 的未来版本中更新在线业务时。</span><span class="sxs-lookup"><span data-stu-id="bd173-106">They will be potentially resolved when the feature is updated in future builds in Office 365 and Skype for Business Online.</span></span>
  
## <a name="calling-plans-known-issues"></a><span data-ttu-id="bd173-107">调用计划的已知的问题</span><span class="sxs-lookup"><span data-stu-id="bd173-107">Calling Plans known issues</span></span>

|<span data-ttu-id="bd173-108">**已知问题**</span><span class="sxs-lookup"><span data-stu-id="bd173-108">**Known issue**</span></span>|<span data-ttu-id="bd173-109">**注释**</span><span class="sxs-lookup"><span data-stu-id="bd173-109">**Comments**</span></span>|
|:-----|:-----|
|<span data-ttu-id="bd173-110">从技术预览过渡到调用计划生产许可证的许可证不自动更新许可证。</span><span class="sxs-lookup"><span data-stu-id="bd173-110">Transitioning from Tech Preview licenses to production licenses for Calling Plans don't automatically update the license.</span></span>  <br/> |<span data-ttu-id="bd173-111">第一次购买新的许可证，这样他们就可以分配给您的用户。</span><span class="sxs-lookup"><span data-stu-id="bd173-111">Purchase your new licenses first so they are ready to be assigned to your users.</span></span> <span data-ttu-id="bd173-112">删除用户，促销 （技术预览） 许可证，然后**立即**将新的**国内调用计划**和 （或）**国内和国际调用规划**许可证分配给用户。</span><span class="sxs-lookup"><span data-stu-id="bd173-112">Remove the promo (Tech Preview) license from a user, and then **IMMEDIATELY** assign the new **Domestic Calling Plan** and/or **Domestic and International Calling Plan** licenses to the user.</span></span> <br/> <span data-ttu-id="bd173-113">如果您删除并添加多个用户的许可证，则极其重要，从所有使用 Windows PowerShell 的用户删除许可证，然后**立即**指派的所有用户同时在使用 Windows PowerShell 的许可证。</span><span class="sxs-lookup"><span data-stu-id="bd173-113">If you are removing and adding licenses for multiple users, it is extremely important that you remove the licenses from all of the users using Windows PowerShell and then **IMMEDIATELY** assign the licenses for all of the users also using Windows PowerShell.</span></span> <span data-ttu-id="bd173-114">这样可确保在处理大量的用户许可证分配没有服务不会中断。</span><span class="sxs-lookup"><span data-stu-id="bd173-114">Doing this will ensure that there is no disruption in service when handling large volumes of user license assignments.</span></span> <span data-ttu-id="bd173-115">PowerShell 的示例脚本，请参阅[分配的 Skype 业务和 Microsoft 小组的许可证](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="bd173-115">For sample PowerShell scripts, see [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>  <br/> <span data-ttu-id="bd173-116">**注意：**如果使用混合用户的内部的 PSTN 连接，您*只*需要分派**电话系统**许可证。</span><span class="sxs-lookup"><span data-stu-id="bd173-116">**Note:** If you are using on-premises PSTN connectivity for hybrid users, you  *only*  need to assign a **Phone System** license.</span></span> <span data-ttu-id="bd173-117">**不**应指定调用计划语音。</span><span class="sxs-lookup"><span data-stu-id="bd173-117">You should **NOT** also assign a voice Calling Plan.</span></span> <span data-ttu-id="bd173-118">但是，如果启用 Office 365 中调用计划为 Office 365 中的用户，您需要**调用计划国内** **，并调用计划国际**许可证的用户仍将分配。</span><span class="sxs-lookup"><span data-stu-id="bd173-118">However, if you are enabling Calling Plans in Office 365 for users that are in Office 365, you need to still assign a **Domestic Calling Plan** or a **Domestic and International Calling Plan** license for those users.</span></span> <span data-ttu-id="bd173-119">请参阅[指派的 Skype 业务和 Microsoft 小组的许可证](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="bd173-119">See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

> [!NOTE]
> <span data-ttu-id="bd173-120">如果您需要得到比这更多的电话号码，请[联系支持业务产品的管理帮助](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |</span><span class="sxs-lookup"><span data-stu-id="bd173-120">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |</span></span>
   
## <a name="related-topics"></a><span data-ttu-id="bd173-121">相关主题</span><span class="sxs-lookup"><span data-stu-id="bd173-121">Related topics</span></span>
[<span data-ttu-id="bd173-122">传送电话号码的常见问题</span><span class="sxs-lookup"><span data-stu-id="bd173-122">Transferring phone numbers common questions</span></span>](transferring-phone-numbers-common-questions.md)

[<span data-ttu-id="bd173-123">不同种类的用于调用计划的电话号码</span><span class="sxs-lookup"><span data-stu-id="bd173-123">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="bd173-124">管理您的组织的电话号码</span><span class="sxs-lookup"><span data-stu-id="bd173-124">Manage phone numbers for your organization</span></span>](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[<span data-ttu-id="bd173-125">紧急呼叫条款和条件</span><span class="sxs-lookup"><span data-stu-id="bd173-125">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)

[<span data-ttu-id="bd173-126">Skype for Business Online：紧急呼叫免责标签</span><span class="sxs-lookup"><span data-stu-id="bd173-126">Skype for Business Online: Emergency Calling disclaimer label</span></span>](https://go.microsoft.com/fwlink/?LinkID=692099)
