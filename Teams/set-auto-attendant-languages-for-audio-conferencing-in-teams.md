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
ms.openlocfilehash: b9613b5e64bad0428975a6acd3b11db16a42c680
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "25017950"
---
# <a name="set-auto-attendant-languages-for-audio-conferencing-in-microsoft-teams"></a><span data-ttu-id="d19bb-103">在 Microsoft Teams 中设置音频会议自动助理语言</span><span class="sxs-lookup"><span data-stu-id="d19bb-103">Set auto attendant languages for Audio Conferencing in Microsoft Teams</span></span>

<span data-ttu-id="d19bb-104">Microsoft Teams 的音频会议自动助理可以在音频呼叫者加入会议时使用多种不同的语言向其问好。</span><span class="sxs-lookup"><span data-stu-id="d19bb-104">The Audio Conferencing auto attendant for Microsoft Teams can greet audio callers in a number of different languages when they join a meeting.</span></span>
  
<span data-ttu-id="d19bb-105">选择一种主要语言和最多四种辅助语言。</span><span class="sxs-lookup"><span data-stu-id="d19bb-105">Choose one primary language and up to four secondary languages.</span></span> <span data-ttu-id="d19bb-106">将首先使用您之前设置的主要语言和自动助理将使用的辅助语言，以便您选择。</span><span class="sxs-lookup"><span data-stu-id="d19bb-106">The primary language that you set will be used first and the secondary languages will be used by the auto-attendant in order that you select.</span></span> 
  
> [!NOTE]
>  <span data-ttu-id="d19bb-107">只能对国内音频访问电话号码配置语言。</span><span class="sxs-lookup"><span data-stu-id="d19bb-107">You can configure the languages on domestic audio access phone numbers only.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="set-the-conferencing-auto-attendant-languages"></a><span data-ttu-id="d19bb-108">设置会议自动助理语言</span><span class="sxs-lookup"><span data-stu-id="d19bb-108">Set the conferencing auto attendant languages</span></span>

1. <span data-ttu-id="d19bb-109">在左侧导航中，转到“**会议**” > “**会议网桥**”。</span><span class="sxs-lookup"><span data-stu-id="d19bb-109">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span>

2. <span data-ttu-id="d19bb-110">从列表中选择音频会议电话号码，然后在页面顶部，单击“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="d19bb-110">Select the audio conferencing phone number from the list, and at the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="d19bb-111">在右侧窗格中，选择所需的默认语言以及任何备用语言。</span><span class="sxs-lookup"><span data-stu-id="d19bb-111">In the pane on the right, choose the default language you want and any alternate languages.</span></span> 
 
    > [!NOTE]
    > <span data-ttu-id="d19bb-112">列出默认和备用语言支持。</span><span class="sxs-lookup"><span data-stu-id="d19bb-112">The default and alternate languages that are supported are listed.</span></span> <span data-ttu-id="d19bb-113">在其中选择这些列表中的顺序将向呼叫者显示的语言的顺序。</span><span class="sxs-lookup"><span data-stu-id="d19bb-113">The order in which you select them in the lists will be the order of the languages presented to callers.</span></span> 

4. <span data-ttu-id="d19bb-114">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="d19bb-114">Click **Save**.</span></span>

    
## <a name="want-else-should-i-know"></a><span data-ttu-id="d19bb-115">我还应该了解哪些信息？</span><span class="sxs-lookup"><span data-stu-id="d19bb-115">Want else should I know?</span></span>

- <span data-ttu-id="d19bb-116">若要查看音频会议支持的语言列表，请参阅[音频会议支持的语言](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/audio-conferencing-supported-languages)。</span><span class="sxs-lookup"><span data-stu-id="d19bb-116">To see the list of supported languages for Audio Conferencing, see [Audio Conferencing supported languages](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/audio-conferencing-supported-languages).</span></span>
    
- <span data-ttu-id="d19bb-117">语言可以设置为专用，但不能设置为共享电话号码。</span><span class="sxs-lookup"><span data-stu-id="d19bb-117">Languages can be set for dedicated but not for shared phone numbers.</span></span>
    
- <span data-ttu-id="d19bb-118">若要查看在 Office 365 中使用 Microsoft 作为提供程序的音频会议可用的国家/地区列表，请参阅[音频会议的电话号码](phone-numbers-for-audio-conferencing-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="d19bb-118">To see a list of countries/regions in which Audio Conferencing in Office 365 using Microsoft as the provider is available, see [Phone numbers for Audio Conferencing](phone-numbers-for-audio-conferencing-in-teams.md).</span></span>
    
## <a name="want-to-use-windows-powershell"></a><span data-ttu-id="d19bb-119">想要使用 Windows PowerShell？</span><span class="sxs-lookup"><span data-stu-id="d19bb-119">Want to use Windows PowerShell?</span></span>

<span data-ttu-id="d19bb-120">有关详细信息，请参阅 [Microsoft Teams PowerShell 参考](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)。</span><span class="sxs-lookup"><span data-stu-id="d19bb-120">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="d19bb-121">相关主题</span><span class="sxs-lookup"><span data-stu-id="d19bb-121">Related topics</span></span>

[<span data-ttu-id="d19bb-122">试用或购买 Office 365 中的音频会议</span><span class="sxs-lookup"><span data-stu-id="d19bb-122">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

