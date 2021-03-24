---
title: 在Skype for Business 中自定义呼叫等待音乐
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3d78e6f9-a4ae-49f4-a89f-4515acb49dac
description: 在 Skype for Business Server 企业语音 中自定义呼叫企业语音。
ms.openlocfilehash: 87dea58d9e339293b047373ac6c44a16bed3bdb3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093040"
---
# <a name="customize-call-park-music-on-hold-inskype-for-business"></a><span data-ttu-id="0436c-103">在Skype for Business 中自定义呼叫等待音乐</span><span class="sxs-lookup"><span data-stu-id="0436c-103">Customize Call Park music on hold inSkype for Business</span></span>
 
<span data-ttu-id="0436c-104">在 Skype for Business Server 企业语音 中自定义呼叫企业语音。</span><span class="sxs-lookup"><span data-stu-id="0436c-104">Customize the Call Park music on hold in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="0436c-105">你可以指定要用于保持音乐的你自己的音乐文件，而不是 Skype for Business Server 附带的默认音乐文件。</span><span class="sxs-lookup"><span data-stu-id="0436c-105">You can specify your own music file to use for music on hold, instead of the default music file that ships with Skype for Business Server.</span></span> <span data-ttu-id="0436c-106">若要自定义保留音乐，请使用 **Set-CsCallParkServiceMusicOnHoldFile** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0436c-106">To customize music on hold, use the **Set-CsCallParkServiceMusicOnHoldFile** cmdlet.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0436c-107">如果自定义保持音乐，并且希望多个站点具有相同的音乐，则必须为运行呼叫保留应用程序的每个站点配置音乐文件。</span><span class="sxs-lookup"><span data-stu-id="0436c-107">If you customize music on hold and want the same music for multiple sites, you must configure the music file for each site that runs the Call Park application.</span></span> 
  
### <a name="to-customize-the-music-file"></a><span data-ttu-id="0436c-108">自定义音乐文件</span><span class="sxs-lookup"><span data-stu-id="0436c-108">To customize the music file</span></span>

1. <span data-ttu-id="0436c-109">以 RTCUniversalServerAdmins 组的成员或委派安装权限中所述的必要用户权限登录到安装了 Skype for Business Server 命令行管理程序 **的计算机**。</span><span class="sxs-lookup"><span data-stu-id="0436c-109">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="0436c-110">启动 Skype for Business Server命令行管理程序：单击"开始"，单击"所有程序"，单击 **"Skype for Business 2015"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**</span><span class="sxs-lookup"><span data-stu-id="0436c-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="0436c-111">运行：</span><span class="sxs-lookup"><span data-stu-id="0436c-111">Run:</span></span>
    
   ```powershell
   Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte >
   ```

    > [!TIP]
    > <span data-ttu-id="0436c-112">使用 **Get-CsService** cmdlet 可标识服务。</span><span class="sxs-lookup"><span data-stu-id="0436c-112">Use the **Get-CsService** cmdlet to identify the service.</span></span> <span data-ttu-id="0436c-113">有关详细信息，请参阅[Get-CsService。](/powershell/module/skype/get-csservice?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="0436c-113">For details, see [Get-CsService](/powershell/module/skype/get-csservice?view=skype-ps).</span></span> 
  
    <span data-ttu-id="0436c-114">以下示例说明了如何以字节数组的形式获取文件 soothingmusic.wma 的内容并将其分配给变量。</span><span class="sxs-lookup"><span data-stu-id="0436c-114">The following example shows how to obtain the contents of a file, soothingmusic.wma, as a byte array and assign it to a variable.</span></span> <span data-ttu-id="0436c-115">然后，将音频文件指定为呼叫寄存的保留音乐文件。</span><span class="sxs-lookup"><span data-stu-id="0436c-115">Then the audio file is assigned as the music-on-hold file for Call Park.</span></span> <span data-ttu-id="0436c-116">有关详细信息，请参阅 [Set-CsCallParkServiceMusicOnHoldFile](/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="0436c-116">For details, see [Set-CsCallParkServiceMusicOnHoldFile](/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps).</span></span>
    
   ```powershell
   $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
   Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a
   ```

## <a name="see-also"></a><span data-ttu-id="0436c-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0436c-117">See also</span></span>

[<span data-ttu-id="0436c-118">Set-CsCallParkServiceMusicOnHoldFile</span><span class="sxs-lookup"><span data-stu-id="0436c-118">Set-CsCallParkServiceMusicOnHoldFile</span></span>](/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)
  
[<span data-ttu-id="0436c-119">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="0436c-119">Get-CsService</span></span>](/powershell/module/skype/get-csservice?view=skype-ps)