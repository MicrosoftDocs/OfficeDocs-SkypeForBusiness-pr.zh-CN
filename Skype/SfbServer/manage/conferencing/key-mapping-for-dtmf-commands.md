---
title: 管理业务服务器中 Skype 的 DTMF 命令的键映射
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f91e80ee-a587-4a1b-ac8f-12fa102c098c
description: 摘要： 了解如何管理业务服务器中 Skype 的双音多频 (DTMF) 命令的键映射。
ms.openlocfilehash: 33ab031e6032b6246dd637bc55c9ec6b600f0c82
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32198009"
---
# <a name="manage-key-mapping-for-dtmf-commands-in-skype-for-business-server"></a><span data-ttu-id="c3253-103">管理业务服务器中 Skype 的 DTMF 命令的键映射</span><span class="sxs-lookup"><span data-stu-id="c3253-103">Manage key mapping for DTMF commands in Skype for Business Server</span></span>
 
<span data-ttu-id="c3253-104">**摘要：** 了解如何管理业务服务器中 Skype 的双音多频 (DTMF) 命令的键映射。</span><span class="sxs-lookup"><span data-stu-id="c3253-104">**Summary:** Learn how to manage key mapping of dual-tone multi-frequency (DTMF) commands in Skype for Business Server.</span></span>
  
<span data-ttu-id="c3253-p101">电话拨入式会议用户可以在电话小键盘上按键以执行双音多频 (DTMF) 命令。通过 DTMF 命令，拨入会议的用户可以使用其电话上的小键盘控制会议设置（例如，将自己静音和取消静音，或者锁定和解锁会议）。</span><span class="sxs-lookup"><span data-stu-id="c3253-p101">Dial-in conferencing users can press keys on the telephone keypad to perform dual-tone multi-frequency (DTMF) commands. DTMF commands enable users who dial in to a conference to control conference settings (such as muting and unmuting themselves or locking and unlocking the conference) by using the keypad on their telephone.</span></span> 
  
<span data-ttu-id="c3253-107">若要管理使用 DTMF 命令的键，用于 Skype **Get-csdialinconferencingdtmfconfiguration**、 **Set-csdialinconferencingdtmfconfiguration**，和**业务 Server Management Shell新 CsDialinConferencingDtmfConfiguration** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c3253-107">To manage the keys used for the DTMF commands, use the Skype for Business Server Management Shell with the **Get-CsDialinConferencingDtmfConfiguration**, **Set-CsDialinConferencingDtmfConfiguration**, and **New-CsDialinConferencingDtmfConfiguration** cmdlets.</span></span>
  
<span data-ttu-id="c3253-108">为站点创建新的 DTMF 设置后，站点设置将优先于全局设置。</span><span class="sxs-lookup"><span data-stu-id="c3253-108">When you create new DTMF settings for sites, the site settings take precedence over the global settings.</span></span> 

### <a name="manage-the-key-mapping-of-dtmf-commands"></a><span data-ttu-id="c3253-109">管理 DTMF 命令的键映射</span><span class="sxs-lookup"><span data-stu-id="c3253-109">Manage the key mapping of DTMF commands</span></span>

1. <span data-ttu-id="c3253-110">以  RTCUniversalServerAdmins  组成员或者  Cs-ServerAdministrator  或  CsAdministrator  角色成员的身份登录计算机。</span><span class="sxs-lookup"><span data-stu-id="c3253-110">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="c3253-111">启动 Skype for Business Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\* 和“Skype for Business 2015”\*\*\*\*，然后单击“Skype for Business Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c3253-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="c3253-112">若要查看用于电话拨入式会议的 DTMF 设置，请在命令提示符下运行下面的命令：</span><span class="sxs-lookup"><span data-stu-id="c3253-112">To view the DTMF settings used for dial-in conferencing, run the following command at the command prompt :</span></span>
    
   ```
   Get-CsDialinConferencingDtmfConfiguration
   ```

4. <span data-ttu-id="c3253-113">若要修改用于电话拨入式会议的 DTMF 设置，请运行下面的 cmdlet，并对你要更改的每个选项指定要按下的键：</span><span class="sxs-lookup"><span data-stu-id="c3253-113">To modify the DTMF settings used for dial-in conferencing, run the following cmdlet and specify the key to be pressed for each option that you want to change:</span></span>
    
   ```
   Set-CsDialinConferencingDtmfConfiguration [-Identity <global or site collection to be changed>]
   [-AdmitAll <default key is 8>] [-AudienceMuteCommand <default key is 4>]
   [-CommandCharacter <* (default) | #>] [-EnableDisableAnnouncementsCommand <default key is 9>]
   [-HelpCommand <default key is 1>] [-LockUnlockConferenceCommand <default key is 7>]
   [-MuteUnmuteCommand <default key is 6>] [-PrivateRollCallCommand <default key is 3>]
   ```

5. <span data-ttu-id="c3253-114">（可选）若要为特定站点创建其他 DTMF 命令集，请使用带有站点 Identity 的 **New-CsDialinConferencingDtmfConfiguration** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c3253-114">(Optional) To create additional sets of DTMF commands for specific sites, use the **New-CsDialinConferencingDtmfConfiguration** cmdlet with a site identity.</span></span>
    
<span data-ttu-id="c3253-p102">下面的示例可使启用或禁用通知所按的键和将所有与会者静音和取消静音所按的键交换。由于未指定 Identity，因此这些更改将应用于全局 DTMF 设置：</span><span class="sxs-lookup"><span data-stu-id="c3253-p102">The following example swaps the key that is pressed to enable or disable announcements and the key that is pressed to mute and unmute all participants. Because no Identity is specified, these changes apply to the global DTMF settings:</span></span>
  
```
Set-CsDialinConferencingDtmfConfiguration -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9
```

<span data-ttu-id="c3253-117">有关详细信息，请参阅[Get-csdialinconferencingdtmfconfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps)、 [Set-csdialinconferencingdtmfconfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps)和[新建 CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="c3253-117">For more information, see [Get-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps), [Set-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps), and [New-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps).</span></span>
  

