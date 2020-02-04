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

# <a name="recommended-create-conference-directories"></a><span data-ttu-id="5093c-102">（建议）创建会议目录</span><span class="sxs-lookup"><span data-stu-id="5093c-102">(Recommended) Create Conference Directories</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5093c-103">_**主题上次修改时间：** 2014-10-03_</span><span class="sxs-lookup"><span data-stu-id="5093c-103">_**Topic Last Modified:** 2014-10-03_</span></span>

<span data-ttu-id="5093c-104">会议目录维护参与者在使用 Lync 2013 时用于加入会议的字母数字会议 ID 之间的映射，以及电话拨入式会议参与者用于加入会议的仅限数字的会议 ID。</span><span class="sxs-lookup"><span data-stu-id="5093c-104">Conference directories maintain a mapping between the alphanumeric meeting ID that a participant uses to join a conference when using Lync 2013, and the numeric-only conference ID that a dial-in conferencing participant uses to join the conference.</span></span> <span data-ttu-id="5093c-105">会议 ID 的格式如下：</span><span class="sxs-lookup"><span data-stu-id="5093c-105">The format of the conference ID is as follows:</span></span>

    <housekeeping digit (1 digit)><conference directory (usually 1-2 digits)><conference number (variable number of digits><check digit (1 digit)>

<span data-ttu-id="5093c-106">创建多个会议目录将确保会议 ID 将短暂停留，直到创建了大量会议。</span><span class="sxs-lookup"><span data-stu-id="5093c-106">Creating multiple conference directories will ensure that conference IDs will stay short until a significant amount of conferences have been created.</span></span> <span data-ttu-id="5093c-107">在每个用户需要参与典型数量会议的组织中，建议您为池中的每 999 个用户创建一个会议目录。</span><span class="sxs-lookup"><span data-stu-id="5093c-107">In an organization with a typical number of conferences per user, we recommend that you create one conference directory for every 999 users in the pool.</span></span> <span data-ttu-id="5093c-108">使用此准则时，会议 Id 通常可以保持较小。</span><span class="sxs-lookup"><span data-stu-id="5093c-108">Using this guideline the conference IDs can generally be kept small.</span></span> <span data-ttu-id="5093c-109">但是，只要会议目录数（所有池中）超过 9，会议 ID 长度就会增加以支持更多会议。</span><span class="sxs-lookup"><span data-stu-id="5093c-109">However, once the number of conference directories (across the pools) exceed 9, the Conference ID length will grow to support additional conferences.</span></span>

<div>

## <a name="creating-a-conference-directory"></a><span data-ttu-id="5093c-110">创建会议目录</span><span class="sxs-lookup"><span data-stu-id="5093c-110">Creating a conference directory</span></span>

1.  <span data-ttu-id="5093c-111">在 Lync Server 命令行管理程序中，键入以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="5093c-111">In Lync Server Management Shell, type the following cmdlet:</span></span>
    
        New-CsConferenceDirectory -Identity <XdsGlobalRelativeIdentity> -HomePool <String> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]
    
    <span data-ttu-id="5093c-112">例如，以下内容将创建一个具有 id 42 的会议目录，该目录在 pool atl-cs-001.litwareinc.com 上托管：</span><span class="sxs-lookup"><span data-stu-id="5093c-112">For example, the following creates a conference directory with the identity 42, hosted on the pool atl-cs-001.litwareinc.com:</span></span>
    
        New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5093c-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5093c-113">See Also</span></span>


[<span data-ttu-id="5093c-114">Lync Server 2013 中的电话拨入式会议要求</span><span class="sxs-lookup"><span data-stu-id="5093c-114">Dial-in conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-dial-in-conferencing-requirements.md)  


[<span data-ttu-id="5093c-115">New-CsConferenceDirectory</span><span class="sxs-lookup"><span data-stu-id="5093c-115">New-CsConferenceDirectory</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsConferenceDirectory)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

