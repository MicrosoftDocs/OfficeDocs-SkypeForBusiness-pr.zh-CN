---
title: Lync Server 2013：安装 Standard Edition server database
description: Lync Server 2013：安装 Standard Edition server database。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install Standard Edition server database
ms:assetid: 0bd3a804-aad6-48cb-981b-54725af032db
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398167(v=OCS.15)
ms:contentKeyID: 48183385
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a20d2c01de94ad88960555db78c57c6b79d92f7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574078"
---
# <a name="install-standard-edition-server-database-for-lync-server-2013"></a><span data-ttu-id="1792b-103">安装适用于 Lync Server 2013 的 Standard Edition 服务器数据库</span><span class="sxs-lookup"><span data-stu-id="1792b-103">Install Standard Edition server database for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1792b-104">_**上次修改的主题：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="1792b-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="1792b-105">将 Standard Edition 服务器设置为基础结构中的唯一服务器，让家庭用户与其他服务器安装不同，因为 **部署向导** 中有专门用于设置初始服务器的选择。</span><span class="sxs-lookup"><span data-stu-id="1792b-105">Setting up a Standard Edition server as the only server in your infrastructure that homes users differs from other server installations in that there is a selection in the **Deployment Wizard** specifically for setting up the initial server.</span></span>

<div>

## <a name="to-install-a-standard-edition-server"></a><span data-ttu-id="1792b-106">安装 Standard Edition Server</span><span class="sxs-lookup"><span data-stu-id="1792b-106">To install a Standard Edition server</span></span>

1.  <span data-ttu-id="1792b-107">登录到要将 Standard Edition server 安装为本地管理员或等效域的服务器。</span><span class="sxs-lookup"><span data-stu-id="1792b-107">Log on to the server where you are going to install Standard Edition server as a local administrator or a domain equivalent.</span></span>

2.  <span data-ttu-id="1792b-108">如果尚未准备好 Active Directory 域服务，则先执行这些过程。</span><span class="sxs-lookup"><span data-stu-id="1792b-108">If you have not prepared Active Directory Domain Services, then first perform those procedures.</span></span> <span data-ttu-id="1792b-109">有关详细信息，请参阅 [为 Lync Server 2013 准备 Active Directory 域服务](lync-server-2013-preparing-active-directory-domain-services.md)。</span><span class="sxs-lookup"><span data-stu-id="1792b-109">For details, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).</span></span>

3.  <span data-ttu-id="1792b-110">在 "Lync Server 部署向导" 中，单击 " **准备第一个 Standard Edition Server**"。</span><span class="sxs-lookup"><span data-stu-id="1792b-110">In the Lync Server Deployment Wizard, click **Prepare first Standard Edition server**.</span></span>

4.  <span data-ttu-id="1792b-111">在“准备单个 Standard Edition Server”\*\*\*\* 页上，单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1792b-111">On the **Prepare single Standard Edition Server** page, click **Next**.</span></span>

5.  <span data-ttu-id="1792b-112">在 " **正在执行命令** " 页上，SQL Server 2012 Express 安装为中央管理存储。</span><span class="sxs-lookup"><span data-stu-id="1792b-112">On the **Executing Commands** page, the SQL Server 2012 Express is installed as the Central Management store.</span></span> <span data-ttu-id="1792b-113">创建必需的防火墙规则。</span><span class="sxs-lookup"><span data-stu-id="1792b-113">Necessary firewall rules are created.</span></span> <span data-ttu-id="1792b-114">安装数据库和必备软件后，单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1792b-114">When the installation of the database and prerequisite software is completed, click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1792b-115">初始安装可能要花费一些时间，这期间命令输出摘要屏幕上不显示更新。</span><span class="sxs-lookup"><span data-stu-id="1792b-115">The initial installation may take some time with no visible updates to the command output summary screen.</span></span> <span data-ttu-id="1792b-116">这是因为安装了 SQL Server Express。</span><span class="sxs-lookup"><span data-stu-id="1792b-116">This is due to the installation of the SQL Server Express.</span></span> <span data-ttu-id="1792b-117">如果需要监视数据库安装，请使用任务管理器监视安装过程。</span><span class="sxs-lookup"><span data-stu-id="1792b-117">If you need to monitor the installation of the database, use Task Manager to monitor the setup.</span></span>

    
    </div>

6.  <span data-ttu-id="1792b-118">在 "Lync Server 部署向导" 页上，单击 " **安装拓扑生成器** " （如果以前未安装过管理工具）。</span><span class="sxs-lookup"><span data-stu-id="1792b-118">On the Lync Server Deployment Wizard page, click **Install Topology Builder** if you have not previously installed the administrative tools.</span></span> <span data-ttu-id="1792b-119">有关详细信息，请参阅 [Install Lync Server 2013 管理工具](lync-server-2013-install-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="1792b-119">For details, see [Install Lync Server 2013 administrative tools](lync-server-2013-install-lync-server-administrative-tools.md).</span></span>

7.  <span data-ttu-id="1792b-120">确认“准备 Active Directory”、“准备第一个 Standard Edition Server”和“安装拓扑生成器”旁边有绿色复选标记。</span><span class="sxs-lookup"><span data-stu-id="1792b-120">Confirm that there are green check marks next to “Prepare Active Directory,” “Prepare first Standard Edition server,” and “Install Topology Builder.”</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

