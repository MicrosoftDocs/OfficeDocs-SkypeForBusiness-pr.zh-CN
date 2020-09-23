---
title: 安装和创建数据库
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.InstallDatabaseCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 515754ad-1344-42dc-8219-ee973de2e4c4
description: 选择要为您的部署创建的数据库。 默认情况下，将在定义的网站中定义的 SQL Server 上创建数据库，并且将根据您要放置数据库的 SQL Server 自动部署和配置数据库文件。
ms.openlocfilehash: ade264fcda73df408f6bb323dd1e3733ccdd45f1
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215383"
---
# <a name="install-and-create-databases"></a><span data-ttu-id="13f82-104">安装和创建数据库</span><span class="sxs-lookup"><span data-stu-id="13f82-104">Install and Create Databases</span></span>

<span data-ttu-id="13f82-105">选择要为您的部署创建的数据库。</span><span class="sxs-lookup"><span data-stu-id="13f82-105">You select the databases that you want to create for your deployment.</span></span> <span data-ttu-id="13f82-106">默认情况下，将在定义的网站中定义的 SQL Server 上创建数据库，并且将根据您要放置数据库的 SQL Server 自动部署和配置数据库文件。</span><span class="sxs-lookup"><span data-stu-id="13f82-106">By default, the database will be created on the defined SQL Server in the defined site, and will automatically deploy and configure the database files based on the SQL Server you are placing the databases on.</span></span>

 <span data-ttu-id="13f82-107">**选择要创建的数据库**：选中您打算部署和配置的任何数据库的复选框。</span><span class="sxs-lookup"><span data-stu-id="13f82-107">**Select the databases you want to create**: Select the checkbox of any databases that you intend to deploy and configure.</span></span> <span data-ttu-id="13f82-108">选中您将部署的任何或所有数据库的复选框。</span><span class="sxs-lookup"><span data-stu-id="13f82-108">Select the check box of any or all databases that you will deploy.</span></span>

> [!CAUTION]
> <span data-ttu-id="13f82-109">如果必须打开任何) 和防火墙端口以适应要将数据库部署到的实例，则必须已为实例 (配置了 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="13f82-109">The SQL Server must already have been configured for the instance (if any) and firewall ports must be opened to accommodate the instance that you are deploying the databases to.</span></span> <span data-ttu-id="13f82-110">有关详细信息，请参阅 [CONFIGURE SQL Server For Lync Server 2013 Preview](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)</span><span class="sxs-lookup"><span data-stu-id="13f82-110">For details, see [Configure SQL Server for Lync Server 2013 Preview](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)</span></span>

 <span data-ttu-id="13f82-111">**高级**：单击 sql server 并单击 " **高级** " 按钮，为 SQL server 上的数据库文件位置选择选项。</span><span class="sxs-lookup"><span data-stu-id="13f82-111">**Advanced**: Click on the SQL Server and click the **Advanced** button to choose options for the database file locations on your SQL Server.</span></span> <span data-ttu-id="13f82-112">有关高级数据库文件放置的详细信息，请参阅 [使用 Lync Server 命令行管理程序进行数据库安装](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)</span><span class="sxs-lookup"><span data-stu-id="13f82-112">For details on advanced database file placement, see [Database Installation Using Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)</span></span>

 <span data-ttu-id="13f82-113">**后退**：单击此按钮将返回到上一个屏幕 (可能并非始终可用，具体取决于您在此对话框中的到达方式) 。</span><span class="sxs-lookup"><span data-stu-id="13f82-113">**Back**: Clicking this button returns you to the previous screen (may not always be available, based on how you arrived at this dialog).</span></span>

 <span data-ttu-id="13f82-114">**下一步**：单击此按钮可提交当前对话框中的选择，并转到下一个用于配置其他信息的对话框</span><span class="sxs-lookup"><span data-stu-id="13f82-114">**Next**: Clicking this button commits your selection on the current dialog and takes you to the next dialog for configuring additional information</span></span>

 <span data-ttu-id="13f82-115">**取消**：单击此按钮将退出配置并放弃所做的更改。</span><span class="sxs-lookup"><span data-stu-id="13f82-115">**Cancel**: Clicking this button will quit the configuration and discard your changes.</span></span> <span data-ttu-id="13f82-116">有些（但不是所有配置屏幕）将会提示您是否要退出并放弃更改。</span><span class="sxs-lookup"><span data-stu-id="13f82-116">Some, but not all configuration screens will prompt you if you want to quit and discard your changes.</span></span> <span data-ttu-id="13f82-117">选择 **"是"** 将关闭当前配置并关闭当前配置并返回拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="13f82-117">Selecting **Yes** will close the current configuration and close the current configuration and return you to Topology Builder.</span></span> <span data-ttu-id="13f82-118">如果选择 " **否** "，将返回到 "当前配置" 对话框，并允许您继续配置。</span><span class="sxs-lookup"><span data-stu-id="13f82-118">Selecting **No** will return you to the current configuration dialog and allow you to continue the configuration.</span></span>

 <span data-ttu-id="13f82-119">**帮助**：单击 " **帮助** " 按钮将显示与 "当前配置" 对话框关联的 "帮助" 信息。</span><span class="sxs-lookup"><span data-stu-id="13f82-119">**Help**: Clicking the **Help** button displays this help information associated with the current configuration dialog.</span></span>


