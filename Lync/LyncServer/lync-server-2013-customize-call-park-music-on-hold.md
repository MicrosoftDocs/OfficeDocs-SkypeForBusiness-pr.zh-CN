---
title: Lync Server 2013：自定义呼叫寄存音乐暂候
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
ms.openlocfilehash: 301625a36d23c69d02dfdcde8c4985def53630af
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728752"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="customize-call-park-music-on-hold-in-lync-server-2013"></a><span data-ttu-id="0c5f7-102">在 Lync Server 2013 中自定义呼叫寄存音乐处于暂停状态</span><span class="sxs-lookup"><span data-stu-id="0c5f7-102">Customize Call Park music on hold in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0c5f7-103">_**主题上次修改时间：** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="0c5f7-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="0c5f7-104">你可以指定自己的音乐文件用于保留音乐，而不是 Lync Server 2013 附带的默认音乐文件。</span><span class="sxs-lookup"><span data-stu-id="0c5f7-104">You can specify your own music file to use for music on hold, instead of the default music file that ships with Lync Server 2013.</span></span> <span data-ttu-id="0c5f7-105">若要自定义保留音乐，请使用 **Set-CsCallParkServiceMusicOnHoldFile** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0c5f7-105">To customize music on hold, use the **Set-CsCallParkServiceMusicOnHoldFile** cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0c5f7-106">如果你自定义暂停的音乐并希望同一音乐用于多个网站，则必须为运行呼叫驻留应用程序的每个网站配置音乐文件。</span><span class="sxs-lookup"><span data-stu-id="0c5f7-106">If you customize music on hold and want the same music for multiple sites, you must configure the music file for each site that runs the Call Park application.</span></span>



</div>

<div>

## <a name="to-customize-the-music-file"></a><span data-ttu-id="0c5f7-107">自定义音乐文件</span><span class="sxs-lookup"><span data-stu-id="0c5f7-107">To customize the music file</span></span>

1.  <span data-ttu-id="0c5f7-108">以 RTCUniversalServerAdmins 组成员的身份或必要的用户权限登录到安装了 Lync Server 管理外壳的计算机，如在[Lync Server 2013 中的 "委派设置权限](lync-server-2013-delegate-setup-permissions.md)" 中所述。</span><span class="sxs-lookup"><span data-stu-id="0c5f7-108">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="0c5f7-109">启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="0c5f7-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="0c5f7-110">运行：</span><span class="sxs-lookup"><span data-stu-id="0c5f7-110">Run:</span></span>
    
        Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte[]>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="0c5f7-111">使用 <STRONG>Get-CsService</STRONG> cmdlet 可标识服务。</span><span class="sxs-lookup"><span data-stu-id="0c5f7-111">Use the <STRONG>Get-CsService</STRONG> cmdlet to identify the service.</span></span> <span data-ttu-id="0c5f7-112">有关详细信息，请参阅<A href="https://docs.microsoft.com/powershell/module/skype/Get-CsService">CsService</A>。</span><span class="sxs-lookup"><span data-stu-id="0c5f7-112">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsService">Get-CsService</A>.</span></span>

    
    </div>
    
    <span data-ttu-id="0c5f7-113">以下示例说明了如何以字节数组的形式获取文件 soothingmusic.wma 的内容并将其分配给变量。</span><span class="sxs-lookup"><span data-stu-id="0c5f7-113">The following example shows how to obtain the contents of a file, soothingmusic.wma, as a byte array and assign it to a variable.</span></span> <span data-ttu-id="0c5f7-114">然后，将音频文件指定为呼叫寄存的保留音乐文件。</span><span class="sxs-lookup"><span data-stu-id="0c5f7-114">Then the audio file is assigned as the music-on-hold file for Call Park.</span></span> <span data-ttu-id="0c5f7-115">有关详细信息，请参阅[Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkServiceMusicOnHoldFile)。</span><span class="sxs-lookup"><span data-stu-id="0c5f7-115">For details, see [Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkServiceMusicOnHoldFile).</span></span>
    
        $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
        Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0c5f7-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0c5f7-116">See Also</span></span>


[<span data-ttu-id="0c5f7-117">Set-CsCallParkServiceMusicOnHoldFile</span><span class="sxs-lookup"><span data-stu-id="0c5f7-117">Set-CsCallParkServiceMusicOnHoldFile</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkServiceMusicOnHoldFile)  
[<span data-ttu-id="0c5f7-118">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="0c5f7-118">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

