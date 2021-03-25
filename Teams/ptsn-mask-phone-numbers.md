---
title: 在 Microsoft Teams 会议中屏蔽电话号码
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: moakram
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 了解如何在 Microsoft Teams 会议中屏蔽电话号码
ms.openlocfilehash: bc3325805db63f86937a27d63cfc08ab0de84006
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117710"
---
# <a name="mask-phone-numbers-in-microsoft-teams-meetings"></a><span data-ttu-id="cbde5-103">在 Microsoft Teams 会议中屏蔽电话号码</span><span class="sxs-lookup"><span data-stu-id="cbde5-103">Mask phone numbers in Microsoft Teams meetings</span></span>

<span data-ttu-id="cbde5-104">为增加隐私性，使用音频会议拨入 Teams 会议的参与者的电话号码将完全向内部参与者显示。</span><span class="sxs-lookup"><span data-stu-id="cbde5-104">For added privacy, the phone numbers of participants who dial in to a Teams meeting using audio conferencing are fully displayed to the internal participants.</span></span> <span data-ttu-id="cbde5-105">号码会从组织外部的参与者中屏蔽。</span><span class="sxs-lookup"><span data-stu-id="cbde5-105">The numbers are masked from the participants outside of your organization.</span></span> <span data-ttu-id="cbde5-106">此设置是所有组织的默认设置。</span><span class="sxs-lookup"><span data-stu-id="cbde5-106">This setting is the default for all organizations.</span></span> <span data-ttu-id="cbde5-107">显示屏蔽数字，如下图所示：</span><span class="sxs-lookup"><span data-stu-id="cbde5-107">The masked number is displayed as shown in the following image:</span></span>

![已屏蔽电话号码的示例](media/hiddenPhoneNum.png)

<span data-ttu-id="cbde5-109">对于特定的行业用例，管理员可以选择音频会议参与者的电话号码在租户中组织的会议中如何显示。</span><span class="sxs-lookup"><span data-stu-id="cbde5-109">For specific industry use cases, admins have the ability to choose how the audio conferencing participants' phone numbers appear in meetings that are organized in their tenant.</span></span> <span data-ttu-id="cbde5-110">管理员可以从三个选项中进行选择：</span><span class="sxs-lookup"><span data-stu-id="cbde5-110">The admins can choose from three options:</span></span>

- <span data-ttu-id="cbde5-111">电话号码仅对外部参与者进行屏蔽。</span><span class="sxs-lookup"><span data-stu-id="cbde5-111">Phone numbers are masked only from external participants.</span></span> <span data-ttu-id="cbde5-112">属于会议组织者租户的参与者仍看到完整电话号码。</span><span class="sxs-lookup"><span data-stu-id="cbde5-112">The participants who belong to the meeting organizer's tenant still see the full phone number.</span></span>
- <span data-ttu-id="cbde5-113">会议中的每个人（组织者除外）都屏蔽了电话号码。</span><span class="sxs-lookup"><span data-stu-id="cbde5-113">Phone numbers are masked from everyone in the meeting except the organizer.</span></span>
- <span data-ttu-id="cbde5-114">电话号码未屏蔽，因此对参加会议的每个人都可见。</span><span class="sxs-lookup"><span data-stu-id="cbde5-114">Phone numbers are unmasked, which makes them visible to everyone in the meeting.</span></span>

<span data-ttu-id="cbde5-115">此设置应用于会议中公开电话号码的所有图面。</span><span class="sxs-lookup"><span data-stu-id="cbde5-115">This setting is applied to all the surfaces in the meeting where phone numbers are exposed.</span></span>

## <a name="use-microsoft-powershell-to-set-phone-number-masking"></a><span data-ttu-id="cbde5-116">使用 Microsoft PowerShell 设置电话号码掩码</span><span class="sxs-lookup"><span data-stu-id="cbde5-116">Use Microsoft PowerShell to set phone-number masking</span></span>

<span data-ttu-id="cbde5-117">若要更改公用电话交换网 (PSTN) 屏蔽设置，请设置 **`MaskPstnNumbersType`** [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet 的参数，以使用其中一个可用选项。</span><span class="sxs-lookup"><span data-stu-id="cbde5-117">To change the Public Switched Telephone Network (PSTN) masking setting, set the **`MaskPstnNumbersType`** parameter of the [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet to one of the available options.</span></span>

<span data-ttu-id="cbde5-118">若要仅屏蔽来自外部参与者的电话号码，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="cbde5-118">To mask phone numbers only from external participants, run the following command:</span></span>

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "MaskedForExternalUsers"
```

<span data-ttu-id="cbde5-119">若要屏蔽会议参与者的电话号码， (组织者) ，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="cbde5-119">To mask phone numbers from all participants in the meeting (except the organizer), run the following command:</span></span>

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "MaskedForAllUsers"
```

<span data-ttu-id="cbde5-120">若要禁用电话号码掩码，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="cbde5-120">To disable phone number masking, run the following command:</span></span>

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "NoMasking"
```