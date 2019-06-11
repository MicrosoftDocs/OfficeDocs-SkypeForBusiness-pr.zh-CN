---
title: 'Lync Server 2013: 从评估版本更新'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Updating from the evaluation version of Lync Server 2013
ms:assetid: 62a88180-4289-4a2a-9cb9-1b9899344a63
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521005(v=OCS.15)
ms:contentKeyID: 48184294
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b00fed276229cbaf0e960e28e622e490fb0bfbf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845516"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="updating-from-the-evaluation-version-of-lync-server-2013"></a><span data-ttu-id="4af2a-102">从 Lync Server 2013 的评估版本更新</span><span class="sxs-lookup"><span data-stu-id="4af2a-102">Updating from the evaluation version of Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4af2a-103">_**主题上次修改时间:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="4af2a-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="4af2a-104">如果已安装 Microsoft Lync Server 2013 的评估版本, 则最终需要更新该安装软件的许可副本;这是因为评估版本在安装后将在180天内过期。</span><span class="sxs-lookup"><span data-stu-id="4af2a-104">If you have installed the Evaluation version of Microsoft Lync Server 2013, you will eventually need to update that installation a licensed copy of the software; that's because the evaluation version expires 180 days after it was installed.</span></span> <span data-ttu-id="4af2a-105">但是, 你无需完全卸载评估版本, 然后安装许可的版本。</span><span class="sxs-lookup"><span data-stu-id="4af2a-105">However, you will not need to completely uninstall the evaluation version and then install the licensed version.</span></span> <span data-ttu-id="4af2a-106">在获取有效的授权密钥之后, 你可以通过在充当 Lync Server 前端服务器、Director 或 Edge 服务器的每台计算机上执行以下过程来更新 Lync Server 2013 的评估版本。</span><span class="sxs-lookup"><span data-stu-id="4af2a-106">Instead, after you have obtained a valid licensing key, you can update the evaluation version of Lync Server 2013 by carrying out the following procedure on each computer acting as a Lync Server Front End Server, Director, or Edge Server.</span></span> <span data-ttu-id="4af2a-107">请注意, 您不必更新执行其他服务器角色 (如监视服务器或存档服务器) 的计算机。</span><span class="sxs-lookup"><span data-stu-id="4af2a-107">Note that you do not have to update computers carrying out other server roles, such as a Monitoring Server or Archiving Server.</span></span>

<div>

## <a name="updating-from-the-evaluation-version-of-microsoft-lync-server-2013"></a><span data-ttu-id="4af2a-108">从 Microsoft Lync Server 2013 的评估版本更新</span><span class="sxs-lookup"><span data-stu-id="4af2a-108">Updating from the Evaluation Version of Microsoft Lync Server 2013</span></span>

<span data-ttu-id="4af2a-109">要将计算机从 Lync Server 2013 的评估版本更新到软件的许可版本, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="4af2a-109">To update a computer from the evaluation version of Lync Server 2013 to the licensed version of the software:</span></span>

<span data-ttu-id="4af2a-110">**从 Microsoft Lync Server 2013 的评估版本更新**</span><span class="sxs-lookup"><span data-stu-id="4af2a-110">**Updating from the Evaluation Version of Microsoft Lync Server 2013**</span></span>

1.  <span data-ttu-id="4af2a-111">以本地管理员身份登录到计算机。</span><span class="sxs-lookup"><span data-stu-id="4af2a-111">Log on to the computer as a local administrator.</span></span>

2.  <span data-ttu-id="4af2a-112">单击 "**开始**", 单击 "**所有程序**", 单击 " **Microsoft Lync server 2013**", 然后单击 " **Lync server Management Shell**"。</span><span class="sxs-lookup"><span data-stu-id="4af2a-112">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="4af2a-113">在 Lync Server 命令行管理器中, 键入以下命令, 然后按 ENTER:</span><span class="sxs-lookup"><span data-stu-id="4af2a-113">In the Lync Server Management Shell, type the following command and then press ENTER:</span></span>
    
        msiexec.exe /fvomus server.msi EVALTOFULL=1 /qb
    
    <span data-ttu-id="4af2a-114">请注意, 你可能需要指定文件服务器 .msi 的完整路径。</span><span class="sxs-lookup"><span data-stu-id="4af2a-114">Note that you might need to specify the full path to the file server.msi.</span></span> <span data-ttu-id="4af2a-115">此文件可在 Lync Server 卷媒体安装文件的 "设置" 文件夹中找到。</span><span class="sxs-lookup"><span data-stu-id="4af2a-115">This file can be found in the Setup folder of the Lync Server Volume media installation files.</span></span>

4.  <span data-ttu-id="4af2a-116">在安装程序完成运行后, 在命令提示符处键入以下内容, 然后按 ENTER:</span><span class="sxs-lookup"><span data-stu-id="4af2a-116">After Setup finishes running, type the following from the command prompt and then press ENTER:</span></span>
    
        Enable-CsComputer

5.  <span data-ttu-id="4af2a-117">在运行 Lync Server 评估副本的任何其他前端服务器、控制器或边缘服务器上重复此过程。</span><span class="sxs-lookup"><span data-stu-id="4af2a-117">Repeat this procedure on any other Front End Server, Director, or Edge Server running an evaluation copy of Lync Server.</span></span> <span data-ttu-id="4af2a-118">还应在使用 Lync Server media 安装文件部署的任何分支机构服务器上执行此过程。</span><span class="sxs-lookup"><span data-stu-id="4af2a-118">This procedure should also be performed on any Branch Office Servers that were deployed by using the Lync Server media installation files.</span></span>

<span data-ttu-id="4af2a-119">如果你不确定 Lync Server 的评估版本是否在给定计算机上运行, 你可以通过在 Lync Server Management Shell 中运行以下命令来验证该版本:</span><span class="sxs-lookup"><span data-stu-id="4af2a-119">If you are not sure if the evaluation version of Lync Server is running on a given computer you can verify that by running the following command from within the Lync Server Management Shell:</span></span>

    Get-CsServerVersion

<span data-ttu-id="4af2a-120">[CsServerVersion](https://docs.microsoft.com/powershell/module/skype/Get-CsServerVersion) cmdlet 将分析本地计算机并向后报告以下情况之一:</span><span class="sxs-lookup"><span data-stu-id="4af2a-120">The [Get-CsServerVersion](https://docs.microsoft.com/powershell/module/skype/Get-CsServerVersion) cmdlet will analyze the local computer and report back one of the following:</span></span>

  - <span data-ttu-id="4af2a-121">已在计算机上安装 Lync Server 批量许可证密钥, 这意味着无需更新。</span><span class="sxs-lookup"><span data-stu-id="4af2a-121">That the Lync Server volume license key has been installed on the computer, meaning that no updating is necessary.</span></span>

  - <span data-ttu-id="4af2a-122">已安装 Lync Server 试用版许可证密钥, 这意味着必须更新计算机。</span><span class="sxs-lookup"><span data-stu-id="4af2a-122">That the Lync Server evaluation license key has been installed, meaning that the computer must be updated.</span></span>

  - <span data-ttu-id="4af2a-123">计算机上不需要批量许可证密钥。</span><span class="sxs-lookup"><span data-stu-id="4af2a-123">That no volume license key is required on the computer.</span></span> <span data-ttu-id="4af2a-124">仅在前端服务器、控制器和边缘服务器上需要从评估版更新到许可版本。</span><span class="sxs-lookup"><span data-stu-id="4af2a-124">Updating from the evaluation version to the licensed version is only required on Front End Servers, Directors, and Edge Servers.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

