---
title: Lync Server 2013：为公用提供程序配置媒体加密
description: Lync Server 2013：为公用提供程序配置媒体加密。
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
ms.openlocfilehash: 177c19f151b67d741c7e26506f7ebc98b3ce831a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577618"
---
# <a name="configure-media-encryption-for-public-providers-in-lync-server-2013"></a><span data-ttu-id="8fd0e-103">在 Lync Server 2013 中为公用提供程序配置媒体加密</span><span class="sxs-lookup"><span data-stu-id="8fd0e-103">Configure media encryption for public providers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8fd0e-104">_**上次修改的主题：** 2014-12-12_</span><span class="sxs-lookup"><span data-stu-id="8fd0e-104">_**Topic Last Modified:** 2014-12-12_</span></span>

<span data-ttu-id="8fd0e-105">如果要使用 Windows Live Messenger 实现音频/视频 (A/V) 联盟，则需要修改两个参数： Lync Server 加密级别和 EnablePublicCloudAccess 策略。</span><span class="sxs-lookup"><span data-stu-id="8fd0e-105">If you are implementing audio/video (A/V) federation with Windows Live Messenger, there are two parameters that you need to modify: the Lync Server encryption level and the EnablePublicCloudAccess policy.</span></span> <span data-ttu-id="8fd0e-106">默认情况下，加密级别为“必需”。</span><span class="sxs-lookup"><span data-stu-id="8fd0e-106">By default, the encryption level is set to Required.</span></span> <span data-ttu-id="8fd0e-107">必须将此设置更改为“支持”。</span><span class="sxs-lookup"><span data-stu-id="8fd0e-107">You must change this setting to Supported.</span></span> <span data-ttu-id="8fd0e-108">如果 nablePublicCloudAccess 策略设置为 False，则需要将其设置为“True”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8fd0e-108">If the EnablePublicCloudAccess policy is set to false, this needs to be set to **True**.</span></span> <span data-ttu-id="8fd0e-109">您可以从 Lync Server 命令行管理程序中执行此操作。</span><span class="sxs-lookup"><span data-stu-id="8fd0e-109">You can do this from the Lync Server Management Shell.</span></span>

<div>

## <a name="configure-federation-for-windows-live"></a><span data-ttu-id="8fd0e-110">为 Windows Live 配置联合</span><span class="sxs-lookup"><span data-stu-id="8fd0e-110">Configure Federation for Windows Live</span></span>

1.  <span data-ttu-id="8fd0e-111">在前端服务器上启动 Lync Server 命令行管理程序：依次单击 " **开始**"、" **所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management Shell**"。</span><span class="sxs-lookup"><span data-stu-id="8fd0e-111">Start the Lync Server Management Shell on the Front End server: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="8fd0e-112">从命令提示符处，键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="8fd0e-112">From the command prompt, type the following commands:</span></span>
    
       ```powershell
        Set-CsMediaConfiguration -EncryptionLevel SupportEncryption
       ```
    
       ```powershell
        Set-CsExternalAccessPolicy Global -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
       ```
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="8fd0e-113">上述步骤是必需步骤，因为 Windows Live Messenger 不支持音频/视频加密。</span><span class="sxs-lookup"><span data-stu-id="8fd0e-113">This is required step because Windows Live Messenger does not support encryption of audio/video.</span></span> <span data-ttu-id="8fd0e-114">该命令会将您的全局策略设置为支持加密设置，而不会设置为要求音频/视频数据加密。</span><span class="sxs-lookup"><span data-stu-id="8fd0e-114">The command sets your global policy to a support encryption setting instead of requiring encryption of the audio/video data.</span></span> <span data-ttu-id="8fd0e-115">支持加密的客户端仍将使用加密，如 Lync 2013。</span><span class="sxs-lookup"><span data-stu-id="8fd0e-115">Clients that support encryption will still use encryption, such as Lync 2013.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

