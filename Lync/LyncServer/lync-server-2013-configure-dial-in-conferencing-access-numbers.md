---
title: Lync Server 2013：配置电话拨入式会议访问号码
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure dial-in conferencing access numbers
ms:assetid: d8a18030-f318-43dd-834d-70e5014b5e8a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398952(v=OCS.15)
ms:contentKeyID: 48185623
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e19d594b8d1661a314b834e6c2e92d8668490ad7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757906"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dial-in-conferencing-access-numbers-in-lync-server-2013"></a><span data-ttu-id="76250-102">在 Lync Server 2013 中配置电话拨入式会议访问号码</span><span class="sxs-lookup"><span data-stu-id="76250-102">Configure dial-in conferencing access numbers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="76250-103">_**主题上次修改时间：** 2011-07-17_</span><span class="sxs-lookup"><span data-stu-id="76250-103">_**Topic Last Modified:** 2011-07-17_</span></span>

<span data-ttu-id="76250-104">部署电话拨入式会议时，需要设置用户可以从公用电话交换网 (PSTN) 拨打以加入会议的音频部分的电话号码。</span><span class="sxs-lookup"><span data-stu-id="76250-104">When you deploy dial-in conferencing, you need to set up phone numbers that users can dial from the public switched telephone network (PSTN) to join the audio portion of conferences.</span></span> <span data-ttu-id="76250-105">这些拨入访问号码显示在会议邀请和“电话拨入式会议设置”网页上。</span><span class="sxs-lookup"><span data-stu-id="76250-105">These dial-in access numbers appear in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>

<span data-ttu-id="76250-106">创建拨入访问号码前，必须首先规划电话拨入式会议区域，然后配置区域的拨号计划。</span><span class="sxs-lookup"><span data-stu-id="76250-106">Before you can create dial-in access numbers, you must first plan your dial-in conferencing regions and then configure dial plans with the regions.</span></span> <span data-ttu-id="76250-107">有关区域的详细信息，请参阅规划文档中[Lync Server 2013 中的电话拨入式会议要求](lync-server-2013-dial-in-conferencing-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="76250-107">For details about regions, see [Dial-in conferencing requirements in Lync Server 2013](lync-server-2013-dial-in-conferencing-requirements.md) in the Planning documentation.</span></span> <span data-ttu-id="76250-108">有关配置电话拨入式会议的拨号计划的详细信息，请参阅[在 Lync Server 2013 中配置电话拨入式会议的拨号计划](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md)。</span><span class="sxs-lookup"><span data-stu-id="76250-108">For details about configuring dial plans for dial-in conferencing, see [Configure dial plans for dial-in conferencing in Lync Server 2013](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="76250-109">在该访问号码的 Active Directory 域服务（AD&nbsp;DS）复制完成之前，您无法使用新的拨入访问号码。</span><span class="sxs-lookup"><span data-stu-id="76250-109">You cannot use a new dial-in access number until Active Directory Domain Services (AD&nbsp;DS) replication of that access number is complete.</span></span> <span data-ttu-id="76250-110">复制可能需要几个小时才能完成。</span><span class="sxs-lookup"><span data-stu-id="76250-110">Replication can take several hours to complete.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="76250-111">创建拨入访问号码后，可以修改 Active Directory 联系人对象的显示名，以便用户可以更轻松地识别正确的访问号码。</span><span class="sxs-lookup"><span data-stu-id="76250-111">After you create dial-in access numbers, you can modify the display name for the Active Directory contact objects so that users can more easily identify the correct access number.</span></span> <span data-ttu-id="76250-112">使用<STRONG>CsDialInConferencingAccessNumber</STRONG> cmdlet 修改显示名称。</span><span class="sxs-lookup"><span data-stu-id="76250-112">Use the <STRONG>Set-CsDialInConferencingAccessNumber</STRONG> cmdlet to modify the display name.</span></span> <span data-ttu-id="76250-113">不应手动修改 Active Directory 对象。</span><span class="sxs-lookup"><span data-stu-id="76250-113">You should not modify Active Directory objects manually.</span></span> <span data-ttu-id="76250-114">有关修改访问号码的详细信息，请参阅 Lync Server Management Shell 文档中的<STRONG>CsDialInConferencingAccessNumber</STRONG> cmdlet。</span><span class="sxs-lookup"><span data-stu-id="76250-114">For details about modifying an access number, see Lync Server Management Shell documentation for the <STRONG>Set-CsDialInConferencingAccessNumber</STRONG> cmdlet.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="76250-115">本节内容</span><span class="sxs-lookup"><span data-stu-id="76250-115">In This Section</span></span>

[<span data-ttu-id="76250-116">在 Lync Server 2013 中创建或修改电话拨入式会议访问号码</span><span class="sxs-lookup"><span data-stu-id="76250-116">Create or modify a dial-in conferencing access number in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-dial-in-conferencing-access-number.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="76250-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="76250-117">See Also</span></span>


[<span data-ttu-id="76250-118">Lync Server 2013 中的电话拨入式会议要求</span><span class="sxs-lookup"><span data-stu-id="76250-118">Dial-in conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-dial-in-conferencing-requirements.md)  


[<span data-ttu-id="76250-119">在 Lync Server 2013 中配置电话拨入式会议的拨号计划</span><span class="sxs-lookup"><span data-stu-id="76250-119">Configure dial plans for dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

