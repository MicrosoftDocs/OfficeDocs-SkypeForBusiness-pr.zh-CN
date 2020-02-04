---
title: （建议）创建会议目录
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: (Recommended) Create Conference Directories
ms:assetid: 787f4c94-1c96-468a-a74d-e06b7bd4b8a3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn832056(v=OCS.15)
ms:contentKeyID: 63146389
ms.date: 10/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5d525951dcb77ee365c9c83461f678c26ae53af6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727332"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="recommended-create-conference-directories"></a>（建议）创建会议目录

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2014-10-03_

会议目录维护参与者在使用 Lync 2013 时用于加入会议的字母数字会议 ID 之间的映射，以及电话拨入式会议参与者用于加入会议的仅限数字的会议 ID。 会议 ID 的格式如下：

    <housekeeping digit (1 digit)><conference directory (usually 1-2 digits)><conference number (variable number of digits><check digit (1 digit)>

创建多个会议目录将确保会议 ID 将短暂停留，直到创建了大量会议。 在每个用户需要参与典型数量会议的组织中，建议您为池中的每 999 个用户创建一个会议目录。 使用此准则时，会议 Id 通常可以保持较小。 但是，只要会议目录数（所有池中）超过 9，会议 ID 长度就会增加以支持更多会议。

<div>

## <a name="creating-a-conference-directory"></a>创建会议目录

1.  在 Lync Server 命令行管理程序中，键入以下 cmdlet：
    
        New-CsConferenceDirectory -Identity <XdsGlobalRelativeIdentity> -HomePool <String> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]
    
    例如，以下内容将创建一个具有 id 42 的会议目录，该目录在 pool atl-cs-001.litwareinc.com 上托管：
    
        New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a>另请参阅


[Lync Server 2013 中的电话拨入式会议要求](lync-server-2013-dial-in-conferencing-requirements.md)  


[New-CsConferenceDirectory](https://docs.microsoft.com/powershell/module/skype/New-CsConferenceDirectory)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

