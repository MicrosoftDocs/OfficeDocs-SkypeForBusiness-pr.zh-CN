---
title: 自定义业务保留 inSkype 的呼叫寄存音乐
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3d78e6f9-a4ae-49f4-a89f-4515acb49dac
description: 自定义音乐中 Skype 业务 Server 企业语音呼叫寄存。
ms.openlocfilehash: 261c3dac0926ca15240eb3c8a345d1a70fecdfb4
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23885113"
---
# <a name="customize-call-park-music-on-hold-inskype-for-business"></a><span data-ttu-id="8913a-103">自定义业务保留 inSkype 的呼叫寄存音乐</span><span class="sxs-lookup"><span data-stu-id="8913a-103">Customize Call Park music on hold inSkype for Business</span></span>
 
<span data-ttu-id="8913a-104">自定义音乐中 Skype 业务 Server 企业语音呼叫寄存。</span><span class="sxs-lookup"><span data-stu-id="8913a-104">Customize the Call Park music on hold in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="8913a-105">您可以指定您自己的音乐文件用于保持音乐，而不是业务服务器附带 Skype 的默认音乐文件。</span><span class="sxs-lookup"><span data-stu-id="8913a-105">You can specify your own music file to use for music on hold, instead of the default music file that ships with Skype for Business Server.</span></span> <span data-ttu-id="8913a-106">若要自定义保留音乐，请使用**Set-cscallparkservicemusiconholdfile** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8913a-106">To customize music on hold, use the **Set-CsCallParkServiceMusicOnHoldFile** cmdlet.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8913a-107">如果您自定义保留音乐并希望多个网站相同的音乐，则必须配置运行呼叫寄存应用程序的每个网站的音乐文件。</span><span class="sxs-lookup"><span data-stu-id="8913a-107">If you customize music on hold and want the same music for multiple sites, you must configure the music file for each site that runs the Call Park application.</span></span> 
  
### <a name="to-customize-the-music-file"></a><span data-ttu-id="8913a-108">自定义音乐文件</span><span class="sxs-lookup"><span data-stu-id="8913a-108">To customize the music file</span></span>

1. <span data-ttu-id="8913a-109">登录到计算机的业务 Server Management Shell 的 Skype 或使用**Delegate Setup Permissions**中所述的必要用户权限的 RTCUniversalServerAdmins 组成员身份的安装。</span><span class="sxs-lookup"><span data-stu-id="8913a-109">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="8913a-110">启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。</span><span class="sxs-lookup"><span data-stu-id="8913a-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="8913a-111">运行：</span><span class="sxs-lookup"><span data-stu-id="8913a-111">Run:</span></span>
    
   ```
   Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte >
   ```

    > [!TIP]
    > <span data-ttu-id="8913a-112">使用**Get-csservice** cmdlet 来标识服务。</span><span class="sxs-lookup"><span data-stu-id="8913a-112">Use the **Get-CsService** cmdlet to identify the service.</span></span> <span data-ttu-id="8913a-113">有关详细信息，请参阅[Get-csservice](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="8913a-113">For details, see [Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps).</span></span> 
  
    <span data-ttu-id="8913a-114">以下示例说明了如何以字节数组的形式获取文件 soothingmusic.wma 的内容并将其分配给变量。</span><span class="sxs-lookup"><span data-stu-id="8913a-114">The following example shows how to obtain the contents of a file, soothingmusic.wma, as a byte array and assign it to a variable.</span></span> <span data-ttu-id="8913a-115">然后，将音频文件指定为呼叫寄存的保留音乐文件。</span><span class="sxs-lookup"><span data-stu-id="8913a-115">Then the audio file is assigned as the music-on-hold file for Call Park.</span></span> <span data-ttu-id="8913a-116">有关详细信息，请参阅[Set-cscallparkservicemusiconholdfile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="8913a-116">For details, see [Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps).</span></span>
    
   ```
   $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
   Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a
   ```

## <a name="see-also"></a><span data-ttu-id="8913a-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8913a-117">See also</span></span>

[<span data-ttu-id="8913a-118">Set-cscallparkservicemusiconholdfile</span><span class="sxs-lookup"><span data-stu-id="8913a-118">Set-CsCallParkServiceMusicOnHoldFile</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)
  
[<span data-ttu-id="8913a-119">Get-csservice</span><span class="sxs-lookup"><span data-stu-id="8913a-119">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)