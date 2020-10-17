---
title: Lync Server 2013： (可选) Modify DTMF 命令的键映射
description: Lync Server 2013： (Optional) Modify DTMF 命令的键映射。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Modify key mapping for DTMF commands
ms:assetid: d753b78d-400c-4df2-957f-e7576b2019c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398943(v=OCS.15)
ms:contentKeyID: 48185563
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7581001c31d929163962378a8734435f6d07c6c8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565788"
---
# <a name="optional-modify-key-mapping-for-dtmf-commands-in-lync-server-2013"></a><span data-ttu-id="05975-103"> (可选) 在 Lync Server 2013 中修改 DTMF 命令的键映射</span><span class="sxs-lookup"><span data-stu-id="05975-103">(Optional) Modify key mapping for DTMF commands in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="05975-104">_**上次修改的主题：** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="05975-104">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="05975-p101">电话拨入式会议用户可以在电话小键盘上按键以执行双音多频 (DTMF) 命令。通过 DTMF 命令，拨入会议的用户可以使用其电话上的小键盘控制会议设置（例如，将自己静音和取消静音，或者锁定和解锁会议）。可以使用 cmdlet 修改用于 DTMF 命令的键。此步骤是可选的。</span><span class="sxs-lookup"><span data-stu-id="05975-p101">Dial-in conferencing users can press keys on the telephone keypad to perform dual-tone multi-frequency (DTMF) commands. DTMF commands enable users who dial in to a conference to control conference settings (such as muting and unmuting themselves or locking and unlocking the conference) by using the keypad on their telephone. You can use cmdlets to modify the keys used for the DTMF commands. This step is optional.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="05975-109">有关这些 cmdlet 和可能的 DTMF 选项的详细信息，请参阅 Lync Server Management Shell 文档或 Lync Server Management Shell 命令行帮助。</span><span class="sxs-lookup"><span data-stu-id="05975-109">For details about these cmdlets and the possible DTMF options, see Lync Server Management Shell documentation or Lync Server Management Shell command-line Help.</span></span>



</div>

<div>

## <a name="to-modify-the-key-mapping-of-dtmf-commands"></a><span data-ttu-id="05975-110">修改 DTMF 命令的键映射</span><span class="sxs-lookup"><span data-stu-id="05975-110">To modify the key mapping of DTMF commands</span></span>

1.  <span data-ttu-id="05975-111">以 **RTCUniversalServerAdmins** 组成员或者 **Cs-ServerAdministrator** 或 **CsAdministrator** 角色成员的身份登录计算机。</span><span class="sxs-lookup"><span data-stu-id="05975-111">Log on to the computer as a member of the **RTCUniversalServerAdmins** group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="05975-112">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="05975-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="05975-113">在命令提示符下，运行以下内容：</span><span class="sxs-lookup"><span data-stu-id="05975-113">Run the following at the command prompt:</span></span>
    
        Get-CsDialinConferencingDtmfConfiguration
    
    <span data-ttu-id="05975-114">此 cmdlet 可返回用于电话拨入式会议的 DTMF 设置。</span><span class="sxs-lookup"><span data-stu-id="05975-114">This cmdlet returns the DTMF settings used for dial-in conferencing.</span></span>

4.  <span data-ttu-id="05975-115">运行以下 cmdlet 并为要更改的每个选项指定要按的键：</span><span class="sxs-lookup"><span data-stu-id="05975-115">Run the following cmdlet and specify the key to be pressed for each option that you want to change:</span></span>
    
        Set-CsDialinConferencingDtmfConfiguration [-Identity <global or site collection to be changed>]
        [-AdmitAll <default key is 8>] [-AudienceMuteCommand <default key is 4>]
        [-CommandCharacter <* (default) | #>] [-EnableDisableAnnouncementsCommand <default key is 9>]
        [-HelpCommand <default key is 1>] [-LockUnlockConferenceCommand <default key is 7>]
        [-MuteUnmuteCommand <default key is 6>] [-PrivateRollCallCommand <default key is 3>]
    
    <span data-ttu-id="05975-116">此 cmdlet 可修改用于电话拨入式会议的 DTMF 设置。</span><span class="sxs-lookup"><span data-stu-id="05975-116">This cmdlet modifies the DTMF settings used for dial-in conferencing.</span></span>
    
    <span data-ttu-id="05975-117">例如：</span><span class="sxs-lookup"><span data-stu-id="05975-117">For example:</span></span>
    
        Set-CsDialinConferencingDtmfConfiguration -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9
    
    <span data-ttu-id="05975-p102">此示例可使启用或禁用通知所按的键和将所有与会者静音和取消静音所按的键交换。由于未指定 Identity，因此这些更改将应用于全局 DTMF 设置。</span><span class="sxs-lookup"><span data-stu-id="05975-p102">This example swaps the key that is pressed to enable or disable announcements and the key that is pressed to mute and unmute all participants. Because no Identity is specified, these changes apply to the global DTMF settings.</span></span>

5.  <span data-ttu-id="05975-120">（可选）要为特定站点创建其他 DTMF 命令集，请使用带有站点 Identity 的 **New-CsDialinConferencingDtmfConfiguration** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="05975-120">(Optional) To create additional sets of DTMF commands for specific sites, use the **New-CsDialinConferencingDtmfConfiguration** cmdlet with a site identity.</span></span> <span data-ttu-id="05975-121">为站点创建新的 DTMF 设置后，站点设置将优先于全局设置。</span><span class="sxs-lookup"><span data-stu-id="05975-121">When you create new DTMF settings for sites, the site settings take precedence over the global settings.</span></span> <span data-ttu-id="05975-122">有关详细信息，请参阅 Lync Server 命令行管理程序文档或 Lync Server Management Shell 命令行帮助。</span><span class="sxs-lookup"><span data-stu-id="05975-122">For details, see Lync Server Management Shell documentation or Lync Server Management Shell command-line Help.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

