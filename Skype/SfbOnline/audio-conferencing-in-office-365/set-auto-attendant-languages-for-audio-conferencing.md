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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 请参阅如何在 Skype for Business Online 中为音频会议号码选择音频会议自动助理语言。
ms.openlocfilehash: 22c3ad1d2386dec07060548cd055a5d289db4364
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41680379"
---
# <a name="set-auto-attendant-languages-for-audio-conferencing-in-skype-for-business-online"></a><span data-ttu-id="3d416-103">在 Skype for Business Online 中设置音频会议自动助理语言</span><span class="sxs-lookup"><span data-stu-id="3d416-103">Set auto attendant languages for Audio Conferencing in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="3d416-104">有关在 Microsoft Teams 中设置自动助理语言的信息，请参阅 [在 Microsoft Teams 中设置音频会议自动助理语言](/MicrosoftTeams/set-auto-attendant-languages-for-audio-conferencing-in-teams)。</span><span class="sxs-lookup"><span data-stu-id="3d416-104">For information about setting the auto attendant language in Microsoft Teams, see [Set auto attendant languages for Audio Conferencing in Microsoft Teams](/MicrosoftTeams/set-auto-attendant-languages-for-audio-conferencing-in-teams).</span></span>

<span data-ttu-id="3d416-105">Skype for Business 的音频会议自动助理可以在加入会议时以多种不同语言向呼叫者播放问候语。</span><span class="sxs-lookup"><span data-stu-id="3d416-105">The Audio Conferencing auto attendant for Skype for Business can greet audio callers in a number of different languages when they join a meeting.</span></span>
  
<span data-ttu-id="3d416-p101">Choose one primary language and up to four secondary languages. The primary language that you set will be used first and the secondary languages will be used by the auto-attendant in order that you select.</span><span class="sxs-lookup"><span data-stu-id="3d416-p101">Choose one primary language and up to four secondary languages. The primary language that you set will be used first and the secondary languages will be used by the auto-attendant in order that you select.</span></span> 
  
> [!NOTE]
>  <span data-ttu-id="3d416-108">只能更改专用类别的音频会议号码的语言。</span><span class="sxs-lookup"><span data-stu-id="3d416-108">You can only change the languages of audio conferencing numbers that are of the Dedicated category.</span></span> <span data-ttu-id="3d416-109">无法更改共享音频会议号码的语言。</span><span class="sxs-lookup"><span data-stu-id="3d416-109">The languages of Shared audio conferencing number can't be changed.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-conferencing-auto-attendant-languages"></a><span data-ttu-id="3d416-110">设置会议自动助理语言</span><span class="sxs-lookup"><span data-stu-id="3d416-110">Set the conferencing auto attendant languages</span></span>

<span data-ttu-id="3d416-111">你必须是[Office 365 全局管理员](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)或 [Skype for Business 管理员](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)才能执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="3d416-111">You must be an [Office 365 global admin](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) or [Skype for Business admin](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) to perform this step.</span></span>
    
1. <span data-ttu-id="3d416-112">在**Skype For business 管理中心**的左侧导航中，转到 "**旧版门户**"。</span><span class="sxs-lookup"><span data-stu-id="3d416-112">In the **Skype for Business admin center**, in the left navigation, go to **Legacy portal**.</span></span> <span data-ttu-id="3d416-113">在旧版门户中，选择 "**音频会议**"，然后单击 " **Microsoft bridge**"。</span><span class="sxs-lookup"><span data-stu-id="3d416-113">Once in the legacy portal, select **Audio conferencing**, and then click **Microsoft bridge**.</span></span>
    
2. <span data-ttu-id="3d416-114">从列表中选择音频会议电话号码，然后在 "操作" 窗格中，单击 "**设置语言**"。</span><span class="sxs-lookup"><span data-stu-id="3d416-114">Select the audio conferencing phone number from the list, and in the Action pane, click **Set languages**.</span></span> <span data-ttu-id="3d416-115">仅可以更改专用音频会议号码的语言。</span><span class="sxs-lookup"><span data-stu-id="3d416-115">It is only possible to change the languages of Dedicated audio conferencing numbers.</span></span>  
    
3. <span data-ttu-id="3d416-116">在 "**设置语言**" 页面上，单击 "**主要语言**" 列表以查看可用语言的完整列表。</span><span class="sxs-lookup"><span data-stu-id="3d416-116">On the **Set languages** page, click the **Primary language** list to view the complete list of available languages.</span></span> <span data-ttu-id="3d416-117">如果需要，请单击每个**次要语言**列表以选择 "辅助语言"。</span><span class="sxs-lookup"><span data-stu-id="3d416-117">If you need to, click each of the **Secondary languages** lists to select secondary language.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="3d416-118">[!注释] 则会显示所支持的主要和辅助语言。</span><span class="sxs-lookup"><span data-stu-id="3d416-118">The primary and secondary languages that are supported are listed.</span></span> <span data-ttu-id="3d416-119">在列表中选择它们的顺序将是向呼叫方提供的语言的顺序。</span><span class="sxs-lookup"><span data-stu-id="3d416-119">The order in which you select them in the lists will be the order of the languages presented to callers.</span></span> 
  
4. <span data-ttu-id="3d416-120">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="3d416-120">Click **Save**.</span></span>
    
## <a name="want-else-should-i-know"></a><span data-ttu-id="3d416-121">还需了解哪些信息？</span><span class="sxs-lookup"><span data-stu-id="3d416-121">Want else should I know?</span></span>

- <span data-ttu-id="3d416-122">若要查看音频会议支持的语言列表，请参阅[音频会议支持的语言](/MicrosoftTeams/audio-conferencing-supported-languages)。</span><span class="sxs-lookup"><span data-stu-id="3d416-122">To see the list of supported languages for Audio Conferencing, see [Audio Conferencing supported languages](/MicrosoftTeams/audio-conferencing-supported-languages).</span></span>
    
- <span data-ttu-id="3d416-123">语言可以设置为专用，但不能设置为共享电话号码。</span><span class="sxs-lookup"><span data-stu-id="3d416-123">Languages can be set for dedicated but not for shared phone numbers.</span></span>
    
- <span data-ttu-id="3d416-124">若要查看在 Office 365 中使用 Microsoft 作为提供程序的音频会议可用的国家/地区列表，请参阅[音频会议的电话号码](phone-numbers-for-audio-conferencing.md)。</span><span class="sxs-lookup"><span data-stu-id="3d416-124">To see a list of countries/regions in which Audio Conferencing in Office 365 using Microsoft as the provider is available, see [Phone numbers for Audio Conferencing](phone-numbers-for-audio-conferencing.md).</span></span>
    
## <a name="want-to-use-windows-powershell"></a><span data-ttu-id="3d416-125">想要使用 Windows PowerShell？</span><span class="sxs-lookup"><span data-stu-id="3d416-125">Want to use Windows PowerShell?</span></span>

<span data-ttu-id="3d416-126">若要自动执行此步骤，你可以使用[set-csonlinedialinconferencingservicenumber](https://go.microsoft.com/fwlink/?LinkId=617689)和[get-csonlinedialinconferencinglanguagessupported](https://go.microsoft.com/fwlink/?LinkId=617684) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3d416-126">To automate this step, you can use the [Set-CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617689) and [Get-CsOnlineDialInConferencingLanguagesSupported](https://go.microsoft.com/fwlink/?LinkId=617684) cmdlets.</span></span>
  
<span data-ttu-id="3d416-127">若要了解详细信息，请参阅[使用 Windows PowerShell 执行常见的 Skype For Business Online 管理任务](https://go.microsoft.com/fwlink/?LinkId=525038)</span><span class="sxs-lookup"><span data-stu-id="3d416-127">To learn more, see [Using Windows PowerShell to do common Skype for Business Online management tasks](https://go.microsoft.com/fwlink/?LinkId=525038)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="3d416-128">相关主题</span><span class="sxs-lookup"><span data-stu-id="3d416-128">Related topics</span></span>

[<span data-ttu-id="3d416-129">试用或购买 Office 365 中的音频会议</span><span class="sxs-lookup"><span data-stu-id="3d416-129">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
