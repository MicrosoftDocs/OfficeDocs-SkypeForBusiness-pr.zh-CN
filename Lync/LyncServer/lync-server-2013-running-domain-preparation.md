---
title: Lync Server 2013：运行域准备
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running domain preparation
ms:assetid: 95dab800-1f2c-4506-b36c-99986643b149
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398761(v=OCS.15)
ms:contentKeyID: 48184847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 408dea780b4136f86ffed30d199d1d0ee63d6821
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765060"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="running-domain-preparation-for-lync-server-2013"></a><span data-ttu-id="2e1e8-102">为 Lync Server 2013 运行域准备</span><span class="sxs-lookup"><span data-stu-id="2e1e8-102">Running domain preparation for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2e1e8-103">_**主题上次修改时间：** 2013-04-16_</span><span class="sxs-lookup"><span data-stu-id="2e1e8-103">_**Topic Last Modified:** 2013-04-16_</span></span>

<span data-ttu-id="2e1e8-104">你可以使用安装程序或 Lync Server Management Shell cmdlet 准备域。</span><span class="sxs-lookup"><span data-stu-id="2e1e8-104">You can use Setup or Lync Server Management Shell cmdlets to prepare domains.</span></span> <span data-ttu-id="2e1e8-105">准备域的 cmdlet 为**Enable-CsAdDomain**。</span><span class="sxs-lookup"><span data-stu-id="2e1e8-105">The cmdlet that prepares a domain is **Enable-CsAdDomain**.</span></span>

<span data-ttu-id="2e1e8-106">域准备是为 Lync Server 2013 准备 Active Directory 域服务的最后一步。</span><span class="sxs-lookup"><span data-stu-id="2e1e8-106">Domain preparation is the final step in preparing Active Directory Domain Services for Lync Server 2013.</span></span>

<div>

## <a name="to-use-setup-to-prepare-domains"></a><span data-ttu-id="2e1e8-107">使用安装程序准备域</span><span class="sxs-lookup"><span data-stu-id="2e1e8-107">To use Setup to prepare domains</span></span>

1.  <span data-ttu-id="2e1e8-108">以域管理员组的成员身份登录域中的任何服务器。</span><span class="sxs-lookup"><span data-stu-id="2e1e8-108">Log on to any server in the domain as a member of the Domain Admins group.</span></span>

2.  <span data-ttu-id="2e1e8-109">从 Lync Server 2013 安装文件夹或媒体中，运行 Setup.exe 以启动 Lync Server 部署向导。</span><span class="sxs-lookup"><span data-stu-id="2e1e8-109">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Lync Server Deployment Wizard.</span></span>

3.  <span data-ttu-id="2e1e8-110">单击“**准备 Active Directory**”，然后等待确定部署状态。</span><span class="sxs-lookup"><span data-stu-id="2e1e8-110">Click **Prepare Active Directory**, and then wait for the deployment state to be determined.</span></span>

4.  <span data-ttu-id="2e1e8-111">在“**步骤 5：准备当前域**”中，单击“**运行**”。</span><span class="sxs-lookup"><span data-stu-id="2e1e8-111">At **Step 5: Prepare Current Domain**, click **Run**.</span></span>

5.  <span data-ttu-id="2e1e8-112">在 "**准备域**" 页面上，单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="2e1e8-112">On the **Prepare Domain** page, click **Next**.</span></span>

6.  <span data-ttu-id="2e1e8-113">在“**正在执行命令**”页上，查找“**任务状态：已完成**”，然后单击“**查看日志**”。</span><span class="sxs-lookup"><span data-stu-id="2e1e8-113">On the **Executing Commands** page, look for **Task status: Completed**, and then click **View Log**.</span></span>

7.  <span data-ttu-id="2e1e8-114">在 "**操作**" 列下，展开 "**域准备**"，查找每个任务末尾的\*\* \<\>成功**执行结果，验证域准备是否成功完成，关闭日志，然后单击 "**完成\*\*"。</span><span class="sxs-lookup"><span data-stu-id="2e1e8-114">Under the **Action** column, expand **Domain Prep**, look for a **\<Success\>** Execution Result at the end of each task to verify that domain preparation completed successfully, close the log, and then click **Finish**.</span></span>

8.  <span data-ttu-id="2e1e8-115">等待 Active Directory 复制完成或强制复制到林根域控制器的 Active Directory 站点和服务管理单元中列出的所有域控制器。</span><span class="sxs-lookup"><span data-stu-id="2e1e8-115">Wait for Active Directory replication to complete or force replication to all the domain controllers listed in the Active Directory Sites and Services snap-in for the forest root domain controller.</span></span>

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-domain"></a><span data-ttu-id="2e1e8-116">使用 cmdlet 准备域</span><span class="sxs-lookup"><span data-stu-id="2e1e8-116">To use cmdlets to prepare the domain</span></span>

1.  <span data-ttu-id="2e1e8-117">以域管理员组的成员身份登录域中的任何服务器。</span><span class="sxs-lookup"><span data-stu-id="2e1e8-117">Log on to any server in the domain as a member of the Domain Admins group.</span></span>

2.  <span data-ttu-id="2e1e8-118">安装 Lync Server Core 组件，如下所示：</span><span class="sxs-lookup"><span data-stu-id="2e1e8-118">Install Lync Server Core components as follows:</span></span>
    
    1.  <span data-ttu-id="2e1e8-119">从 Lync Server 2013 安装文件夹或媒体中，运行 Setup.exe 以启动 Lync Server 部署向导。</span><span class="sxs-lookup"><span data-stu-id="2e1e8-119">From the Lync Server 2013 installation folder or media, run Setup.exe to start the Lync Server Deployment Wizard.</span></span>
    
    2.  <span data-ttu-id="2e1e8-120">如果系统提示您安装 Microsoft Visual c + + 可再发行组件，请单击 **"是"**。</span><span class="sxs-lookup"><span data-stu-id="2e1e8-120">If you are prompted to install the Microsoft Visual C++ Redistributable, click **Yes**.</span></span>
    
    3.  <span data-ttu-id="2e1e8-121">"Lync Server 2013 设置" 对话框提示你输入安装 Lync Server 文件的位置。</span><span class="sxs-lookup"><span data-stu-id="2e1e8-121">The Lync Server 2013 Setup dialog box prompts you for a location to install the Lync Server files.</span></span> <span data-ttu-id="2e1e8-122">选择默认位置或**浏览**到您选择的位置，然后单击 "**安装**"。</span><span class="sxs-lookup"><span data-stu-id="2e1e8-122">Choose the default location or **Browse** to a location of your choice, and then click **Install**.</span></span>
    
    4.  <span data-ttu-id="2e1e8-123">在 "许可协议" 页面上，选中 "**我接受许可协议中的条款**"，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="2e1e8-123">On the License Agreement page, check **I accept the terms in the license agreement**, and then click **OK**.</span></span> <span data-ttu-id="2e1e8-124">安装程序安装 Lync Server 2013 核心组件。</span><span class="sxs-lookup"><span data-stu-id="2e1e8-124">The installer installs the Lync Server 2013 Core Components.</span></span>

3.  <span data-ttu-id="2e1e8-125">启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="2e1e8-125">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="2e1e8-126">运行：</span><span class="sxs-lookup"><span data-stu-id="2e1e8-126">Run:</span></span>
    
        Enable-CsAdDomain [-Domain <DomainFQDN>] 
    
    <span data-ttu-id="2e1e8-127">例如：</span><span class="sxs-lookup"><span data-stu-id="2e1e8-127">For example:</span></span>
    
        Enable-CsAdDomain -Domain domain1.contoso.net 
    
    <span data-ttu-id="2e1e8-128">如果不指定 Domain 参数，则默认为本地域。</span><span class="sxs-lookup"><span data-stu-id="2e1e8-128">If you do not specify the Domain parameter, the default is the local domain.</span></span>

5.  <span data-ttu-id="2e1e8-129">验证域准备是否成功。</span><span class="sxs-lookup"><span data-stu-id="2e1e8-129">Verify that domain preparation was successful.</span></span> <span data-ttu-id="2e1e8-130">运行：</span><span class="sxs-lookup"><span data-stu-id="2e1e8-130">Run:</span></span>
    
        Get-CsAdDomain [-Domain <Domain FQDN>] [-DomainController <Domain controller FQDN>] [-GlobalCatalog <Global catalog server FQDN>] [-GlobalSettingsDomainController <Domain controller FQDN where global settings are stored>] 
    
    <span data-ttu-id="2e1e8-131">例如：</span><span class="sxs-lookup"><span data-stu-id="2e1e8-131">For example:</span></span>
    
        Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2e1e8-132">参数 GlobalSettingsDomainController 允许你指示全局设置的存储位置。</span><span class="sxs-lookup"><span data-stu-id="2e1e8-132">The parameter GlobalSettingsDomainController allows you to indicate where global settings are stored.</span></span> <span data-ttu-id="2e1e8-133">如果你的设置存储在系统容器中（这与未将全局设置迁移到配置容器的升级部署的典型设置），请在 Active Directory 林的根中定义域控制器。</span><span class="sxs-lookup"><span data-stu-id="2e1e8-133">If your settings are stored in the System container (which is typical with upgrade deployments that have not had the global settings migrated to the Configuration container), you define a domain controller in the root of your Active Directory forest.</span></span> <span data-ttu-id="2e1e8-134">如果全局设置存储在“配置”容器中（在新部署或设置已迁移到“配置”容器的升级部署中时通常是这种情况），则定义林中的任何域控制器。</span><span class="sxs-lookup"><span data-stu-id="2e1e8-134">If the global settings are in the Configuration container (which is typical with new deployments or upgrade deployments where the settings have been migrated to the Configuration container), you define any domain controller in the forest.</span></span> <span data-ttu-id="2e1e8-135">如果不指定此参数，则 cmdlet 假定设置存储在配置容器中，并引用 AD&nbsp;DS 中的任何域控制器。</span><span class="sxs-lookup"><span data-stu-id="2e1e8-135">If you do not specify this parameter, the cmdlet assumes that the settings are stored in the Configuration container and refers to any domain controller in AD&nbsp;DS.</span></span>

    
    </div>
    
    <span data-ttu-id="2e1e8-136">如果不指定**Domain**参数，则默认为本地域。</span><span class="sxs-lookup"><span data-stu-id="2e1e8-136">If you do not specify the **Domain** parameter, the default is the local domain.</span></span>
    
    <span data-ttu-id="2e1e8-137">如果域准备成功，此 cmdlet 将返回**\_LC DOMAINSETTINGS\_状态\_** 的值为 "已准备就绪"。</span><span class="sxs-lookup"><span data-stu-id="2e1e8-137">This cmdlet returns a value of **LC\_DOMAINSETTINGS\_STATE\_READY** if domain preparation was successful.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2e1e8-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2e1e8-138">See Also</span></span>


[<span data-ttu-id="2e1e8-139">使用 Cmdlet 为 Lync Server 2013 反向执行域准备</span><span class="sxs-lookup"><span data-stu-id="2e1e8-139">Using cmdlets to reverse domain preparation for Lync Server 2013</span></span>](lync-server-2013-using-cmdlets-to-reverse-domain-preparation.md)  


[<span data-ttu-id="2e1e8-140">为 Lync Server 2013 准备域</span><span class="sxs-lookup"><span data-stu-id="2e1e8-140">Preparing domains for Lync Server 2013</span></span>](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

