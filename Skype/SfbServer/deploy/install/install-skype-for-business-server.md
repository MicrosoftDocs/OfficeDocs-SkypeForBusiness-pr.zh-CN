---
title: 在拓扑内的服务器上安装 Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: defd6b2c-f267-4f8c-bc94-8894e2a429b6
description: 摘要：了解如何在拓扑中的每台服务器上安装 Skype for Business Server 系统组件。 从 Microsoft 评估中心的以下位置下载 Skype for Business Server 的免费试用版：https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server。
ms.openlocfilehash: 8ecf298809a6c4c37b5c075e7ac16623f1669ff9
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41791750"
---
# <a name="install-skype-for-business-server-on-servers-in-the-topology"></a><span data-ttu-id="c36b5-104">在拓扑内的服务器上安装 Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c36b5-104">Install Skype for Business Server on servers in the topology</span></span>
 
<span data-ttu-id="c36b5-105">**摘要：** 了解如何在拓扑中的每台服务器上安装 Skype for Business Server 系统组件。</span><span class="sxs-lookup"><span data-stu-id="c36b5-105">**Summary:** Learn how to install the Skype for Business Server system components on each server in the topology.</span></span> <span data-ttu-id="c36b5-106">从[Microsoft 评估中心](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)下载 Skype For business 服务器的免费试用版。</span><span class="sxs-lookup"><span data-stu-id="c36b5-106">Download a free trial of Skype for Business Server from the [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="c36b5-107">将拓扑加载到中央管理存储并且 Active Directory 知道哪些服务器将执行哪些角色后，你需要在拓扑中的每台服务器上安装 Skype for Business Server 系统。</span><span class="sxs-lookup"><span data-stu-id="c36b5-107">Once the topology is loaded into the Central Management Store and Active Directory knows which servers will perform which roles, you need to install the Skype for Business Server system on each of the servers in the topology.</span></span> <span data-ttu-id="c36b5-108">您可以按照任意顺序完成第 1 步至第 5 步。</span><span class="sxs-lookup"><span data-stu-id="c36b5-108">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="c36b5-109">但第 6、7、8 步必须在第 1 步至第 5 步之后按照图表所示顺序依次完成。</span><span class="sxs-lookup"><span data-stu-id="c36b5-109">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5 as outlined in the diagram.</span></span> <span data-ttu-id="c36b5-110">安装 Skype for Business 服务器系统是第7步，共8步。</span><span class="sxs-lookup"><span data-stu-id="c36b5-110">Installing the Skype for Business Server system is step 7 of 8.</span></span>
  
![概述图表。](../../media/6855713d-a5b4-4e5b-8f83-fef3d7a5ec5d.png)
  
## <a name="install-skype-for-business-server-system"></a><span data-ttu-id="c36b5-112">安装 Skype for Business 服务器系统</span><span class="sxs-lookup"><span data-stu-id="c36b5-112">Install Skype for Business Server system</span></span>

<span data-ttu-id="c36b5-113">发布拓扑后，您可以在拓扑结构中的每台服务器上安装 Skype for Business 服务器组件。</span><span class="sxs-lookup"><span data-stu-id="c36b5-113">Once you have published a topology, you can install the Skype for Business Server components on each server in the topology.</span></span> <span data-ttu-id="c36b5-114">本部分将引导你完成以下步骤：安装 Skype for Business Server 和设置前端池的服务器角色以及与前端服务器 collocated 的任何服务器角色。</span><span class="sxs-lookup"><span data-stu-id="c36b5-114">This section guides you through installing Skype for Business Server and setting up the server roles for the Front End pool and any server roles that are collocated with the Front End servers.</span></span> <span data-ttu-id="c36b5-115">若要安装和设置服务器角色，请在要安装服务器角色的每台计算机上运行 Skype for Business 服务器部署向导。</span><span class="sxs-lookup"><span data-stu-id="c36b5-115">To install and set up server roles, you run the Skype for Business Server Deployment Wizard on each computer on which you are installing a server role.</span></span> <span data-ttu-id="c36b5-116">使用部署向导完成所有四个部署步骤，包括安装本地配置存储、安装前端服务器、配置证书和启动服务。</span><span class="sxs-lookup"><span data-stu-id="c36b5-116">You use the Deployment Wizard to complete all four deployment steps, including installing the Local Configuration store, installing the Front End Servers, configuring certificates, and starting services.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="c36b5-117">必须使用拓扑生成器完成并发布拓扑，然后才能在服务器上安装 Skype for Business 服务器。</span><span class="sxs-lookup"><span data-stu-id="c36b5-117">You must use Topology Builder to complete and publish the topology before you can install Skype for Business Server on servers.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="c36b5-118">必须对拓扑中的所有服务器完成此步骤。</span><span class="sxs-lookup"><span data-stu-id="c36b5-118">This procedure must be completed for all servers in the topology.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="c36b5-119">在前端服务器上安装 Skype for Business 服务器后，首次启动服务时，必须确保 Windows 防火墙服务在服务器上运行。</span><span class="sxs-lookup"><span data-stu-id="c36b5-119">After you install Skype for Business Server on a Front End Server, the first time you start services, you must make sure that the Windows Firewall Service is running on the server.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="c36b5-120">在执行这些步骤之前，请确保你使用既是本地管理员又是 RTCUniversalServerAdmins 组成员的域用户帐户登录到服务器。</span><span class="sxs-lookup"><span data-stu-id="c36b5-120">Before you follow these steps, make sure you're logged onto the server with a domain user account that's both a local administrator and a member of the RTCUniversalServerAdmins group.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="c36b5-121">如果以前未在此服务器上运行 Skype for Business Server 设置，系统将提示你输入安装的驱动器和路径。</span><span class="sxs-lookup"><span data-stu-id="c36b5-121">If you haven't run Skype for Business Server setup on this server before, you'll be prompted for a drive and path for the installation.</span></span> <span data-ttu-id="c36b5-122">如果您的组织要求安装到系统驱动器之外的某个驱动器上或者您考虑空间问题，这将允许您安装到非系统驱动器上。</span><span class="sxs-lookup"><span data-stu-id="c36b5-122">This provides the capability to install to a drive other than the system drive, if your organization requires it, or if you have space concerns.</span></span> <span data-ttu-id="c36b5-123">你可以在 "**设置**" 对话框中将 Skype For business 服务器文件的安装位置路径更改为新的可用驱动器。</span><span class="sxs-lookup"><span data-stu-id="c36b5-123">You can change the installation location path for the Skype for Business Server files in the **Setup** dialog box to a new, available drive.</span></span> <span data-ttu-id="c36b5-124">如果将安装文件安装到此路径（包括 OCSCore），则 Skype for business 服务器文件的其余部分也将部署到其中。</span><span class="sxs-lookup"><span data-stu-id="c36b5-124">If you install the Setup files to this path, including OCSCore.msi, the rest of the Skype for Business Server files will deploy there as well.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="c36b5-125">开始安装之前，请确保 Windows Server 是使用 Windows 更新的最新版本。</span><span class="sxs-lookup"><span data-stu-id="c36b5-125">Before you begin the installation, make sure that Windows Server is up-to-date by using Windows Update.</span></span> 
  
![Windows Server 最新版本。](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
### <a name="install-skype-for-business-server-system"></a><span data-ttu-id="c36b5-127">安装 Skype for Business 服务器系统</span><span class="sxs-lookup"><span data-stu-id="c36b5-127">Install Skype for Business Server system</span></span>

1. <span data-ttu-id="c36b5-128">插入 Skype for Business 服务器安装媒体。</span><span class="sxs-lookup"><span data-stu-id="c36b5-128">Insert the Skype for Business Server installation media.</span></span> <span data-ttu-id="c36b5-129">如果安装未自动开始，请双击“**安装**”。</span><span class="sxs-lookup"><span data-stu-id="c36b5-129">If the setup does not automatically begin, double-click **Setup**.</span></span>
    
2. <span data-ttu-id="c36b5-p107">安装介质需要 Microsoft Visual C++ 才能运行。将有一个对话框弹出，询问您是否要安装。单击“**是**”。</span><span class="sxs-lookup"><span data-stu-id="c36b5-p107">The installation media requires Microsoft Visual C++ to run. A dialog will pop up asking if you want to install it. Click **Yes.**</span></span>
    
3. <span data-ttu-id="c36b5-133">仔细阅读许可协议，如果同意条款，请选择“**我接受许可协议中的条款**”，然后单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="c36b5-133">Carefully review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and click **OK**.</span></span> 
    
4. <span data-ttu-id="c36b5-134">智能设置是 Skype for Business 服务器中的一项功能，您可以在其中连接到 Internet 以在安装过程中检查来自 Microsoft Update （MU）的更新，如图所示。</span><span class="sxs-lookup"><span data-stu-id="c36b5-134">Smart Setup is a feature in Skype for Business Server where you can connect to the Internet to check for updates from Microsoft Update (MU) during the installation process, as shown in the figure.</span></span> <span data-ttu-id="c36b5-135">这能确保你获得最新产品更新，从而提供更好的体验。</span><span class="sxs-lookup"><span data-stu-id="c36b5-135">This provides a better experience by making sure you have the most recent updates for the product.</span></span> <span data-ttu-id="c36b5-136">单击“**安装**”开始安装。</span><span class="sxs-lookup"><span data-stu-id="c36b5-136">Click **Install** to begin the installation.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c36b5-137">很多组织在其企业环境中部署了 Windows Server Update Services (WSUS)。</span><span class="sxs-lookup"><span data-stu-id="c36b5-137">Many organizations have Windows Server Update Services (WSUS) deployed in their corporate environments.</span></span> <span data-ttu-id="c36b5-138">WSUS 可以让管理员完全管理通过 Microsoft Update 发布到其网络中的计算机的更新分发过程。</span><span class="sxs-lookup"><span data-stu-id="c36b5-138">WSUS lets administrators fully manage the distribution of updates that are released through Microsoft Update to computers in their network.</span></span> <span data-ttu-id="c36b5-139">作为累积更新1发行版 Skype for Business 服务器的一部分，引入了对智能设置的支持，以便与 WSUS 配合使用。</span><span class="sxs-lookup"><span data-stu-id="c36b5-139">As part of the Cumulative Update 1 release Skype for Business Server introduced support for Smart Setup to work with WSUS.</span></span> <span data-ttu-id="c36b5-140">如果客户首次部署 Skype for Business 服务器或从 Lync Server 2013 环境升级到 Lync Server 环境，使用就地升级功能将获得从 WSUS 获取 Skype for Windows 更新的智能设置，而不是提取更新从 MU 开始。</span><span class="sxs-lookup"><span data-stu-id="c36b5-140">Customers with WSUS who are deploying Skype for Business Server for the first time or upgrading from the Lync Server 2013 environment using the In-Place Upgrade feature will have Smart Setup fetching Skype for Windows updates from WSUS as opposed to fetching updates from MU.</span></span> <span data-ttu-id="c36b5-141">想使用智能设置的客户在运行 Setup.exe 之前，需要在所有计算机上运行 SmartSetupWithWSUS.psq。</span><span class="sxs-lookup"><span data-stu-id="c36b5-141">Customers wanting to use Smart Setup need to run the SmartSetupWithWSUS.psq on all the machines before running Setup.exe.</span></span> 
  
     ![智能设置屏幕截图。](../../media/d35c6cd9-3b8d-4510-871c-30ad07b1f4f2.png)
  
5. <span data-ttu-id="c36b5-143">在 "部署向导" 页面上，单击 "**安装或更新 Skype For Business 服务器系统**"。</span><span class="sxs-lookup"><span data-stu-id="c36b5-143">On the Deployment Wizard page, click **Install or Update Skype for Business Server System**.</span></span>
    
6. <span data-ttu-id="c36b5-144">执行以下过程中的过程，完成这些过程后，单击 "**退出**" 以关闭 "部署向导"。</span><span class="sxs-lookup"><span data-stu-id="c36b5-144">Perform the procedures in the following procedures, when you've completed them, click **Exit** to close the Deployment Wizard.</span></span> <span data-ttu-id="c36b5-145">对池中的每台前端服务器重复此过程。</span><span class="sxs-lookup"><span data-stu-id="c36b5-145">Repeat the procedures for each Front End server in the pool.</span></span>
    
### <a name="step-1-install-local-configuration-store"></a><span data-ttu-id="c36b5-146">步骤 1：安装本地配置存储</span><span class="sxs-lookup"><span data-stu-id="c36b5-146">Step 1: Install Local Configuration Store</span></span>

1. <span data-ttu-id="c36b5-147">检查前提条件，单击”**步骤 1：安装本地配置存储**”旁边的“**运行**”。</span><span class="sxs-lookup"><span data-stu-id="c36b5-147">Review the prerequisites, and then click **Run** next to **Step 1: Install Local Configuration Store**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c36b5-p111">本地配置存储是中央管理存储的只读副本。在 Standard Edition 部署中，将使用前端服务器上的 SQL Server Express Edition 本地副本创建中央管理存储。在运行“准备第一台 Standard Edition Server”流程时将出现此情况。在 Enterprise Edition 部署中，在您发布包含 Enterprise Edition 前端池的拓扑时，将会创建中央管理存储。</span><span class="sxs-lookup"><span data-stu-id="c36b5-p111">The Local Configuration Store is a read-only copy of the Central Management Store. In a Standard Edition deployment, the Central Management Store is created using a local copy of SQL Server Express Edition on the Front End server. This happens when you run the Prepare First Standard Edition Server procedure. In an Enterprise Edition deployment, the Central Management store is created when you publish the topology that includes an Enterprise Edition Front End pool.</span></span> 
  
2. <span data-ttu-id="c36b5-152">在“**安装本地配置存储**”页面上，确保选择“**直接从中央管理存储中检索**”选项，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="c36b5-152">On the **Install Local Configuration Store** page, make sure that the **Retrieve directly from the Central Management store** option is selected, and then click **Next**.</span></span>
    
    <span data-ttu-id="c36b5-p112">SQL Server Express Edition 将安装到本地服务器上。SQL Server Express Edition 是本地配置存储的必要前提。</span><span class="sxs-lookup"><span data-stu-id="c36b5-p112">SQL Server Express Edition is installed on the local server. SQL Server Express Edition is required for the local configuration store.</span></span>
    
3. <span data-ttu-id="c36b5-155">完成本地服务器配置安装后，单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="c36b5-155">When the local server configuration installation is complete, click **Finish**.</span></span>
    
### <a name="step-2-setup-or-remove-skype-for-business-server-components"></a><span data-ttu-id="c36b5-156">步骤2：设置或删除 Skype for Business 服务器组件</span><span class="sxs-lookup"><span data-stu-id="c36b5-156">Step 2: Setup or remove Skype for Business Server components</span></span>

1. <span data-ttu-id="c36b5-157">查看必备条件，然后单击 "**步骤2：设置" 或 "删除 Skype For Business 服务器组件**" 旁边的 "**运行**"。</span><span class="sxs-lookup"><span data-stu-id="c36b5-157">Review the prerequisites, and then click **Run** next to **Step 2: Setup or Remove Skype for Business Server Components**.</span></span>
    
2. <span data-ttu-id="c36b5-158">在 "**设置 Skype For Business 服务器组件**" 页面上，单击 "**下一步**" 以设置在已发布拓扑中定义的组件。</span><span class="sxs-lookup"><span data-stu-id="c36b5-158">On the **Set Up Skype for Business Server Components** page, click **Next** to set up components as defined in your published topology.</span></span>
    
3. <span data-ttu-id="c36b5-159">“**正在执行命令**”页将显示安装过程中的命令和安装信息摘要。</span><span class="sxs-lookup"><span data-stu-id="c36b5-159">The **Executing Commands** page displays a summary of commands and installation information as the set up takes place.</span></span> <span data-ttu-id="c36b5-160">完成后，你可以使用列表选择要查看的日志，然后单击 "**查看日志**"。</span><span class="sxs-lookup"><span data-stu-id="c36b5-160">When it's done, you can use the list to select a log to view, and then click **View Log**.</span></span>
    
4. <span data-ttu-id="c36b5-161">当 Skype for Business Server 组件设置完成并且你已查看所需的日志时，请单击 "**完成**" 以在安装中完成此步骤。</span><span class="sxs-lookup"><span data-stu-id="c36b5-161">When Skype for Business Server components setup is done and you've reviewed the logs as needed, click **Finish** to complete this step in the installation.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c36b5-162">如果提示重新启动服务器（如果需要安装 Windows 桌面体验则可能会发生这种情况），请执行此操作。</span><span class="sxs-lookup"><span data-stu-id="c36b5-162">Restart the server if prompted (which might happen if Windows Desktop Experience needed to be installed).</span></span> <span data-ttu-id="c36b5-163">当计算机恢复正常运行时，你需要再次运行此操作（步骤2：设置或删除 Skype for Business Server 组件）过程。</span><span class="sxs-lookup"><span data-stu-id="c36b5-163">When the computer is back up and running, you need to run this (Step 2: Setup or Remove Skype for Business Server Components) procedure again.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="c36b5-164">如果安装程序发现存在任何未满足的先决条件，系统将向您通知一条“不满足先决条件”消息，如图所示。</span><span class="sxs-lookup"><span data-stu-id="c36b5-164">If the installer finds any prerequisites that have not been satisfied, you will be notified with a "Prerequisite not satisfied" message, as shown in the figure.</span></span> <span data-ttu-id="c36b5-165">满足所需的先决条件，然后再开始（步骤2：设置或删除 Skype for Business Server 组件）过程。</span><span class="sxs-lookup"><span data-stu-id="c36b5-165">Satisfy the required prerequisite, and then start this (Step 2: Setup or Remove Skype for Business Server Components) procedure again.</span></span> 
  
     ![需要必备组件。](../../media/21a84dfe-70ff-4f76-bd7e-41032660200a.png)
  
5. <span data-ttu-id="c36b5-p116">验证前两步已经如期完成。确认显示如图所示的绿色对勾和“**完成**”字样。</span><span class="sxs-lookup"><span data-stu-id="c36b5-p116">Verify that the first two steps completed as expected. Confirm that there is a green checkmark with the word **Complete**, as shown in the figure.</span></span>
    
     ![安装组件时已完成的前两个步骤。](../../media/59851804-d805-4fa8-854b-60c3de2d109f.png)
  
6. <span data-ttu-id="c36b5-170">在安装 Skype for Business 服务器组件后，再次运行**Windows 更新**以检查是否有任何更新。</span><span class="sxs-lookup"><span data-stu-id="c36b5-170">Run **Windows Update** again to check if there are any updates after you install the Skype for Business Server Components.</span></span>
    
### <a name="step-3-request-install-or-assign-certificates"></a><span data-ttu-id="c36b5-171">步骤 3：请求、安装或分配证书</span><span class="sxs-lookup"><span data-stu-id="c36b5-171">Step 3: Request, install, or assign certificates</span></span>

1. <span data-ttu-id="c36b5-172">检查先决条件，然后单击“**步骤 3：请求、安装或分配证书**”旁边的“**运行**”。</span><span class="sxs-lookup"><span data-stu-id="c36b5-172">Review the prerequisites, and then click **Run** next to **Step 3: Request, Install or Assign Certificates**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c36b5-173">Skype for Business 服务器包括对 SHA-1 套件的支持（SHA-2 使用224、256、384或512位）的摘要哈希和签名算法的摘要哈希和签名算法来自运行 Windows 10、Windows 8、windows 7、Windows Server 2012 R2 和 Windows 的客户端的连接服务器2012或 Windows Server 2008 R2 操作系统。</span><span class="sxs-lookup"><span data-stu-id="c36b5-173">Skype for Business Server includes support for the SHA-2 suite (SHA-2 uses digest lengths of 224, 256, 384 or 512 bits) of digest hash and signing algorithms for connections from clients running the Windows 10, Windows 8, Windows 7, Windows Server 2012 R2, Windows Server 2012, or Windows Server 2008 R2 operating systems.</span></span> <span data-ttu-id="c36b5-174">要支持使用 SHA-2 套件进行外部访问，外部证书必须由公共 CA 颁发，公共 CA 也可颁发具有相同位长度摘要的证书。</span><span class="sxs-lookup"><span data-stu-id="c36b5-174">To support external access using the SHA-2 suite, the external certificate is issued by a public CA that also can issue a certificate with the same bit length digest.</span></span> 
  
    > [!IMPORTANT]
    > <span data-ttu-id="c36b5-175">选择哪种哈希摘要和签名算法取决于将使用证书的客户端和服务器，客户端和服务器将与其通信的其他计算机和设备也必须知道如何使用证书中所用的算法。</span><span class="sxs-lookup"><span data-stu-id="c36b5-175">The selection of which hash digest and signing algorithm is dependent on the clients and the servers that will use the certificate, and other computers and devices that clients and servers will communicate with who must also know how to use the algorithms used in the certificate.</span></span> <span data-ttu-id="c36b5-176">有关操作系统和某些客户端应用程序支持哪些摘要长度的信息，请参阅[WINDOWS PKI 博客 SHA2 和 windows](https://go.microsoft.com/fwlink/p/?LinkId=287002)。</span><span class="sxs-lookup"><span data-stu-id="c36b5-176">For information on which digest lengths are supported in the operating system and some client applications, see [Windows PKI blog - SHA2 and Windows](https://go.microsoft.com/fwlink/p/?LinkId=287002).</span></span> 
  
    <span data-ttu-id="c36b5-177">每台 Standard Edition 或前端服务器最多需要四个证书：oAuthTokenIssuer 证书、默认证书、Web 内部证书和 Web 外部证书。</span><span class="sxs-lookup"><span data-stu-id="c36b5-177">Each Standard Edition or Front End server requires up to four certificates: the oAuthTokenIssuer certificate, a default certificate, a web internal certificate, and a web external certificate.</span></span> <span data-ttu-id="c36b5-178">但是，也可以请求和分配单个具有相应使用者替代名称条目的默认证书以及 oAuthTokenIssuer 证书。</span><span class="sxs-lookup"><span data-stu-id="c36b5-178">However, you can request and assign a single default certificate with appropriate subject alternative name entries as well as the oAuthTokenIssuer certificate.</span></span> <span data-ttu-id="c36b5-179">有关证书要求的详细信息，请参阅 Skype for business 服务器2019的[环境要求](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)或 skype For business [Server 的服务器要求](../../../SfBServer2019/plan/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c36b5-179">For details about the certificate requirements, see [Environmental requirements for Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="c36b5-180">以下过程介绍了如何配置来自基于内部 Active Directory 证书服务的证书颁发机构的证书。</span><span class="sxs-lookup"><span data-stu-id="c36b5-180">The following procedure describes how to configure certificates from an internal Active Directory Certificate Services based certificate authority.</span></span> 
  
2. <span data-ttu-id="c36b5-181">在“**证书向导**”页上，单击“**请求**”。</span><span class="sxs-lookup"><span data-stu-id="c36b5-181">On the **Certificate Wizard** page, click **Request**.</span></span>
    
3. <span data-ttu-id="c36b5-182">在“**证书请求**”页上，填写相关数据，包括选择 SIP 域在内，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="c36b5-182">On the **Certificate Request** page fill in the relevant data including selecting the SIP domain and , click **Next**.</span></span>
    
4. <span data-ttu-id="c36b5-p120">在“**延迟的请求或即时请求**”页上，可通过单击“**下一步**”接受默认的“**立即将请求发送给联机证书颁发机构**”选项。如果选择此选项，具有自动联机注册的内部 CA 必须可用。如果选择了延迟请求的选项，系统将提示您输入用于保存证书请求文件的名称和位置。证书请求必须由组织内部的 CA 或公共 CA 提出和处理。然后您需要导入证书响应并将其分配给适当的证书角色。</span><span class="sxs-lookup"><span data-stu-id="c36b5-p120">On the **Delayed or Immediate Requests** page, you can accept the default **Send the request immediately to an online certification authority** option by clicking **Next**. The internal CA with automatic online enrollment must be available if you select this option. If you choose the option to delay the request, you will be prompted for a name and location to save the certificate request file. The certificate request must be presented and processed by a CA either inside your organization, or by a public CA. You will then need to import the certificate response and assign it to the proper certificate role.</span></span>
    
5. <span data-ttu-id="c36b5-188">在 "**选择证书颁发机构（CA）** " 页面上，选择 "**从你的环境中检测到的列表中选择一个 CA** " 选项，然后从列表中选择一个已知（通过注册 Active DIRECTORY 域服务） ca。</span><span class="sxs-lookup"><span data-stu-id="c36b5-188">On the **Choose a Certificate Authority (CA)** page, select the **Select a CA from the list detected in your environment** option, and then select a known (through registration in Active Directory Domain Services) CA from the list.</span></span> <span data-ttu-id="c36b5-189">或者，选择“**指定其他证书颁发机构**”选项，在框中输入其他 CA 的名称，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="c36b5-189">Or, select the **Specify another certification authority** option, enter the name of another CA in the box, and then click **Next**.</span></span>
    
6. <span data-ttu-id="c36b5-p122">在“**证书颁发机构帐户**”页上，将提示您提供凭据，以在 CA 中请求证书和处理证书请求。您应该已经确定提前请求证书是否需要用户名和密码。CA 管理员将拥有所需的信息，并且可能需要协助您完成此步骤。如果需要提供备用凭据，请选中相应的复选框，在文本框中输入用户名和密码，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="c36b5-p122">On the **Certificate Authority Account** page, you are prompted for credentials to request and process the certificate request at the CA. You should have determined if a user name and password is necessary to request a certificate in advance. Your CA administrator will have the required information and might have to assist you in this step. If you need to supply alternate credentials, select the check box, provide a user name and password in the text boxes, and then click **Next**.</span></span>
    
7. <span data-ttu-id="c36b5-194">在“**指定替代证书模板**”页上，要使用默认的 Web 服务器模板，请单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="c36b5-194">On the **Specify Alternate Certificate Template** page, to use the default Web Server template, click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c36b5-p123">如果组织已经创建了模板，以用作默认 Web 服务器 CA 模板的备用模板，请选中相应的复选框，然后输入备用模板的名称。您将需要 CA 管理员定义的模板名称。</span><span class="sxs-lookup"><span data-stu-id="c36b5-p123">If your organization has created a template for use as an alternative for the default Web server CA template, select the check box, and then enter the name of the alternate template. You will need the template name as defined by the CA administrator.</span></span> 
  
8. <span data-ttu-id="c36b5-197">在“**名称和安全设置**”页上，指定一个“**友好名称**”。</span><span class="sxs-lookup"><span data-stu-id="c36b5-197">On the **Name and Security Settings** page, specify a **Friendly Name**.</span></span> <span data-ttu-id="c36b5-198">通过使用友好名称，您可以快速标识证书和目的。</span><span class="sxs-lookup"><span data-stu-id="c36b5-198">By using a friendly name, you can quickly identify the certificate and purpose.</span></span> <span data-ttu-id="c36b5-199">如果将此处留空，则系统会自动生成一个名称。</span><span class="sxs-lookup"><span data-stu-id="c36b5-199">If you leave it blank, a name will be generated automatically.</span></span> <span data-ttu-id="c36b5-200">设置密钥的“**位长度**”，或接受默认值 2048 位。</span><span class="sxs-lookup"><span data-stu-id="c36b5-200">Set the **Bit length** of the key, or accept the default of 2048 bits.</span></span> <span data-ttu-id="c36b5-201">如果确定需要将证书和私钥移动或复制到其他系统，请选择 "将**证书的私钥标记为可导出**"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="c36b5-201">Select the **Mark the certificate's private key as exportable** if you determine that the certificate and private key needs to be moved or copied to other systems, and then click **Next**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c36b5-202">Skype for business 服务器对可导出私钥的要求最低。</span><span class="sxs-lookup"><span data-stu-id="c36b5-202">Skype for Business Server has minimal requirements for an exportable private key.</span></span> <span data-ttu-id="c36b5-203">其中一个可导出的位置是池中的边缘服务器，在这里媒体中继身份验证服务使用证书副本，而不是对池中的每个实例都分别使用单个证书。</span><span class="sxs-lookup"><span data-stu-id="c36b5-203">One such place is on the Edge Servers in a pool, where the Media Relay Authentication Service uses copies of the certificate, rather than individual certificates for each instance in the pool.</span></span> 
  
9. <span data-ttu-id="c36b5-204">在“**组织信息**”页上，可选择提供组织信息，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="c36b5-204">On the **Organization Information** page, optionally provide organization information, and then click **Next**.</span></span>
    
10. <span data-ttu-id="c36b5-205">在“**地理信息**”页上，可选择提供地理信息，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="c36b5-205">On the **Geographical Information** page, optionally provide geographical information, and then click **Next**.</span></span>
    
11. <span data-ttu-id="c36b5-206">在“**使用者名称/使用者替代名称**”页上，检查将添加的使用者替代名称，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="c36b5-206">On the **Subject Name / Subject Alternate Names** page, review the subject alternative names that will be added, and then click **Next**.</span></span>
    
12. <span data-ttu-id="c36b5-207">在“**SIP 域设置**”页上，选择“**SIP 域**”，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="c36b5-207">On the **SIP Domain setting** page, select the **SIP Domain**, and then click **Next**.</span></span>
    
13. <span data-ttu-id="c36b5-208">在“**配置其他使用者替代名称**”页上，添加其他任何需要的使用者替代名称，包括将来其他 SIP 域可能需要的使用者替代名称，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="c36b5-208">On the **Configure Additional Subject Alternate Names** page, add any additional required subject alternative names, including any that might be required for additional SIP domains in the future, and then click **Next**.</span></span>
    
14. <span data-ttu-id="c36b5-p126">在“**证书请求摘要**”页上，检查摘要中的信息。如果信息正确，请单击“**下一步**”。如果需要更正或修改设置，请单击“**上一步**”返回相应的页面进行更正或修改。</span><span class="sxs-lookup"><span data-stu-id="c36b5-p126">On the **Certificate Request Summary** page, review the information in the summary. If the information is correct, click **Next**. If you need to correct or modify a setting, click **Back** to the proper page to make the correction or modification.</span></span>
    
15. <span data-ttu-id="c36b5-212">在“**正在执行命令**”页上，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="c36b5-212">On the **Executing Commands** page, click **Next**.</span></span>
    
16. <span data-ttu-id="c36b5-213">On the **Online Certificate Request Status** page, review the information returned.</span><span class="sxs-lookup"><span data-stu-id="c36b5-213">On the **Online Certificate Request Status** page, review the information returned.</span></span> <span data-ttu-id="c36b5-214">You should note that the certificate was issued and installed into the local certificate store.</span><span class="sxs-lookup"><span data-stu-id="c36b5-214">You should note that the certificate was issued and installed into the local certificate store.</span></span> <span data-ttu-id="c36b5-215">如果报告为已颁发并已安装，但它无效，请确保 CA 根证书已安装在服务器的受信任根 CA 存储中。</span><span class="sxs-lookup"><span data-stu-id="c36b5-215">If it is reported as having been issued and installed, but it is not valid, make sure that the CA root certificate has been installed in the server's Trusted Root CA store.</span></span> <span data-ttu-id="c36b5-216">Refer to your CA documentation on how to retrieve a Trusted Root CA certificate.</span><span class="sxs-lookup"><span data-stu-id="c36b5-216">Refer to your CA documentation on how to retrieve a Trusted Root CA certificate.</span></span> <span data-ttu-id="c36b5-217">If you need to view the retrieved certificate, click **View Certificate Details**.</span><span class="sxs-lookup"><span data-stu-id="c36b5-217">If you need to view the retrieved certificate, click **View Certificate Details**.</span></span> <span data-ttu-id="c36b5-218">默认情况下，"**将证书分配给 Skype for Business 服务器证书使用**情况" 复选框处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="c36b5-218">By default, the check box for **Assign the certificate to Skype for Business Server certificate usages** is selected.</span></span> <span data-ttu-id="c36b5-219">If you want to manually assign the certificate, clear the check box, and then click **Finish**.</span><span class="sxs-lookup"><span data-stu-id="c36b5-219">If you want to manually assign the certificate, clear the check box, and then click **Finish**.</span></span>
    
17. <span data-ttu-id="c36b5-220">如果已清除 "**将证书分配给以前页面上的 Skype for Business 服务器证书使用**情况" 复选框，则会显示 "**证书分配**" 页面。</span><span class="sxs-lookup"><span data-stu-id="c36b5-220">If you cleared the check box for **Assign the certificate to Skype for Business Server certificate usages** on the previous page, you will be presented with the **Certificate Assignment** page.</span></span> <span data-ttu-id="c36b5-221">Click **Next**.</span><span class="sxs-lookup"><span data-stu-id="c36b5-221">Click **Next**.</span></span>
    
18. <span data-ttu-id="c36b5-p129">在“**证书存储**”页上，选择已请求的证书。如果要查看证书，请单击“**查看证书详细信息**”，然后单击“**下一步**”继续。</span><span class="sxs-lookup"><span data-stu-id="c36b5-p129">On the **Certificate Store** page, select the certificate that you requested. If you want to view the certificate, click **View Certificate Details**, and then click **Next** to continue.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c36b5-p130">如果“**联机证书请求状态**”页报告证书存在问题（例如证书无效），查看实际证书可协助解决问题。可能导致证书无效的两个具体问题为：先前提到的受信任根 CA 证书缺失，与证书相关联的私钥缺失。有关如何解决这两个问题的信息，请参阅 CA 文档。</span><span class="sxs-lookup"><span data-stu-id="c36b5-p130">If the **Online Certificate Request Status** page reported an issue with the certificate, such as the certificate is not valid, view the actual certificate for help in resolving the issue. Two specific issues that can cause a certificate to not be valid is the previously mentioned missing Trusted Root CA certificate, and a missing private key that is associated with the certificate. Refer to your CA documentation to resolve these two issues.</span></span>
  
19. <span data-ttu-id="c36b5-227">在“**证书分配摘要**”页上，检查显示的信息以确保此证书是应分配的证书，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="c36b5-227">On the **Certificate Assignment Summary** page, review the information presented to make sure that this is the certificate that should be assigned, and then click **Next**.</span></span>
    
20. <span data-ttu-id="c36b5-p131">在“**正在执行命令**”页上，检查命令的输出。如果要检查分配过程或查看是否出现错误或警告，请单击“**查看日志**”。检查完成后，单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="c36b5-p131">On the **Executing Commands** page, review the output of the command. Click **View Log** if you want to review the assignment process or if there was an error or warning issued. When you are finished with your review, click **Finish**.</span></span>
    
21. <span data-ttu-id="c36b5-231">在“**证书向导**”页上，确认所有服务均显示绿色对勾，指示均已分配证书，包括图中所示的 OAuthTokenIssuer 在内，然后单击“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="c36b5-231">On the **Certificate Wizard** page, confirm that all services have a green check to indicate that all have been assigned a certificate, including the OAuthTokenIssuer ,as shown in the figure, and then click **Close**.</span></span>
    
     ![已正确安装和分配的证书。](../../media/d8e1911c-d096-4f88-97a9-d2a704defa17.png)
  
    > [!TIP]
    > <span data-ttu-id="c36b5-233">如果您在实验室环境中进行安装，并且使用 Active Directory 证书服务设置了证书颁发机构，您需要重新启动运行证书服务的服务器和前端服务器，然后才能成功颁发证书。</span><span class="sxs-lookup"><span data-stu-id="c36b5-233">If you are installing in a lab environment and have just set up the Certificate Authority using Active Directory Certificate Services, you will need to reboot both the server running Certificate Services and also the Front End server before the certificate assignment can go through successfully.</span></span> 
  
    > [!TIP]
    >  <span data-ttu-id="c36b5-234">有关 Active Directory 证书服务中的证书的详细信息，请参阅[Active Directory 证书服务](https://technet.microsoft.com/en-us/windowsserver/dd448615.aspx)。</span><span class="sxs-lookup"><span data-stu-id="c36b5-234">For more information about certificates in Active Directory Certificate Services, see [Active Directory Certificate Services](https://technet.microsoft.com/en-us/windowsserver/dd448615.aspx).</span></span> 
  
### <a name="step-4-start-services"></a><span data-ttu-id="c36b5-235">步骤 4：启动服务</span><span class="sxs-lookup"><span data-stu-id="c36b5-235">Step 4: Start Services</span></span>

1. <span data-ttu-id="c36b5-236">检查“**步骤 4：启动服务**”的先决条件。</span><span class="sxs-lookup"><span data-stu-id="c36b5-236">Review the prerequisites for **Step 4: Start Services**.</span></span>
    
2. <span data-ttu-id="c36b5-237">If this is an Enterprise Edition Front End pool with at least three servers, Windows Fabric is used, and you must use the **Start-CsPool** cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c36b5-237">If this is an Enterprise Edition Front End pool with at least three servers, Windows Fabric is used, and you must use the **Start-CsPool** cmdlet.</span></span> <span data-ttu-id="c36b5-238">如果使用单个服务器（使用标准版时总是如此），则 muse 使用**CsWindowsService** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c36b5-238">If a single server is used, which is always the case with Standard Edition, you muse use the **Start-CsWindowsService** cmdlet.</span></span> <span data-ttu-id="c36b5-239">在此示例中，我们将企业版与池中的三个前端服务器配合使用，打开**Skype For Business Server 命令行管理**程序，并运行**CsPool** cmdlet，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="c36b5-239">In this example we are using Enterprise Edition with three Front End servers in the pool, open the **Skype for Business Server Management Shell** and run the **Start-CsPool** cmdlet as shown in the figure.</span></span> <span data-ttu-id="c36b5-240">For all other roles, including Standard Edition server, you must use **Start-CsWindowsService**.</span><span class="sxs-lookup"><span data-stu-id="c36b5-240">For all other roles, including Standard Edition server, you must use **Start-CsWindowsService**.</span></span> <span data-ttu-id="c36b5-241">To deploy roles other than the Front End role, see documentation for those particular roles.</span><span class="sxs-lookup"><span data-stu-id="c36b5-241">To deploy roles other than the Front End role, see documentation for those particular roles.</span></span>
    
     ![启动 Skype for Business 服务。](../../media/f52ec719-9476-419f-9a78-df08368395f7.png)
  
3. <span data-ttu-id="c36b5-243">在“**正在执行命令**”页上，成功启动所有服务后，单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="c36b5-243">On the **Executing Commands** page, after all services have started successfully, click **Finish**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="c36b5-244">用于启动服务器上的服务的命令是报告实际上已启动服务的最佳方法。</span><span class="sxs-lookup"><span data-stu-id="c36b5-244">The command to start the services on the server is a best effort method to report that the services have, in fact, started.</span></span> <span data-ttu-id="c36b5-245">该命令可能无法反映服务的实际状态。</span><span class="sxs-lookup"><span data-stu-id="c36b5-245">It might not reflect the actual state of the service.</span></span> <span data-ttu-id="c36b5-246">建议使用步骤“**服务状态（可选）**”来打开 Microsoft 管理控制台 (MMC) 并确认服务已成功启动，如图所示。</span><span class="sxs-lookup"><span data-stu-id="c36b5-246">We recommend that you use the step **Service Status (Optional)** to open the Microsoft Management Console (MMC) and confirm that the services have started successfully, as shown in the figure.</span></span> <span data-ttu-id="c36b5-247">如果任何 Skype for Business 服务器服务尚未启动，可以右键单击 MMC 中的该服务，然后单击 "**开始**"。</span><span class="sxs-lookup"><span data-stu-id="c36b5-247">If any Skype for Business Server service has not started, you can right-click that service in the MMC, and then click **Start**.</span></span> 
  
     ![验证服务是否已启动。](../../media/47906fb7-9d37-4d55-8d8d-e5a4a2366510.png)
  

