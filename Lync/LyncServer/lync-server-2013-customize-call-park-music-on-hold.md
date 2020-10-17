---
title: Lync Server 2013：自定义呼叫寄存暂停音乐
description: Lync Server 2013：自定义呼叫寄存暂停音乐。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Customize Call Park music on hold
ms:assetid: 3d78e6f9-a4ae-49f4-a89f-4515acb49dac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688031(v=OCS.15)
ms:contentKeyID: 49733621
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 19219e4a77d4be4a18a43255e142339a4af6f463
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543998"
---
# <a name="customize-call-park-music-on-hold-in-lync-server-2013"></a><span data-ttu-id="bd389-103">在 Lync Server 2013 中自定义呼叫寄存暂停音乐</span><span class="sxs-lookup"><span data-stu-id="bd389-103">Customize Call Park music on hold in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bd389-104">_**上次修改的主题：** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="bd389-104">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="bd389-105">您可以指定自己的音乐文件以用于保留音乐，而不是 Lync Server 2013 附带的默认音乐文件。</span><span class="sxs-lookup"><span data-stu-id="bd389-105">You can specify your own music file to use for music on hold, instead of the default music file that ships with Lync Server 2013.</span></span> <span data-ttu-id="bd389-106">若要自定义保留音乐，请使用 **Set-CsCallParkServiceMusicOnHoldFile** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="bd389-106">To customize music on hold, use the **Set-CsCallParkServiceMusicOnHoldFile** cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bd389-107">如果你自定义保留的音乐并希望多个网站具有相同的音乐，则必须为运行呼叫寄存应用程序的每个网站配置音乐文件。</span><span class="sxs-lookup"><span data-stu-id="bd389-107">If you customize music on hold and want the same music for multiple sites, you must configure the music file for each site that runs the Call Park application.</span></span>



</div>

<div>

## <a name="to-customize-the-music-file"></a><span data-ttu-id="bd389-108">自定义音乐文件</span><span class="sxs-lookup"><span data-stu-id="bd389-108">To customize the music file</span></span>

1.  <span data-ttu-id="bd389-109">登录到安装了 Lync Server 命令行管理程序的计算机，作为 RTCUniversalServerAdmins 组的成员或具有必要的用户权限（如在 [Lync Server 2013 中委派安装权限](lync-server-2013-delegate-setup-permissions.md)中所述）。</span><span class="sxs-lookup"><span data-stu-id="bd389-109">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="bd389-110">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bd389-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="bd389-111">以</span><span class="sxs-lookup"><span data-stu-id="bd389-111">Run:</span></span>
    
        Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte[]>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="bd389-112">使用 <STRONG>Get-CsService</STRONG> cmdlet 可标识服务。</span><span class="sxs-lookup"><span data-stu-id="bd389-112">Use the <STRONG>Get-CsService</STRONG> cmdlet to identify the service.</span></span> <span data-ttu-id="bd389-113">有关详细信息，请参阅 <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsService">get-csservice</A>。</span><span class="sxs-lookup"><span data-stu-id="bd389-113">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsService">Get-CsService</A>.</span></span>

    
    </div>
    
    <span data-ttu-id="bd389-114">以下示例说明了如何以字节数组的形式获取文件 soothingmusic.wma 的内容并将其分配给变量。</span><span class="sxs-lookup"><span data-stu-id="bd389-114">The following example shows how to obtain the contents of a file, soothingmusic.wma, as a byte array and assign it to a variable.</span></span> <span data-ttu-id="bd389-115">然后，将音频文件指定为呼叫寄存的保留音乐文件。</span><span class="sxs-lookup"><span data-stu-id="bd389-115">Then the audio file is assigned as the music-on-hold file for Call Park.</span></span> <span data-ttu-id="bd389-116">有关详细信息，请参阅 [CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkServiceMusicOnHoldFile)。</span><span class="sxs-lookup"><span data-stu-id="bd389-116">For details, see [Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkServiceMusicOnHoldFile).</span></span>
    
        $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
        Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bd389-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bd389-117">See Also</span></span>


[<span data-ttu-id="bd389-118">CsCallParkServiceMusicOnHoldFile</span><span class="sxs-lookup"><span data-stu-id="bd389-118">Set-CsCallParkServiceMusicOnHoldFile</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkServiceMusicOnHoldFile)  
[<span data-ttu-id="bd389-119">Get-csservice</span><span class="sxs-lookup"><span data-stu-id="bd389-119">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

