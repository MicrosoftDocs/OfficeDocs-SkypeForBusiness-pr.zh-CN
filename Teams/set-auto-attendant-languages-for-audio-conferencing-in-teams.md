---
title: 在 Microsoft Teams 中设置音频会议自动助理语言
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26d73dda-ab26-4af4-8aec-d17f3479ae50
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 了解如何在 Microsoft Teams 中针对音频会议号码选择音频会议自动助理语言。
ms.openlocfilehash: 8cd57dea5b50a69f95670f81d6f3b73748d9699a
ms.sourcegitcommit: 0458232441d3aed8dd578f41a13078aa379c9b00
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/10/2019
ms.locfileid: "27789312"
---
# <a name="set-auto-attendant-languages-for-audio-conferencing-in-microsoft-teams"></a><span data-ttu-id="33b8b-103">在 Microsoft Teams 中设置音频会议自动助理语言</span><span class="sxs-lookup"><span data-stu-id="33b8b-103">Set auto attendant languages for Audio Conferencing in Microsoft Teams</span></span>

<span data-ttu-id="33b8b-104">Microsoft Teams 的音频会议自动助理可以在音频呼叫者加入会议时使用多种不同的语言向其问好。</span><span class="sxs-lookup"><span data-stu-id="33b8b-104">The Audio Conferencing auto attendant for Microsoft Teams can greet audio callers in a number of different languages when they join a meeting.</span></span>
  
<span data-ttu-id="33b8b-105">可选择一种主要语言以及最多四种辅助语言。</span><span class="sxs-lookup"><span data-stu-id="33b8b-105">Choose one primary language and up to four secondary languages.</span></span> <span data-ttu-id="33b8b-106">自动助理将首先使用你设置的主要语言，然后按你选择的顺序使用辅助语言。</span><span class="sxs-lookup"><span data-stu-id="33b8b-106">The primary language that you set will be used first and the secondary languages will be used by the auto-attendant in order that you select.</span></span> 
  
> [!NOTE]
>  <span data-ttu-id="33b8b-107">仅能更改音频会议号码的专用类别的语言。</span><span class="sxs-lookup"><span data-stu-id="33b8b-107">You can only change the languages of audio conferencing numbers that are of the Dedicated category.</span></span> <span data-ttu-id="33b8b-108">不能更改共享音频会议号码的语言。</span><span class="sxs-lookup"><span data-stu-id="33b8b-108">The languages of Shared audio conferencing number can't be changed.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="set-the-conferencing-auto-attendant-languages"></a><span data-ttu-id="33b8b-109">设置会议自动助理语言</span><span class="sxs-lookup"><span data-stu-id="33b8b-109">Set the conferencing auto attendant languages</span></span>

![团队-徽标-30x30.png](media/teams-logo-30x30.png) <span data-ttu-id="33b8b-111">使用 Microsoft 团队和 Skype for Business Admin Center</span><span class="sxs-lookup"><span data-stu-id="33b8b-111">Using the Microsoft Teams and Skype for Business Admin Center</span></span>

1. <span data-ttu-id="33b8b-112">在左侧导航中，转到“**会议**” > “**会议网桥**”。</span><span class="sxs-lookup"><span data-stu-id="33b8b-112">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span>

2. <span data-ttu-id="33b8b-113">选择一个**Dedidcated**音频会议电话号码，从列表中，并在页面顶部，单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="33b8b-113">Select a **Dedidcated** audio conferencing phone number from the list, and at the top of the page, click **Edit**.</span></span> <span data-ttu-id="33b8b-114">仅能更改专用的音频会议号码的语言。</span><span class="sxs-lookup"><span data-stu-id="33b8b-114">It is only possible to change the languages of Dedicated audio conferencing numbers.</span></span> <span data-ttu-id="33b8b-115">选择专用的音频会议号码时，才会显示**编辑**选项。</span><span class="sxs-lookup"><span data-stu-id="33b8b-115">The **Edit** option is only shown when a Dedicated audio conferencing number is selected.</span></span>

3. <span data-ttu-id="33b8b-116">在右侧窗格中，选择所需的默认语言和任何备用语言。</span><span class="sxs-lookup"><span data-stu-id="33b8b-116">In the pane on the right, choose the default language you want and any alternate languages.</span></span> 
 
    > [!NOTE]
    > <span data-ttu-id="33b8b-117">列出默认和备用语言支持。</span><span class="sxs-lookup"><span data-stu-id="33b8b-117">The default and alternate languages that are supported are listed.</span></span> <span data-ttu-id="33b8b-118">在其中选择这些列表中的顺序将向呼叫者显示的语言的顺序。</span><span class="sxs-lookup"><span data-stu-id="33b8b-118">The order in which you select them in the lists will be the order of the languages presented to callers.</span></span> 

4. <span data-ttu-id="33b8b-119">单击" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="33b8b-119">Click **Save**.</span></span>

    
## <a name="want-else-should-i-know"></a><span data-ttu-id="33b8b-120">还需了解哪些信息？</span><span class="sxs-lookup"><span data-stu-id="33b8b-120">Want else should I know?</span></span>

- <span data-ttu-id="33b8b-121">若要查看音频会议支持的语言列表，请参阅[音频会议支持的语言](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/audio-conferencing-supported-languages)。</span><span class="sxs-lookup"><span data-stu-id="33b8b-121">To see the list of supported languages for Audio Conferencing, see [Audio Conferencing supported languages](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/audio-conferencing-supported-languages).</span></span>
    
- <span data-ttu-id="33b8b-122">语言可以设置为专用，但不能设置为共享电话号码。</span><span class="sxs-lookup"><span data-stu-id="33b8b-122">Languages can be set for dedicated but not for shared phone numbers.</span></span>
    
- <span data-ttu-id="33b8b-123">若要查看在 Office 365 中使用 Microsoft 作为提供程序的音频会议可用的国家/地区列表，请参阅[音频会议的电话号码](phone-numbers-for-audio-conferencing-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="33b8b-123">To see a list of countries/regions in which Audio Conferencing in Office 365 using Microsoft as the provider is available, see [Phone numbers for Audio Conferencing](phone-numbers-for-audio-conferencing-in-teams.md).</span></span>
    
## <a name="want-to-use-windows-powershell"></a><span data-ttu-id="33b8b-124">想要使用 Windows PowerShell？</span><span class="sxs-lookup"><span data-stu-id="33b8b-124">Want to use Windows PowerShell?</span></span>

<span data-ttu-id="33b8b-125">请参阅[Microsoft 团队 PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)（英文） 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="33b8b-125">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="33b8b-126">相关主题</span><span class="sxs-lookup"><span data-stu-id="33b8b-126">Related topics</span></span>

[<span data-ttu-id="33b8b-127">试用或购买 Office 365 中的音频会议</span><span class="sxs-lookup"><span data-stu-id="33b8b-127">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

