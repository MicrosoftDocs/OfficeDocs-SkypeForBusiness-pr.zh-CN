---
title: Lync Server 2013：配置公共提供商的媒体加密
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure media encryption for public providers
ms:assetid: a95814cf-c5a9-4652-8ffc-c469a2653153
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205149(v=OCS.15)
ms:contentKeyID: 48185036
ms.date: 12/13/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1496bda01456593066efd212241e3d930f1e2cc6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837348"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-media-encryption-for-public-providers-in-lync-server-2013"></a><span data-ttu-id="43573-102">在 Lync Server 2013 中配置公共提供商的媒体加密</span><span class="sxs-lookup"><span data-stu-id="43573-102">Configure media encryption for public providers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="43573-103">_**主题上次修改时间:** 2014-12-12_</span><span class="sxs-lookup"><span data-stu-id="43573-103">_**Topic Last Modified:** 2014-12-12_</span></span>

<span data-ttu-id="43573-104">如果你使用 Windows Live Messenger 实现音频/视频 (A/V) 联合, 则需要修改两个参数: Lync Server 加密级别和 EnablePublicCloudAccess 策略。</span><span class="sxs-lookup"><span data-stu-id="43573-104">If you are implementing audio/video (A/V) federation with Windows Live Messenger, there are two parameters that you need to modify: the Lync Server encryption level and the EnablePublicCloudAccess policy.</span></span> <span data-ttu-id="43573-105">默认情况下, 加密级别设置为 "必需"。</span><span class="sxs-lookup"><span data-stu-id="43573-105">By default, the encryption level is set to Required.</span></span> <span data-ttu-id="43573-106">必须将此设置更改为 "支持"。</span><span class="sxs-lookup"><span data-stu-id="43573-106">You must change this setting to Supported.</span></span> <span data-ttu-id="43573-107">如果 EnablePublicCloudAccess 策略设置为 false, 则需要将其设置为**True**。</span><span class="sxs-lookup"><span data-stu-id="43573-107">If the EnablePublicCloudAccess policy is set to false, this needs to be set to **True**.</span></span> <span data-ttu-id="43573-108">你可以从 Lync Server 命令行管理程序中执行此操作。</span><span class="sxs-lookup"><span data-stu-id="43573-108">You can do this from the Lync Server Management Shell.</span></span>

<div>

## <a name="configure-federation-for-windows-live"></a><span data-ttu-id="43573-109">为 Windows Live 配置联合</span><span class="sxs-lookup"><span data-stu-id="43573-109">Configure Federation for Windows Live</span></span>

1.  <span data-ttu-id="43573-110">在前端服务器上启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management Shell**"。</span><span class="sxs-lookup"><span data-stu-id="43573-110">Start the Lync Server Management Shell on the Front End server: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="43573-111">在命令提示符处, 键入以下命令:</span><span class="sxs-lookup"><span data-stu-id="43573-111">From the command prompt, type the following commands:</span></span>
    
       ```
        Set-CsMediaConfiguration -EncryptionLevel SupportEncryption
       ```
    
       ```
        Set-CsExternalAccessPolicy Global -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
       ```
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="43573-112">这是必需的步骤, 因为 Windows Live Messenger 不支持音频/视频加密。</span><span class="sxs-lookup"><span data-stu-id="43573-112">This is required step because Windows Live Messenger does not support encryption of audio/video.</span></span> <span data-ttu-id="43573-113">该命令将你的全局策略设置为支持加密设置, 而不是需要加密音频/视频数据。</span><span class="sxs-lookup"><span data-stu-id="43573-113">The command sets your global policy to a support encryption setting instead of requiring encryption of the audio/video data.</span></span> <span data-ttu-id="43573-114">支持加密的客户仍将使用加密, 如 Lync 2013。</span><span class="sxs-lookup"><span data-stu-id="43573-114">Clients that support encryption will still use encryption, such as Lync 2013.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

