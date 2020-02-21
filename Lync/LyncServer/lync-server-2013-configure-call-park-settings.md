---
title: Lync Server 2013：配置呼叫寄存设置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Call Park settings
ms:assetid: 3bed9d09-8363-4fff-a220-f0f6d3a81241
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425886(v=OCS.15)
ms:contentKeyID: 48183922
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b99bc06f22490013dd14dc8527bd3eb88938380
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205138"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-call-park-settings-in-lync-server-2013"></a><span data-ttu-id="13ecd-102">在 Lync Server 2013 中配置呼叫寄存设置</span><span class="sxs-lookup"><span data-stu-id="13ecd-102">Configure Call Park settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="13ecd-103">_**上次修改的主题：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="13ecd-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="13ecd-104">如果不想使用默认呼叫寄存设置，可以对其进行自定义。</span><span class="sxs-lookup"><span data-stu-id="13ecd-104">If you don't want to use default Call Park settings, you can customize them.</span></span> <span data-ttu-id="13ecd-105">当您安装呼叫寄存应用程序时，默认情况下会配置全局设置。</span><span class="sxs-lookup"><span data-stu-id="13ecd-105">When you install the Call Park application, global settings are configured by default.</span></span> <span data-ttu-id="13ecd-106">您可以修改全局设置，也可以指定特定于站点的设置。</span><span class="sxs-lookup"><span data-stu-id="13ecd-106">You can modify the global settings, and you can also specify site-specific settings.</span></span> <span data-ttu-id="13ecd-107">使用 **New-CsCpsConfiguration** cmdlet 可创建新的特定于站点的设置。</span><span class="sxs-lookup"><span data-stu-id="13ecd-107">Use the **New-CsCpsConfiguration** cmdlet to create new site-specific settings.</span></span> <span data-ttu-id="13ecd-108">使用 **Set-CsCpsConfiguration** cmdlet 可修改现有设置。</span><span class="sxs-lookup"><span data-stu-id="13ecd-108">Use the **Set-CsCpsConfiguration** cmdlet to modify existing settings.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="13ecd-109">寄存呼叫超时且回拨失败时，我们建议您至少为要使用的回退目标配置 <STRONG>OnTimeoutURI</STRONG> 选项。</span><span class="sxs-lookup"><span data-stu-id="13ecd-109">At a minimum, we recommend that you configure the <STRONG>OnTimeoutURI</STRONG> option for the fallback destination to use when a parked call times out and ringback fails.</span></span>



</div>

<span data-ttu-id="13ecd-110">使用 **New-CsCpsConfiguration** cmdlet 或 **Set-CsCpsConfiguration** cmdlet 配置以下任何设置：</span><span class="sxs-lookup"><span data-stu-id="13ecd-110">Use **New-CsCpsConfiguration** cmdlet or the **Set-CsCpsConfiguration** cmdlet to configure any of the following settings:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="13ecd-111">此选项：</span><span class="sxs-lookup"><span data-stu-id="13ecd-111">This option:</span></span></th>
<th><span data-ttu-id="13ecd-112">指定以下内容：</span><span class="sxs-lookup"><span data-stu-id="13ecd-112">Specifies this:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="13ecd-113"><strong>CallPickupTimeoutThreshold</strong></span><span class="sxs-lookup"><span data-stu-id="13ecd-113"><strong>CallPickupTimeoutThreshold</strong></span></span></p></td>
<td><p><span data-ttu-id="13ecd-114">呼叫寄存后到回拨此前应答呼叫的电话之前等待的时间。</span><span class="sxs-lookup"><span data-stu-id="13ecd-114">The amount of time that elapses after a call has been parked before it rings back to the phone where the call was answered.</span></span></p>
<p><span data-ttu-id="13ecd-p102">该值必须采用 hh:mm:ss 的格式输入，以便指定小时数、分钟数和秒数。最小值为 10 秒，最大值为 10 分钟。默认值为 00:01:30。</span><span class="sxs-lookup"><span data-stu-id="13ecd-p102">The value must be entered in the format hh:mm:ss to specify the hours, minutes, and seconds. The minimum value is 10 seconds, and the maximum value is 10 minutes. The default is 00:01:30.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="13ecd-118"><strong>EnableMusicOnHold</strong></span><span class="sxs-lookup"><span data-stu-id="13ecd-118"><strong>EnableMusicOnHold</strong></span></span></p></td>
<td><p><span data-ttu-id="13ecd-119">寄存呼叫时是否向呼叫者播放音乐。</span><span class="sxs-lookup"><span data-stu-id="13ecd-119">Whether music plays for a caller while a call is parked.</span></span></p>
<p><span data-ttu-id="13ecd-p103">值为 True 或 False。默认值为 True。</span><span class="sxs-lookup"><span data-stu-id="13ecd-p103">Values are True or False. The default is True.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="13ecd-122"><strong>MaxCallPickupAttempts</strong></span><span class="sxs-lookup"><span data-stu-id="13ecd-122"><strong>MaxCallPickupAttempts</strong></span></span></p></td>
<td><p><span data-ttu-id="13ecd-p104">在将寄存呼叫转接到为 <strong>OnTimeoutURI</strong> 指定的回退统一资源标识符 (URI) 之前该寄存呼叫回拨应答电话的次数。默认值为 1。</span><span class="sxs-lookup"><span data-stu-id="13ecd-p104">The number of times a parked call rings back to the answering phone before it is forwarded to the fallback Uniform Resource Identifier (URI) that is specified for <strong>OnTimeoutURI</strong>. The default is 1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="13ecd-125"><strong>OnTimeoutURI</strong></span><span class="sxs-lookup"><span data-stu-id="13ecd-125"><strong>OnTimeoutURI</strong></span></span></p></td>
<td><p><span data-ttu-id="13ecd-126">超出 <strong>MaxCallPickupAttempts</strong> 时未应答的寄存呼叫将路由到的用户或响应组的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="13ecd-126">The SIP address of the user or response group to which an unanswered parked call is routed when <strong>MaxCallPickupAttempts</strong> is exceeded.</span></span></p>
<p><span data-ttu-id="13ecd-p105">值必须为以字符串 sip: 开头的 SIP URI。例如，sip:bob@contoso.com。默认情况下没有转接地址。</span><span class="sxs-lookup"><span data-stu-id="13ecd-p105">Value must be a SIP URI beginning with the string sip:. For example, sip:bob@contoso.com. The default is no forwarding address.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-call-park-settings"></a><span data-ttu-id="13ecd-130">配置呼叫寄存设置</span><span class="sxs-lookup"><span data-stu-id="13ecd-130">To configure Call Park settings</span></span>

1.  <span data-ttu-id="13ecd-131">登录到安装了 Lync Server 命令行管理程序的计算机，作为 RTCUniversalServerAdmins 组的成员或具有必要的用户权限（如在[Lync Server 2013 中委派安装权限](lync-server-2013-delegate-setup-permissions.md)中所述）。</span><span class="sxs-lookup"><span data-stu-id="13ecd-131">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="13ecd-132">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="13ecd-132">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="13ecd-133">以</span><span class="sxs-lookup"><span data-stu-id="13ecd-133">Run:</span></span>
    
        New-CsCpsConfiguration -Identity site:<sitename to apply settings> [-CallPickupTimeoutThreshold <hh:mm:ss>] -[EnableMusicOnHold <$true | $false>] [-MaxCallPickupAttempts <number of rings>] [-OnTimeoutURI sip:<sip URI for routing unanswered call>]
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="13ecd-134">使用 <STRONG>Get-CsSite</STRONG> cmdlet 可标识站点。</span><span class="sxs-lookup"><span data-stu-id="13ecd-134">Use the <STRONG>Get-CsSite</STRONG> cmdlet to identify the site.</span></span> <span data-ttu-id="13ecd-135">有关详细信息，请参阅 Lync Server 命令行管理程序文档。</span><span class="sxs-lookup"><span data-stu-id="13ecd-135">For details, see Lync Server Management Shell documentation.</span></span>

    
    </div>
    
    <span data-ttu-id="13ecd-136">例如：</span><span class="sxs-lookup"><span data-stu-id="13ecd-136">For example:</span></span>
    
        New-CsCpsConfiguration -Identity site:Redmond1 -CallPickupTimeoutThreshold 00:01:00 -EnableMusicOnHold $false -MaxCallPickupAttempts 2 -OnTimeoutURI sip:bob@contoso.com

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="13ecd-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="13ecd-137">See Also</span></span>


[<span data-ttu-id="13ecd-138">在 Lync Server 2013 中自定义呼叫寄存暂停音乐</span><span class="sxs-lookup"><span data-stu-id="13ecd-138">Customize Call Park music on hold in Lync Server 2013</span></span>](lync-server-2013-customize-call-park-music-on-hold.md)  


[<span data-ttu-id="13ecd-139">新 CsCpsConfiguration</span><span class="sxs-lookup"><span data-stu-id="13ecd-139">New-CsCpsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsCpsConfiguration)  
[<span data-ttu-id="13ecd-140">CsCpsConfiguration</span><span class="sxs-lookup"><span data-stu-id="13ecd-140">Set-CsCpsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCpsConfiguration)  
[<span data-ttu-id="13ecd-141">Get-cssite</span><span class="sxs-lookup"><span data-stu-id="13ecd-141">Get-CsSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsSite)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

