---
title: 在 Skype for Business 2015 中自定义呼叫寄存保持音乐
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 3d78e6f9-a4ae-49f4-a89f-4515acb49dac
description: 自定义音乐上的停留在 Skype 业务服务器企业语音调用公园。
ms.openlocfilehash: 5af98ee95c59f7fd945232f77d713255ca1c42d5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="customize-call-park-music-on-hold-inskype-for-business-2015"></a><span data-ttu-id="35e2c-103">在 Skype for Business 2015 中自定义呼叫寄存保持音乐</span><span class="sxs-lookup"><span data-stu-id="35e2c-103">Customize Call Park music on hold inSkype for Business 2015</span></span>
 
<span data-ttu-id="35e2c-104">自定义音乐上的停留在 Skype 业务服务器企业语音调用公园。</span><span class="sxs-lookup"><span data-stu-id="35e2c-104">Customize the Call Park music on hold in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="35e2c-105">您可以指定您自己的音乐文件用于处于等待状态，而不是默认的音乐文件附带 Skype 业务服务器的音乐。</span><span class="sxs-lookup"><span data-stu-id="35e2c-105">You can specify your own music file to use for music on hold, instead of the default music file that ships with Skype for Business Server.</span></span> <span data-ttu-id="35e2c-106">若要自定义音乐候，使用**集 CsCallParkServiceMusicOnHoldFile** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="35e2c-106">To customize music on hold, use the **Set-CsCallParkServiceMusicOnHoldFile** cmdlet.</span></span>
  
> [!NOTE]
> <span data-ttu-id="35e2c-107">如果您自定义音乐候，并用于多个站点需要相同的音乐，必须配置为运行应用程序调用公园每个站点的音乐文件。</span><span class="sxs-lookup"><span data-stu-id="35e2c-107">If you customize music on hold and want the same music for multiple sites, you must configure the music file for each site that runs the Call Park application.</span></span> 
  
### <a name="to-customize-the-music-file"></a><span data-ttu-id="35e2c-108">自定义音乐文件</span><span class="sxs-lookup"><span data-stu-id="35e2c-108">To customize the music file</span></span>

1. <span data-ttu-id="35e2c-109">登录到业务服务器管理外壳的 Skype 为成员的 RTCUniversalServerAdmins 组或**委托安装程序权限**中所述的必要的用户权限的安装位置的计算机上。</span><span class="sxs-lookup"><span data-stu-id="35e2c-109">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="35e2c-110">启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。</span><span class="sxs-lookup"><span data-stu-id="35e2c-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="35e2c-111">运行：</span><span class="sxs-lookup"><span data-stu-id="35e2c-111">Run:</span></span>
    
   ```
   Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte >
   ```

    > [!TIP]
    > <span data-ttu-id="35e2c-112">使用**Get CsService** cmdlet 来标识服务。</span><span class="sxs-lookup"><span data-stu-id="35e2c-112">Use the **Get-CsService** cmdlet to identify the service.</span></span> <span data-ttu-id="35e2c-113">有关详细信息，请参阅[获取 CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="35e2c-113">For details, see [Get-CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps).</span></span> 
  
    <span data-ttu-id="35e2c-114">以下示例说明了如何以字节数组的形式获取文件 soothingmusic.wma 的内容并将其分配给变量。</span><span class="sxs-lookup"><span data-stu-id="35e2c-114">The following example shows how to obtain the contents of a file, soothingmusic.wma, as a byte array and assign it to a variable.</span></span> <span data-ttu-id="35e2c-115">然后，将音频文件指定为呼叫寄存的保留音乐文件。</span><span class="sxs-lookup"><span data-stu-id="35e2c-115">Then the audio file is assigned as the music-on-hold file for Call Park.</span></span> <span data-ttu-id="35e2c-116">有关详细信息，请参阅[设置 CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="35e2c-116">For details, see [Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps).</span></span>
    
   ```
   $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
   Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a
   ```

## <a name="see-also"></a><span data-ttu-id="35e2c-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="35e2c-117">See also</span></span>

#### 

[<span data-ttu-id="35e2c-118">一组 CsCallParkServiceMusicOnHoldFile</span><span class="sxs-lookup"><span data-stu-id="35e2c-118">Set-CsCallParkServiceMusicOnHoldFile</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cscallparkservicemusiconholdfile?view=skype-ps)
  
[<span data-ttu-id="35e2c-119">获得 CsService</span><span class="sxs-lookup"><span data-stu-id="35e2c-119">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps)

