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
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 请参阅如何在 Skype for Business Online 中为音频会议号码选择音频会议自动助理语言。
ms.openlocfilehash: 393ba3433ba7241ca5c992114de02191b7fb1044
ms.sourcegitcommit: 0458232441d3aed8dd578f41a13078aa379c9b00
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/10/2019
ms.locfileid: "27788982"
---
# <a name="set-auto-attendant-languages-for-audio-conferencing-in-skype-for-business-online"></a><span data-ttu-id="2f193-103">在 Skype for Business Online 中设置音频会议自动助理语言</span><span class="sxs-lookup"><span data-stu-id="2f193-103">Set auto attendant languages for Audio Conferencing in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="2f193-104">有关在 Microsoft Teams 中设置自动助理语言的信息，请参阅 [在 Microsoft Teams 中设置音频会议自动助理语言](/MicrosoftTeams/set-auto-attendant-languages-for-audio-conferencing-in-teams)。</span><span class="sxs-lookup"><span data-stu-id="2f193-104">For information about setting the auto attendant language in Microsoft Teams, see [Set auto attendant languages for Audio Conferencing in Microsoft Teams](/MicrosoftTeams/set-auto-attendant-languages-for-audio-conferencing-in-teams).</span></span>

<span data-ttu-id="2f193-105">Skype for Business 的音频会议自动助理可以在加入会议时以多种不同语言向呼叫者播放问候语。</span><span class="sxs-lookup"><span data-stu-id="2f193-105">The Audio Conferencing auto attendant for Skype for Business can greet audio callers in a number of different languages when they join a meeting.</span></span>
  
<span data-ttu-id="2f193-106">选择一种主要语言和最多四种辅助语言。</span><span class="sxs-lookup"><span data-stu-id="2f193-106">Choose one primary language and up to four secondary languages.</span></span> <span data-ttu-id="2f193-107">将首先使用您之前设置的主要语言和自动助理将使用的辅助语言，以便您选择。</span><span class="sxs-lookup"><span data-stu-id="2f193-107">The primary language that you set will be used first and the secondary languages will be used by the auto-attendant in order that you select.</span></span> 
  
> [!NOTE]
>  <span data-ttu-id="2f193-108">仅能更改音频会议号码的专用类别的语言。</span><span class="sxs-lookup"><span data-stu-id="2f193-108">You can only change the languages of audio conferencing numbers that are of the Dedicated category.</span></span> <span data-ttu-id="2f193-109">不能更改共享音频会议号码的语言。</span><span class="sxs-lookup"><span data-stu-id="2f193-109">The languages of Shared audio conferencing number can't be changed.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-conferencing-auto-attendant-languages"></a><span data-ttu-id="2f193-110">设置会议自动助理语言</span><span class="sxs-lookup"><span data-stu-id="2f193-110">Set the conferencing auto attendant languages</span></span>

<span data-ttu-id="2f193-111">你必须是[Office 365 全局管理员](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)或 [Skype for Business 管理员](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)才能执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="2f193-111">You must be an [Office 365 global admin](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) or [Skype for Business admin](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) to perform this step.</span></span>
    
1. <span data-ttu-id="2f193-112">在**业务管理中心的 Skype**，在左侧导航窗格中，转到**旧门户**。</span><span class="sxs-lookup"><span data-stu-id="2f193-112">In the **Skype for Business admin center**, in the left navigation, go to **Legacy portal**.</span></span> <span data-ttu-id="2f193-113">一次在旧门户中，选择**音频会议**，然后单击**Microsoft 桥**。</span><span class="sxs-lookup"><span data-stu-id="2f193-113">Once in the legacy portal, select **Audio conferencing**, and then click **Microsoft bridge**.</span></span>
    
2. <span data-ttu-id="2f193-114">选择音频会议电话号码，从列表中，并在操作窗格中，单击**设置语言**。</span><span class="sxs-lookup"><span data-stu-id="2f193-114">Select the audio conferencing phone number from the list, and in the Action pane, click **Set languages**.</span></span> <span data-ttu-id="2f193-115">仅能更改专用的音频会议号码的语言。</span><span class="sxs-lookup"><span data-stu-id="2f193-115">It is only possible to change the languages of Dedicated audio conferencing numbers.</span></span>  
    
3. <span data-ttu-id="2f193-116">在**设置语言**页上，单击**主要语言**列表，以查看可用的语言的完整列表。</span><span class="sxs-lookup"><span data-stu-id="2f193-116">On the **Set languages** page, click the **Primary language** list to view the complete list of available languages.</span></span> <span data-ttu-id="2f193-117">如果需要请单击每个**辅助语言**列表选择辅助语言。</span><span class="sxs-lookup"><span data-stu-id="2f193-117">If you need to, click each of the **Secondary languages** lists to select secondary language.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="2f193-118">[!注释] 则会显示所支持的主要和辅助语言。</span><span class="sxs-lookup"><span data-stu-id="2f193-118">The primary and secondary languages that are supported are listed.</span></span> <span data-ttu-id="2f193-119">在其中选择这些列表中的顺序将向呼叫者显示的语言的顺序。</span><span class="sxs-lookup"><span data-stu-id="2f193-119">The order in which you select them in the lists will be the order of the languages presented to callers.</span></span> 
  
4. <span data-ttu-id="2f193-120">单击" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="2f193-120">Click **Save**.</span></span>
    
## <a name="want-else-should-i-know"></a><span data-ttu-id="2f193-121">还需了解哪些信息？</span><span class="sxs-lookup"><span data-stu-id="2f193-121">Want else should I know?</span></span>

- <span data-ttu-id="2f193-122">若要查看音频会议支持的语言列表，请参阅[音频会议支持的语言](/MicrosoftTeams/audio-conferencing-supported-languages)。</span><span class="sxs-lookup"><span data-stu-id="2f193-122">To see the list of supported languages for Audio Conferencing, see [Audio Conferencing supported languages](/MicrosoftTeams/audio-conferencing-supported-languages).</span></span>
    
- <span data-ttu-id="2f193-123">语言可以设置为专用，但不能设置为共享电话号码。</span><span class="sxs-lookup"><span data-stu-id="2f193-123">Languages can be set for dedicated but not for shared phone numbers.</span></span>
    
- <span data-ttu-id="2f193-124">若要查看在 Office 365 中使用 Microsoft 作为提供程序的音频会议可用的国家/地区列表，请参阅[音频会议的电话号码](phone-numbers-for-audio-conferencing.md)。</span><span class="sxs-lookup"><span data-stu-id="2f193-124">To see a list of countries/regions in which Audio Conferencing in Office 365 using Microsoft as the provider is available, see [Phone numbers for Audio Conferencing](phone-numbers-for-audio-conferencing.md).</span></span>
    
## <a name="want-to-use-windows-powershell"></a><span data-ttu-id="2f193-125">想要使用 Windows PowerShell？</span><span class="sxs-lookup"><span data-stu-id="2f193-125">Want to use Windows PowerShell?</span></span>

<span data-ttu-id="2f193-126">自动执行此步骤，您可以使用[集 CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617689)和[Get CsOnlineDialInConferencingLanguagesSupported](https://go.microsoft.com/fwlink/?LinkId=617684) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2f193-126">To automate this step, you can use the [Set-CsOnlineDialInConferencingServiceNumber ](https://go.microsoft.com/fwlink/?LinkId=617689) and [Get-CsOnlineDialInConferencingLanguagesSupported ](https://go.microsoft.com/fwlink/?LinkId=617684) cmdlets.</span></span>
  
<span data-ttu-id="2f193-127">若要了解详细信息，请参阅[使用 Windows PowerShell，可以执行的业务 Online 管理任务的常见 Skype](https://go.microsoft.com/fwlink/?LinkId=525038)</span><span class="sxs-lookup"><span data-stu-id="2f193-127">To learn more, see [Using Windows PowerShell to do common Skype for Business Online management tasks](https://go.microsoft.com/fwlink/?LinkId=525038)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="2f193-128">相关主题</span><span class="sxs-lookup"><span data-stu-id="2f193-128">Related topics</span></span>

[<span data-ttu-id="2f193-129">试用或购买 Office 365 中的音频会议</span><span class="sxs-lookup"><span data-stu-id="2f193-129">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
