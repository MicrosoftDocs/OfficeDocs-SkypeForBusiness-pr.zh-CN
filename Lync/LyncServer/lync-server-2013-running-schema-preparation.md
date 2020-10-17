---
title: Lync Server 2013：运行架构准备
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running schema preparation
ms:assetid: 9d02bdb1-ff29-417a-bcce-b068b31207d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412729(v=OCS.15)
ms:contentKeyID: 48184911
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 202052ce01bca6cdc11e8ed36dfede9afba74b8d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511099"
---
# <a name="running-active-directory-schema-preparation-in-lync-server-2013"></a><span data-ttu-id="a2e69-102">在 Lync Server 2013 中运行 Active Directory 架构准备</span><span class="sxs-lookup"><span data-stu-id="a2e69-102">Running Active Directory schema preparation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a2e69-103">_**上次修改的主题：** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="a2e69-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="a2e69-104">您可以使用安装程序或 Lync Server 命令行管理程序 cmdlet 来准备 Active Directory 架构。</span><span class="sxs-lookup"><span data-stu-id="a2e69-104">You can use Setup or Lync Server Management Shell cmdlets to prepare the Active Directory schema.</span></span> <span data-ttu-id="a2e69-105">展开 Active Directory 架构的 cmdlet 为 **Install-CsAdServerSchema**。</span><span class="sxs-lookup"><span data-stu-id="a2e69-105">The cmdlet that extends the Active Directory schema is **Install-CsAdServerSchema**.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a2e69-106">架构准备 cmdlet (<STRONG>Install-CsAdServerSchema</STRONG>) 必须访问架构主机，这就要求运行远程注册表服务并启用远程注册表项。</span><span class="sxs-lookup"><span data-stu-id="a2e69-106">The schema preparation cmdlet (<STRONG>Install-CsAdServerSchema</STRONG>) must access the schema master, which requires that the remote registry service is running and that the remote registry key is enabled.</span></span> <span data-ttu-id="a2e69-107">如果无法在架构主机上启用远程注册表服务，可以在架构主机上本地运行该 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a2e69-107">If the remote registry service cannot be enabled on the schema master, you can run the cmdlet locally on the schema master.</span></span> <span data-ttu-id="a2e69-108">有关注册表远程访问的详细信息，请参阅 Microsoft 知识库文章 314837 "如何管理对注册表的远程访问？" <A href="https://go.microsoft.com/fwlink/p/?linkid=125769">https://go.microsoft.com/fwlink/p/?linkId=125769</A> 。</span><span class="sxs-lookup"><span data-stu-id="a2e69-108">For details about registry remote access, see Microsoft Knowledge Base article 314837, "How to Manage Remote Access to the Registry," at <A href="https://go.microsoft.com/fwlink/p/?linkid=125769">https://go.microsoft.com/fwlink/p/?linkId=125769</A>.</span></span>



</div>

<span data-ttu-id="a2e69-109">完成架构准备之后，在继续林准备之前手动验证是否复制了架构分区。</span><span class="sxs-lookup"><span data-stu-id="a2e69-109">After you complete schema preparation, manually verify that the schema partition has been replicated before proceeding to forest preparation.</span></span> <span data-ttu-id="a2e69-110">有关详细信息，请参阅 [在 Lync Server 2013 中验证 Active Directory 架构复制](lync-server-2013-verifying-schema-replication.md)。</span><span class="sxs-lookup"><span data-stu-id="a2e69-110">For details, see [Verifying Active Directory schema replication in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span></span>

<div>

## <a name="to-use-setup-to-prepare-the-schema-of-the-current-forest"></a><span data-ttu-id="a2e69-111">使用安装程序准备当前林的架构</span><span class="sxs-lookup"><span data-stu-id="a2e69-111">To use Setup to prepare the schema of the current forest</span></span>

1.  <span data-ttu-id="a2e69-112">以 Schema Admins 组成员和在架构主机上具有 Administrator 权限的身份登录到林中的服务器。</span><span class="sxs-lookup"><span data-stu-id="a2e69-112">Log on to a server in your forest as a member of the Schema Admins group and with administrator rights on the schema master.</span></span>

2.  <span data-ttu-id="a2e69-113">在 Lync Server 2013 安装文件夹或媒体中，运行 Setup.exe 以启动部署向导。</span><span class="sxs-lookup"><span data-stu-id="a2e69-113">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Deployment Wizard.</span></span>

3.  <span data-ttu-id="a2e69-114">如果提示您安装 Microsoft Visual C++ 可再发行软件产品，单击“是”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a2e69-114">If you are prompted to install the Microsoft Visual C++ Redistributable, click **Yes**.</span></span>

4.  <span data-ttu-id="a2e69-115">"Lync Server 2013 安装程序" 对话框将提示您输入安装 Lync Server 文件的位置。</span><span class="sxs-lookup"><span data-stu-id="a2e69-115">The Lync Server 2013 Setup dialog box prompts you for a location to install the Lync Server files.</span></span> <span data-ttu-id="a2e69-116">选择默认位置或“浏览”\*\*\*\* 至要选择的位置，然后单击“安装”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a2e69-116">Choose the default location or **Browse** to a location of your choice, and then click **Install**.</span></span>

5.  <span data-ttu-id="a2e69-117">在“许可协议”页上，选中“我接受许可协议中的条款”\*\*\*\*，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a2e69-117">On the License Agreement page, check **I accept the terms in the license agreement**, and then click **OK**.</span></span>

6.  <span data-ttu-id="a2e69-118">安装程序安装 Lync Server Core 组件。</span><span class="sxs-lookup"><span data-stu-id="a2e69-118">The installer installs the Lync Server Core Components.</span></span>

7.  <span data-ttu-id="a2e69-119">部署向导准备就绪后，单击“准备 Active Directory”\*\*\*\*，然后等待确定部署状态。</span><span class="sxs-lookup"><span data-stu-id="a2e69-119">When the Deployment Wizard is ready, click **Prepare Active Directory**, and then wait for the deployment state to be determined.</span></span>

8.  <span data-ttu-id="a2e69-120">在“步骤 1: 准备架构”\*\*\*\* 中，单击“运行”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a2e69-120">At **Step 1: Prepare Schema**, click **Run**.</span></span>

9.  <span data-ttu-id="a2e69-121">在“准备架构”\*\*\*\* 页上，单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a2e69-121">On the **Prepare Schema** page, click **Next**.</span></span>

10. <span data-ttu-id="a2e69-122">在“正在执行命令”\*\*\*\* 页上，查找“任务状态: 已完成”\*\*\*\*，然后单击“查看日志”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a2e69-122">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span>

11. <span data-ttu-id="a2e69-123">在 " **操作** " 列下，展开 " **架构准备**"， **\<Success\>** 在每个任务的末尾查找执行结果，以验证架构准备是否已成功完成，关闭日志，然后单击 " **完成**"。</span><span class="sxs-lookup"><span data-stu-id="a2e69-123">Under the **Action** column, expand **Schema Prep**, look for the **\<Success\>** Execution Result at the end of each task to verify that schema preparation completed successfully, close the log, and then click **Finish**.</span></span>

12. <span data-ttu-id="a2e69-124">等待 Active Directory 复制完成，或强制执行复制。</span><span class="sxs-lookup"><span data-stu-id="a2e69-124">Wait for Active Directory replication to complete or force replication.</span></span>

13. <span data-ttu-id="a2e69-125">手动验证是否已将架构更改复制到其他所有域控制器。</span><span class="sxs-lookup"><span data-stu-id="a2e69-125">Manually verify that the schema changes replicated to all other domain controllers.</span></span> <span data-ttu-id="a2e69-126">有关详细信息，请参阅 [在 Lync Server 2013 中验证 Active Directory 架构复制](lync-server-2013-verifying-schema-replication.md)。</span><span class="sxs-lookup"><span data-stu-id="a2e69-126">For details, see [Verifying Active Directory schema replication in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span></span>

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-schema-of-the-current-forest"></a><span data-ttu-id="a2e69-127">使用 cmdlet 准备当前林的架构</span><span class="sxs-lookup"><span data-stu-id="a2e69-127">To use cmdlets to prepare the schema of the current forest</span></span>

1.  <span data-ttu-id="a2e69-128">以 Schema Admins 组成员的身份和架构主机上的管理员权限登录到林中的计算机。</span><span class="sxs-lookup"><span data-stu-id="a2e69-128">Log on to a computer in the forest as a member of the Schema Admins group and with administrator rights on the schema master.</span></span>

2.  <span data-ttu-id="a2e69-129">安装 Lync Server Core 组件，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a2e69-129">Install Lync Server Core components as follows:</span></span>
    
    1.  <span data-ttu-id="a2e69-130">在 Lync Server 2013 安装文件夹或媒体中，运行 Setup.exe 以启动 Lync Server 部署向导。</span><span class="sxs-lookup"><span data-stu-id="a2e69-130">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Lync Server Deployment Wizard.</span></span>
    
    2.  <span data-ttu-id="a2e69-131">如果提示您安装 Microsoft Visual C++ 可再发行软件产品，单击“是”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a2e69-131">If you are prompted to install the Microsoft Visual C++ Redistributable, click **Yes**.</span></span>
    
    3.  <span data-ttu-id="a2e69-132">"Lync Server 2013 安装程序" 对话框将提示您输入安装 Lync Server 文件的位置。</span><span class="sxs-lookup"><span data-stu-id="a2e69-132">The Lync Server 2013 Setup dialog box prompts you for a location to install the Lync Server files.</span></span> <span data-ttu-id="a2e69-133">选择默认位置或“浏览”\*\*\*\* 至要选择的位置，然后单击“安装”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a2e69-133">Choose the default location or **Browse** to a location of your choice, and then click **Install**.</span></span>
    
    4.  <span data-ttu-id="a2e69-134">在“许可协议”页上，选中“我接受许可协议中的条款”\*\*\*\*，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a2e69-134">On the License Agreement page, check **I accept the terms in the license agreement**, and then click **OK**.</span></span> <span data-ttu-id="a2e69-135">安装程序安装 Lync Server 2013 核心组件。</span><span class="sxs-lookup"><span data-stu-id="a2e69-135">The installer installs the Lync Server 2013 Core Components.</span></span>

3.  <span data-ttu-id="a2e69-136">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a2e69-136">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="a2e69-137">以</span><span class="sxs-lookup"><span data-stu-id="a2e69-137">Run:</span></span>
    
        Install-CsAdServerSchema [-Ldf <directory where the .ldf file is located>] 
    
    <span data-ttu-id="a2e69-138">如果不指定 Ldf 参数，则默认值是从注册表中读取的 Lync Server 2013 安装路径。</span><span class="sxs-lookup"><span data-stu-id="a2e69-138">If you do not specify the Ldf parameter, the default value is the Lync Server 2013 installation path that is read from the registry.</span></span>
    
    <span data-ttu-id="a2e69-139">例如：</span><span class="sxs-lookup"><span data-stu-id="a2e69-139">For example:</span></span>
    
        Install-CsAdServerSchema -Ldf "C:\Program Files\Microsoft Lync Server 2013\Deployment\Setup"

5.  <span data-ttu-id="a2e69-140">使用以下 cmdlet 确认架构准备运行结束。</span><span class="sxs-lookup"><span data-stu-id="a2e69-140">Use the following cmdlet to verify that schema preparation ran to completion.</span></span>
    
        Get-CsAdServerSchema 
    
    <span data-ttu-id="a2e69-141">如果架构准备成功，则此 cmdlet 返回 **架构 \_ 版本 \_ 状态的 \_ 当前** 值。</span><span class="sxs-lookup"><span data-stu-id="a2e69-141">This cmdlet returns a value of **SCHEMA\_VERSION\_STATE\_CURRENT** if schema preparation was successful.</span></span>

6.  <span data-ttu-id="a2e69-142">等待 Active Directory 复制完成，或强制执行复制。</span><span class="sxs-lookup"><span data-stu-id="a2e69-142">Wait for Active Directory replication to complete or force replication.</span></span>

7.  <span data-ttu-id="a2e69-143">手动验证是否已将架构更改复制到其他所有域控制器。</span><span class="sxs-lookup"><span data-stu-id="a2e69-143">Manually verify that the schema changes replicated to all other domain controllers.</span></span> <span data-ttu-id="a2e69-144">有关详细信息，请参阅 [在 Lync Server 2013 中验证 Active Directory 架构复制](lync-server-2013-verifying-schema-replication.md)。</span><span class="sxs-lookup"><span data-stu-id="a2e69-144">For details, see [Verifying Active Directory schema replication in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a2e69-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a2e69-145">See Also</span></span>


[<span data-ttu-id="a2e69-146">在 Lync Server 2013 中验证 Active Directory 架构复制</span><span class="sxs-lookup"><span data-stu-id="a2e69-146">Verifying Active Directory schema replication in Lync Server 2013</span></span>](lync-server-2013-verifying-schema-replication.md)  


[<span data-ttu-id="a2e69-147">在 Lync Server 2013 中准备 Active Directory 架构</span><span class="sxs-lookup"><span data-stu-id="a2e69-147">Preparing the Active Directory schema in Lync Server 2013</span></span>](lync-server-2013-preparing-the-active-directory-schema.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

