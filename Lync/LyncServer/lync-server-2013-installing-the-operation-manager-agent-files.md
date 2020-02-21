---
title: Lync Server 2013：安装 Operation Manager 代理文件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing the Operation Manager agent files
ms:assetid: e2246c44-0c75-43fc-8b04-26e53c5dd572
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205345(v=OCS.15)
ms:contentKeyID: 48185692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e685abf7916c446bf9acf73e50f5633271b2942
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207248"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="installing-the-operation-manager-agent-files-in-lync-server-2013"></a><span data-ttu-id="d237e-102">在 Lync Server 2013 中安装 Operation Manager 代理文件</span><span class="sxs-lookup"><span data-stu-id="d237e-102">Installing the Operation Manager agent files in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d237e-103">_**上次修改的主题：** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="d237e-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="d237e-104">若要在计算机上安装 Operations Manager 代理文件，请完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="d237e-104">To install the Operations Manager agent files on the computer, complete the following steps.</span></span>

1.  <span data-ttu-id="d237e-105">在您的 System Center 安装程序媒体上，双击 " **SetupOM**"。</span><span class="sxs-lookup"><span data-stu-id="d237e-105">On your System Center setup media, double-click **SetupOM.exe**.</span></span>

2.  <span data-ttu-id="d237e-106">在 System Center Operation Manager 安装程序中，单击 "**安装 Operations Manager 代理**"。</span><span class="sxs-lookup"><span data-stu-id="d237e-106">In System Center Operation Manager setup, click **Install Operations Manager Agent**.</span></span>

3.  <span data-ttu-id="d237e-107">在 System Center 安装向导中，在 "**欢迎使用 System Center Operations Manager 安装**向导" 页上，单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="d237e-107">In System Center Setup wizard, on the **Welcome to the System Center Operations Manager Setup** wizard page, click **Next**.</span></span>

4.  <span data-ttu-id="d237e-108">在 "**目标文件夹**" 页上，选择将在其中安装 Operations Manager 代理文件的文件夹，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="d237e-108">On the **Destination Folder** page, select the folder where the Operations Manager Agent files will be installed, and then click **Next**.</span></span>

5.  <span data-ttu-id="d237e-109">在 "**管理组配置**" 页上，选择 "**指定管理组信息**"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="d237e-109">On the **Management Group Configuration** page, select **Specify Management Group information**, and then click **Next**.</span></span>

6.  <span data-ttu-id="d237e-110">在 "**管理组配置**" 页上，在 "**管理组名称**" 框中键入 operations manager 管理组的名称，然后在 "**管理服务器**" 框中键入 operations manager 服务器的主机名称（例如，atl-ws-01-001）。</span><span class="sxs-lookup"><span data-stu-id="d237e-110">On the **Management Group Configuration** page, type the name of your Operations Manager Management Group in the **Management Group Name** box, and then type the host name of your Operations Manager server (for example, atl-scom-001) in the **Management Server** box.</span></span> <span data-ttu-id="d237e-111">如果更改了 Operations Manager 使用的端口号，请在 "管理服务器端口" 框中键入新的端口号。</span><span class="sxs-lookup"><span data-stu-id="d237e-111">If you have changed the port number used by Operations Manager, then type the new port number in the Management Server Port box.</span></span> <span data-ttu-id="d237e-112">否则，将端口保留为默认值5723，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="d237e-112">Otherwise, leave the port at the default value of 5723 and click **Next**.</span></span>

7.  <span data-ttu-id="d237e-113">在 "**代理操作帐户**" 页上，选择 "**本地系统**"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="d237e-113">On the **Agent Action Account** page, select **Local System**, and then click **Next**.</span></span>

8.  <span data-ttu-id="d237e-114">在 " **Microsoft update** " 页上，选择 "**我不想使用 Microsoft 更新**"，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="d237e-114">On the **Microsoft Update** page, select **I don't want to use Microsoft Update**, and then click **Next**.</span></span>

9.  <span data-ttu-id="d237e-115">在 "**准备安装**" 页上，单击 "**安装**"。</span><span class="sxs-lookup"><span data-stu-id="d237e-115">On the **Ready to Install** page, click **Install**.</span></span>

10. <span data-ttu-id="d237e-116">在 "**正在完成 System Center Operations Manager 安装向导**" 页上，单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="d237e-116">On the **Completing the System Center Operations Manager Setup wizard** page, click **Finish**.</span></span>

11. <span data-ttu-id="d237e-117">单击“退出”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d237e-117">Click **Exit**.</span></span>

<span data-ttu-id="d237e-118">如果使用的是 System Center 2007 R2，可以通过单击 "**开始**"，单击 "**所有程序**"，单击 " **System Center Operations Manager 2007 R2**"，然后单击 " **Operations Manager Shell**" 来验证是否已创建代理。</span><span class="sxs-lookup"><span data-stu-id="d237e-118">If you are using System Center 2007 R2, you can verify that the agent has been created by clicking **Start**, clicking **All Programs**, clicking **System Center Operations Manager 2007 R2**, and then clicking **Operations Manager Shell**.</span></span> <span data-ttu-id="d237e-119">在 Operations Manager 命令行管理程序中，键入以下 Windows PowerShell 命令，然后按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="d237e-119">In the Operations Manager Shell, type the following Windows PowerShell command, and then press ENTER:</span></span>

    Get-Agent 

<span data-ttu-id="d237e-120">将在屏幕上显示所有 Operations Manager 代理的列表。</span><span class="sxs-lookup"><span data-stu-id="d237e-120">A list of all your Operations Manager agents will appear onscreen.</span></span>

<span data-ttu-id="d237e-121">如果使用的是 System Center 2012，请从 Operations 2012 Manager 命令行管理程序中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="d237e-121">If you are using System Center 2012, run this command from the Operations 2012 Manager Shell:</span></span>

    Get-SCOMAgent

</div>

<span> </span>

</div>

</div>

</div>

