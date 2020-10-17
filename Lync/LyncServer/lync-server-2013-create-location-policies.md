---
title: Lync Server 2013：创建位置策略
description: Lync Server 2013：创建位置策略。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create location policies
ms:assetid: f1878194-c756-4794-8fa1-15dd2118b4b3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413006(v=OCS.15)
ms:contentKeyID: 48185794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 464ea9893890ab6185f180434e2dad13818123d1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562258"
---
# <a name="create-location-policies-in-lync-server-2013"></a><span data-ttu-id="3041f-103">在 Lync Server 2013 中创建位置策略</span><span class="sxs-lookup"><span data-stu-id="3041f-103">Create location policies in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3041f-104">_**上次修改的主题：** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="3041f-104">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="3041f-105">Lync Server 使用位置策略在客户端注册过程中为 E9-1-1 启用 Lync 客户端。</span><span class="sxs-lookup"><span data-stu-id="3041f-105">Lync Server uses a location policy to enable Lync clients for E9-1-1 during client registration.</span></span> <span data-ttu-id="3041f-106">位置策略包含定义 E9-1-1 实现方式的设置。</span><span class="sxs-lookup"><span data-stu-id="3041f-106">A location policy contains the settings that define how E9-1-1 will be implemented.</span></span>

<span data-ttu-id="3041f-p102">可以编辑全局位置策略，并创建新的带标记的位置策略。客户端所在的子网没有关联位置策略，或没有直接为客户端分配位置策略时，客户端会获取全局策略。向子网或用户分配带标记的策略。</span><span class="sxs-lookup"><span data-stu-id="3041f-p102">You can edit the global location policy and create new tagged location policies. A client obtains a global policy when it is not located within a subnet with an associated location policy, or when the client has not been directly assigned a location policy. Tagged policies are assigned to subnets or users.</span></span>

<span data-ttu-id="3041f-110">要创建位置策略，必须使用 RTCUniversalServerAdmins 组成员或 CsVoiceAdministrator 管理角色成员的帐户，或者具有等效管理员权限的帐户。</span><span class="sxs-lookup"><span data-stu-id="3041f-110">To create a location policy, you must use an account that is a member of the RTCUniversalServerAdmins group, or is a member of the CsVoiceAdministrator administrative role, or has equivalent administrator rights and permissions.</span></span>

<span data-ttu-id="3041f-111">有关位置策略的完整说明，请参阅 [定义 Lync Server 2013 的位置策略](lync-server-2013-defining-the-location-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="3041f-111">For a complete description of Location policies, see [Defining the location policy for Lync Server 2013](lync-server-2013-defining-the-location-policy.md).</span></span> <span data-ttu-id="3041f-112">此过程中的 Cmdlet 使用下列值定义的位置策略：</span><span class="sxs-lookup"><span data-stu-id="3041f-112">Cmdlets in this procedure use a location policy defined using the following values:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3041f-113">元素</span><span class="sxs-lookup"><span data-stu-id="3041f-113">Element</span></span></th>
<th><span data-ttu-id="3041f-114">值</span><span class="sxs-lookup"><span data-stu-id="3041f-114">Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3041f-115">EnhancedEmergencyServicesEnabled</span><span class="sxs-lookup"><span data-stu-id="3041f-115">EnhancedEmergencyServicesEnabled</span></span></p></td>
<td><p><span data-ttu-id="3041f-116"><strong>True</strong></span><span class="sxs-lookup"><span data-stu-id="3041f-116"><strong>True</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3041f-117">LocationRequired</span><span class="sxs-lookup"><span data-stu-id="3041f-117">LocationRequired</span></span></p></td>
<td><p><span data-ttu-id="3041f-118"><strong>免责声明</strong></span><span class="sxs-lookup"><span data-stu-id="3041f-118"><strong>Disclaimer</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3041f-119">EnhancedEmergencyServiceDisclaimer</span><span class="sxs-lookup"><span data-stu-id="3041f-119">EnhancedEmergencyServiceDisclaimer</span></span></p></td>
<td><p><span data-ttu-id="3041f-p104">您的公司策略要求您设置一个位置。如果不设置位置，紧急情况下，紧急服务将无法找到您。请设置一个位置。</span><span class="sxs-lookup"><span data-stu-id="3041f-p104">Your company policy requires you to set a location. If you do not set a location, emergency services will not be able to locate you in an emergency. Please set a location.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3041f-123">UseLocationForE911Only</span><span class="sxs-lookup"><span data-stu-id="3041f-123">UseLocationForE911Only</span></span></p></td>
<td><p><span data-ttu-id="3041f-124"><strong>False</strong></span><span class="sxs-lookup"><span data-stu-id="3041f-124"><strong>False</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3041f-125">PstnUsage</span><span class="sxs-lookup"><span data-stu-id="3041f-125">PstnUsage</span></span></p></td>
<td><p><span data-ttu-id="3041f-126"><strong>EmergencyUsage</strong></span><span class="sxs-lookup"><span data-stu-id="3041f-126"><strong>EmergencyUsage</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3041f-127">EmergencyDialString</span><span class="sxs-lookup"><span data-stu-id="3041f-127">EmergencyDialString</span></span></p></td>
<td><p><span data-ttu-id="3041f-128"><strong>911</strong></span><span class="sxs-lookup"><span data-stu-id="3041f-128"><strong>911</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3041f-129">EmergencyDialMask</span><span class="sxs-lookup"><span data-stu-id="3041f-129">EmergencyDialMask</span></span></p></td>
<td><p><span data-ttu-id="3041f-130"><strong>112</strong></span><span class="sxs-lookup"><span data-stu-id="3041f-130"><strong>112</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3041f-131">NotificationUri</span><span class="sxs-lookup"><span data-stu-id="3041f-131">NotificationUri</span></span></p></td>
<td><p><span data-ttu-id="3041f-132"><strong>sip:security@litwareinc.com</strong></span><span class="sxs-lookup"><span data-stu-id="3041f-132"><strong>sip:security@litwareinc.com</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3041f-133">ConferenceUri</span><span class="sxs-lookup"><span data-stu-id="3041f-133">ConferenceUri</span></span></p></td>
<td><p><span data-ttu-id="3041f-134"><strong>sip:+14255550123@litwareinc.com</strong></span><span class="sxs-lookup"><span data-stu-id="3041f-134"><strong>sip:+14255550123@litwareinc.com</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3041f-135">ConferenceMode</span><span class="sxs-lookup"><span data-stu-id="3041f-135">ConferenceMode</span></span></p></td>
<td><p><span data-ttu-id="3041f-136"><strong>twoway</strong></span><span class="sxs-lookup"><span data-stu-id="3041f-136"><strong>twoway</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3041f-137">LocationRefreshInterval</span><span class="sxs-lookup"><span data-stu-id="3041f-137">LocationRefreshInterval</span></span></p></td>
<td><p><span data-ttu-id="3041f-138"><strong>2</strong></span><span class="sxs-lookup"><span data-stu-id="3041f-138"><strong>2</strong></span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="3041f-139">有关使用位置策略的详细信息，请参阅 Lync Server 命令行管理程序文档中的以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="3041f-139">For details about working with location policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="3041f-140">New-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="3041f-140">New-CsLocationPolicy</span></span>

  - <span data-ttu-id="3041f-141">Get-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="3041f-141">Get-CsLocationPolicy</span></span>

  - <span data-ttu-id="3041f-142">Set-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="3041f-142">Set-CsLocationPolicy</span></span>

  - <span data-ttu-id="3041f-143">Remove-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="3041f-143">Remove-CsLocationPolicy</span></span>

  - <span data-ttu-id="3041f-144">Grant-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="3041f-144">Grant-CsLocationPolicy</span></span>

<div>

## <a name="to-create-location-policies"></a><span data-ttu-id="3041f-145">创建位置策略</span><span class="sxs-lookup"><span data-stu-id="3041f-145">To create location policies</span></span>

1.  <span data-ttu-id="3041f-146">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3041f-146">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3041f-147">如果 PstnUsages 的全局列表中还没有 <STRONG>PstnUsage</STRONG> 设置，则 CsLocationPolicy 会失败。</span><span class="sxs-lookup"><span data-stu-id="3041f-147">CsLocationPolicy will fail if the setting for <STRONG>PstnUsage</STRONG> is not already in the Global list of PstnUsages.</span></span>

    
    </div>

2.  <span data-ttu-id="3041f-148">也可以选择运行以下 cmdlet 编辑全局位置策略：</span><span class="sxs-lookup"><span data-stu-id="3041f-148">Optionally, run the following cmdlet to edit the global Location Policy:</span></span>
    
        Set-CsLocationPolicy -Identity Global -EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -PstnUsage "emergencyUsage" -EmergencyDialString "911" -ConferenceMode "twoway" -ConferenceUri "sip:+14255550123@litwareinc.com" -EmergencyDialMask "112" NotificationUri "sip:security@litwareinc.com" -UseLocationForE911Only $true -LocationRefreshInterval 2

3.  <span data-ttu-id="3041f-149">运行以下命令创建带标记的位置策略。</span><span class="sxs-lookup"><span data-stu-id="3041f-149">Run the following to create a tagged Location Policy.</span></span>
    
        New-CsLocationPolicy -Identity Tag:Redmond - EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -UseLocationForE911Only $false -PstnUsage "EmergencyUsage" -EmergencyDialString "911" -EmergencyDialMask "112" -NotificationUri "sip:security@litwareinc.com" -ConferenceUri "sip:+14255550123@litwareinc.com" -ConferenceMode "twoway" -LocationRefreshInterval 2

4.  <span data-ttu-id="3041f-150">运行以下 cmdlet 将步骤 3 中创建的带标记的位置策略应用于用户策略。</span><span class="sxs-lookup"><span data-stu-id="3041f-150">Run the following cmdlet to apply the tagged Location Policy created in step 3 to a user policy.</span></span>
    
        (Get-CsUser | where { $_.Name -match "UserName" }) | Grant-CsLocationPolicy -PolicyName Redmond

</div>

</div>

<span> </span>

</div>

</div>

</div>

