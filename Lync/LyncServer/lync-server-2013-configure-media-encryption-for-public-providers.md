---
title: Lync Server 2013：为公用提供程序配置媒体加密
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure media encryption for public providers
ms:assetid: a95814cf-c5a9-4652-8ffc-c469a2653153
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205149(v=OCS.15)
ms:contentKeyID: 48185036
ms.date: 12/13/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 73d914e77f5ae53e5b7e22cdc3392fe6bc22ef64
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42179899"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-media-encryption-for-public-providers-in-lync-server-2013"></a><span data-ttu-id="9932f-102">在 Lync Server 2013 中为公用提供程序配置媒体加密</span><span class="sxs-lookup"><span data-stu-id="9932f-102">Configure media encryption for public providers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9932f-103">_**上次修改的主题：** 2014-12-12_</span><span class="sxs-lookup"><span data-stu-id="9932f-103">_**Topic Last Modified:** 2014-12-12_</span></span>

<span data-ttu-id="9932f-104">如果要实现与 Windows Live Messenger 的音频/视频（A/V）联合，则需要修改两个参数： Lync Server 加密级别和 EnablePublicCloudAccess 策略。</span><span class="sxs-lookup"><span data-stu-id="9932f-104">If you are implementing audio/video (A/V) federation with Windows Live Messenger, there are two parameters that you need to modify: the Lync Server encryption level and the EnablePublicCloudAccess policy.</span></span> <span data-ttu-id="9932f-105">默认情况下，加密级别为“必需”。</span><span class="sxs-lookup"><span data-stu-id="9932f-105">By default, the encryption level is set to Required.</span></span> <span data-ttu-id="9932f-106">必须将此设置更改为“支持”。</span><span class="sxs-lookup"><span data-stu-id="9932f-106">You must change this setting to Supported.</span></span> <span data-ttu-id="9932f-107">如果 nablePublicCloudAccess 策略设置为 False，则需要将其设置为“True”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9932f-107">If the EnablePublicCloudAccess policy is set to false, this needs to be set to **True**.</span></span> <span data-ttu-id="9932f-108">您可以从 Lync Server 命令行管理程序中执行此操作。</span><span class="sxs-lookup"><span data-stu-id="9932f-108">You can do this from the Lync Server Management Shell.</span></span>

<div>

## <a name="configure-federation-for-windows-live"></a><span data-ttu-id="9932f-109">为 Windows Live 配置联合</span><span class="sxs-lookup"><span data-stu-id="9932f-109">Configure Federation for Windows Live</span></span>

1.  <span data-ttu-id="9932f-110">在前端服务器上启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management Shell**"。</span><span class="sxs-lookup"><span data-stu-id="9932f-110">Start the Lync Server Management Shell on the Front End server: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="9932f-111">从命令提示符处，键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="9932f-111">From the command prompt, type the following commands:</span></span>
    
       ```powershell
        Set-CsMediaConfiguration -EncryptionLevel SupportEncryption
       ```
    
       ```powershell
        Set-CsExternalAccessPolicy Global -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
       ```
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="9932f-112">上述步骤是必需步骤，因为 Windows Live Messenger 不支持音频/视频加密。</span><span class="sxs-lookup"><span data-stu-id="9932f-112">This is required step because Windows Live Messenger does not support encryption of audio/video.</span></span> <span data-ttu-id="9932f-113">该命令会将您的全局策略设置为支持加密设置，而不会设置为要求音频/视频数据加密。</span><span class="sxs-lookup"><span data-stu-id="9932f-113">The command sets your global policy to a support encryption setting instead of requiring encryption of the audio/video data.</span></span> <span data-ttu-id="9932f-114">支持加密的客户端仍将使用加密，如 Lync 2013。</span><span class="sxs-lookup"><span data-stu-id="9932f-114">Clients that support encryption will still use encryption, such as Lync 2013.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

