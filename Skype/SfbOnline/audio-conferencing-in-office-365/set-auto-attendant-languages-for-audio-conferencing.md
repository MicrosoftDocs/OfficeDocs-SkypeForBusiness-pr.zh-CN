---
title: 在 Skype for Business Online 中设置音频会议自动助理语言
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26d73dda-ab26-4af4-8aec-d17f3479ae50
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 请参阅如何在 Skype for Business Online 中为音频会议号码选择音频会议自动助理语言。
ms.openlocfilehash: 70313648f04b05e622ddb34e871ff1b303ac02a7
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23864982"
---
# <a name="set-auto-attendant-languages-for-audio-conferencing-in-skype-for-business-online"></a><span data-ttu-id="e8427-103">在 Skype for Business Online 中设置音频会议自动助理语言</span><span class="sxs-lookup"><span data-stu-id="e8427-103">Set auto attendant languages for Audio Conferencing in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="e8427-104">有关在 Microsoft Teams 中设置自动助理语言的信息，请参阅 [在 Microsoft Teams 中设置音频会议自动助理语言](/MicrosoftTeams/set-auto-attendant-languages-for-audio-conferencing-in-teams)。</span><span class="sxs-lookup"><span data-stu-id="e8427-104">For information about setting the auto attendant language in Microsoft Teams, see [Set auto attendant languages for Audio Conferencing in Microsoft Teams](/MicrosoftTeams/set-auto-attendant-languages-for-audio-conferencing-in-teams).</span></span>

<span data-ttu-id="e8427-105">Skype for Business 的音频会议自动助理可以在加入会议时以多种不同语言向呼叫者播放问候语。</span><span class="sxs-lookup"><span data-stu-id="e8427-105">The Audio Conferencing auto attendant for Skype for Business can greet audio callers in a number of different languages when they join a meeting.</span></span>
  
<span data-ttu-id="e8427-106">选择一种主要语言和最多四种辅助语言。</span><span class="sxs-lookup"><span data-stu-id="e8427-106">Choose one primary language and up to four secondary languages.</span></span> <span data-ttu-id="e8427-107">自动助理将优先使用设置的主要语言，随后按照选择的顺序使用辅助语言。</span><span class="sxs-lookup"><span data-stu-id="e8427-107">The primary language that you set will be used first and the secondary languages will be used in order that you select.</span></span> 
  
> [!NOTE]
>  <span data-ttu-id="e8427-108">只能在国内音频访问电话号码上配置语言。</span><span class="sxs-lookup"><span data-stu-id="e8427-108">You can configure the languages on domestic dial-in access numbers only.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-conferencing-auto-attendant-languages"></a><span data-ttu-id="e8427-109">设置会议自动助理语言</span><span class="sxs-lookup"><span data-stu-id="e8427-109">Set the conferencing auto attendant languages</span></span>

<span data-ttu-id="e8427-110">你必须是[Office 365 全局管理员](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)或 [Skype for Business 管理员](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)才能执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="e8427-110">You must be an [Office 365 global admin](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) or [Skype for Business admin](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) to perform this step.</span></span>
    
1. <span data-ttu-id="e8427-111">在 **Skype for Business 管理中心** 中的左侧导航中，转到 **音频会议** ，然后单击 **Microsoft 网桥** 。</span><span class="sxs-lookup"><span data-stu-id="e8427-111">In the **Skype for Business admin center**, in the left navigation go to **Dial-in conferencing** and then click **Microsoft bridge**.</span></span>
    
2. <span data-ttu-id="e8427-112">从列表中选择音频会议电话号码，然后在操作窗格中单击 **设置语言** 。</span><span class="sxs-lookup"><span data-stu-id="e8427-112">Select the phone number from the list and in the Action pane, click **Unassign**.</span></span> 
    
3. <span data-ttu-id="e8427-113">在 **设置语言** 页面上，单击 **主要语言** 列表以查看可用语言的完整列表。</span><span class="sxs-lookup"><span data-stu-id="e8427-113">On the **Set languages** page, click the drop down under **Primary language** to view the complete list of available languages.</span></span> <span data-ttu-id="e8427-114">如果需要，单击每种 **辅助语言** 列表以选择辅助语言。</span><span class="sxs-lookup"><span data-stu-id="e8427-114">If you need to click each of the **Secondary language** drop downs to select a secondary language.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e8427-115">则会显示所支持的主要语言和辅助语言。</span><span class="sxs-lookup"><span data-stu-id="e8427-115">The primary and secondary languages that are supported are listed.</span></span> <span data-ttu-id="e8427-116">在列表中选择它们的顺序将是向呼叫者显示的语言顺序。</span><span class="sxs-lookup"><span data-stu-id="e8427-116">The order that you select in the drop-downs will be the order of the languages that will be presented to the callers.</span></span> 
  
4. <span data-ttu-id="e8427-117">单击 **保存** 。</span><span class="sxs-lookup"><span data-stu-id="e8427-117">Click **Save**.</span></span>
    
## <a name="want-else-should-i-know"></a><span data-ttu-id="e8427-118">还需了解哪些信息？</span><span class="sxs-lookup"><span data-stu-id="e8427-118">Want else should I know?</span></span>

- <span data-ttu-id="e8427-119">若要查看音频会议支持的语言列表，请参阅[音频会议支持的语言](/MicrosoftTeams/audio-conferencing-supported-languages)。</span><span class="sxs-lookup"><span data-stu-id="e8427-119">To see the list of supported languages for Audio Conferencing, see [Audio Conferencing supported languages](/MicrosoftTeams/audio-conferencing-supported-languages).</span></span>
    
- <span data-ttu-id="e8427-120">语言可以设置为专用，但不能设置为共享电话号码。</span><span class="sxs-lookup"><span data-stu-id="e8427-120">Languages can be set for dedicated but not for shared phone numbers.</span></span>
    
- <span data-ttu-id="e8427-121">若要查看在 Office 365 中使用 Microsoft 作为提供程序的音频会议可用的国家/地区列表，请参阅[音频会议的电话号码](phone-numbers-for-audio-conferencing.md)。</span><span class="sxs-lookup"><span data-stu-id="e8427-121">To see a list of countries/regions in which Audio Conferencing in Office 365 using Microsoft as the provider is available, see [Phone numbers for Audio Conferencing](phone-numbers-for-audio-conferencing.md).</span></span>
    
## <a name="want-to-use-windows-powershell"></a><span data-ttu-id="e8427-122">想要使用 Windows PowerShell？</span><span class="sxs-lookup"><span data-stu-id="e8427-122">Want to use Windows PowerShell?</span></span>

<span data-ttu-id="e8427-123">为自动执行此操作，可以使用 [Set-CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617689) 和 [Get-CsOnlineDialInConferencingLanguagesSupported](https://go.microsoft.com/fwlink/?LinkId=617684) cmdlet 。</span><span class="sxs-lookup"><span data-stu-id="e8427-123">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingServiceNumber ](https://go.microsoft.com/fwlink/?LinkId=617689)and [Get-CsOnlineDialInConferencingLanguagesSupported ](https://go.microsoft.com/fwlink/?LinkId=617684) cmdlets.</span></span>
  
<span data-ttu-id="e8427-124">若要了解更多信息，请参阅 [使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)</span><span class="sxs-lookup"><span data-stu-id="e8427-124">To learn more, see [Quick reference: Using Windows PowerShell to do common Skype for Business Online management tasks](https://go.microsoft.com/fwlink/?LinkId=525038).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="e8427-125">相关主题</span><span class="sxs-lookup"><span data-stu-id="e8427-125">Related topics</span></span>

[<span data-ttu-id="e8427-126">试用或购买 Office 365 中的音频会议</span><span class="sxs-lookup"><span data-stu-id="e8427-126">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
