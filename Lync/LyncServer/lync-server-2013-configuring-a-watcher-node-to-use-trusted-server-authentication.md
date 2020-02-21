---
title: 将观察程序节点配置为使用受信任的服务器身份验证
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
ms.openlocfilehash: 8272dc0097205749ca3c0e5d613bc3da853fc7ea
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191975"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-in-lync-server-2013-to-use-trusted-server-authentication"></a><span data-ttu-id="bc2f0-102">在 Lync Server 2013 中配置观察程序节点以使用受信任的服务器身份验证</span><span class="sxs-lookup"><span data-stu-id="bc2f0-102">Configuring a watcher node in Lync Server 2013 to use Trusted Server authentication</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bc2f0-103">_**上次修改的主题：** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="bc2f0-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="bc2f0-104">如果观察程序节点计算机位于外围网络中，则使用受信任服务器身份验证可大大降低管理负担，只需维护单个证书即可，而无需维护大量用户帐户密码。</span><span class="sxs-lookup"><span data-stu-id="bc2f0-104">If your watcher node computer lies inside the perimeter network, using Trusted Server authentication can greatly reduce administration taxes to maintaining a single certificate rather than numerous user account passwords.</span></span>

<span data-ttu-id="bc2f0-p101">配置受信任服务器身份验证的第一步是创建受信任应用程序池以承载观察程序节点计算机。在创建受信任应用程序池后，您必须对观察程序节点上的综合事务进行配置，使其作为受信任应用程序运行。</span><span class="sxs-lookup"><span data-stu-id="bc2f0-p101">The first step in configuring Trusted Server authentication is to create a trusted application pool to host the watcher node computer. After the trusted application pool has been created, you must then configure synthetic transactions on that watcher node to run as a trusted application.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="bc2f0-107">受信任的应用程序是具有受信任状态的应用程序，可作为 Lync Server 2013 的一部分运行，但这并不是产品的内置部件。</span><span class="sxs-lookup"><span data-stu-id="bc2f0-107">A trusted application is an application that is given trusted status to run as part of Lync Server 2013, but that is not a built-in part of the product.</span></span> <span data-ttu-id="bc2f0-108">受信任的状态意味着，每次运行该应用程序时，将不会要求其进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="bc2f0-108">Trusted status means that the application will not be challenged for authentication each time it runs.</span></span>



</div>

<span data-ttu-id="bc2f0-109">若要创建受信任的应用程序池，请打开 Lync Server 2013 命令行管理程序，并运行与以下内容类似的命令：</span><span class="sxs-lookup"><span data-stu-id="bc2f0-109">To create a trusted application pool, open the Lync Server 2013 Management Shell and run a command similar to this:</span></span>

    New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond

<div>


> [!NOTE]
> <span data-ttu-id="bc2f0-110">有关上述命令中使用的参数的详细信息，请在 Lync Server 命令行管理程序提示符处键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="bc2f0-110">For details about the parameters used in the preceding command, type the following at the Lync Server Management Shell prompt:</span></span><BR><span data-ttu-id="bc2f0-111">Get-Help New-CsTrustedApplicationPool -Full | more</span><span class="sxs-lookup"><span data-stu-id="bc2f0-111">Get-Help New-CsTrustedApplicationPool -Full | more</span></span>



</div>

<span data-ttu-id="bc2f0-112">在创建受信任的应用程序池之后，可将观察程序节点计算机配置为将综合事务作为受信任的应用程序运行。</span><span class="sxs-lookup"><span data-stu-id="bc2f0-112">After creating the trusted application pool, configure the watcher node computer to run synthetic transactions as a trusted application.</span></span> <span data-ttu-id="bc2f0-113">这可以通过使用 **New-CsTrustedApplication** cmdlet 和类似于以下内容的命令来实现的：</span><span class="sxs-lookup"><span data-stu-id="bc2f0-113">This is done by using the **New-CsTrustedApplication** cmdlet and a command similar to this:</span></span>

    New-CsTrustedApplication -ApplicationId STWatcherNode -TrustedApplicationPoolFqdn atl-watcher-001.litwareinc.com -Port 5061

<span data-ttu-id="bc2f0-114">在完成上述命令并创建受信任的应用程序之后，请运行 Enable-CsTopology 以确保更改生效：</span><span class="sxs-lookup"><span data-stu-id="bc2f0-114">When the preceding command completes and the trusted application has been created, run Enable-CsTopology to make sure that the changes take effect:</span></span>

    Enable-CsTopology

<span data-ttu-id="bc2f0-115">运行 Enable-CsTopology 之后，建议您重新启动计算机。</span><span class="sxs-lookup"><span data-stu-id="bc2f0-115">After running Enable-CsTopology, we recommend that you restart the computer.</span></span>

<span data-ttu-id="bc2f0-116">若要验证是否已创建新的受信任应用程序，请在 Lync Server 命令行管理程序提示符处键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="bc2f0-116">To verify that the new trusted application has been created, type the following at the Lync Server Management Shell prompt:</span></span>

    Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"

<div>

## <a name="configuring-a-default-certificate-on-the-watcher-node"></a><span data-ttu-id="bc2f0-117">在观察程序节点上配置默认证书</span><span class="sxs-lookup"><span data-stu-id="bc2f0-117">Configuring a Default Certificate on the Watcher Node</span></span>

<span data-ttu-id="bc2f0-118">每个观察程序节点都必须有一个使用 Lync Server 部署向导分配的默认证书。</span><span class="sxs-lookup"><span data-stu-id="bc2f0-118">Each watcher node must have a Default certificate assigned by using the Lync Server Deployment Wizard.</span></span>

<span data-ttu-id="bc2f0-119">**分配默认证书**</span><span class="sxs-lookup"><span data-stu-id="bc2f0-119">**To assign a Default certificate**</span></span>

1.  <span data-ttu-id="bc2f0-120">依次单击 "**开始**"、"**所有程序**"、" **Lync Server**" 和 " **lync server 部署向导**"。</span><span class="sxs-lookup"><span data-stu-id="bc2f0-120">Click **Start**, click **All Programs**, click **Lync Server**, and then click **Lync Server Deployment Wizard**.</span></span>

2.  <span data-ttu-id="bc2f0-121">在 "Lync Server 部署向导" 中，单击 "**安装或更新 Lync Server 系统**"，然后在标题**请求、"安装" 或 "分配证书**" 下单击 "**运行**"。</span><span class="sxs-lookup"><span data-stu-id="bc2f0-121">In the Lync Server Deployment Wizard, click **Install or Update Lync Server System** and then click **Run** under the heading **Request, Install, or Assign Certificate**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="bc2f0-122">如果禁用“运行”<STRONG></STRONG>按钮，则您可能需要先单击“安装本地配置存储”<STRONG></STRONG>下方的“运行”<STRONG></STRONG>。</span><span class="sxs-lookup"><span data-stu-id="bc2f0-122">If the <STRONG>Run</STRONG> button is disabled, you may need to first click <STRONG>Run</STRONG> under <STRONG>Install Local Configuration Store</STRONG>.</span></span>

    
    </div>

3.  <span data-ttu-id="bc2f0-123">执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="bc2f0-123">Do one of the following:</span></span>
    
      - <span data-ttu-id="bc2f0-p104">如果您已有一个可用作默认证书的证书，请单击证书向导中的“默认”\*\*\*\*，然后单击“分配”\*\*\*\*。按照证书分配向导中的步骤进行操作以分配此证书。</span><span class="sxs-lookup"><span data-stu-id="bc2f0-p104">If you already have a certificate that can be used as the Default certificate, click **Default** in the Certificate wizard and then click **Assign**. Follow the steps in the Certificate Assignment wizard to assign that certificate.</span></span>
    
      - <span data-ttu-id="bc2f0-p105">如果您需要请求用作默认证书的证书，请单击“请求”\*\*\*\*，然后按照证书请求向导中的步骤进行操作以请求该证书。如果您使用 Web Server 证书的默认值，则您将获得可作为默认证书分配的证书。</span><span class="sxs-lookup"><span data-stu-id="bc2f0-p105">If you need to request a certificate for use the Default certificate, click **Request** and then follow the steps in the Certificate Request wizard to request that certificate. If you use the default values for the Web Server certificate, you get a certificate that you can assign as the Default certificate.</span></span>

</div>

<div>

## <a name="installing-and-configuring-a-watcher-node"></a><span data-ttu-id="bc2f0-128">安装和配置观察程序节点</span><span class="sxs-lookup"><span data-stu-id="bc2f0-128">Installing and Configuring a Watcher Node</span></span>

<span data-ttu-id="bc2f0-129">在重新启动观察程序节点计算机并配置证书后，您需要运行文件 Watchernode.msi。</span><span class="sxs-lookup"><span data-stu-id="bc2f0-129">After you have restarted the watcher node computer and configured a certificate, you need to run the file Watchernode.msi.</span></span> <span data-ttu-id="bc2f0-130">（必须在同时安装了 Operations Manager 代理文件和 Lync Server 2013 核心组件的计算机上运行 Watchernode.msi。）</span><span class="sxs-lookup"><span data-stu-id="bc2f0-130">(You must run Watchernode.msi on a computer where both the Operations Manager agent files and the Lync Server 2013 core components are installed.)</span></span>

<span data-ttu-id="bc2f0-131">**安装和配置观察程序节点**</span><span class="sxs-lookup"><span data-stu-id="bc2f0-131">**To install and configure a watcher node**</span></span>

1.  <span data-ttu-id="bc2f0-132">依次单击 "**开始**"、"**所有程序**"、" **lync server**"，然后单击 " **Lync Server Management Shell**"，打开 Lync Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="bc2f0-132">Open the Lync Server Management Shell by clicking **Start**, clicking **All Programs**, clicking **Lync Server**, and then clicking **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="bc2f0-133">在 Lync Server 命令行管理程序中，键入以下命令，然后按 ENTER （指定 Watchernode.msi 副本的实际路径）：</span><span class="sxs-lookup"><span data-stu-id="bc2f0-133">In the Lync Server Management Shell, type the following command and then press ENTER (specify the actual path to your copy of Watchernode.msi):</span></span>
    
        C:\Tools\Watchernode.msi Authentication=TrustedServer
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="bc2f0-p107">您还可以从命令窗口运行 Watchernode.msi。若要打开命令窗口，请单击“开始”<STRONG></STRONG>，右键单击“命令提示符”<STRONG></STRONG>，然后单击“以管理员身份运行”<STRONG></STRONG>。在打开命令窗口后，键入相同的上述命令。</span><span class="sxs-lookup"><span data-stu-id="bc2f0-p107">You can also run Watchernode.msi from a command window. To open a command window, click <STRONG>Start</STRONG>, right-click <STRONG>Command Prompt</STRONG>, and then click <STRONG>Run as administrator</STRONG>. When the command window opens, type the same preceding command.</span></span>

    
    </div>

<span data-ttu-id="bc2f0-p108">请注意，上述命令 Authentication=TrustedServer 中的名称/值对是区分大小写的。您必须如上所示准确地键入该命令。以下命令就是由于没有使用正确的字母大小写而失败了：</span><span class="sxs-lookup"><span data-stu-id="bc2f0-p108">Note that the name/value pair in the preceding command Authentication=TrustedServer is case-sensitive. You must type it exactly as shown. The following command fails because it does not use the correct letter casing:</span></span>

<span data-ttu-id="bc2f0-140">C：\\Tools\\watchernode.msi authentication = trustedserver</span><span class="sxs-lookup"><span data-stu-id="bc2f0-140">C:\\Tools\\Watchernode.msi authentication=trustedserver</span></span>

<span data-ttu-id="bc2f0-p109">您只能对外围网络中的计算机使用 TrustedServer 模式。当观察程序节点在 TrustedServer 模式中运行时，管理员无需维护计算机上的测试用户密码。</span><span class="sxs-lookup"><span data-stu-id="bc2f0-p109">You can use TrustedServer mode only with computers that are located within the perimeter network. When a watcher node is running in TrustedServer mode, administrators do not have to maintain test user passwords on the computer.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

