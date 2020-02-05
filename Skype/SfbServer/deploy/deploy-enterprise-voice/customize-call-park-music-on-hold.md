---
title: 自定义呼叫驻留 inSkype for Business 的暂停音乐
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 在 Skype for Business Server Enterprise Voice 中自定义呼叫寄存音乐处于暂候状态。
ms.openlocfilehash: 61c82a9ba6c817eb3c61e93ae28d76208855e089
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767735"
---
# <a name="customize-call-park-music-on-hold-inskype-for-business"></a><span data-ttu-id="dcc76-103">自定义呼叫驻留 inSkype for Business 的暂停音乐</span><span class="sxs-lookup"><span data-stu-id="dcc76-103">Customize Call Park music on hold inSkype for Business</span></span>
 
<span data-ttu-id="dcc76-104">在 Skype for Business Server Enterprise Voice 中自定义呼叫寄存音乐处于暂候状态。</span><span class="sxs-lookup"><span data-stu-id="dcc76-104">Customize the Call Park music on hold in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="dcc76-105">你可以将自己的音乐文件指定为保留音乐，而不是 Skype for Business 服务器随附的默认音乐文件。</span><span class="sxs-lookup"><span data-stu-id="dcc76-105">You can specify your own music file to use for music on hold, instead of the default music file that ships with Skype for Business Server.</span></span> <span data-ttu-id="dcc76-106">若要自定义保留音乐，请使用 **Set-CsCallParkServiceMusicOnHoldFile** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="dcc76-106">To customize music on hold, use the **Set-CsCallParkServiceMusicOnHoldFile** cmdlet.</span></span>
  
> [!NOTE]
> <span data-ttu-id="dcc76-107">如果你自定义暂停的音乐并希望同一音乐用于多个网站，则必须为运行呼叫驻留应用程序的每个网站配置音乐文件。</span><span class="sxs-lookup"><span data-stu-id="dcc76-107">If you customize music on hold and want the same music for multiple sites, you must configure the music file for each site that runs the Call Park application.</span></span> 
  
### <a name="to-customize-the-music-file"></a><span data-ttu-id="dcc76-108">自定义音乐文件</span><span class="sxs-lookup"><span data-stu-id="dcc76-108">To customize the music file</span></span>

1. <span data-ttu-id="dcc76-109">登录到将 Skype for Business Server Management Shell 作为 RTCUniversalServerAdmins 组的成员或必要的用户权限（如 "**委派设置权限**" 中所述）进行安装的计算机。</span><span class="sxs-lookup"><span data-stu-id="dcc76-109">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="dcc76-110">启动 Skype for Business Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\* 和“Skype for Business 2015”\*\*\*\*，然后单击“Skype for Business Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dcc76-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="dcc76-111">运行：</span><span class="sxs-lookup"><span data-stu-id="dcc76-111">Run:</span></span>
    
   ```powershell
   Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte >
   ```

    > [!TIP]
    > <span data-ttu-id="dcc76-112">使用 **Get-CsService** cmdlet 可标识服务。</span><span class="sxs-lookup"><span data-stu-id="dcc76-112">Use the **Get-CsService** cmdlet to identify the service.</span></span> <span data-ttu-id="dcc76-113">有关详细信息，请参阅[CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="dcc76-113">For details, see [Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps).</span></span> 
  
    <span data-ttu-id="dcc76-114">以下示例说明了如何以字节数组的形式获取文件 soothingmusic.wma 的内容并将其分配给变量。</span><span class="sxs-lookup"><span data-stu-id="dcc76-114">The following example shows how to obtain the contents of a file, soothingmusic.wma, as a byte array and assign it to a variable.</span></span> <span data-ttu-id="dcc76-115">然后，将音频文件指定为呼叫寄存的保留音乐文件。</span><span class="sxs-lookup"><span data-stu-id="dcc76-115">Then the audio file is assigned as the music-on-hold file for Call Park.</span></span> <span data-ttu-id="dcc76-116">有关详细信息，请参阅[Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="dcc76-116">For details, see [Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps).</span></span>
    
   ```powershell
   $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
   Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a
   ```

## <a name="see-also"></a><span data-ttu-id="dcc76-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dcc76-117">See also</span></span>

[<span data-ttu-id="dcc76-118">Set-CsCallParkServiceMusicOnHoldFile</span><span class="sxs-lookup"><span data-stu-id="dcc76-118">Set-CsCallParkServiceMusicOnHoldFile</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)
  
[<span data-ttu-id="dcc76-119">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="dcc76-119">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)
