---
title: Lync Server 2013：（可选）修改 DTMF 命令的键映射
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
ms.openlocfilehash: 86986ba2715021e7bf39f5d448f9de5f9a733f54
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216488"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="optional-modify-key-mapping-for-dtmf-commands-in-lync-server-2013"></a>Optional在 Lync Server 2013 中修改 DTMF 命令的键映射

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-30_

电话拨入式会议用户可以在电话小键盘上按键以执行双音多频 (DTMF) 命令。通过 DTMF 命令，拨入会议的用户可以使用其电话上的小键盘控制会议设置（例如，将自己静音和取消静音，或者锁定和解锁会议）。可以使用 cmdlet 修改用于 DTMF 命令的键。此步骤是可选的。

<div>


> [!NOTE]  
> 有关这些 cmdlet 和可能的 DTMF 选项的详细信息，请参阅 Lync Server Management Shell 文档或 Lync Server Management Shell 命令行帮助。



</div>

<div>

## <a name="to-modify-the-key-mapping-of-dtmf-commands"></a>修改 DTMF 命令的键映射

1.  以 **RTCUniversalServerAdmins** 组成员或者 **Cs-ServerAdministrator** 或 **CsAdministrator** 角色成员的身份登录计算机。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

3.  在命令提示符下，运行以下内容：
    
        Get-CsDialinConferencingDtmfConfiguration
    
    此 cmdlet 可返回用于电话拨入式会议的 DTMF 设置。

4.  运行以下 cmdlet 并为要更改的每个选项指定要按的键：
    
        Set-CsDialinConferencingDtmfConfiguration [-Identity <global or site collection to be changed>]
        [-AdmitAll <default key is 8>] [-AudienceMuteCommand <default key is 4>]
        [-CommandCharacter <* (default) | #>] [-EnableDisableAnnouncementsCommand <default key is 9>]
        [-HelpCommand <default key is 1>] [-LockUnlockConferenceCommand <default key is 7>]
        [-MuteUnmuteCommand <default key is 6>] [-PrivateRollCallCommand <default key is 3>]
    
    此 cmdlet 可修改用于电话拨入式会议的 DTMF 设置。
    
    例如：
    
        Set-CsDialinConferencingDtmfConfiguration -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9
    
    此示例可使启用或禁用通知所按的键和将所有与会者静音和取消静音所按的键交换。由于未指定 Identity，因此这些更改将应用于全局 DTMF 设置。

5.  （可选）要为特定站点创建其他 DTMF 命令集，请使用带有站点 Identity 的 **New-CsDialinConferencingDtmfConfiguration** cmdlet。 为站点创建新的 DTMF 设置后，站点设置将优先于全局设置。 有关详细信息，请参阅 Lync Server 命令行管理程序文档或 Lync Server Management Shell 命令行帮助。

</div>

</div>

<span> </span>

</div>

</div>

</div>

