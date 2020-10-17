---
title: " (建议) 创建会议目录"
description: " (建议) 创建会议目录。"
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: (Recommended) Create Conference Directories
ms:assetid: 787f4c94-1c96-468a-a74d-e06b7bd4b8a3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn832056(v=OCS.15)
ms:contentKeyID: 63146389
ms.date: 10/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b14982893fbc14a87818875a787d0f776da84ae3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563658"
---
# <a name="recommended-create-conference-directories"></a> (建议) 创建会议目录

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-10-03_

会议目录维护参与者在使用 Lync 2013 时用于加入会议的字母数字会议 ID 之间的映射，以及电话拨入式会议参与者用于加入会议的仅数字会议 ID。 会议 ID 的格式如下：

    <housekeeping digit (1 digit)><conference directory (usually 1-2 digits)><conference number (variable number of digits><check digit (1 digit)>

创建多个会议目录将确保会议 ID 将短暂停留，直到创建了大量会议。 在每个用户需要参与典型数量会议的组织中，建议您为池中的每 999 个用户创建一个会议目录。 通过使用此指南，通常可使会议 ID 保持较小数目。 但是，一旦池 (的会议目录数) 超过9，会议 ID 长度将增长以支持其他会议。

<div>

## <a name="creating-a-conference-directory"></a>创建会议目录

1.  在 Lync Server 命令行管理程序中，键入以下 cmdlet：
    
        New-CsConferenceDirectory -Identity <XdsGlobalRelativeIdentity> -HomePool <String> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]
    
    例如，以下命令将创建一个 id 为42的会议目录，该目录驻留在池 atl-cs-001.litwareinc.com 上：
    
        New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a>另请参阅


[Lync Server 2013 中的电话拨入式会议要求](lync-server-2013-dial-in-conferencing-requirements.md)  


[新 New-csconferencedirectory](https://docs.microsoft.com/powershell/module/skype/New-CsConferenceDirectory)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

