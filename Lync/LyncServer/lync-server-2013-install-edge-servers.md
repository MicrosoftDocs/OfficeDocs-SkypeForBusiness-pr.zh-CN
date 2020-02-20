---
title: Lync Server 2013：安装边缘服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install Edge Servers
ms:assetid: 1655ab69-3899-4ee4-a1cc-8243bc1bfa0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398230(v=OCS.15)
ms:contentKeyID: 48183503
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8060d72c6a5c727f0171d3082e7c17d0ed4ac5ab
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147205"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="install-edge-servers-for-lync-server-2013"></a><span data-ttu-id="54ad2-102">安装适用于 Lync Server 2013 的边缘服务器</span><span class="sxs-lookup"><span data-stu-id="54ad2-102">Install Edge Servers for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="54ad2-103">_**上次修改的主题：** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="54ad2-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="54ad2-104">您可以使用 Lync Server 部署向导在边缘服务器上安装 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="54ad2-104">You install Lync Server 2013 on Edge Servers by using Lync Server Deployment Wizard.</span></span> <span data-ttu-id="54ad2-105">通过在每台边缘服务器上运行部署向导，可以完成设置边缘服务器所需的大部分任务。</span><span class="sxs-lookup"><span data-stu-id="54ad2-105">By running the Deployment Wizard on each Edge Server, you can complete most of the tasks required to set up the Edge Server.</span></span> <span data-ttu-id="54ad2-106">若要在边缘服务器上部署 Lync Server 2013，必须已运行拓扑生成器以定义和发布边缘服务器拓扑，并将其导出到边缘服务器上提供的媒体。</span><span class="sxs-lookup"><span data-stu-id="54ad2-106">In order to deploy Lync Server 2013 on an Edge Server, you must have already run Topology Builder to define and publish your Edge Server topology, and exported it to media that is available from the Edge Server.</span></span> <span data-ttu-id="54ad2-107">有关详细信息，请参阅[Lync server 2013 中的外部用户访问应用场景](lync-server-2013-scenarios-for-external-user-access.md)和[导出 Lync server 2013 拓扑，并将其复制到外部媒体以进行边缘安装](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)。</span><span class="sxs-lookup"><span data-stu-id="54ad2-107">For details, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) and [Export your Lync Server 2013 topology and copy it to external media for edge installation](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md).</span></span>

<span data-ttu-id="54ad2-108">使用部署向导安装每台边缘服务器、安装和分配所需的证书并启动所需的服务后，您可以使用在[Lync server 2013 中配置对外部用户访问的支持](lync-server-2013-configuring-support-for-external-user-access.md)来启用和配置外部用户访问，以及在[lync Server 2013 中验证边缘部署](lync-server-2013-verifying-your-edge-deployment.md)中的信息来验证安装程序（包括服务器和客户端连接），以完成安装程序。</span><span class="sxs-lookup"><span data-stu-id="54ad2-108">After using the Deployment Wizard to install each Edge Server, install and assign the required certificates, and start the required services, you can complete the setup by using the information in [Configuring support for external user access in Lync Server 2013](lync-server-2013-configuring-support-for-external-user-access.md) to enable and configure external user access and the information in [Verifying your edge deployment in Lync Server 2013](lync-server-2013-verifying-your-edge-deployment.md) to validate the setup, including server and client connectivity.</span></span>

<div>

## <a name="to-install-an-edge-server"></a><span data-ttu-id="54ad2-109">安装边缘服务器</span><span class="sxs-lookup"><span data-stu-id="54ad2-109">To install an Edge Server</span></span>

1.  <span data-ttu-id="54ad2-110">以本地 Administrators 组成员的身份或使用具有等效用户权限的帐户登录到要安装边缘服务器的计算机。</span><span class="sxs-lookup"><span data-stu-id="54ad2-110">Log on to the computer on which you want to install your Edge Server as a member of the local Administrators group or an account with equivalent user rights and permissions.</span></span>

2.  <span data-ttu-id="54ad2-111">确保在边缘服务器上提供了使用拓扑生成器创建的拓扑配置文件，然后将其导出并复制到外部媒体（例如，访问复制拓扑配置文件的 USB 驱动器），或验证对复制文件的网络共享的访问权限。</span><span class="sxs-lookup"><span data-stu-id="54ad2-111">Ensure that the topology configuration file you created using Topology Builder, and then exported and copied to external media, is available on the Edge Server (for example, access to the USB drive onto which you copied the topology configuration file, or verify access to the network share where you copied the file).</span></span>

3.  <span data-ttu-id="54ad2-112">启动部署向导。</span><span class="sxs-lookup"><span data-stu-id="54ad2-112">Start the Deployment Wizard.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="54ad2-p102">如果收到需要安装 Microsoft Visual C++ 可再发行软件包的消息，请单击“是”<STRONG></STRONG>。在下一个对话框中，接受默认的“安装位置”<STRONG></STRONG>或单击“浏览”<STRONG></STRONG>选择备用位置，然后单击“安装”<STRONG></STRONG>。在下一个对话框中，选中“我接受许可协议中的条款”<STRONG></STRONG>复选框，然后单击“确定”<STRONG></STRONG>。</span><span class="sxs-lookup"><span data-stu-id="54ad2-p102">If you get a message saying that you need to install Microsoft Visual C++ Redistributable, click <STRONG>Yes</STRONG>. In the next dialog box, you can accept the default <STRONG>Installation Location</STRONG> or click the <STRONG>Browse</STRONG> to select an alternate location, and then click <STRONG>Install</STRONG>. In the next dialog box, select the <STRONG>I accept the terms in the license agreement</STRONG> check box, and then click <STRONG>OK</STRONG>.</span></span>

    
    </div>

4.  <span data-ttu-id="54ad2-116">在部署向导中，单击“安装或更新 Lync Server 系统”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="54ad2-116">In the Deployment Wizard, click **Install or Update Lync Server System**.</span></span>

5.  <span data-ttu-id="54ad2-117">向导确定部署状态后，对于“步骤 1. 安装本地配置存储”\*\*\*\*，单击“运行”\*\*\*\*，然后执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="54ad2-117">After the wizard determines the deployment state, for **Step 1. Install Local Configuration Store**, click **Run** and then do the following:</span></span>
    
      - <span data-ttu-id="54ad2-118">在“配置中央管理存储的本地副本”\*\*\*\* 对话框中，单击“从文件导入(建议用于边缘服务器)”\*\*\*\*，转到拓扑配置文件导出到的位置，选择 .zip 文件，单击“打开”\*\*\*\*，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="54ad2-118">In the **Configure Local Replica of Central Management Store** dialog box, click **Import from a file (Recommended for Edge Servers)**, go to the location of the exported topology configuration file, select the .zip file, click **Open**, and then click **Next**.</span></span>
    
      - <span data-ttu-id="54ad2-119">部署向导从配置文件读取配置信息，并将 XML 配置文件写入本地计算机。</span><span class="sxs-lookup"><span data-stu-id="54ad2-119">The Deployment Wizard reads the configuration information from the configuration file and writes the XML configuration file to the local computer.</span></span>
    
      - <span data-ttu-id="54ad2-120">“正在执行命令”\*\*\*\* 过程完成后，单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="54ad2-120">After the **Executing Commands** process is finished, click **Finish**.</span></span>

6.  <span data-ttu-id="54ad2-121">在部署向导中，单击 "**步骤2：设置" 或 "删除 Lync Server 组件**"，以安装在存储在本地计算机上的 XML 配置文件中指定的 lync server 2013 edge 组件。</span><span class="sxs-lookup"><span data-stu-id="54ad2-121">In the Deployment Wizard, click **Step 2: SetUp or Remove Lync Server Components** to install the Lync Server 2013 edge components specified in the XML configuration file that is stored on the local computer.</span></span>

7.  <span data-ttu-id="54ad2-122">完成安装后，请使用为[Lync Server 2013 设置边缘证书](lync-server-2013-set-up-edge-certificates.md)中的信息，以便在启动服务之前安装和分配所需的证书。</span><span class="sxs-lookup"><span data-stu-id="54ad2-122">After completing the installation, use the information in [Set up Edge certificates for Lync Server 2013](lync-server-2013-set-up-edge-certificates.md) to install and assign the required certificates before you start services.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

