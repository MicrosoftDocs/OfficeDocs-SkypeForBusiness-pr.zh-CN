---
title: 将观察程序节点配置为使用受信任服务器身份验证
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a watcher node to use Trusted Server authentication
ms:assetid: 42d879ac-aa90-4ed6-b5e2-1e208711672a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204852(v=OCS.15)
ms:contentKeyID: 48184017
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7279e18c73ecca9340f57d40794a3e9eb2dd160b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741222"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-in-lync-server-2013-to-use-trusted-server-authentication"></a><span data-ttu-id="3b114-102">在 Lync Server 2013 中配置观察程序节点以使用受信任的服务器身份验证</span><span class="sxs-lookup"><span data-stu-id="3b114-102">Configuring a watcher node in Lync Server 2013 to use Trusted Server authentication</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3b114-103">_**主题上次修改时间：** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="3b114-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="3b114-104">如果你的观察程序节点计算机位于外围网络内，使用受信任服务器身份验证，可以大大减少管理税，以维护单个证书而不是多个用户帐户密码。</span><span class="sxs-lookup"><span data-stu-id="3b114-104">If your watcher node computer lies inside the perimeter network, using Trusted Server authentication can greatly reduce administration taxes to maintaining a single certificate rather than numerous user account passwords.</span></span>

<span data-ttu-id="3b114-105">配置受信任服务器身份验证的第一步是创建一个受信任的应用程序池来托管观察程序节点计算机。</span><span class="sxs-lookup"><span data-stu-id="3b114-105">The first step in configuring Trusted Server authentication is to create a trusted application pool to host the watcher node computer.</span></span> <span data-ttu-id="3b114-106">创建受信任的应用程序池后，必须随后在该观察程序节点上配置合成事务以作为受信任的应用程序运行。</span><span class="sxs-lookup"><span data-stu-id="3b114-106">After the trusted application pool has been created, you must then configure synthetic transactions on that watcher node to run as a trusted application.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="3b114-107">受信任的应用程序是以 Lync Server 2013 的一部分运行的受信任状态的应用程序，但这不是产品的内置部分。</span><span class="sxs-lookup"><span data-stu-id="3b114-107">A trusted application is an application that is given trusted status to run as part of Lync Server 2013, but that is not a built-in part of the product.</span></span> <span data-ttu-id="3b114-108">受信任状态意味着，每次运行该应用程序时，将不会要求其进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="3b114-108">Trusted status means that the application will not be challenged for authentication each time it runs.</span></span>



</div>

<span data-ttu-id="3b114-109">若要创建受信任的应用程序池，请打开 Lync Server 2013 命令行管理程序，并运行如下所示的命令：</span><span class="sxs-lookup"><span data-stu-id="3b114-109">To create a trusted application pool, open the Lync Server 2013 Management Shell and run a command similar to this:</span></span>

    New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond

<div>


> [!NOTE]
> <span data-ttu-id="3b114-110">有关前一个命令中使用的参数的详细信息，请在 Lync Server Management Shell 提示符处键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="3b114-110">For details about the parameters used in the preceding command, type the following at the Lync Server Management Shell prompt:</span></span><BR><span data-ttu-id="3b114-111">获取-帮助全新 CsTrustedApplicationPool-完全 |不再</span><span class="sxs-lookup"><span data-stu-id="3b114-111">Get-Help New-CsTrustedApplicationPool -Full | more</span></span>



</div>

<span data-ttu-id="3b114-112">创建受信任的应用程序池后，将观察程序节点计算机配置为将合成事务作为受信任的应用程序运行。</span><span class="sxs-lookup"><span data-stu-id="3b114-112">After creating the trusted application pool, configure the watcher node computer to run synthetic transactions as a trusted application.</span></span> <span data-ttu-id="3b114-113">通过使用**CsTrustedApplication** cmdlet 和类似如下的命令来完成此操作：</span><span class="sxs-lookup"><span data-stu-id="3b114-113">This is done by using the **New-CsTrustedApplication** cmdlet and a command similar to this:</span></span>

    New-CsTrustedApplication -ApplicationId STWatcherNode -TrustedApplicationPoolFqdn atl-watcher-001.litwareinc.com -Port 5061

<span data-ttu-id="3b114-114">当前面的命令完成且已创建受信任的应用程序时，请运行 Enable-CsTopology 以确保所做的更改会生效：</span><span class="sxs-lookup"><span data-stu-id="3b114-114">When the preceding command completes and the trusted application has been created, run Enable-CsTopology to make sure that the changes take effect:</span></span>

    Enable-CsTopology

<span data-ttu-id="3b114-115">运行 Enable-CsTopology 后，建议重新启动计算机。</span><span class="sxs-lookup"><span data-stu-id="3b114-115">After running Enable-CsTopology, we recommend that you restart the computer.</span></span>

<span data-ttu-id="3b114-116">若要验证是否已创建新的受信任的应用程序，请在 Lync Server Management Shell 提示符处键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="3b114-116">To verify that the new trusted application has been created, type the following at the Lync Server Management Shell prompt:</span></span>

    Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"

<div>

## <a name="configuring-a-default-certificate-on-the-watcher-node"></a><span data-ttu-id="3b114-117">在 "观察程序" 节点上配置默认证书</span><span class="sxs-lookup"><span data-stu-id="3b114-117">Configuring a Default Certificate on the Watcher Node</span></span>

<span data-ttu-id="3b114-118">每个观察程序节点都必须具有使用 Lync Server 部署向导分配的默认证书。</span><span class="sxs-lookup"><span data-stu-id="3b114-118">Each watcher node must have a Default certificate assigned by using the Lync Server Deployment Wizard.</span></span>

<span data-ttu-id="3b114-119">**分配默认证书**</span><span class="sxs-lookup"><span data-stu-id="3b114-119">**To assign a Default certificate**</span></span>

1.  <span data-ttu-id="3b114-120">单击 "**开始**"，单击 "**所有程序**"，单击 " **lync server**"，然后单击 " **lync server 部署向导**"。</span><span class="sxs-lookup"><span data-stu-id="3b114-120">Click **Start**, click **All Programs**, click **Lync Server**, and then click **Lync Server Deployment Wizard**.</span></span>

2.  <span data-ttu-id="3b114-121">在 Lync Server 部署向导中，单击 "**安装或更新 Lync Server 系统**"，然后单击标题请求下的 "**运行**" **，安装或分配证书**。</span><span class="sxs-lookup"><span data-stu-id="3b114-121">In the Lync Server Deployment Wizard, click **Install or Update Lync Server System** and then click **Run** under the heading **Request, Install, or Assign Certificate**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="3b114-122">如果禁用 "<STRONG>运行</STRONG>" 按钮，可能需要先单击 "<STRONG>安装本地配置存储</STRONG>" 下的 "<STRONG>运行</STRONG>"。</span><span class="sxs-lookup"><span data-stu-id="3b114-122">If the <STRONG>Run</STRONG> button is disabled, you may need to first click <STRONG>Run</STRONG> under <STRONG>Install Local Configuration Store</STRONG>.</span></span>

    
    </div>

3.  <span data-ttu-id="3b114-123">请执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="3b114-123">Do one of the following:</span></span>
    
      - <span data-ttu-id="3b114-124">如果您已经拥有可用作默认证书的证书，请单击证书向导中的 "**默认**"，然后单击 "**分配**"。</span><span class="sxs-lookup"><span data-stu-id="3b114-124">If you already have a certificate that can be used as the Default certificate, click **Default** in the Certificate wizard and then click **Assign**.</span></span> <span data-ttu-id="3b114-125">按照证书分配向导中的步骤分配此证书。</span><span class="sxs-lookup"><span data-stu-id="3b114-125">Follow the steps in the Certificate Assignment wizard to assign that certificate.</span></span>
    
      - <span data-ttu-id="3b114-126">如果需要申请使用默认证书的证书，请单击 "**请求**"，然后按照证书请求向导中的步骤请求该证书。</span><span class="sxs-lookup"><span data-stu-id="3b114-126">If you need to request a certificate for use the Default certificate, click **Request** and then follow the steps in the Certificate Request wizard to request that certificate.</span></span> <span data-ttu-id="3b114-127">如果您使用 Web Server 证书的默认值，则您将获得可作为默认证书分配的证书。</span><span class="sxs-lookup"><span data-stu-id="3b114-127">If you use the default values for the Web Server certificate, you get a certificate that you can assign as the Default certificate.</span></span>

</div>

<div>

## <a name="installing-and-configuring-a-watcher-node"></a><span data-ttu-id="3b114-128">安装和配置观察程序节点</span><span class="sxs-lookup"><span data-stu-id="3b114-128">Installing and Configuring a Watcher Node</span></span>

<span data-ttu-id="3b114-129">重新启动观察程序节点计算机并配置证书后，您需要运行文件 Watchernode。</span><span class="sxs-lookup"><span data-stu-id="3b114-129">After you have restarted the watcher node computer and configured a certificate, you need to run the file Watchernode.msi.</span></span> <span data-ttu-id="3b114-130">（必须在安装了 Operations Manager 代理文件和 Lync Server 2013 核心组件的计算机上运行 Watchernode。）</span><span class="sxs-lookup"><span data-stu-id="3b114-130">(You must run Watchernode.msi on a computer where both the Operations Manager agent files and the Lync Server 2013 core components are installed.)</span></span>

<span data-ttu-id="3b114-131">**安装和配置观察程序节点**</span><span class="sxs-lookup"><span data-stu-id="3b114-131">**To install and configure a watcher node**</span></span>

1.  <span data-ttu-id="3b114-132">依次单击 "**开始**"、"**所有程序**"、" **lync server**"，然后单击 " **Lync Server Management Shell**"，打开 Lync Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="3b114-132">Open the Lync Server Management Shell by clicking **Start**, clicking **All Programs**, clicking **Lync Server**, and then clicking **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="3b114-133">在 Lync Server 命令行管理器中，键入以下命令，然后按 ENTER （指定 Watchernode 副本的实际路径）：</span><span class="sxs-lookup"><span data-stu-id="3b114-133">In the Lync Server Management Shell, type the following command and then press ENTER (specify the actual path to your copy of Watchernode.msi):</span></span>
    
        C:\Tools\Watchernode.msi Authentication=TrustedServer
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="3b114-134">您也可以从命令窗口运行 Watchernode。</span><span class="sxs-lookup"><span data-stu-id="3b114-134">You can also run Watchernode.msi from a command window.</span></span> <span data-ttu-id="3b114-135">若要打开命令窗口，请单击“开始”<STRONG></STRONG>，右键单击“命令提示符”<STRONG></STRONG>，然后单击“以管理员身份运行”<STRONG></STRONG>。</span><span class="sxs-lookup"><span data-stu-id="3b114-135">To open a command window, click <STRONG>Start</STRONG>, right-click <STRONG>Command Prompt</STRONG>, and then click <STRONG>Run as administrator</STRONG>.</span></span> <span data-ttu-id="3b114-136">当 "命令" 窗口打开时，请键入相同的前述命令。</span><span class="sxs-lookup"><span data-stu-id="3b114-136">When the command window opens, type the same preceding command.</span></span>

    
    </div>

<span data-ttu-id="3b114-137">请注意，前面的命令身份验证 = TrustedServer 中的名称/值对是区分大小写的。</span><span class="sxs-lookup"><span data-stu-id="3b114-137">Note that the name/value pair in the preceding command Authentication=TrustedServer is case-sensitive.</span></span> <span data-ttu-id="3b114-138">必须严格按显示内容键入。</span><span class="sxs-lookup"><span data-stu-id="3b114-138">You must type it exactly as shown.</span></span> <span data-ttu-id="3b114-139">以下命令将失败，因为它不使用正确的字母大小写：</span><span class="sxs-lookup"><span data-stu-id="3b114-139">The following command fails because it does not use the correct letter casing:</span></span>

<span data-ttu-id="3b114-140">C：\\Tools\\Watchernode 身份验证 = trustedserver</span><span class="sxs-lookup"><span data-stu-id="3b114-140">C:\\Tools\\Watchernode.msi authentication=trustedserver</span></span>

<span data-ttu-id="3b114-141">只能将 TrustedServer 模式用于位于外围网络内的计算机。</span><span class="sxs-lookup"><span data-stu-id="3b114-141">You can use TrustedServer mode only with computers that are located within the perimeter network.</span></span> <span data-ttu-id="3b114-142">当观察程序节点在 TrustedServer 模式下运行时，管理员不必在计算机上维护测试用户密码。</span><span class="sxs-lookup"><span data-stu-id="3b114-142">When a watcher node is running in TrustedServer mode, administrators do not have to maintain test user passwords on the computer.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

