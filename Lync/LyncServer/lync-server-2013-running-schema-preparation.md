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
ms.openlocfilehash: 06b02981e9baa589801839c8fd8c871ae35b0dde
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765040"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="running-active-directory-schema-preparation-in-lync-server-2013"></a><span data-ttu-id="d9552-102">在 Lync Server 2013 中运行 Active Directory 架构准备</span><span class="sxs-lookup"><span data-stu-id="d9552-102">Running Active Directory schema preparation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d9552-103">_**主题上次修改时间：** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="d9552-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="d9552-104">你可以使用安装程序或 Lync Server Management Shell cmdlet 来准备 Active Directory 架构。</span><span class="sxs-lookup"><span data-stu-id="d9552-104">You can use Setup or Lync Server Management Shell cmdlets to prepare the Active Directory schema.</span></span> <span data-ttu-id="d9552-105">扩展 Active Directory 架构的 cmdlet 为**Install-CsAdServerSchema**。</span><span class="sxs-lookup"><span data-stu-id="d9552-105">The cmdlet that extends the Active Directory schema is **Install-CsAdServerSchema**.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d9552-106">架构准备 cmdlet （<STRONG>Install-CsAdServerSchema</STRONG>）必须访问架构主机，这要求远程注册表服务正在运行且远程注册表项已启用。</span><span class="sxs-lookup"><span data-stu-id="d9552-106">The schema preparation cmdlet (<STRONG>Install-CsAdServerSchema</STRONG>) must access the schema master, which requires that the remote registry service is running and that the remote registry key is enabled.</span></span> <span data-ttu-id="d9552-107">如果无法在架构主机上启用远程注册表服务，则可以在架构主机上本地运行 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d9552-107">If the remote registry service cannot be enabled on the schema master, you can run the cmdlet locally on the schema master.</span></span> <span data-ttu-id="d9552-108">有关注册表远程访问的详细信息，请参阅 Microsoft 知识库文章 314837 "如何管理对注册表的远程访问" <A href="http://go.microsoft.com/fwlink/p/?linkid=125769">http://go.microsoft.com/fwlink/p/?linkId=125769</A>。</span><span class="sxs-lookup"><span data-stu-id="d9552-108">For details about registry remote access, see Microsoft Knowledge Base article 314837, "How to Manage Remote Access to the Registry," at <A href="http://go.microsoft.com/fwlink/p/?linkid=125769">http://go.microsoft.com/fwlink/p/?linkId=125769</A>.</span></span>



</div>

<span data-ttu-id="d9552-109">完成架构准备后，手动验证架构分区是否已复制，然后再继续执行林准备。</span><span class="sxs-lookup"><span data-stu-id="d9552-109">After you complete schema preparation, manually verify that the schema partition has been replicated before proceeding to forest preparation.</span></span> <span data-ttu-id="d9552-110">有关详细信息，请参阅[在 Lync Server 2013 中验证 Active Directory 架构复制](lync-server-2013-verifying-schema-replication.md)。</span><span class="sxs-lookup"><span data-stu-id="d9552-110">For details, see [Verifying Active Directory schema replication in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span></span>

<div>

## <a name="to-use-setup-to-prepare-the-schema-of-the-current-forest"></a><span data-ttu-id="d9552-111">使用安装程序准备当前林的架构</span><span class="sxs-lookup"><span data-stu-id="d9552-111">To use Setup to prepare the schema of the current forest</span></span>

1.  <span data-ttu-id="d9552-112">以架构管理员组的成员身份登录到林中的服务器，并使用架构主机上的管理员权限登录。</span><span class="sxs-lookup"><span data-stu-id="d9552-112">Log on to a server in your forest as a member of the Schema Admins group and with administrator rights on the schema master.</span></span>

2.  <span data-ttu-id="d9552-113">从 Lync Server 2013 安装文件夹或媒体中，运行 Setup.exe 以启动部署向导。</span><span class="sxs-lookup"><span data-stu-id="d9552-113">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Deployment Wizard.</span></span>

3.  <span data-ttu-id="d9552-114">如果系统提示您安装 Microsoft Visual c + + 可再发行组件，请单击 **"是"**。</span><span class="sxs-lookup"><span data-stu-id="d9552-114">If you are prompted to install the Microsoft Visual C++ Redistributable, click **Yes**.</span></span>

4.  <span data-ttu-id="d9552-115">"Lync Server 2013 设置" 对话框提示你输入安装 Lync Server 文件的位置。</span><span class="sxs-lookup"><span data-stu-id="d9552-115">The Lync Server 2013 Setup dialog box prompts you for a location to install the Lync Server files.</span></span> <span data-ttu-id="d9552-116">选择默认位置或**浏览**到您选择的位置，然后单击 "**安装**"。</span><span class="sxs-lookup"><span data-stu-id="d9552-116">Choose the default location or **Browse** to a location of your choice, and then click **Install**.</span></span>

5.  <span data-ttu-id="d9552-117">在 "许可协议" 页面上，选中 "**我接受许可协议中的条款**"，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="d9552-117">On the License Agreement page, check **I accept the terms in the license agreement**, and then click **OK**.</span></span>

6.  <span data-ttu-id="d9552-118">安装程序安装 Lync Server 核心组件。</span><span class="sxs-lookup"><span data-stu-id="d9552-118">The installer installs the Lync Server Core Components.</span></span>

7.  <span data-ttu-id="d9552-119">当部署向导准备就绪时，单击 "**准备 Active Directory**"，然后等待确定部署状态。</span><span class="sxs-lookup"><span data-stu-id="d9552-119">When the Deployment Wizard is ready, click **Prepare Active Directory**, and then wait for the deployment state to be determined.</span></span>

8.  <span data-ttu-id="d9552-120">在**步骤1：准备架构**中，单击 "**运行**"。</span><span class="sxs-lookup"><span data-stu-id="d9552-120">At **Step 1: Prepare Schema**, click **Run**.</span></span>

9.  <span data-ttu-id="d9552-121">在 "**准备架构**" 页面上，单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="d9552-121">On the **Prepare Schema** page, click **Next**.</span></span>

10. <span data-ttu-id="d9552-122">在“**正在执行命令**”页上，查找“**任务状态：已完成**”，然后单击“**查看日志**”。</span><span class="sxs-lookup"><span data-stu-id="d9552-122">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span>

11. <span data-ttu-id="d9552-123">在 "**操作**" 列下，展开 "**架构准备**"，查找每个任务末尾的\*\* \<\>成功**执行结果，验证架构准备是否已成功完成，关闭日志，然后单击 "**完成\*\*"。</span><span class="sxs-lookup"><span data-stu-id="d9552-123">Under the **Action** column, expand **Schema Prep**, look for the **\<Success\>** Execution Result at the end of each task to verify that schema preparation completed successfully, close the log, and then click **Finish**.</span></span>

12. <span data-ttu-id="d9552-124">等待 Active Directory 复制完成或强制执行复制。</span><span class="sxs-lookup"><span data-stu-id="d9552-124">Wait for Active Directory replication to complete or force replication.</span></span>

13. <span data-ttu-id="d9552-125">手动验证架构更改是否已复制到所有其他域控制器。</span><span class="sxs-lookup"><span data-stu-id="d9552-125">Manually verify that the schema changes replicated to all other domain controllers.</span></span> <span data-ttu-id="d9552-126">有关详细信息，请参阅[在 Lync Server 2013 中验证 Active Directory 架构复制](lync-server-2013-verifying-schema-replication.md)。</span><span class="sxs-lookup"><span data-stu-id="d9552-126">For details, see [Verifying Active Directory schema replication in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span></span>

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-schema-of-the-current-forest"></a><span data-ttu-id="d9552-127">使用 cmdlet 准备当前林的架构</span><span class="sxs-lookup"><span data-stu-id="d9552-127">To use cmdlets to prepare the schema of the current forest</span></span>

1.  <span data-ttu-id="d9552-128">以架构管理员组的成员身份登录到林中的计算机，并使用架构主机上的管理员权限登录。</span><span class="sxs-lookup"><span data-stu-id="d9552-128">Log on to a computer in the forest as a member of the Schema Admins group and with administrator rights on the schema master.</span></span>

2.  <span data-ttu-id="d9552-129">安装 Lync Server Core 组件，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d9552-129">Install Lync Server Core components as follows:</span></span>
    
    1.  <span data-ttu-id="d9552-130">从 Lync Server 2013 安装文件夹或媒体中，运行 Setup.exe 以启动 Lync Server 部署向导。</span><span class="sxs-lookup"><span data-stu-id="d9552-130">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Lync Server Deployment Wizard.</span></span>
    
    2.  <span data-ttu-id="d9552-131">如果系统提示您安装 Microsoft Visual c + + 可再发行组件，请单击 **"是"**。</span><span class="sxs-lookup"><span data-stu-id="d9552-131">If you are prompted to install the Microsoft Visual C++ Redistributable, click **Yes**.</span></span>
    
    3.  <span data-ttu-id="d9552-132">"Lync Server 2013 设置" 对话框提示你输入安装 Lync Server 文件的位置。</span><span class="sxs-lookup"><span data-stu-id="d9552-132">The Lync Server 2013 Setup dialog box prompts you for a location to install the Lync Server files.</span></span> <span data-ttu-id="d9552-133">选择默认位置或**浏览**到您选择的位置，然后单击 "**安装**"。</span><span class="sxs-lookup"><span data-stu-id="d9552-133">Choose the default location or **Browse** to a location of your choice, and then click **Install**.</span></span>
    
    4.  <span data-ttu-id="d9552-134">在 "许可协议" 页面上，选中 "**我接受许可协议中的条款**"，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="d9552-134">On the License Agreement page, check **I accept the terms in the license agreement**, and then click **OK**.</span></span> <span data-ttu-id="d9552-135">安装程序安装 Lync Server 2013 核心组件。</span><span class="sxs-lookup"><span data-stu-id="d9552-135">The installer installs the Lync Server 2013 Core Components.</span></span>

3.  <span data-ttu-id="d9552-136">启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="d9552-136">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="d9552-137">运行：</span><span class="sxs-lookup"><span data-stu-id="d9552-137">Run:</span></span>
    
        Install-CsAdServerSchema [-Ldf <directory where the .ldf file is located>] 
    
    <span data-ttu-id="d9552-138">如果不指定 Ldf 参数，则默认值为从注册表中读取的 Lync Server 2013 安装路径。</span><span class="sxs-lookup"><span data-stu-id="d9552-138">If you do not specify the Ldf parameter, the default value is the Lync Server 2013 installation path that is read from the registry.</span></span>
    
    <span data-ttu-id="d9552-139">例如：</span><span class="sxs-lookup"><span data-stu-id="d9552-139">For example:</span></span>
    
        Install-CsAdServerSchema -Ldf "C:\Program Files\Microsoft Lync Server 2013\Deployment\Setup"

5.  <span data-ttu-id="d9552-140">使用以下 cmdlet 验证架构准备是否已完成运行。</span><span class="sxs-lookup"><span data-stu-id="d9552-140">Use the following cmdlet to verify that schema preparation ran to completion.</span></span>
    
        Get-CsAdServerSchema 
    
    <span data-ttu-id="d9552-141">如果架构准备成功，此 cmdlet 将返回**架构\_\_版本状态\_的当前**值。</span><span class="sxs-lookup"><span data-stu-id="d9552-141">This cmdlet returns a value of **SCHEMA\_VERSION\_STATE\_CURRENT** if schema preparation was successful.</span></span>

6.  <span data-ttu-id="d9552-142">等待 Active Directory 复制完成或强制执行复制。</span><span class="sxs-lookup"><span data-stu-id="d9552-142">Wait for Active Directory replication to complete or force replication.</span></span>

7.  <span data-ttu-id="d9552-143">手动验证架构更改是否已复制到所有其他域控制器。</span><span class="sxs-lookup"><span data-stu-id="d9552-143">Manually verify that the schema changes replicated to all other domain controllers.</span></span> <span data-ttu-id="d9552-144">有关详细信息，请参阅[在 Lync Server 2013 中验证 Active Directory 架构复制](lync-server-2013-verifying-schema-replication.md)。</span><span class="sxs-lookup"><span data-stu-id="d9552-144">For details, see [Verifying Active Directory schema replication in Lync Server 2013](lync-server-2013-verifying-schema-replication.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d9552-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d9552-145">See Also</span></span>


[<span data-ttu-id="d9552-146">在 Lync Server 2013 中验证 Active Directory 架构复制</span><span class="sxs-lookup"><span data-stu-id="d9552-146">Verifying Active Directory schema replication in Lync Server 2013</span></span>](lync-server-2013-verifying-schema-replication.md)  


[<span data-ttu-id="d9552-147">在 Lync Server 2013 中准备 Active Directory 架构</span><span class="sxs-lookup"><span data-stu-id="d9552-147">Preparing the Active Directory schema in Lync Server 2013</span></span>](lync-server-2013-preparing-the-active-directory-schema.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

