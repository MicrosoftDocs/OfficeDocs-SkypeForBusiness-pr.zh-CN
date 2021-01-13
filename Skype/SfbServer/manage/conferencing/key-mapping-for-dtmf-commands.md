---
title: 在 Skype for Business Server 中管理 DTMF 命令的键映射
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: f91e80ee-a587-4a1b-ac8f-12fa102c098c
description: 摘要：了解如何在 Skype for Business Server 中管理双音多频 (DTMF) 命令的关键映射。
ms.openlocfilehash: b804c9a0923630f6de3d1b5af2acdda123cc6331
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828092"
---
# <a name="manage-key-mapping-for-dtmf-commands-in-skype-for-business-server"></a><span data-ttu-id="5ad77-103">在 Skype for Business Server 中管理 DTMF 命令的键映射</span><span class="sxs-lookup"><span data-stu-id="5ad77-103">Manage key mapping for DTMF commands in Skype for Business Server</span></span>
 
<span data-ttu-id="5ad77-104">**摘要：** 了解如何在 Skype for Business Server 中管理双音多频 (DTMF) 命令的键映射。</span><span class="sxs-lookup"><span data-stu-id="5ad77-104">**Summary:** Learn how to manage key mapping of dual-tone multi-frequency (DTMF) commands in Skype for Business Server.</span></span>
  
<span data-ttu-id="5ad77-105">电话拨入式会议用户可以在电话小键盘上按键以执行双音多频 (DTMF) 命令。</span><span class="sxs-lookup"><span data-stu-id="5ad77-105">Dial-in conferencing users can press keys on the telephone keypad to perform dual-tone multi-frequency (DTMF) commands.</span></span> <span data-ttu-id="5ad77-106">通过 DTMF 命令，拨入会议的用户可以使用其电话上的小键盘控制会议设置（例如，将自己静音和取消静音，或者锁定和解锁会议）。</span><span class="sxs-lookup"><span data-stu-id="5ad77-106">DTMF commands enable users who dial in to a conference to control conference settings (such as muting and unmuting themselves or locking and unlocking the conference) by using the keypad on their telephone.</span></span> 
  
<span data-ttu-id="5ad77-107">要管理用于 DTMF 命令的密钥，请通过 **Get-CsDialinConferencingDtmfConfiguration、Set-CsDialinConferencingDtmfConfiguration** 和 **New-CsDialinConferencingDtmfConfiguration** cmdlet 使用 Skype for Business Server 命令行管理程序。 </span><span class="sxs-lookup"><span data-stu-id="5ad77-107">To manage the keys used for the DTMF commands, use the Skype for Business Server Management Shell with the **Get-CsDialinConferencingDtmfConfiguration**, **Set-CsDialinConferencingDtmfConfiguration**, and **New-CsDialinConferencingDtmfConfiguration** cmdlets.</span></span>
  
<span data-ttu-id="5ad77-108">为站点创建新的 DTMF 设置后，站点设置将优先于全局设置。</span><span class="sxs-lookup"><span data-stu-id="5ad77-108">When you create new DTMF settings for sites, the site settings take precedence over the global settings.</span></span> 

### <a name="manage-the-key-mapping-of-dtmf-commands"></a><span data-ttu-id="5ad77-109">管理 DTMF 命令的键映射</span><span class="sxs-lookup"><span data-stu-id="5ad77-109">Manage the key mapping of DTMF commands</span></span>

1. <span data-ttu-id="5ad77-110">以 RTCUniversalServerAdmins 组成员或者 Cs-ServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。</span><span class="sxs-lookup"><span data-stu-id="5ad77-110">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="5ad77-111">启动 Skype for Business Server命令行管理程序：单击"开始"，**单击"所有** 程序"，再单击 **"Skype for Business 2015"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**</span><span class="sxs-lookup"><span data-stu-id="5ad77-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="5ad77-112">若要查看用于电话拨入式会议 DTMF 设置，在命令提示符下运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="5ad77-112">To view the DTMF settings used for dial-in conferencing, run the following command at the command prompt :</span></span>
    
   ```PowerShell
   Get-CsDialinConferencingDtmfConfiguration
   ```

4. <span data-ttu-id="5ad77-113">要修改用于电话拨入式会议的 DTMF 设置，请运行以下 cmdlet 并指定要针对要更改的每个选项按下的键：</span><span class="sxs-lookup"><span data-stu-id="5ad77-113">To modify the DTMF settings used for dial-in conferencing, run the following cmdlet and specify the key to be pressed for each option that you want to change:</span></span>
    
   ```PowerShell
   Set-CsDialinConferencingDtmfConfiguration [-Identity <global or site collection to be changed>]
   [-AdmitAll <default key is 8>] [-AudienceMuteCommand <default key is 4>]
   [-CommandCharacter <* (default) | #>] [-EnableDisableAnnouncementsCommand <default key is 9>]
   [-HelpCommand <default key is 1>] [-LockUnlockConferenceCommand <default key is 7>]
   [-MuteUnmuteCommand <default key is 6>] [-PrivateRollCallCommand <default key is 3>]
   ```

5. <span data-ttu-id="5ad77-114">（可选）要为特定站点创建其他 DTMF 命令集，请使用带有站点 Identity 的 **New-CsDialinConferencingDtmfConfiguration** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="5ad77-114">(Optional) To create additional sets of DTMF commands for specific sites, use the **New-CsDialinConferencingDtmfConfiguration** cmdlet with a site identity.</span></span>
    
<span data-ttu-id="5ad77-115">以下示例将切换启用或禁用通知所按的键，以及将所有参与者静音和取消静音所按的键。</span><span class="sxs-lookup"><span data-stu-id="5ad77-115">The following example swaps the key that is pressed to enable or disable announcements and the key that is pressed to mute and unmute all participants.</span></span> <span data-ttu-id="5ad77-116">由于未指定 Identity，因此这些更改适用于全局 DTMF 设置：</span><span class="sxs-lookup"><span data-stu-id="5ad77-116">Because no Identity is specified, these changes apply to the global DTMF settings:</span></span>
  
```PowerShell
Set-CsDialinConferencingDtmfConfiguration -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9
```

<span data-ttu-id="5ad77-117">有关详细信息，请参阅[Get-CsDialInConferencingDtmfConfiguration、Set-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps)和[New-CsDialInConferencingDtmfConfiguration。](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps) [](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="5ad77-117">For more information, see [Get-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps), [Set-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps), and [New-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps).</span></span>
  

