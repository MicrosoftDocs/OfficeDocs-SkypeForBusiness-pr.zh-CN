---
title: Lync Server 2013：运行林准备
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running forest preparation
ms:assetid: 9d62f7be-bcfe-421d-8d8a-225567102a35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412732(v=OCS.15)
ms:contentKeyID: 48184991
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e4ed33466e9b31fbabb3432927baea8f087ea1d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511119"
---
# <a name="running-forest-preparation-for-lync-server-2013"></a><span data-ttu-id="7ab44-102">为 Lync Server 2013 运行林准备</span><span class="sxs-lookup"><span data-stu-id="7ab44-102">Running forest preparation for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7ab44-103">_**上次修改的主题：** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="7ab44-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="7ab44-104">您可以使用安装程序或 Lync Server 命令行管理程序 cmdlet 来准备林。</span><span class="sxs-lookup"><span data-stu-id="7ab44-104">You can use Setup or Lync Server Management Shell cmdlets to prepare the forest.</span></span> <span data-ttu-id="7ab44-105">准备林的 cmdlet 为 **Enable-CsAdForest**。</span><span class="sxs-lookup"><span data-stu-id="7ab44-105">The cmdlet that prepares the forest is **Enable-CsAdForest**.</span></span>

<span data-ttu-id="7ab44-106">在准备林之后，您必须验证在运行域准备之前是否复制了全局设置。</span><span class="sxs-lookup"><span data-stu-id="7ab44-106">After you prepare the forest, you must verify that global settings have been replicated before running domain preparation.</span></span>

<div>

## <a name="to-use-setup-to-prepare-the-forest"></a><span data-ttu-id="7ab44-107">使用安装程序准备林</span><span class="sxs-lookup"><span data-stu-id="7ab44-107">To use Setup to prepare the forest</span></span>

1.  <span data-ttu-id="7ab44-108">以目录林级根域的 Enterprise Admins 组成员的身份登录到加入域的计算机。</span><span class="sxs-lookup"><span data-stu-id="7ab44-108">Log on to a computer that is joined to a domain as a member of the Enterprise Admins group for the forest root domain.</span></span>

2.  <span data-ttu-id="7ab44-109">在 Lync Server 2013 安装文件夹或媒体中，运行 Setup.exe 以启动部署向导。</span><span class="sxs-lookup"><span data-stu-id="7ab44-109">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Deployment Wizard.</span></span>

3.  <span data-ttu-id="7ab44-110">单击“准备 Active Directory”\*\*\*\*，然后等待确定部署状态。</span><span class="sxs-lookup"><span data-stu-id="7ab44-110">Click **Prepare Active Directory**, and then wait for the deployment state to be determined.</span></span>

4.  <span data-ttu-id="7ab44-111">在“步骤 3: 准备当前林”\*\*\*\* 中，单击“运行”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7ab44-111">At **Step 3: Prepare Current Forest**, click **Run**.</span></span>

5.  <span data-ttu-id="7ab44-112">在“准备林”\*\*\*\* 页上，单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7ab44-112">On the **Prepare Forest** page, click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7ab44-113">林准备允许你选择将 Lync Server 2013 的通用组放置在什么位置。</span><span class="sxs-lookup"><span data-stu-id="7ab44-113">Forest Preparation allows you to choose where to place the Universal Groups for Lync Server 2013.</span></span> <span data-ttu-id="7ab44-114">选择与组织要求一致的位置。</span><span class="sxs-lookup"><span data-stu-id="7ab44-114">Choose a location that is consistent with the requirements of your organization.</span></span>

    
    </div>

6.  <span data-ttu-id="7ab44-115">在“正在执行命令”\*\*\*\* 页上，查找“任务状态: 已完成”\*\*\*\*，然后单击“查看日志”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7ab44-115">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span>

7.  <span data-ttu-id="7ab44-116">在 " **操作** " 列下，展开 " **林准备**"，查找 **\<Success\>** 每个任务末尾的 "执行结果"，以验证是否已成功完成 "林准备"，然后关闭日志，然后单击 " **完成**"。</span><span class="sxs-lookup"><span data-stu-id="7ab44-116">Under the **Action** column, expand **Forest Prep**, look for a **\<Success\>** Execution Result at the end of each task to verify that forest preparation completed successfully, close the log, and then click **Finish**.</span></span>

8.  <span data-ttu-id="7ab44-p103">等待 Active Directory 复制完成，或者强制向目录林根级域控制器的“Active Directory 站点和服务”\*\*\*\* 管理单元中列出的所有域控制器进行复制，然后再运行域准备。在所有 Active Directory 站点中的域控制器之间强制进行复制，以使几分钟内就在站点中进行复制操作。</span><span class="sxs-lookup"><span data-stu-id="7ab44-p103">Wait for Active Directory replication to complete, or force replication to all domain controllers listed in the **Active Directory Sites and Services** snap-in for the forest root domain controller, before running domain preparation. Force replication between the domain controllers in all Active Directory sites to cause replication within the sites to occur within minutes.</span></span>

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-forest"></a><span data-ttu-id="7ab44-119">使用 cmdlet 准备林</span><span class="sxs-lookup"><span data-stu-id="7ab44-119">To use cmdlets to prepare the forest</span></span>

1.  <span data-ttu-id="7ab44-120">以目录林根级域中的 Domain Admins 组成员身份登录到加入域的计算机。</span><span class="sxs-lookup"><span data-stu-id="7ab44-120">Log on to a computer that is joined to a domain as a member of the Domain Admins group in the forest root domain.</span></span>

2.  <span data-ttu-id="7ab44-121">安装 Lync Server Core 组件，如下所示：</span><span class="sxs-lookup"><span data-stu-id="7ab44-121">Install Lync Server Core components as follows:</span></span>
    
    1.  <span data-ttu-id="7ab44-122">在 Lync Server 2013 安装文件夹或媒体中，运行 Setup.exe 以启动 Lync Server 部署向导。</span><span class="sxs-lookup"><span data-stu-id="7ab44-122">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Lync Server Deployment Wizard.</span></span>
    
    2.  <span data-ttu-id="7ab44-123">如果提示您安装 Microsoft Visual C++ 可再发行软件产品，单击“是”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7ab44-123">If you are prompted to install the Microsoft Visual C++ Redistributable, click **Yes**.</span></span>
    
    3.  <span data-ttu-id="7ab44-124">"Lync Server 2013 安装程序" 对话框将提示您输入安装 Lync Server 文件的位置。</span><span class="sxs-lookup"><span data-stu-id="7ab44-124">The Lync Server 2013 Setup dialog box prompts you for a location to install the Lync Server files.</span></span> <span data-ttu-id="7ab44-125">选择默认位置或“浏览”\*\*\*\* 至要选择的位置，然后单击“安装”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7ab44-125">Choose the default location or **Browse** to a location of your choice, and then click **Install**.</span></span>
    
    4.  <span data-ttu-id="7ab44-126">在“许可协议”页上，选中“我接受许可协议中的条款”\*\*\*\*，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7ab44-126">On the License Agreement page, check **I accept the terms in the license agreement**, and then click **OK**.</span></span> <span data-ttu-id="7ab44-127">安装程序安装 Lync Server 2013 核心组件。</span><span class="sxs-lookup"><span data-stu-id="7ab44-127">The installer installs the Lync Server 2013 Core Components.</span></span>

3.  <span data-ttu-id="7ab44-128">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7ab44-128">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="7ab44-129">以</span><span class="sxs-lookup"><span data-stu-id="7ab44-129">Run:</span></span>
    
        Enable-CsAdForest [-GroupDomain <FQDN of the domain in which to create the universal groups>]
    
    <span data-ttu-id="7ab44-130">例如：</span><span class="sxs-lookup"><span data-stu-id="7ab44-130">For example:</span></span>
    
        Enable-CsAdForest -GroupDomain domain1.contoso.com 
    
    <span data-ttu-id="7ab44-p106">如果不指定 GroupDomain 参数，则默认值为本地域。如果先前在默认域以外的域中创建了通用组，则必须显式指定 GroupDomain 参数。</span><span class="sxs-lookup"><span data-stu-id="7ab44-p106">If you do not specify the GroupDomain parameter, the default value is the local domain. If universal groups were created previously in a domain that is not the default domain, you must specify the GroupDomain parameter explicitly.</span></span>

5.  <span data-ttu-id="7ab44-133">等待 Active Directory 复制完成，或者强制向目录林根级域控制器的“Active Directory 站点和服务”\*\*\*\* 管理单元中列出的所有域控制器进行复制，然后再运行域准备。</span><span class="sxs-lookup"><span data-stu-id="7ab44-133">Wait for Active Directory replication to complete, or force replication to all domain controllers listed in the **Active Directory Sites and Services** snap-in for the forest root domain controller, before running domain preparation.</span></span>

6.  <span data-ttu-id="7ab44-p107">验证林准备是否成功。运行：</span><span class="sxs-lookup"><span data-stu-id="7ab44-p107">Verify that forest preparation was successful. Run:</span></span>
    
        Get-CsAdForest 
    
    <span data-ttu-id="7ab44-136">如果林准备成功，则此 cmdlet 将返回 \*\*LC \_ FORESTSETTINGS \_ 状态 \_ \*\* 为 "就绪" 的值。</span><span class="sxs-lookup"><span data-stu-id="7ab44-136">This cmdlet returns a value of **LC\_FORESTSETTINGS\_STATE\_READY** if forest preparation was successful.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7ab44-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7ab44-137">See Also</span></span>


[<span data-ttu-id="7ab44-138">使用 cmdlet 对 Lync Server 2013 反向林准备</span><span class="sxs-lookup"><span data-stu-id="7ab44-138">Using cmdlets to reverse forest preparation for Lync Server 2013</span></span>](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)  


[<span data-ttu-id="7ab44-139">准备 Lync Server 2013 的林</span><span class="sxs-lookup"><span data-stu-id="7ab44-139">Preparing the forest for Lync Server 2013</span></span>](lync-server-2013-preparing-the-forest.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

