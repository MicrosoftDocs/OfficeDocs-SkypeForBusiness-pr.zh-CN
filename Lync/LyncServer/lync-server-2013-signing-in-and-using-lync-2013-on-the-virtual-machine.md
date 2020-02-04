---
title: Lync Server 2013：登录虚拟机并使用 Lync 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Signing in and using Lync 2013 on the virtual machine
ms:assetid: 6140fc19-5bef-4b58-9b0f-19112b5ecd00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204948(v=OCS.15)
ms:contentKeyID: 48184318
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 40c5c18c4e991c3b53e37e090e7f2d960a32f71c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732032"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="signing-in-and-using-lync-2013-on-the-virtual-machine"></a><span data-ttu-id="9cacb-102">登录虚拟机并使用 Lync 2013</span><span class="sxs-lookup"><span data-stu-id="9cacb-102">Signing in and using Lync 2013 on the virtual machine</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9cacb-103">_**主题上次修改时间：** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="9cacb-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="9cacb-104">启用 VDI 插件后，当用户登录到 Lync 2013 时，将发生以下步骤。</span><span class="sxs-lookup"><span data-stu-id="9cacb-104">After the VDI plug-in is enabled, the following steps occur when the user signs in to Lync 2013.</span></span>

1.  <span data-ttu-id="9cacb-105">用户在运行在虚拟机上的 Lync 2013 客户端中键入其凭据。</span><span class="sxs-lookup"><span data-stu-id="9cacb-105">The user types his or her credentials in to the Lync 2013 client running on the virtual machine.</span></span>

2.  <span data-ttu-id="9cacb-106">在 Lync 检测到 VDI 插件的可用性后，Lync 将提示用户重新输入其凭据。</span><span class="sxs-lookup"><span data-stu-id="9cacb-106">After Lync detects the availability of the VDI plug-in, Lync prompts the user to re-enter his or her credentials.</span></span> <span data-ttu-id="9cacb-107">在此对话框中，建议用户选中“**保存我的密码**”复选框以便后续登录期间不需要输入凭据。</span><span class="sxs-lookup"><span data-stu-id="9cacb-107">In this dialog box, we recommend that the user select the **Save my password** check box so that he or she will not be required to enter credentials during subsequent sign in.</span></span>

3.  <span data-ttu-id="9cacb-108">Lync 将通过 VDI 插件开始配对。</span><span class="sxs-lookup"><span data-stu-id="9cacb-108">Lync begins pairing with the VDI plug-in.</span></span> <span data-ttu-id="9cacb-109">配对完成之前，客户端将在 Lync 状态栏中显示两个图标。</span><span class="sxs-lookup"><span data-stu-id="9cacb-109">Before pairing is complete, the client displays two icons in the Lync status bar.</span></span> <span data-ttu-id="9cacb-110">左下角的图标指示没有可用的音频设备，右下角的闪烁图标表示 VDI 配对正在进行，如下所示：</span><span class="sxs-lookup"><span data-stu-id="9cacb-110">The icon in the lower left indicates that no audio devices are available, and the blinking icon in the lower right indicates that the VDI pairing is in progress, as shown:</span></span>
    
    <span data-ttu-id="9cacb-111">![Lync VDI 图标显示成功配对](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "Lync VDI 图标显示成功配对")</span><span class="sxs-lookup"><span data-stu-id="9cacb-111">![Lync VDI icon showing successful pairing](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "Lync VDI icon showing successful pairing")</span></span>  

4.  <span data-ttu-id="9cacb-112">VDI 配对成功后，这两个图标将更改为分别指示用于呼叫的音频设备和 VDI 配对成功：</span><span class="sxs-lookup"><span data-stu-id="9cacb-112">After VDI pairing is successful, the icons change to indicate the audio device that will be used for calls and the VDI pairing success:</span></span>
    
    <span data-ttu-id="9cacb-113">![Lync VDI 配对图标显示成功](images/JJ204948.57be3387-a3e5-4949-831e-f5ff9fcc5598(OCS.15).png "Lync VDI 配对图标显示成功")</span><span class="sxs-lookup"><span data-stu-id="9cacb-113">![Lync VDI pairing icon showing success](images/JJ204948.57be3387-a3e5-4949-831e-f5ff9fcc5598(OCS.15).png "Lync VDI pairing icon showing success")</span></span>  

5.  <span data-ttu-id="9cacb-114">Lync 对使用 VDI 插件后，用户可以在连接到本地计算机的 Lync 兼容设备上看到其状态。</span><span class="sxs-lookup"><span data-stu-id="9cacb-114">After Lync pairs with the VDI plug-in, the user can see his or her presence on Lync compatible devices that are connected to the local computer.</span></span> <span data-ttu-id="9cacb-115">用户现在可以照常发出和接听通话。</span><span class="sxs-lookup"><span data-stu-id="9cacb-115">The user can now place and answer calls as usual.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

