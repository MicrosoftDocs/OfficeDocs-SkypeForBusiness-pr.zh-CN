---
title: 'Lync Server 2013: 安装中介服务器的文件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Install the files for Mediation Server
ms:assetid: f0f7dd15-58e1-40fd-aa7e-6db50ceafacd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412998(v=OCS.15)
ms:contentKeyID: 48185772
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60274ced1bf72a17b4c05b4908f60bde32323f12
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830004"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-the-files-for-mediation-server-in-lync-server-2013"></a><span data-ttu-id="f7991-102">在 Lync Server 2013 中安装中介服务器的文件</span><span class="sxs-lookup"><span data-stu-id="f7991-102">Install the files for Mediation Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f7991-103">_**主题上次修改时间:** 2012-08-06_</span><span class="sxs-lookup"><span data-stu-id="f7991-103">_**Topic Last Modified:** 2012-08-06_</span></span>

<span data-ttu-id="f7991-104">要成功完成此过程，应至少以本地管理员身份和至少在 RTCUniversalReadOnlyAdmins 组中具有成员身份的域用户身份登录服务器。</span><span class="sxs-lookup"><span data-stu-id="f7991-104">To successfully complete this procedure, you should be logged on to the server, at the minimum, as a local administrator and a domain user who has membership in at least the RTCUniversalReadOnlyAdmins group.</span></span>

<span data-ttu-id="f7991-105">使用本主题中的步骤运行 Lync Server 2013 部署向导, 以便在你使用拓扑生成器定义和发布池时, 在你添加到中介服务器池中的计算机上安装中介服务器的文件。</span><span class="sxs-lookup"><span data-stu-id="f7991-105">Use the steps in this topic to run Lync Server 2013 Deployment Wizard to install the files for Mediation Server on a computer that you added to a Mediation Server pool when you used Topology Builder to define and publish the pool.</span></span> <span data-ttu-id="f7991-106">在安装 "中介服务器" 时, 你还可以在中介服务器池中安装和分配每台计算机所需的证书。</span><span class="sxs-lookup"><span data-stu-id="f7991-106">When installing files Mediation Server, you also install and assign the certificate required by each computer in a Mediation Server pool.</span></span>

<span data-ttu-id="f7991-107">在此网站上, 如果你已在前端池或标准版服务器上部署了中介服务器 collocated, 则可以跳过本主题, 而[在 Lync server 2013 中继续配置中继](lync-server-2013-configuring-trunks.md)。</span><span class="sxs-lookup"><span data-stu-id="f7991-107">At this site, if you have already deployed Mediation Servers collocated on the Front End pools or Standard Edition server, you can skip this topic and, instead, continue to [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f7991-108">本主题假定你已经定义并发布了独立的中介服务器池, 如在<A href="lync-server-2013-define-a-mediation-server-in-topology-builder.md">Lync server 2013 中的拓扑生成器中定义中介服务器</A>和在部署中<A href="lync-server-2013-publish-the-topology.md">发布 Lync server 2013 中的拓扑</A>中所述。文档, 并且已验证中介服务器池中的计算机满足<A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">Lync server 2013 中的 "企业语音软件先决条件</A>" 中所述的先决条件, 以及 "<A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">安全和配置先决条件"Lync Server 2013 中的企业语音</A>。</span><span class="sxs-lookup"><span data-stu-id="f7991-108">This topic assumes that you have already defined and published a stand-alone Mediation Server pool as described in <A href="lync-server-2013-define-a-mediation-server-in-topology-builder.md">Define a Mediation Server in Topology Builder in Lync Server 2013</A> and <A href="lync-server-2013-publish-the-topology.md">Publish the topology in Lync Server 2013</A> in the Deployment documentation, and that you have verified that the computers in the Mediation Server pool meet the prerequisites described in <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">Software prerequisites for Enterprise Voice in Lync Server 2013</A> and <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">Security and configuration prerequisites for Enterprise Voice in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a><span data-ttu-id="f7991-109">为独立的中介服务器池安装文件</span><span class="sxs-lookup"><span data-stu-id="f7991-109">To install the files for a stand-alone Mediation Server pool</span></span>

1.  <span data-ttu-id="f7991-110">在安装媒体中\<, 右键单击 "安装媒体\>**\\设置\\amd64\\**setup.exe", 然后单击 "**以管理员身份运行**"。</span><span class="sxs-lookup"><span data-stu-id="f7991-110">From the installation media, right-click \<installation media\>**\\Setup\\amd64\\Setup.exe**, and then click **Run as Administrator**.</span></span>

2.  <span data-ttu-id="f7991-111">在“安装位置”\*\*\*\* 页上，单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f7991-111">On the **Installation Location** page, click **OK**.</span></span>

3.  <span data-ttu-id="f7991-p102">在“最终用户许可协议”\*\*\*\* 页上，单击“我接受”\*\*\*\*，然后单击“确定”\*\*\*\*。（必须单击该按钮才能继续。）</span><span class="sxs-lookup"><span data-stu-id="f7991-p102">On the **End User License Agreement** page, click **I accept**, and then click **OK**. (Required to continue.)</span></span>

4.  <span data-ttu-id="f7991-114">在 " **Lync server 2010 部署向导**" 页面上, 单击 "**安装或更新 Lync Server 系统**"。</span><span class="sxs-lookup"><span data-stu-id="f7991-114">On the **Lync Server 2010 Deployment Wizard** page, click **Install or Update Lync Server System**.</span></span>

5.  <span data-ttu-id="f7991-115">单击“步骤 1: 安装本地配置存储”\*\*\*\* 旁边的“运行”\*\*\*\*，然后按照屏幕上的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="f7991-115">Next to **Step 1: Install Local Configuration Store**, click **Run**, and then follow the instructions on the screen.</span></span>

6.  <span data-ttu-id="f7991-116">在“配置中央管理存储的本地副本”\*\*\*\* 页上，接受默认的“直接从中央管理存储检索”\*\*\*\*，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f7991-116">On the **Configure Local Replica of Central Management Store** page, accept the default **Retrieve directly from the Central Management Store**, and then click **Next**.</span></span>

7.  <span data-ttu-id="f7991-117">在“正在执行命令”\*\*\*\* 页上，当任务状态显示为“已完成”\*\*\*\* 时，单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f7991-117">On the **Executing Commands** page, when the task status is shown as **Completed**, click **Finish**.</span></span>

8.  <span data-ttu-id="f7991-118">在 "**步骤 2: 设置" 或 "删除 Lync 服务器组件**" 旁边, 单击 "**运行**", 然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="f7991-118">Next to **Step 2: Setup or Remove Lync Server Components**, click **Run**, and then click **Next**.</span></span>

9.  <span data-ttu-id="f7991-119">在“正在执行命令”\*\*\*\* 页上，当任务状态显示为“已完成”\*\*\*\* 时，单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f7991-119">On the **Executing Commands** page, when the task status is shown as **Completed**, click **Finish**.</span></span>

10. <span data-ttu-id="f7991-p103">单击“步骤 3: 请求、安装或分配证书”\*\*\*\* 旁边的“运行”\*\*\*\*。按照屏幕上的说明进行操作，接受默认设置。中介服务器需要一个证书，因此要运行“步骤 3”\*\*\*\* 两次：第一次是颁发所需证书，第二次是分配该证书。</span><span class="sxs-lookup"><span data-stu-id="f7991-p103">Next to **Step 3: Request, Install or Assign Certificates**, click **Run**. Follow the instructions on the screen, accepting the default settings. The Mediation Server requires one certificate, and so you will run **Step 3** twice: once to issue the required certificate, and once more to assign it.</span></span>

11. <span data-ttu-id="f7991-123">正确颁发并分配证书后，在“步骤 4: 启动服务”\*\*\*\* 旁边，单击“运行”\*\*\*\*，然后按照屏幕上的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="f7991-123">When the certificate has been issued and assigned correctly, beside **Step 4: Start Services**, click **Run**, and then follow the instructions on the screen.</span></span>

12. <span data-ttu-id="f7991-124">成功完成“步骤 4”\*\*\*\* 后，重新启动服务器，然后以 DomainAdmins 组的成员身份登录到服务器。</span><span class="sxs-lookup"><span data-stu-id="f7991-124">When **Step 4** has completed successfully, restart the server, and log on to the server as a member of the DomainAdmins group.</span></span>

13. <span data-ttu-id="f7991-125">在运行 Lync Server "控制面板" 的计算机上, 验证中介服务器的服务状态是否显示为绿色复选标记的 "Lync Server 控制面板" 的 "**拓扑**" 页面。</span><span class="sxs-lookup"><span data-stu-id="f7991-125">On the computer where you are running Lync Server Control Panel, verify on the **Topology** page of Lync Server Control Panel that the service status of the Mediation Server is shown as a green check mark.</span></span> <span data-ttu-id="f7991-126">如果显示红色 X，请选择相应的中介服务器。</span><span class="sxs-lookup"><span data-stu-id="f7991-126">If a red X appears instead, select the Mediation Server.</span></span> <span data-ttu-id="f7991-127">在“操作”\*\*\*\* 菜单上，单击“启动所有服务”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f7991-127">On the **Action** menu, click **Start All Services**.</span></span>

<span data-ttu-id="f7991-128">如果向中介服务器池添加了多台计算机, 请在中介服务器池中的所有其他计算机上执行此过程中的步骤。</span><span class="sxs-lookup"><span data-stu-id="f7991-128">If you added more than one computer to the Mediation Server pool, perform the steps in this procedure on all other computers in the Mediation Server pool.</span></span> <span data-ttu-id="f7991-129">如果不需要为任何其他计算机安装中介服务器的文件, 请按照在[Lync server 2013 中配置中继中](lync-server-2013-configuring-trunks.md)的过程配置此中介服务器池 (或所有中介) 之间的中继连接设置。站点上的服务器) 及其对等。</span><span class="sxs-lookup"><span data-stu-id="f7991-129">If you do not need to install files for Mediation Server for any other computers, then follow the procedures in [Configuring trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md) to configure settings for the trunk connection between this Mediation Server pool (or all Mediation Servers at a site) and its peer.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f7991-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f7991-130">See Also</span></span>


[<span data-ttu-id="f7991-131">Lync Server 2013 中内部服务器的证书要求</span><span class="sxs-lookup"><span data-stu-id="f7991-131">Certificate requirements for internal servers in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-internal-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

