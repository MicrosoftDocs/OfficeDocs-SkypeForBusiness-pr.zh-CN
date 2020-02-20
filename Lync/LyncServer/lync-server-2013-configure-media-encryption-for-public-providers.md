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
ms.openlocfilehash: 571aa8309ee310353adebecfc7b8fe737076b384
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153744"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-media-encryption-for-public-providers-in-lync-server-2013"></a><span data-ttu-id="7af3c-102">在 Lync Server 2013 中为公用提供程序配置媒体加密</span><span class="sxs-lookup"><span data-stu-id="7af3c-102">Configure media encryption for public providers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7af3c-103">_**上次修改的主题：** 2014-12-12_</span><span class="sxs-lookup"><span data-stu-id="7af3c-103">_**Topic Last Modified:** 2014-12-12_</span></span>

<span data-ttu-id="7af3c-104">如果要实现与 Windows Live Messenger 的音频/视频（A/V）联合，则需要修改两个参数： Lync Server 加密级别和 EnablePublicCloudAccess 策略。</span><span class="sxs-lookup"><span data-stu-id="7af3c-104">If you are implementing audio/video (A/V) federation with Windows Live Messenger, there are two parameters that you need to modify: the Lync Server encryption level and the EnablePublicCloudAccess policy.</span></span> <span data-ttu-id="7af3c-105">默认情况下，加密级别为“必需”。</span><span class="sxs-lookup"><span data-stu-id="7af3c-105">By default, the encryption level is set to Required.</span></span> <span data-ttu-id="7af3c-106">必须将此设置更改为“支持”。</span><span class="sxs-lookup"><span data-stu-id="7af3c-106">You must change this setting to Supported.</span></span> <span data-ttu-id="7af3c-107">如果 nablePublicCloudAccess 策略设置为 False，则需要将其设置为“True”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7af3c-107">If the EnablePublicCloudAccess policy is set to false, this needs to be set to **True**.</span></span> <span data-ttu-id="7af3c-108">您可以从 Lync Server 命令行管理程序中执行此操作。</span><span class="sxs-lookup"><span data-stu-id="7af3c-108">You can do this from the Lync Server Management Shell.</span></span>

<div>

## <a name="configure-federation-for-windows-live"></a><span data-ttu-id="7af3c-109">为 Windows Live 配置联合</span><span class="sxs-lookup"><span data-stu-id="7af3c-109">Configure Federation for Windows Live</span></span>

1.  <span data-ttu-id="7af3c-110">在前端服务器上启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management Shell**"。</span><span class="sxs-lookup"><span data-stu-id="7af3c-110">Start the Lync Server Management Shell on the Front End server: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="7af3c-111">从命令提示符处，键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="7af3c-111">From the command prompt, type the following commands:</span></span>
    
       ```powershell
        Set-CsMediaConfiguration -EncryptionLevel SupportEncryption
       ```
    
       ```powershell
        Set-CsExternalAccessPolicy Global -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
       ```
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="7af3c-112">上述步骤是必需步骤，因为 Windows Live Messenger 不支持音频/视频加密。</span><span class="sxs-lookup"><span data-stu-id="7af3c-112">This is required step because Windows Live Messenger does not support encryption of audio/video.</span></span> <span data-ttu-id="7af3c-113">该命令会将您的全局策略设置为支持加密设置，而不会设置为要求音频/视频数据加密。</span><span class="sxs-lookup"><span data-stu-id="7af3c-113">The command sets your global policy to a support encryption setting instead of requiring encryption of the audio/video data.</span></span> <span data-ttu-id="7af3c-114">支持加密的客户端仍将使用加密，如 Lync 2013。</span><span class="sxs-lookup"><span data-stu-id="7af3c-114">Clients that support encryption will still use encryption, such as Lync 2013.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

