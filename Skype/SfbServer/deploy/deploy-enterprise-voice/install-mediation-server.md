---
title: 在 Skype for Business Server 2015 中安装中介服务器的文件
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: f0f7dd15-58e1-40fd-aa7e-6db50ceafacd
description: 摘要： 了解如何为业务服务器 2015年在 Skype 的中介服务器的安装文件。
ms.openlocfilehash: 8b7b68142c180ee1b06963afbb1b7a9ca6d4319c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="install-the-files-for-mediation-server-in-skype-for-business-server-2015"></a><span data-ttu-id="51f1b-103">在 Skype for Business Server 2015 中安装中介服务器的文件</span><span class="sxs-lookup"><span data-stu-id="51f1b-103">Install the files for Mediation Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="51f1b-104">**摘要：**了解如何为业务服务器 2015年在 Skype 的中介服务器的安装文件。</span><span class="sxs-lookup"><span data-stu-id="51f1b-104">**Summary:** Learn how to install the files for Mediation Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="51f1b-105">要成功完成此过程，应至少以本地管理员身份和至少在 RTCUniversalReadOnlyAdmins 组中具有成员身份的域用户身份登录服务器。</span><span class="sxs-lookup"><span data-stu-id="51f1b-105">To successfully complete this procedure, you should be logged on to the server, at the minimum, as a local administrator and a domain user who has membership in at least the RTCUniversalReadOnlyAdmins group.</span></span>
  
<span data-ttu-id="51f1b-106">使用本主题中的步骤运行业务服务器部署向导中介服务器的文件安装在您使用拓扑生成器来定义并发布该池之后，到中介服务器池添加一台计算机上的 Skype。</span><span class="sxs-lookup"><span data-stu-id="51f1b-106">Use the steps in this topic to run Skype for Business Server Deployment Wizard to install the files for Mediation Server on a computer that you added to a Mediation Server pool after you have used Topology Builder to define and publish the pool.</span></span> <span data-ttu-id="51f1b-107">安装时中介服务器的文件，您还安装，并指定所需的中介服务器池中的每台计算机的证书。</span><span class="sxs-lookup"><span data-stu-id="51f1b-107">When installing files Mediation Server, you also install and assign the certificate required by each computer in a Mediation Server pool.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="51f1b-108">本主题假定您已经定义并发布您的拓扑结构，在一个独立的中介服务器池[部署在拓扑生成器在 Skype 业务服务器 2015年的中介服务器](deploy-a-mediation-server.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="51f1b-108">This topic assumes that you have already defined and published a stand-alone Mediation Server pool in your topology, as described in [Deploy a Mediation Server in Topology Builder in Skype for Business Server 2015](deploy-a-mediation-server.md).</span></span> 
  
### <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a><span data-ttu-id="51f1b-109">为独立的中介服务器池安装文件</span><span class="sxs-lookup"><span data-stu-id="51f1b-109">To install the files for a stand-alone Mediation Server pool</span></span>

1. <span data-ttu-id="51f1b-110">从安装媒体中，用鼠标右键单击_\<安装介质\>_ **\Setup\amd64\Setup.exe**，然后单击**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="51f1b-110">From the installation media, right-click  _\<installation media\>_ **\Setup\amd64\Setup.exe**, and then click **Run as Administrator**.</span></span>
    
2. <span data-ttu-id="51f1b-111">在“安装位置”****页上，单击“确定”****。</span><span class="sxs-lookup"><span data-stu-id="51f1b-111">On the **Installation Location** page, click **OK**.</span></span>
    
3. <span data-ttu-id="51f1b-p102">在“最终用户许可协议”****页上，单击“我接受”****，然后单击“确定”****。（必须单击该按钮才能继续。）</span><span class="sxs-lookup"><span data-stu-id="51f1b-p102">On the **End User License Agreement** page, click **I accept**, and then click **OK**. (Required to continue.)</span></span>
    
4. <span data-ttu-id="51f1b-114">在**Skype 业务服务器部署向导**页上，单击**安装或更新 Skype 业务服务器系统**。</span><span class="sxs-lookup"><span data-stu-id="51f1b-114">On the **Skype for Business Server Deployment Wizard** page, click **Install or Update Skype for Business Server System**.</span></span>
    
5. <span data-ttu-id="51f1b-115">单击“步骤 1: 安装本地配置存储”****旁边的“运行”****，然后按照屏幕上的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="51f1b-115">Next to **Step 1: Install Local Configuration Store**, click **Run**, and then follow the instructions on the screen.</span></span>
    
6. <span data-ttu-id="51f1b-116">在“配置中央管理存储的本地副本”****页上，接受默认的“直接从中央管理存储检索”****，然后单击“下一步”****。</span><span class="sxs-lookup"><span data-stu-id="51f1b-116">On the **Configure Local Replica of Central Management Store** page, accept the default **Retrieve directly from the Central Management Store**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="51f1b-117">在“正在执行命令”****页上，当任务状态显示为“已完成”****时，单击“完成”****。</span><span class="sxs-lookup"><span data-stu-id="51f1b-117">On the **Executing Commands** page, when the task status is shown as **Completed**, click **Finish**.</span></span>
    
8. <span data-ttu-id="51f1b-118">下一步**步骤 2： 安装或删除的 Skype 业务服务器组件**，单击**运行**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="51f1b-118">Next to **Step 2: Setup or Remove Skype for Business Server Components**, click **Run**, and then click **Next**.</span></span>
    
9. <span data-ttu-id="51f1b-119">在“正在执行命令”****页上，当任务状态显示为“已完成”****时，单击“完成”****。</span><span class="sxs-lookup"><span data-stu-id="51f1b-119">On the **Executing Commands** page, when the task status is shown as **Completed**, click **Finish**.</span></span>
    
10. <span data-ttu-id="51f1b-p103">单击“步骤 3: 请求、安装或分配证书”****旁边的“运行”****。按照屏幕上的说明进行操作，接受默认设置。中介服务器需要一个证书，因此要运行“步骤 3”****两次：第一次是颁发所需证书，第二次是分配该证书。</span><span class="sxs-lookup"><span data-stu-id="51f1b-p103">Next to **Step 3: Request, Install or Assign Certificates**, click **Run**. Follow the instructions on the screen, accepting the default settings. The Mediation Server requires one certificate, and so you will run **Step 3** twice: once to issue the required certificate, and once more to assign it.</span></span>
    
11. <span data-ttu-id="51f1b-123">正确颁发并分配证书后，在“步骤 4: 启动服务”****旁边，单击“运行”****，然后按照屏幕上的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="51f1b-123">When the certificate has been issued and assigned correctly, beside **Step 4: Start Services**, click **Run**, and then follow the instructions on the screen.</span></span>
    
12. <span data-ttu-id="51f1b-124">成功完成“步骤 4”****后，重新启动服务器，然后以 DomainAdmins 组的成员身份登录到服务器。</span><span class="sxs-lookup"><span data-stu-id="51f1b-124">When **Step 4** has completed successfully, restart the server, and log on to the server as a member of the DomainAdmins group.</span></span>
    
13. <span data-ttu-id="51f1b-125">在计算机上运行 Skype 业务服务器的控制面板，验证**拓扑**页上的 Skype 业务服务器控件面板的中介服务器的服务状态将显示为一个绿色的复选标记。</span><span class="sxs-lookup"><span data-stu-id="51f1b-125">On the computer where you are running Skype for Business Server Control Panel, verify on the **Topology** page of Skype for Business Server Control Panel that the service status of the Mediation Server is shown as a green check mark.</span></span> <span data-ttu-id="51f1b-126">如果显示红色 X，请选择相应的中介服务器。</span><span class="sxs-lookup"><span data-stu-id="51f1b-126">If a red X appears instead, select the Mediation Server.</span></span> <span data-ttu-id="51f1b-127">在“操作”****菜单上，单击“启动所有服务”****。</span><span class="sxs-lookup"><span data-stu-id="51f1b-127">On the **Action** menu, click **Start All Services**.</span></span> 
    
<span data-ttu-id="51f1b-128">如果您对中介服务器池添加多台计算机，在此过程中的中介服务器池的所有其他计算机上执行的步骤。</span><span class="sxs-lookup"><span data-stu-id="51f1b-128">If you added more than one computer to the Mediation Server pool, perform the steps in this procedure on all other computers in the Mediation Server pool.</span></span> <span data-ttu-id="51f1b-129">如果不需要的任何其他计算机中介服务器的安装文件，然后按照中[配置中继业务服务器 2015年的 Skype 在](configure-trunks.md)为此中介服务器池 （或所有之间的主干连接配置设置的步骤在站点的中介服务器） 及其对等。</span><span class="sxs-lookup"><span data-stu-id="51f1b-129">If you do not need to install files for Mediation Server for any other computers, then follow the procedures in [Configure trunks in Skype for Business Server 2015](configure-trunks.md) to configure settings for the trunk connection between this Mediation Server pool (or all Mediation Servers at a site) and its peer.</span></span>

