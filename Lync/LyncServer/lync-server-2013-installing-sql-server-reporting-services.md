---
title: Lync Server 2013：安装 SQL Server Reporting Services
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing SQL Server Reporting Services
ms:assetid: 638a1d0c-1ac7-4735-83f2-4df3d03c7cf9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204957(v=OCS.15)
ms:contentKeyID: 48184345
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e1663bad8515082603a411a42de5c98d7f70594
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045244"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-sql-server-reporting-services-in-lync-server-2013"></a><span data-ttu-id="9c94b-102">在 Lync Server 2013 中安装 SQL Server Reporting Services</span><span class="sxs-lookup"><span data-stu-id="9c94b-102">Installing SQL Server Reporting Services in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9c94b-103">_**上次修改的主题：** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="9c94b-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="9c94b-104">如果打算使用 Microsoft Lync Server 2013 监控报告（有关详细信息，请参阅本文档的下一节），必须先安装 SQL Server Reporting Services;可以在安装 Microsoft SQL Server 的同时安装 Reporting Services，也可以在安装 SQL Server 之后安装任何时间。</span><span class="sxs-lookup"><span data-stu-id="9c94b-104">If you intend to use Microsoft Lync Server 2013 Monitoring Reports (see the next section of this documentation for more information) you must first install SQL Server Reporting Services; Reporting Services can be installed at the same time you install Microsoft SQL Server or any time after SQL Server has been installed.</span></span> <span data-ttu-id="9c94b-105">如果您未安装 SQL Server，则请按照本文档之前提供的说明操作。</span><span class="sxs-lookup"><span data-stu-id="9c94b-105">If you have not installed SQL Server, then follow the instructions provided earlier in this documentation.</span></span> <span data-ttu-id="9c94b-106">安装 SQL Server 时，确保在“功能选择”页上选择 Reporting Services。</span><span class="sxs-lookup"><span data-stu-id="9c94b-106">When installing SQL Server, make sure that, on the Feature Selection page, you select Reporting Services.</span></span> <span data-ttu-id="9c94b-107">这将安装 SQL Server Reporting Services。</span><span class="sxs-lookup"><span data-stu-id="9c94b-107">That will install SQL Server Reporting Services.</span></span>

<span data-ttu-id="9c94b-108">如果您已安装 SQL Server 但未安装 SQL Server Reporting Services，则可根据需要按照 SQL Server 2008 R2 或 SQL Server 2012 中的相应说明集添加此功能。</span><span class="sxs-lookup"><span data-stu-id="9c94b-108">If you have already installed SQL Server but did not install SQL Server Reporting Services you can add that feature by following the appropriate set of instructions for SQL Server 2008 R2 or SQL Server 2012, as appropriate.</span></span>

<span data-ttu-id="9c94b-109">若要验证 reporting Services 安装是否成功，请完成下列步骤：</span><span class="sxs-lookup"><span data-stu-id="9c94b-109">To verify that the reporting Services have been successfully installed, complete the following steps:</span></span>

1.  <span data-ttu-id="9c94b-110">如果您运行的是 Microsoft SQL Server 2008 R2，则依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft SQL Server 2008 R2”\*\*\*\*、“配置工具”\*\*\*\* 和“Reporting Services 配置管理器”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9c94b-110">If you are running Microsoft SQL Server 2008 R2, then click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2**, click **Configuration Tools**, and then click **Reporting Services Configuration Manager**.</span></span>
    
    <span data-ttu-id="9c94b-111">如果您运行的是 Microsoft SQL Server 2012，则依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft SQL Server 2012”\*\*\*\*、“配置工具”\*\*\*\* 和“Reporting Services 配置管理器”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9c94b-111">If you are running Microsoft SQL Server 2012, then click **Start**, click **All Programs**, click **Microsoft SQL Server 2012**, click **Configuration Tools**, and then click **Reporting Services Configuration Manager**.</span></span>

2.  <span data-ttu-id="9c94b-p102">在“Reporting Services 配置连接”\*\*\*\* 对话框中，验证服务器的名称是否显示在“服务器名称”\*\*\*\* 框中以及存储监控数据的 SQL Server 实例的名称是否显示在“报表服务器实例”\*\*\*\* 框中。单击“连接”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9c94b-p102">In the **Reporting Services Configuration Connection** dialog box, verify that the name of your server appears in the **Server Name** box and that the name of the SQL Server instance that stores your monitoring data appears in the **Report Server Instance** box. Click **Connect**.</span></span>

<span data-ttu-id="9c94b-114">在 Reporting Service 配置管理器中，报表服务器状态窗格应显示已安装 SQL Server Reporting Services 且当前正在运行 Reporting Services：报表服务器状态应显示为 "**已启动**"，并且 "**启动**" 按钮应显示为 "灰色" 且不可用。</span><span class="sxs-lookup"><span data-stu-id="9c94b-114">In the Reporting Service Configuration Manager, the Report Server Status pane should show that SQL Server Reporting Services has been installed and that the Reporting Services are currently running: the Report Server Status should be shown as **Started** and the **Start** button should be grayed-out and unavailable.</span></span> <span data-ttu-id="9c94b-115">如果 Reporting Service 未在运行，则单击“开始”\*\*\*\* 以启动此服务。</span><span class="sxs-lookup"><span data-stu-id="9c94b-115">If the Reporting Service is not running, click **Start** in order to start the service.</span></span>

<span data-ttu-id="9c94b-116">如果报表服务器数据库名称标签旁未列出任何数据库，则执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="9c94b-116">If no database is listed next to the Report Server Database Name label then do the following:</span></span>

1.  <span data-ttu-id="9c94b-117">在 Reporting Services 配置管理器中，单击“数据库”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9c94b-117">In the Reporting Services Configuration Manager click **Database**.</span></span>

2.  <span data-ttu-id="9c94b-118">在“报表服务器数据库”窗格中，单击“更改数据库”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9c94b-118">In the Report Server Database pane click **Change Database**.</span></span>

3.  <span data-ttu-id="9c94b-119">在“报表服务器数据库配置”向导的“操作”窗格中，选择“创建新的报表服务器数据库”\*\*\*\*，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9c94b-119">In the Report Server Database Configuration wizard, in the Action pane, select **Create a new report server database** and then click **Next**.</span></span>

4.  <span data-ttu-id="9c94b-p104">在“报表服务器数据库配置”向导的“数据库服务器”窗格中，验证“服务器名称”\*\*\*\*、“身份验证类型”\*\*\*\* 和“用户名”\*\*\*\* 中列出的信息是否正确。单击“测试连接”\*\*\*\* 以验证是否能连接到数据库服务器，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9c94b-p104">In the Report Server Database Configuration wizard, in the Database Server pane, verify that the information listed in the **Server Name**, **Authentication Type**, and **Username** boxes is correct. Click **Test Connection** to verify that a connection can be made to the database server and then click **Next**.</span></span>

5.  <span data-ttu-id="9c94b-122">在“报表服务器数据库配置”向导的“数据库”窗格中，接受“数据库名称”\*\*\*\*、“语言”\*\*\*\* 和“报表服务器模式”\*\*\*\* 的默认值，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9c94b-122">In the Report Server Database Configuration wizard, in the Database pane, accept the default values for **Database Name**, **Language**, and **Report Server Mode** and then click **Next**.</span></span>

6.  <span data-ttu-id="9c94b-123">在“报表服务器数据库配置”向导的“凭据”窗格中，验证“身份验证类型”\*\*\*\* 下拉列表和“用户名”\*\*\*\* 框以及“密码”\*\*\*\* 框中是否列出了正确的信息，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9c94b-123">In the Report Server Database Configuration wizard, in the Credentials pane, verify that the correct information is listed in the **Authentication Type** dropdown list and the **User name** and **Password** boxes, and then click **Next**.</span></span>

7.  <span data-ttu-id="9c94b-124">在“报表服务器数据库配置”向导的“摘要”窗格中，单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9c94b-124">In the Report Server Database Configuration wizard, in the Summary pane, click **Next**.</span></span>

8.  <span data-ttu-id="9c94b-125">在“报表服务器数据库配置”向导的“进度和完成”窗格中，单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9c94b-125">In the Report Server Database Configuration wizard, in the Progress and Finish pane, click **Finish**.</span></span>

<span data-ttu-id="9c94b-p105">若要验证是否配置了 Reporting Service URL，请单击“Web 服务 URL”\*\*\*\*。您应在标题“报表服务器 Web 服务 URL”\*\*\*\* 下看到列出了一个或多个 URL。单击其中每个 URL 以验证您是否能够访问本地安装的 SQL Server Reporting Services 的主页。</span><span class="sxs-lookup"><span data-stu-id="9c94b-p105">To verify that the Reporting Service URLs have been configured, click **Web Service URL**. You should see one or more URLs listed under the heading **Report Server Web Service URLs**. Click each of these URLs to verify that you can reach the home page for the local installation of SQL Server Reporting Services.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

