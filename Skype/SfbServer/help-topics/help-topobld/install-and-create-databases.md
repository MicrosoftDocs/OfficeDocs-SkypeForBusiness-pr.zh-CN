---
title: 安装和创建数据库
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 选择要为部署创建的数据库。 默认情况下，将在已定义网站中定义的 SQL Server 上创建数据库，并基于要放置数据库的 SQL Server自动部署和配置数据库文件。
ms.openlocfilehash: 3e7e2e0aaec55c595a4f538238c431feb9173152
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120924"
---
# <a name="install-and-create-databases"></a><span data-ttu-id="4c58c-104">安装和创建数据库</span><span class="sxs-lookup"><span data-stu-id="4c58c-104">Install and Create Databases</span></span>

<span data-ttu-id="4c58c-105">选择要为部署创建的数据库。</span><span class="sxs-lookup"><span data-stu-id="4c58c-105">You select the databases that you want to create for your deployment.</span></span> <span data-ttu-id="4c58c-106">默认情况下，将在已定义网站中定义的 SQL Server 上创建数据库，并基于要放置数据库的 SQL Server自动部署和配置数据库文件。</span><span class="sxs-lookup"><span data-stu-id="4c58c-106">By default, the database will be created on the defined SQL Server in the defined site, and will automatically deploy and configure the database files based on the SQL Server you are placing the databases on.</span></span>

 <span data-ttu-id="4c58c-107">**选择要创建的数据库**：选中要部署和配置的任何数据库的复选框。</span><span class="sxs-lookup"><span data-stu-id="4c58c-107">**Select the databases you want to create**: Select the checkbox of any databases that you intend to deploy and configure.</span></span> <span data-ttu-id="4c58c-108">选中要部署的任何或所有数据库的复选框。</span><span class="sxs-lookup"><span data-stu-id="4c58c-108">Select the check box of any or all databases that you will deploy.</span></span>

> [!CAUTION]
> <span data-ttu-id="4c58c-109">SQL Server 如果必须打开任何) 和防火墙端口以容纳要部署数据库的实例，则必须为实例 (配置该端口。</span><span class="sxs-lookup"><span data-stu-id="4c58c-109">The SQL Server must already have been configured for the instance (if any) and firewall ports must be opened to accommodate the instance that you are deploying the databases to.</span></span> <span data-ttu-id="4c58c-110">有关详细信息，请参阅 [Configure SQL Server for Lync Server 2013 Preview](/previous-versions/office/lync-server-2013/lync-server-2013-configure-sql-server-for-lync-server)</span><span class="sxs-lookup"><span data-stu-id="4c58c-110">For details, see [Configure SQL Server for Lync Server 2013 Preview](/previous-versions/office/lync-server-2013/lync-server-2013-configure-sql-server-for-lync-server)</span></span>

 <span data-ttu-id="4c58c-111">**高级**：单击SQL Server然后单击" **高级** "按钮以选择数据库中数据库文件位置SQL Server。</span><span class="sxs-lookup"><span data-stu-id="4c58c-111">**Advanced**: Click on the SQL Server and click the **Advanced** button to choose options for the database file locations on your SQL Server.</span></span> <span data-ttu-id="4c58c-112">有关高级数据库文件放置的详细信息，请参阅 Database [Installation Using Lync Server Management Shell](/previous-versions/office/lync-server-2013/lync-server-2013-database-installation-using-lync-server-management-shell)</span><span class="sxs-lookup"><span data-stu-id="4c58c-112">For details on advanced database file placement, see [Database Installation Using Lync Server Management Shell](/previous-versions/office/lync-server-2013/lync-server-2013-database-installation-using-lync-server-management-shell)</span></span>

 <span data-ttu-id="4c58c-113">**返回**：单击此按钮将返回到上一 (可能并不总是可用，根据你到达此对话框) 。</span><span class="sxs-lookup"><span data-stu-id="4c58c-113">**Back**: Clicking this button returns you to the previous screen (may not always be available, based on how you arrived at this dialog).</span></span>

 <span data-ttu-id="4c58c-114">**Next**： Clicking this button commits your selection on the current dialog and takes you to the next dialog for configuring additional information</span><span class="sxs-lookup"><span data-stu-id="4c58c-114">**Next**: Clicking this button commits your selection on the current dialog and takes you to the next dialog for configuring additional information</span></span>

 <span data-ttu-id="4c58c-115">**取消**：单击此按钮将退出配置并放弃更改。</span><span class="sxs-lookup"><span data-stu-id="4c58c-115">**Cancel**: Clicking this button will quit the configuration and discard your changes.</span></span> <span data-ttu-id="4c58c-116">如果要退出并放弃更改，某些（但不是所有）配置屏幕将提示你。</span><span class="sxs-lookup"><span data-stu-id="4c58c-116">Some, but not all configuration screens will prompt you if you want to quit and discard your changes.</span></span> <span data-ttu-id="4c58c-117">选择 **"** 是"将关闭当前配置并关闭当前配置，并返回到拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="4c58c-117">Selecting **Yes** will close the current configuration and close the current configuration and return you to Topology Builder.</span></span> <span data-ttu-id="4c58c-118">选择 **否** 将返回到当前配置对话框，并允许你继续配置。</span><span class="sxs-lookup"><span data-stu-id="4c58c-118">Selecting **No** will return you to the current configuration dialog and allow you to continue the configuration.</span></span>

 <span data-ttu-id="4c58c-119">**帮助**：单击 **"帮助** "按钮将显示与当前配置对话框关联的帮助信息。</span><span class="sxs-lookup"><span data-stu-id="4c58c-119">**Help**: Clicking the **Help** button displays this help information associated with the current configuration dialog.</span></span>