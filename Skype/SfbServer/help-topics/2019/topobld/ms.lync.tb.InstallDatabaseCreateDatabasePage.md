---
title: 安装和创建数据库
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.InstallDatabaseCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 515754ad-1344-42dc-8219-ee973de2e4c4
ROBOTS: NOINDEX, NOFOLLOW
description: 选择您要为您的部署创建的数据库。 默认情况下，数据库将在定义网站中，在定义 SQL 服务器上创建和将自动部署并配置根据您要将数据库放在 SQL Server 数据库文件。
ms.openlocfilehash: a0a49f5c751503c166d83c16e815a1cd63db751a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33906632"
---
# <a name="install-and-create-databases"></a><span data-ttu-id="f8344-104">安装和创建数据库</span><span class="sxs-lookup"><span data-stu-id="f8344-104">Install and Create Databases</span></span>

<span data-ttu-id="f8344-105">选择您要为您的部署创建的数据库。</span><span class="sxs-lookup"><span data-stu-id="f8344-105">You select the databases that you want to create for your deployment.</span></span> <span data-ttu-id="f8344-106">默认情况下，数据库将在定义网站中，在定义 SQL 服务器上创建和将自动部署并配置根据您要将数据库放在 SQL Server 数据库文件。</span><span class="sxs-lookup"><span data-stu-id="f8344-106">By default, the database will be created on the defined SQL Server in the defined site, and will automatically deploy and configure the database files based on the SQL Server you are placing the databases on.</span></span>

 <span data-ttu-id="f8344-107">**选择您想要创建的数据库**： 选中您打算部署和配置任何数据库的复选框。</span><span class="sxs-lookup"><span data-stu-id="f8344-107">**Select the databases you want to create**: Select the checkbox of any databases that you intend to deploy and configure.</span></span> <span data-ttu-id="f8344-108">选择将部署的任何或所有数据库的复选框。</span><span class="sxs-lookup"><span data-stu-id="f8344-108">Select the check box of any or all databases that you will deploy.</span></span>

> [!CAUTION]
> <span data-ttu-id="f8344-109">SQL Server 必须已进行了配置实例 （如果有），并且必须打开防火墙端口以容纳要部署到的数据库的实例。</span><span class="sxs-lookup"><span data-stu-id="f8344-109">The SQL Server must already have been configured for the instance (if any) and firewall ports must be opened to accommodate the instance that you are deploying the databases to.</span></span> <span data-ttu-id="f8344-110">有关详细信息，请参阅[Configure SQL Server](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)</span><span class="sxs-lookup"><span data-stu-id="f8344-110">For details, see [Configure SQL Server](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)</span></span>

 <span data-ttu-id="f8344-111">**高级**： 单击 SQL Server 上，单击**高级**按钮以选择 SQL Server 上的文件位置选项的数据库。</span><span class="sxs-lookup"><span data-stu-id="f8344-111">**Advanced**: Click on the SQL Server and click the **Advanced** button to choose options for the database file locations on your SQL Server.</span></span> <span data-ttu-id="f8344-112">有关高级的数据库文件位置的详细信息，请参阅[数据库安装使用 Lync Server 命令行管理程序](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)</span><span class="sxs-lookup"><span data-stu-id="f8344-112">For details on advanced database file placement, see [Database Installation Using Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)</span></span>

 <span data-ttu-id="f8344-113">**返回**： 单击此按钮返回到上一个屏幕 （可能始终不可用，基于如何到达此对话框）。</span><span class="sxs-lookup"><span data-stu-id="f8344-113">**Back**: Clicking this button returns you to the previous screen (may not always be available, based on how you arrived at this dialog).</span></span>

 <span data-ttu-id="f8344-114">**下一步**： 单击此按钮应用当前对话框上的您所选内容，并转到下一步对话框中配置其他信息</span><span class="sxs-lookup"><span data-stu-id="f8344-114">**Next**: Clicking this button commits your selection on the current dialog and takes you to the next dialog for configuring additional information</span></span>

 <span data-ttu-id="f8344-115">**取消**： 单击此按钮将退出配置并放弃所做的更改。</span><span class="sxs-lookup"><span data-stu-id="f8344-115">**Cancel**: Clicking this button will quit the configuration and discard your changes.</span></span> <span data-ttu-id="f8344-116">如果您想要退出并放弃所做的更改，某些，而不是全部配置屏幕将提示您。</span><span class="sxs-lookup"><span data-stu-id="f8344-116">Some, but not all configuration screens will prompt you if you want to quit and discard your changes.</span></span> <span data-ttu-id="f8344-117">选择**是**时，将关闭当前配置和关闭当前配置并返回到拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="f8344-117">Selecting **Yes** will close the current configuration and close the current configuration and return you to Topology Builder.</span></span> <span data-ttu-id="f8344-118">选择**无**将您返回到配置对话框，并允许您继续配置。</span><span class="sxs-lookup"><span data-stu-id="f8344-118">Selecting **No** will return you to the current configuration dialog and allow you to continue the configuration.</span></span>

 <span data-ttu-id="f8344-119">**帮助**： 单击**帮助**按钮显示与当前配置对话框关联的此帮助信息。</span><span class="sxs-lookup"><span data-stu-id="f8344-119">**Help**: Clicking the **Help** button displays this help information associated with the current configuration dialog.</span></span>


