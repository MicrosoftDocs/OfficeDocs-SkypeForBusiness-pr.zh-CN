---
title: Lync Server 2013：配置移动策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring mobility policy
ms:assetid: 595536e0-9bb3-49a3-8d13-1a77351ebc62
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690018(v=OCS.15)
ms:contentKeyID: 48184204
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82ca5fbd079f428edf48ef3f0c28bd3677a5acde
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134748"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-mobility-policy-in-lync-server-2013"></a><span data-ttu-id="68abb-102">在 Lync Server 2013 中配置移动策略</span><span class="sxs-lookup"><span data-stu-id="68abb-102">Configuring mobility policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="68abb-103">_**上次修改的主题：** 2013-02-13_</span><span class="sxs-lookup"><span data-stu-id="68abb-103">_**Topic Last Modified:** 2013-02-13_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="68abb-104">Lync Server 2013 提供了移动性策略，用于确定谁可以使用移动功能、通过工作呼叫、IP 语音（VoIP）或视频，以及 VoIP 或视频是否需要 WiFi。</span><span class="sxs-lookup"><span data-stu-id="68abb-104">Lync Server 2013 provides mobility policies that determine who can use mobility features, Call via Work, voice over IP (VoIP) or video, and whether WiFi will be required for either VoIP or video.</span></span> <span data-ttu-id="68abb-105">通过 "通过工作进行呼叫" 功能，移动用户可以通过使用工作电话号码而不是移动电话号码，在移动电话上拨打和接听呼叫。</span><span class="sxs-lookup"><span data-stu-id="68abb-105">The Call via Work feature enables a mobile user to make and receive calls on a mobile phone by using a work phone number instead of the mobile phone number.</span></span> <span data-ttu-id="68abb-106">此功能可防止被叫方查看呼叫者的移动电话号码，并允许用户避免出站通话费用。</span><span class="sxs-lookup"><span data-stu-id="68abb-106">This feature prevents the called party from seeing the caller's mobile phone number and enables a user to avoid outbound calling charges.</span></span> <span data-ttu-id="68abb-107">配置 VoIP 和视频使用户可以接收和发出 VoIP 呼叫和视频。</span><span class="sxs-lookup"><span data-stu-id="68abb-107">Configuring VoIP and video makes it possible for users to receive and make VoIP calls and video.</span></span> <span data-ttu-id="68abb-108">WiFi 用法的设置定义用户的设备是否需要通过蜂窝数据网络使用 WiFi 网络。</span><span class="sxs-lookup"><span data-stu-id="68abb-108">Settings for WiFi usage define if a user’s device will be required to use a WiFi network over a cellular data network.</span></span>

<span data-ttu-id="68abb-109">默认情况下，移动性、通过工作进行呼叫以及启用 VoIP 和视频功能。</span><span class="sxs-lookup"><span data-stu-id="68abb-109">By default, mobility, Call via Work, and the VoIP and video features are enabled.</span></span> <span data-ttu-id="68abb-110">禁用 VoIp 和视频需要 WiFi 的设置。</span><span class="sxs-lookup"><span data-stu-id="68abb-110">The settings to require WiFi for VoIp and video are disabled.</span></span> <span data-ttu-id="68abb-111">管理员可确定哪些用户可通过运行 cmdlet 访问这些功能。</span><span class="sxs-lookup"><span data-stu-id="68abb-111">Administrators can determine who has access to these features by running a cmdlet.</span></span> <span data-ttu-id="68abb-112">您可以按网站或用户全局关闭这些选项。</span><span class="sxs-lookup"><span data-stu-id="68abb-112">You can turn options off globally, by site, or by user.</span></span>

<span data-ttu-id="68abb-113">为了能够使用移动功能和单位电话呼叫功能，用户必须满足以下先决条件：</span><span class="sxs-lookup"><span data-stu-id="68abb-113">To be able to use mobility features and Call via Work, users must meet the following prerequisites:</span></span>

  - <span data-ttu-id="68abb-114">必须为用户启用 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="68abb-114">Users must be enabled for Lync Server 2013.</span></span>

  - <span data-ttu-id="68abb-115">用户必须启用企业语音。</span><span class="sxs-lookup"><span data-stu-id="68abb-115">Users must be enabled for Enterprise Voice.</span></span>

  - <span data-ttu-id="68abb-116">必须为用户分配已将“EnableMobility”\*\*\*\* 选项设置为 True 的移动策略。</span><span class="sxs-lookup"><span data-stu-id="68abb-116">Users must be assigned a mobility policy that has the **EnableMobility** option set to True.</span></span>

<span data-ttu-id="68abb-117">对于希望能使用单位电话呼叫功能的用户，他们必须满足以下两个额外的先决条件：</span><span class="sxs-lookup"><span data-stu-id="68abb-117">For users to be able to use Call via Work, they must meet the following two additional prerequisites:</span></span>

  - <span data-ttu-id="68abb-118">必须为用户分配已选择“允许多部电话同时响铃”\*\*\*\* 选项的语音策略。</span><span class="sxs-lookup"><span data-stu-id="68abb-118">Users must be assigned a voice policy that has the **Enable simultaneous ringing of phones** option selected.</span></span>

  - <span data-ttu-id="68abb-119">必须为用户分配已将“EnableOutsideVoice”\*\*\*\* 选项设置为 True 的移动策略。</span><span class="sxs-lookup"><span data-stu-id="68abb-119">Users must be assigned a mobility policy that has the **EnableOutsideVoice** option set to True.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="68abb-120">未启用企业语音的用户可以使用其移动设备将 Lync 设置为通过 IP （VoIP）呼叫，也可以通过在其移动设备上单击加入链接来加入会议，前提是为这些用户分配语音策略的相应选项。</span><span class="sxs-lookup"><span data-stu-id="68abb-120">Users who are not enabled for Enterprise Voice can use their mobile devices to make Lync to Lync Voice over IP (VoIP) calls, or can join conferences by using the Click to Join link on their mobile devices, if you assign those users the appropriate options for voice policy.</span></span> <span data-ttu-id="68abb-121">有关详细信息，请参阅为<A href="lync-server-2013-defining-your-mobility-requirements.md">Lync Server 2013 定义移动性要求</A>。</span><span class="sxs-lookup"><span data-stu-id="68abb-121">For details, see <A href="lync-server-2013-defining-your-mobility-requirements.md">Defining your mobility requirements for Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="68abb-122">有关为用户启用 Lync Server 2013 的详细信息，请参阅[Disable or 重新启用 Lync server 2013 的用户帐户](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)。</span><span class="sxs-lookup"><span data-stu-id="68abb-122">For details about enabling users for Lync Server 2013, see [Disable or re-enable user account for Lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md).</span></span> <span data-ttu-id="68abb-123">有关为用户启用企业语音的详细信息，请参阅[Enable users For Enterprise voice In Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md)。</span><span class="sxs-lookup"><span data-stu-id="68abb-123">For details about enabling users for Enterprise Voice, see [Enable users for Enterprise Voice in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span></span> <span data-ttu-id="68abb-124">有关设置语音策略选项的详细信息，请参阅[在 Lync Server 2013 中修改语音策略和配置 PSTN 用法记录](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)。</span><span class="sxs-lookup"><span data-stu-id="68abb-124">For details about setting voice policy options, see [Modify a voice policy and configure PSTN usage records in Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md).</span></span>

<div>

## <a name="to-modify-global-mobility-policy"></a><span data-ttu-id="68abb-125">修改全局移动策略</span><span class="sxs-lookup"><span data-stu-id="68abb-125">To modify global mobility policy</span></span>

1.  <span data-ttu-id="68abb-126">登录到安装了 Lync Server 命令行管理程序和 Ocscore 的任何计算机作为 CsAdministrator 角色的成员。</span><span class="sxs-lookup"><span data-stu-id="68abb-126">Log on to any computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="68abb-127">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="68abb-127">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="68abb-p105">全局禁用对移动功能和单位电话呼叫功能的访问。在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="68abb-p105">Turn off access to mobility and Call via Work globally. At the command line, type:</span></span>
    
        Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="68abb-p106">您可禁用单位电话呼叫功能，而不禁用对移动功能的访问。但是，您无法在不禁用单位电话呼叫功能的情况下禁用移动功能。</span><span class="sxs-lookup"><span data-stu-id="68abb-p106">You can turn off Call via Work without turning off access to mobility. However, you cannot turn off mobility without also turning off Call via Work.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-mobility-policy-by-site"></a><span data-ttu-id="68abb-132">按网站修改移动策略</span><span class="sxs-lookup"><span data-stu-id="68abb-132">To modify mobility policy by site</span></span>

1.  <span data-ttu-id="68abb-133">登录到安装了 Lync Server 命令行管理程序和 Ocscore 的任何计算机作为 CsAdministrator 角色的成员。</span><span class="sxs-lookup"><span data-stu-id="68abb-133">Log on to any computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="68abb-134">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="68abb-134">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="68abb-135">创建网站级策略，并关闭 VoIP 和视频，并启用站点的 IP 音频和 IP 视频需要 WiFi。</span><span class="sxs-lookup"><span data-stu-id="68abb-135">Create a site-level policy, and turn off VoIP and video, and enable Require WiFi for IP Audio and for IP Video by site.</span></span> <span data-ttu-id="68abb-136">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="68abb-136">At the command line, type:</span></span>
    
        New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $False -RequireWiFiForIPAudio $True -RequireWiFiForIPVideo $True

</div>

<div>

## <a name="to-modify-mobility-policy-by-user"></a><span data-ttu-id="68abb-137">通过用户修改移动策略</span><span class="sxs-lookup"><span data-stu-id="68abb-137">To modify mobility policy by user</span></span>

1.  <span data-ttu-id="68abb-138">登录到安装了 Lync Server 命令行管理程序和 Ocscore 的任何计算机作为 CsAdministrator 角色的成员。</span><span class="sxs-lookup"><span data-stu-id="68abb-138">Log on to any computer where Lync Server Management Shell and Ocscore are installed as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="68abb-139">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="68abb-139">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="68abb-p108">创建用户级别移动策略，然后按用户禁用对移动功能和单位电话呼叫功能的访问。在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="68abb-p108">Create user level mobility policies and turn off mobility and Call via Work by user. At the command line, type:</span></span>
    
        New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
    
    <span data-ttu-id="68abb-p109">您可禁用单位电话呼叫功能，而不禁用对移动功能的访问。但是，您无法在不禁用单位电话呼叫功能的情况下禁用移动功能。</span><span class="sxs-lookup"><span data-stu-id="68abb-p109">You can turn off Call via Work without turning off access to mobility. However, you cannot turn off mobility without also turning off Call via Work.</span></span>
    
    <span data-ttu-id="68abb-144">例如：</span><span class="sxs-lookup"><span data-stu-id="68abb-144">For example:</span></span>
    
        New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity -MobileUser1@contoso.com -PolicyName Tag:disableOutsideVoice

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="68abb-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="68abb-145">See Also</span></span>


[<span data-ttu-id="68abb-146">为 Lync Server 2013 禁用或重新启用用户帐户</span><span class="sxs-lookup"><span data-stu-id="68abb-146">Disable or re-enable user account for Lync Server 2013</span></span>](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  
[<span data-ttu-id="68abb-147">在 Lync Server 2013 中为用户启用企业语音</span><span class="sxs-lookup"><span data-stu-id="68abb-147">Enable users for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-enable-users-for-enterprise-voice.md)  
[<span data-ttu-id="68abb-148">在 Lync Server 2013 中修改语音策略和配置 PSTN 用法记录</span><span class="sxs-lookup"><span data-stu-id="68abb-148">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  


[<span data-ttu-id="68abb-149">定义 Lync Server 2013 的移动性要求</span><span class="sxs-lookup"><span data-stu-id="68abb-149">Defining your mobility requirements for Lync Server 2013</span></span>](lync-server-2013-defining-your-mobility-requirements.md)  


[<span data-ttu-id="68abb-150">新 Set-csmobilitypolicy</span><span class="sxs-lookup"><span data-stu-id="68abb-150">New-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy)  
[<span data-ttu-id="68abb-151">Set-csmobilitypolicy</span><span class="sxs-lookup"><span data-stu-id="68abb-151">Set-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy)  
[<span data-ttu-id="68abb-152">Set-csmobilitypolicy</span><span class="sxs-lookup"><span data-stu-id="68abb-152">Get-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsMobilityPolicy)  
[<span data-ttu-id="68abb-153">Grant-Set-csmobilitypolicy</span><span class="sxs-lookup"><span data-stu-id="68abb-153">Grant-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsMobilityPolicy)  
[<span data-ttu-id="68abb-154">Set-csmobilitypolicy</span><span class="sxs-lookup"><span data-stu-id="68abb-154">Remove-CsMobilityPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsMobilityPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

