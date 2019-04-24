---
title: 安装 Business Server Skype 中的中介服务器的文件
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f0f7dd15-58e1-40fd-aa7e-6db50ceafacd
description: 摘要： 了解如何安装 Business Server Skype 中的中介服务器的文件。
ms.openlocfilehash: ab02655dc812815c79720d76c87bfefe91c90c73
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32223053"
---
# <a name="install-the-files-for-mediation-server-in-skype-for-business-server"></a><span data-ttu-id="28c1a-103">安装 Business Server Skype 中的中介服务器的文件</span><span class="sxs-lookup"><span data-stu-id="28c1a-103">Install the files for Mediation Server in Skype for Business Server</span></span>
 
<span data-ttu-id="28c1a-104">**摘要：** 了解如何安装 Business Server Skype 中的中介服务器的文件。</span><span class="sxs-lookup"><span data-stu-id="28c1a-104">**Summary:** Learn how to install the files for Mediation Server in Skype for Business Server.</span></span>
  
<span data-ttu-id="28c1a-105">要成功完成此过程，应至少以本地管理员身份和至少在 RTCUniversalReadOnlyAdmins 组中具有成员身份的域用户身份登录服务器。</span><span class="sxs-lookup"><span data-stu-id="28c1a-105">To successfully complete this procedure, you should be logged on to the server, at the minimum, as a local administrator and a domain user who has membership in at least the RTCUniversalReadOnlyAdmins group.</span></span>
  
<span data-ttu-id="28c1a-106">使用本主题中的步骤运行 Skype 的业务 Server 部署向导，以您使用拓扑生成器定义和发布池之后添加到中介服务器池的计算机上安装中介服务器的文件。</span><span class="sxs-lookup"><span data-stu-id="28c1a-106">Use the steps in this topic to run Skype for Business Server Deployment Wizard to install the files for Mediation Server on a computer that you added to a Mediation Server pool after you have used Topology Builder to define and publish the pool.</span></span> <span data-ttu-id="28c1a-107">当安装文件中介服务器，您还安装并分配所需的中介服务器池中的每台计算机的证书。</span><span class="sxs-lookup"><span data-stu-id="28c1a-107">When installing files Mediation Server, you also install and assign the certificate required by each computer in a Mediation Server pool.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="28c1a-108">本主题假定您已定义并发布拓扑，在独立的中介服务器池[部署中介服务器中的业务服务器 Skype 的拓扑生成器中](deploy-a-mediation-server.md)所述。</span><span class="sxs-lookup"><span data-stu-id="28c1a-108">This topic assumes that you have already defined and published a stand-alone Mediation Server pool in your topology, as described in [Deploy a Mediation Server in Topology Builder in Skype for Business Server](deploy-a-mediation-server.md).</span></span> 
  
### <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a><span data-ttu-id="28c1a-109">为独立的中介服务器池安装文件</span><span class="sxs-lookup"><span data-stu-id="28c1a-109">To install the files for a stand-alone Mediation Server pool</span></span>

1. <span data-ttu-id="28c1a-110">从安装媒体中，右键单击_\<安装媒体\>_ **\Setup\amd64\Setup.exe**，，然后单击**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="28c1a-110">From the installation media, right-click  _\<installation media\>_ **\Setup\amd64\Setup.exe**, and then click **Run as Administrator**.</span></span>
    
2. <span data-ttu-id="28c1a-111">在“安装位置”\*\*\*\* 页上，单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="28c1a-111">On the **Installation Location** page, click **OK**.</span></span>
    
3. <span data-ttu-id="28c1a-p102">在“最终用户许可协议”\*\*\*\* 页上，单击“我接受”\*\*\*\*，然后单击“确定”\*\*\*\*。（必须单击该按钮才能继续。）</span><span class="sxs-lookup"><span data-stu-id="28c1a-p102">On the **End User License Agreement** page, click **I accept**, and then click **OK**. (Required to continue.)</span></span>
    
4. <span data-ttu-id="28c1a-114">在**Skype 的业务 Server 部署向导**页上，单击**安装或更新 Skype 业务 Server 系统**。</span><span class="sxs-lookup"><span data-stu-id="28c1a-114">On the **Skype for Business Server Deployment Wizard** page, click **Install or Update Skype for Business Server System**.</span></span>
    
5. <span data-ttu-id="28c1a-115">单击“步骤 1: 安装本地配置存储”\*\*\*\* 旁边的“运行”\*\*\*\*，然后按照屏幕上的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="28c1a-115">Next to **Step 1: Install Local Configuration Store**, click **Run**, and then follow the instructions on the screen.</span></span>
    
6. <span data-ttu-id="28c1a-116">在“配置中央管理存储的本地副本”\*\*\*\* 页上，接受默认的“直接从中央管理存储检索”\*\*\*\*，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="28c1a-116">On the **Configure Local Replica of Central Management Store** page, accept the default **Retrieve directly from the Central Management Store**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="28c1a-117">在“正在执行命令”\*\*\*\* 页上，当任务状态显示为“已完成”\*\*\*\* 时，单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="28c1a-117">On the **Executing Commands** page, when the task status is shown as **Completed**, click **Finish**.</span></span>
    
8. <span data-ttu-id="28c1a-118">单击**步骤 2： 安装或删除业务服务器组件的 Skype**，单击**运行**，，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="28c1a-118">Next to **Step 2: Setup or Remove Skype for Business Server Components**, click **Run**, and then click **Next**.</span></span>
    
9. <span data-ttu-id="28c1a-119">在“正在执行命令”\*\*\*\* 页上，当任务状态显示为“已完成”\*\*\*\* 时，单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="28c1a-119">On the **Executing Commands** page, when the task status is shown as **Completed**, click **Finish**.</span></span>
    
10. <span data-ttu-id="28c1a-p103">单击“步骤 3: 请求、安装或分配证书”\*\*\*\* 旁边的“运行”\*\*\*\*。按照屏幕上的说明进行操作，接受默认设置。中介服务器需要一个证书，因此要运行“步骤 3”\*\*\*\* 两次：第一次是颁发所需证书，第二次是分配该证书。</span><span class="sxs-lookup"><span data-stu-id="28c1a-p103">Next to **Step 3: Request, Install or Assign Certificates**, click **Run**. Follow the instructions on the screen, accepting the default settings. The Mediation Server requires one certificate, and so you will run **Step 3** twice: once to issue the required certificate, and once more to assign it.</span></span>
    
11. <span data-ttu-id="28c1a-123">正确颁发并分配证书后，在“步骤 4: 启动服务”\*\*\*\* 旁边，单击“运行”\*\*\*\*，然后按照屏幕上的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="28c1a-123">When the certificate has been issued and assigned correctly, beside **Step 4: Start Services**, click **Run**, and then follow the instructions on the screen.</span></span>
    
12. <span data-ttu-id="28c1a-124">成功完成“步骤 4”\*\*\*\* 后，重新启动服务器，然后以 DomainAdmins 组的成员身份登录到服务器。</span><span class="sxs-lookup"><span data-stu-id="28c1a-124">When **Step 4** has completed successfully, restart the server, and log on to the server as a member of the DomainAdmins group.</span></span>
    
13. <span data-ttu-id="28c1a-125">在您的业务 Server Control Panel for 运行 Skype 计算机上，验证 Skype 的**拓扑**页上的中介服务器服务状态显示为绿色复选标记的业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="28c1a-125">On the computer where you are running Skype for Business Server Control Panel, verify on the **Topology** page of Skype for Business Server Control Panel that the service status of the Mediation Server is shown as a green check mark.</span></span> <span data-ttu-id="28c1a-126">如果显示红色 X，请选择相应的中介服务器。</span><span class="sxs-lookup"><span data-stu-id="28c1a-126">If a red X appears instead, select the Mediation Server.</span></span> <span data-ttu-id="28c1a-127">在“操作”\*\*\*\* 菜单上，单击“启动所有服务”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="28c1a-127">On the **Action** menu, click **Start All Services**.</span></span> 
    
<span data-ttu-id="28c1a-128">如果多台计算机添加到中介服务器池，请在此过程中在中介服务器池的所有其他计算机上执行步骤。</span><span class="sxs-lookup"><span data-stu-id="28c1a-128">If you added more than one computer to the Mediation Server pool, perform the steps in this procedure on all other computers in the Mediation Server pool.</span></span> <span data-ttu-id="28c1a-129">如果您不需要安装中介服务器的任何其他计算机文件，然后按照本节[中的业务服务器 Skype 配置中继](configure-trunks.md)配置的此中介服务器池 （或所有中介之间的中继连接设置中的过程在站点的服务器） 及其对等。</span><span class="sxs-lookup"><span data-stu-id="28c1a-129">If you do not need to install files for Mediation Server for any other computers, then follow the procedures in [Configure trunks in Skype for Business Server](configure-trunks.md) to configure settings for the trunk connection between this Mediation Server pool (or all Mediation Servers at a site) and its peer.</span></span>

