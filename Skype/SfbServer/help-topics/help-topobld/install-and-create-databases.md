---
title: 安装和创建数据库
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.InstallDatabaseCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 515754ad-1344-42dc-8219-ee973de2e4c4
description: 选择要在其中创建您的部署的数据库。 默认情况下，数据库将在定义的站点中定义的 SQL Server 上创建并将自动部署并配置基于正在将数据库放在 SQL Server 的数据库文件。
ms.openlocfilehash: cf838e66dc5e9592ba71dd9d44fa5fc333c6dbc7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="install-and-create-databases"></a><span data-ttu-id="8294d-104">安装和创建数据库</span><span class="sxs-lookup"><span data-stu-id="8294d-104">Install and Create Databases</span></span>
 
<span data-ttu-id="8294d-105">选择要在其中创建您的部署的数据库。</span><span class="sxs-lookup"><span data-stu-id="8294d-105">You select the databases that you want to create for your deployment.</span></span> <span data-ttu-id="8294d-106">默认情况下，数据库将在定义的站点中定义的 SQL Server 上创建并将自动部署并配置基于正在将数据库放在 SQL Server 的数据库文件。</span><span class="sxs-lookup"><span data-stu-id="8294d-106">By default, the database will be created on the defined SQL Server in the defined site, and will automatically deploy and configure the database files based on the SQL Server you are placing the databases on.</span></span>
  
 <span data-ttu-id="8294d-107">**选择您想要创建的数据库**： 选择您打算部署和配置的任何数据库的复选框。</span><span class="sxs-lookup"><span data-stu-id="8294d-107">**Select the databases you want to create**: Select the checkbox of any databases that you intend to deploy and configure.</span></span> <span data-ttu-id="8294d-108">请选择您将部署的任何或所有数据库。</span><span class="sxs-lookup"><span data-stu-id="8294d-108">Select the check box of any or all databases that you will deploy.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="8294d-109">SQL Server 必须已进行了配置 （如果有） 的实例，必须打开的防火墙端口以适应您要部署到的数据库的实例。</span><span class="sxs-lookup"><span data-stu-id="8294d-109">The SQL Server must already have been configured for the instance (if any) and firewall ports must be opened to accommodate the instance that you are deploying the databases to.</span></span> <span data-ttu-id="8294d-110">有关详细信息，请参阅[将 SQL Server 配置 Lync 服务器 2013年预览](http://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)</span><span class="sxs-lookup"><span data-stu-id="8294d-110">For details, see [Configure SQL Server for Lync Server 2013 Preview](http://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)</span></span>
  
 <span data-ttu-id="8294d-111">**高级**： 在 SQL Server 上单击，单击**高级**按钮以选择文件位置上 SQL Server 数据库的选项。</span><span class="sxs-lookup"><span data-stu-id="8294d-111">**Advanced**: Click on the SQL Server and click the **Advanced** button to choose options for the database file locations on your SQL Server.</span></span> <span data-ttu-id="8294d-112">高级的数据库文件的位置的详细信息，请参阅[数据库安装使用 Lync 服务器命令行管理程序](http://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)</span><span class="sxs-lookup"><span data-stu-id="8294d-112">For details on advanced database file placement, see [Database Installation Using Lync Server Management Shell](http://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)</span></span>
  
 <span data-ttu-id="8294d-113">**回**： 单击此按钮将返回到前一个屏幕 （不总是可能可用，请根据您如何到达此对话框）。</span><span class="sxs-lookup"><span data-stu-id="8294d-113">**Back**: Clicking this button returns you to the previous screen (may not always be available, based on how you arrived at this dialog).</span></span>
  
 <span data-ttu-id="8294d-114">**下一步**： 单击此按钮提交在对话框中当前所选内容并将您带到下一对话框用于配置的其他信息</span><span class="sxs-lookup"><span data-stu-id="8294d-114">**Next**: Clicking this button commits your selection on the current dialog and takes you to the next dialog for configuring additional information</span></span>
  
 <span data-ttu-id="8294d-115">**取消**： 单击此按钮将退出配置并放弃所做的更改。</span><span class="sxs-lookup"><span data-stu-id="8294d-115">**Cancel**: Clicking this button will quit the configuration and discard your changes.</span></span> <span data-ttu-id="8294d-116">某些但不是所有配置屏幕将提示您，如果您想要退出并放弃更改。</span><span class="sxs-lookup"><span data-stu-id="8294d-116">Some, but not all configuration screens will prompt you if you want to quit and discard your changes.</span></span> <span data-ttu-id="8294d-117">选择**是**将关闭当前配置并关闭当前的配置并使您返回到拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="8294d-117">Selecting **Yes** will close the current configuration and close the current configuration and return you to Topology Builder.</span></span> <span data-ttu-id="8294d-118">选择**否**会使您返回到配置对话框，允许您继续配置。</span><span class="sxs-lookup"><span data-stu-id="8294d-118">Selecting **No** will return you to the current configuration dialog and allow you to continue the configuration.</span></span>
  
 <span data-ttu-id="8294d-119">**帮助**： 单击**帮助**按钮显示该帮助信息，与当前配置对话框。</span><span class="sxs-lookup"><span data-stu-id="8294d-119">**Help**: Clicking the **Help** button displays this help information associated with the current configuration dialog.</span></span>
  

