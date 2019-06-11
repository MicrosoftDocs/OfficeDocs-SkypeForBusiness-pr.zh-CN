---
title: 'Lync Server 2013: 安装 SQL Server Reporting Services'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Installing SQL Server Reporting Services
ms:assetid: 638a1d0c-1ac7-4735-83f2-4df3d03c7cf9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204957(v=OCS.15)
ms:contentKeyID: 48184345
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6707cafc3a08123bd2189639704741681eb9cdd6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829986"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-sql-server-reporting-services-in-lync-server-2013"></a><span data-ttu-id="15512-102">在 Lync Server 2013 中安装 SQL Server Reporting Services</span><span class="sxs-lookup"><span data-stu-id="15512-102">Installing SQL Server Reporting Services in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="15512-103">_**主题上次修改时间:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="15512-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="15512-104">如果您打算使用 Microsoft Lync Server 2013 监视报告 (有关详细信息, 请参阅本文档的下一节), 必须首先安装 SQL Server Reporting Services;可以在安装 Microsoft SQL Server 时或在安装 SQL Server 之后的任何时间安装 Reporting Services。</span><span class="sxs-lookup"><span data-stu-id="15512-104">If you intend to use Microsoft Lync Server 2013 Monitoring Reports (see the next section of this documentation for more information) you must first install SQL Server Reporting Services; Reporting Services can be installed at the same time you install Microsoft SQL Server or any time after SQL Server has been installed.</span></span> <span data-ttu-id="15512-105">如果你未安装 SQL Server，则请按照本文档之前提供的说明操作。</span><span class="sxs-lookup"><span data-stu-id="15512-105">If you have not installed SQL Server, then follow the instructions provided earlier in this documentation.</span></span> <span data-ttu-id="15512-106">安装 SQL Server 时，确保在“功能选择”页上选择 Reporting Services。</span><span class="sxs-lookup"><span data-stu-id="15512-106">When installing SQL Server, make sure that, on the Feature Selection page, you select Reporting Services.</span></span> <span data-ttu-id="15512-107">这将安装 SQL Server Reporting Services。</span><span class="sxs-lookup"><span data-stu-id="15512-107">That will install SQL Server Reporting Services.</span></span>

<span data-ttu-id="15512-108">如果你已安装 SQL Server 但未安装 SQL Server Reporting Services, 你可以根据需要按照相应的 SQL Server 2008 R2 或 SQL Server 2012 的相应指令集添加该功能。</span><span class="sxs-lookup"><span data-stu-id="15512-108">If you have already installed SQL Server but did not install SQL Server Reporting Services you can add that feature by following the appropriate set of instructions for SQL Server 2008 R2 or SQL Server 2012, as appropriate.</span></span>

<span data-ttu-id="15512-109">若要验证是否已成功安装 reporting Services, 请完成以下步骤:</span><span class="sxs-lookup"><span data-stu-id="15512-109">To verify that the reporting Services have been successfully installed, complete the following steps:</span></span>

1.  <span data-ttu-id="15512-110">如果你运行的是 Microsoft SQL Server 2008 R2, 请单击 "**开始**", 单击 "**所有程序**", 单击 " **Microsoft SQL Server 2008 R2**", 单击 "**配置工具**", 然后单击 " **Reporting Services 配置管理器**"。</span><span class="sxs-lookup"><span data-stu-id="15512-110">If you are running Microsoft SQL Server 2008 R2, then click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2**, click **Configuration Tools**, and then click **Reporting Services Configuration Manager**.</span></span>
    
    <span data-ttu-id="15512-111">如果你运行的是 Microsoft SQL Server 2012, 请单击 "**开始**", 单击 "**所有程序**", 单击 " **Microsoft SQL Server 2012**", 单击 "**配置工具**", 然后单击 " **Reporting Services 配置管理器**"。</span><span class="sxs-lookup"><span data-stu-id="15512-111">If you are running Microsoft SQL Server 2012, then click **Start**, click **All Programs**, click **Microsoft SQL Server 2012**, click **Configuration Tools**, and then click **Reporting Services Configuration Manager**.</span></span>

2.  <span data-ttu-id="15512-112">在 " **Reporting Services 配置连接**" 对话框中, 验证服务器名称是否显示在 "**服务器名称**" 框中, 以及存储监视数据的 SQL server 实例的名称是否显示在**报表服务器中"实例**" 框。</span><span class="sxs-lookup"><span data-stu-id="15512-112">In the **Reporting Services Configuration Connection** dialog box, verify that the name of your server appears in the **Server Name** box and that the name of the SQL Server instance that stores your monitoring data appears in the **Report Server Instance** box.</span></span> <span data-ttu-id="15512-113">单击 "**连接**"。</span><span class="sxs-lookup"><span data-stu-id="15512-113">Click **Connect**.</span></span>

<span data-ttu-id="15512-114">在 Reporting Services 配置管理器中, 报表服务器状态窗格应显示已安装 SQL Server Reporting Services 且报表服务当前正在运行: 报表服务器状态应显示为 "**已启动**", 然后"**开始**" 按钮应灰显且不可用。</span><span class="sxs-lookup"><span data-stu-id="15512-114">In the Reporting Service Configuration Manager, the Report Server Status pane should show that SQL Server Reporting Services has been installed and that the Reporting Services are currently running: the Report Server Status should be shown as **Started** and the **Start** button should be grayed-out and unavailable.</span></span> <span data-ttu-id="15512-115">如果报告服务未运行, 请单击 "**开始**" 以启动该服务。</span><span class="sxs-lookup"><span data-stu-id="15512-115">If the Reporting Service is not running, click **Start** in order to start the service.</span></span>

<span data-ttu-id="15512-116">如果报表服务器数据库名称标签旁边未列出任何数据库, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="15512-116">If no database is listed next to the Report Server Database Name label then do the following:</span></span>

1.  <span data-ttu-id="15512-117">在 Reporting Services 配置管理器中, 单击 "**数据库**"。</span><span class="sxs-lookup"><span data-stu-id="15512-117">In the Reporting Services Configuration Manager click **Database**.</span></span>

2.  <span data-ttu-id="15512-118">在报表服务器数据库窗格中, 单击 "**更改数据库**"。</span><span class="sxs-lookup"><span data-stu-id="15512-118">In the Report Server Database pane click **Change Database**.</span></span>

3.  <span data-ttu-id="15512-119">在报表服务器数据库配置向导的 "操作" 窗格中, 选择 "**创建新的报表服务器数据库**", 然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="15512-119">In the Report Server Database Configuration wizard, in the Action pane, select **Create a new report server database** and then click **Next**.</span></span>

4.  <span data-ttu-id="15512-120">在报表服务器数据库配置向导的 "数据库服务器" 窗格中, 验证 "**服务器名称**"、"**身份验证类型**" 和 "**用户名**" 框中列出的信息是否正确。</span><span class="sxs-lookup"><span data-stu-id="15512-120">In the Report Server Database Configuration wizard, in the Database Server pane, verify that the information listed in the **Server Name**, **Authentication Type**, and **Username** boxes is correct.</span></span> <span data-ttu-id="15512-121">单击 "**测试连接**" 以验证是否可以与数据库服务器建立连接, 然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="15512-121">Click **Test Connection** to verify that a connection can be made to the database server and then click **Next**.</span></span>

5.  <span data-ttu-id="15512-122">在报表服务器数据库配置向导的 "数据库" 窗格中, 接受 "**数据库名称**"、"**语言**" 和 "**报表服务器" 模式**的默认值, 然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="15512-122">In the Report Server Database Configuration wizard, in the Database pane, accept the default values for **Database Name**, **Language**, and **Report Server Mode** and then click **Next**.</span></span>

6.  <span data-ttu-id="15512-123">在报表服务器数据库配置向导的 "凭据" 窗格中, 验证 "**身份验证类型**" 下拉列表和 "**用户名**" 和 "**密码**" 框中列出的信息是否正确, 然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="15512-123">In the Report Server Database Configuration wizard, in the Credentials pane, verify that the correct information is listed in the **Authentication Type** dropdown list and the **User name** and **Password** boxes, and then click **Next**.</span></span>

7.  <span data-ttu-id="15512-124">在报表服务器数据库配置向导的 "摘要" 窗格中, 单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="15512-124">In the Report Server Database Configuration wizard, in the Summary pane, click **Next**.</span></span>

8.  <span data-ttu-id="15512-125">在报表服务器数据库配置向导中的 "进度" 和 "完成" 窗格中, 单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="15512-125">In the Report Server Database Configuration wizard, in the Progress and Finish pane, click **Finish**.</span></span>

<span data-ttu-id="15512-126">若要验证报告服务 Url 是否已配置, 请单击 " **Web 服务 url**"。</span><span class="sxs-lookup"><span data-stu-id="15512-126">To verify that the Reporting Service URLs have been configured, click **Web Service URL**.</span></span> <span data-ttu-id="15512-127">您应看到标题**报表服务器 Web 服务 url**下列出一个或多个 url。</span><span class="sxs-lookup"><span data-stu-id="15512-127">You should see one or more URLs listed under the heading **Report Server Web Service URLs**.</span></span> <span data-ttu-id="15512-128">单击其中每个 Url, 验证您是否可以访问本地安装 SQL Server Reporting Services 的主页。</span><span class="sxs-lookup"><span data-stu-id="15512-128">Click each of these URLs to verify that you can reach the home page for the local installation of SQL Server Reporting Services.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

