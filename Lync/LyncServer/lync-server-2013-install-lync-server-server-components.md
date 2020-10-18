---
title: Lync Server 2013：安装 Lync Server server 组件
description: Lync Server 2013：安装 Lync Server server 组件。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install Lync Server server components
ms:assetid: 186aed6e-7adf-4a92-9f2e-f9a4de5ff202
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398239(v=OCS.15)
ms:contentKeyID: 48183528
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1930926f3a46be868d838abf646eb8702c9713a8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574118"
---
# <a name="install-server-components-for-lync-server-2013"></a><span data-ttu-id="7c2a5-103">安装 Lync Server 2013 的服务器组件</span><span class="sxs-lookup"><span data-stu-id="7c2a5-103">Install server components for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7c2a5-104">_**上次修改的主题：** 2014-05-05_</span><span class="sxs-lookup"><span data-stu-id="7c2a5-104">_**Topic Last Modified:** 2014-05-05_</span></span>

<span data-ttu-id="7c2a5-105">在执行以下步骤之前，请确保您使用具有本地管理员的域用户帐户和 Active Directory 中的 RTCUniversalReadOnlyAdmins 组的成员登录到服务器。</span><span class="sxs-lookup"><span data-stu-id="7c2a5-105">Before following these steps, make sure you’re logged onto the server with a domain user account that’s both a local administrator and a member of the RTCUniversalReadOnlyAdmins group in Active Directory.</span></span>

<span data-ttu-id="7c2a5-106">Lync Server 部署向导用于为每个 Lync server 角色安装所需的组件并激活服务器。</span><span class="sxs-lookup"><span data-stu-id="7c2a5-106">The Lync Server Deployment Wizard is used to install the needed components for each Lync server role and to activate the server.</span></span> <span data-ttu-id="7c2a5-107">本文将引导您完成在 Lync 基础结构中部署 Standard Edition server 或前端服务器的步骤。</span><span class="sxs-lookup"><span data-stu-id="7c2a5-107">This article walks you through the steps of deploying a Standard Edition server or a Front End Server in your Lync infrastructure.</span></span>

<div>

## <a name="to-install-lync-server-components"></a><span data-ttu-id="7c2a5-108">安装 Lync Server 组件</span><span class="sxs-lookup"><span data-stu-id="7c2a5-108">To install Lync Server components</span></span>

1.  <span data-ttu-id="7c2a5-109">如果未运行 Lync Server 部署向导，请在要安装 Lync 的服务器上启动它。</span><span class="sxs-lookup"><span data-stu-id="7c2a5-109">If the Lync Server Deployment Wizard isn’t running, start it on the server you want to install Lync onto.</span></span>

2.  <span data-ttu-id="7c2a5-110">单击 " **安装或更新 Lync Server 系统**"。</span><span class="sxs-lookup"><span data-stu-id="7c2a5-110">Click **Install or Update Lync Server System**.</span></span>

3.  <span data-ttu-id="7c2a5-111">在部署向导中，确认 " **步骤1：安装本地配置存储区** " 带有绿色的复选标记，这表示此服务器已成功安装存储的本地副本。</span><span class="sxs-lookup"><span data-stu-id="7c2a5-111">In the Deployment Wizard, confirm that **Step 1: Install Local Configuration Store** has a green check mark, which means that this server has a local copy of the store installed successfully.</span></span> <span data-ttu-id="7c2a5-112">如果未选中此项，则需要在服务器上安装本地配置存储。</span><span class="sxs-lookup"><span data-stu-id="7c2a5-112">If it’s not checked, you need to install the Local Configuration store on the server.</span></span> <span data-ttu-id="7c2a5-113">按照在 [Lync Server 2013 中安装本地配置存储中](lync-server-2013-install-the-local-configuration-store.md) 的步骤操作，然后回到此处。</span><span class="sxs-lookup"><span data-stu-id="7c2a5-113">Follow the steps at [Install the Local Configuration store in Lync Server 2013](lync-server-2013-install-the-local-configuration-store.md) and then come back here.</span></span>

4.  <span data-ttu-id="7c2a5-114">当您准备好在服务器上安装 Lync Server 2013 组件时，请单击 "**步骤2：安装或删除 Lync Server 组件**" 旁边的 "**运行**"。</span><span class="sxs-lookup"><span data-stu-id="7c2a5-114">When you’re ready to install the Lync Server 2013 components on your server, click **Run** next to **Step 2: Setup or Remove Lync Server Components**.</span></span>

5.  <span data-ttu-id="7c2a5-115">在 "安装 **Lync Server 组件** " 页上，单击 " **下一步** " 设置在已发布拓扑中定义的组件。</span><span class="sxs-lookup"><span data-stu-id="7c2a5-115">On the **Set Up Lync Server Components** page, click **Next** to set up components as defined in your published topology.</span></span>

6.  <span data-ttu-id="7c2a5-116">" **正在执行命令** " 页将在设置发生时显示命令和安装信息的摘要。</span><span class="sxs-lookup"><span data-stu-id="7c2a5-116">The **Executing Commands** page will display a summary of commands and installation information as the set up takes place.</span></span> <span data-ttu-id="7c2a5-117">完成后，可以使用列表选择要查看的日志，然后单击 " **查看日志**"。</span><span class="sxs-lookup"><span data-stu-id="7c2a5-117">When it’s done, you can use the list to select a log to view, and then click **View Log**.</span></span>

7.  <span data-ttu-id="7c2a5-118">在安装了 Lync Server 2013 组件并根据需要查看日志后，请单击 " **完成** " 以完成安装中的此步骤。</span><span class="sxs-lookup"><span data-stu-id="7c2a5-118">When Lync Server 2013 components setup is done, and you’ve reviewed the logs as needed, click **Finish** to complete this step in the installation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7c2a5-119">如果系统提示您重新启动服务器 (如果需要安装 Windows 桌面体验) ，则可能会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="7c2a5-119">If you’re prompted to restart the server (which might happen if Windows Desktop Experience needed to be installed), definitely do that.</span></span> <span data-ttu-id="7c2a5-120">当计算机重新启动并运行时，您需要再次执行这些步骤，从上面列出的第三步开始 (基本上在 "部署向导" 中再次运行步骤 2) 。</span><span class="sxs-lookup"><span data-stu-id="7c2a5-120">When the computer is back up and running, you need to do these steps over again, starting from step three listed above (basically run Step 2 in the Deployment Wizard one more time).</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

