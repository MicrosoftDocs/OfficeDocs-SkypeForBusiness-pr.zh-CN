---
title: 配置 SCOM 监控
description: 配置 SCOM 监视。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure SCOM monitoring
ms:assetid: 4003d225-2a33-448c-abd9-571750661140
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688033(v=OCS.15)
ms:contentKeyID: 49733624
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c93e10c705a1a1e08972d7534e00a33c472d23a3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542988"
---
# <a name="configure-scom-monitoring"></a><span data-ttu-id="a3cf4-103">配置 SCOM 监控</span><span class="sxs-lookup"><span data-stu-id="a3cf4-103">Configure SCOM monitoring</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a3cf4-104">_**上次修改的主题：** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="a3cf4-104">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="a3cf4-105">迁移到 Microsoft Lync Server 2013 后，必须完成几个任务，才能配置 Lync Server 2013 以使用 System Center Operations Manager。</span><span class="sxs-lookup"><span data-stu-id="a3cf4-105">After migrating to Microsoft Lync Server 2013, you must complete a few tasks to configure Lync Server 2013 to work with System Center Operations Manager.</span></span>

  - <span data-ttu-id="a3cf4-106">将 Lync Server 2010 更新应用于选择的服务器以管理中央发现逻辑。</span><span class="sxs-lookup"><span data-stu-id="a3cf4-106">Apply Lync Server 2010 updates to a server elected to manage the central discovery logic.</span></span>

  - <span data-ttu-id="a3cf4-107">更新中央发现候选服务器注册表项。</span><span class="sxs-lookup"><span data-stu-id="a3cf4-107">Update the central discovery candidate server registry key.</span></span>

  - <span data-ttu-id="a3cf4-108">将主 System Center Operations Manager 管理服务器配置为覆盖候选中央发现节点。</span><span class="sxs-lookup"><span data-stu-id="a3cf4-108">Configure your primary System Center Operations Manager management server to override the candidate central discovery node.</span></span>

<span data-ttu-id="a3cf4-109">下面提供了有关执行所有这些任务的说明。</span><span class="sxs-lookup"><span data-stu-id="a3cf4-109">Instructions for carrying out each of these tasks are provided below.</span></span>

<span data-ttu-id="a3cf4-110">**将 Lync Server 2010 更新应用于选择的服务器以管理中央发现逻辑。**</span><span class="sxs-lookup"><span data-stu-id="a3cf4-110">**Apply Lync Server 2010 updates to a server elected to manage the central discovery logic.**</span></span>

1.  <span data-ttu-id="a3cf4-111">选择安装了 System Center Operations Manager 代理文件且配置为候选发现节点的服务器。</span><span class="sxs-lookup"><span data-stu-id="a3cf4-111">Elect a server that has the System Center Operations Manager agent files installed and is configured as a candidate discovery node.</span></span>

2.  <span data-ttu-id="a3cf4-112">将 Lync Server 2010 更新应用到此服务器。</span><span class="sxs-lookup"><span data-stu-id="a3cf4-112">Apply Lync Server 2010 updates to this server.</span></span> <span data-ttu-id="a3cf4-113">请参阅 [应用 Lync Server 2010 更新](apply-lync-server-2010-updates.md)主题。</span><span class="sxs-lookup"><span data-stu-id="a3cf4-113">See the topic [Apply Lync Server 2010 updates](apply-lync-server-2010-updates.md).</span></span>

<span data-ttu-id="a3cf4-114">**更新中央发现候选服务器注册表项。**</span><span class="sxs-lookup"><span data-stu-id="a3cf4-114">**Update the central discovery candidate server registry key.**</span></span>

1.  <span data-ttu-id="a3cf4-115">在选择了管理中央发现逻辑的服务器上，打开 Windows PowerShell 命令窗口。</span><span class="sxs-lookup"><span data-stu-id="a3cf4-115">On the server elected to manage the central discovery logic, open a Windows PowerShell command window.</span></span>

2.  <span data-ttu-id="a3cf4-116">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="a3cf4-116">At the command line, type the following:</span></span>
    
       ```PowerShell
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
       ```
    
       ```PowerShell
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
       ```
    
    <div class="">
    

    > [!NOTE]  
    > <span data-ttu-id="a3cf4-p102">在您编辑注册表时，如果已存在注册表项，则您可能会遇到一个指示命令失败的错误。如果遇到此错误，可以安全地将其忽略。</span><span class="sxs-lookup"><span data-stu-id="a3cf4-p102">Whenever you edit the registry, you may experience an error that the command failed if the registry key already exists. If you experience this, you can safely ignore the error.</span></span>

    
    </div>

<span data-ttu-id="a3cf4-119">**将您的主 System Center Operations Manager 管理服务器配置为覆盖候选中央发现观察程序节点。**</span><span class="sxs-lookup"><span data-stu-id="a3cf4-119">**Configure your primary System Center Operations Manager management server to override the candidate central discovery watcher node.**</span></span>

1.  <span data-ttu-id="a3cf4-120">在已安装 System Center Operations Manager 控制台的计算机上，展开“管理包对象”\*\*\*\*，然后选择“对象发现”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a3cf4-120">On a computer where the System Center Operations Manager console has been installed, expand **Management Pack Objects** and then select **Object Discoveries**.</span></span>

2.  <span data-ttu-id="a3cf4-121">单击“更改范围”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a3cf4-121">Click **Change Scope...**</span></span>

3.  <span data-ttu-id="a3cf4-122">从“范围管理包对象”\*\*\*\* 页中，选择“LS 发现候选”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a3cf4-122">From the **Scope Management Pack Objects** page, select **LS Discovery Candidate**.</span></span>

4.  <span data-ttu-id="a3cf4-123">将“LS 发现候选有效值”\*\*\*\* 覆盖为在之前的过程中选定的候选服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="a3cf4-123">Override the **LS Discovery Candidate Effective Value** to the name of the candidate server elected in the earlier procedure.</span></span>

<span data-ttu-id="a3cf4-124">最后，若要最终完成您的更改，请重新启动 System Center Operations Manager Root Management Server 上的运行状况服务。</span><span class="sxs-lookup"><span data-stu-id="a3cf4-124">Lastly, to finalize your changes, restart the health service on the System Center Operations Manager Root Management Server.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

