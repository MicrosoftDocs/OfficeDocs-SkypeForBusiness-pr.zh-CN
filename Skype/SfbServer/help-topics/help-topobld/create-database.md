---
title: 创建数据库
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.PublishTopologyCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d391619-1cab-4265-ae8a-2519993705bc
description: 拓扑生成器提供了在 SQL Server 应用商店上安装数据库的方法。 使用拓扑生成器安装数据库时, 应用程序读取拓扑中的信息, 然后在指定的 SQL Server 计算机或 SQL Server 群集上安装所需的数据库。 这是唯一可以使用拓扑生成器进行的数据库安装类型。 如果需要在特定计算机上安装特定数据库, 或者必须安装 collocated 数据库, 则必须改为使用 Windows PowerShell 命令行接口和 CsDatabase cmdlet。
ms.openlocfilehash: a4248827b7eba83534b0fdc2dc82dcaa3487e2d0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34305960"
---
# <a name="create-database"></a><span data-ttu-id="1028f-106">创建数据库</span><span class="sxs-lookup"><span data-stu-id="1028f-106">Create Database</span></span>
 
<span data-ttu-id="1028f-107">拓扑生成器提供了在 SQL Server 应用商店上安装数据库的方法。</span><span class="sxs-lookup"><span data-stu-id="1028f-107">Topology Builder provides a way to install databases on a SQL Server store.</span></span> <span data-ttu-id="1028f-108">使用拓扑生成器安装数据库时, 应用程序读取拓扑中的信息, 然后在指定的 SQL Server 计算机或 SQL Server 群集上安装所需的数据库。</span><span class="sxs-lookup"><span data-stu-id="1028f-108">When you install databases by using Topology Builder, the application reads information from the topology and then installs the required databases on the specified SQL Server computer or SQL Server cluster.</span></span> <span data-ttu-id="1028f-109">这是唯一可以使用拓扑生成器进行的数据库安装类型。</span><span class="sxs-lookup"><span data-stu-id="1028f-109">This is the only type of database installation available by using Topology Builder.</span></span> <span data-ttu-id="1028f-110">如果需要在特定计算机上安装特定数据库, 或者必须安装 collocated 数据库, 则必须改为使用 Windows PowerShell 命令行接口和[CsDatabase](https://docs.microsoft.com/powershell/module/skype/install-csdatabase?view=skype-ps) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1028f-110">If you need to install a specific database on a specific computer, or if you must install a collocated database, you must use Windows PowerShell command-line interface and the [Install-CsDatabase](https://docs.microsoft.com/powershell/module/skype/install-csdatabase?view=skype-ps) cmdlet instead.</span></span>
  
### <a name="creating-a-database"></a><span data-ttu-id="1028f-111">创建数据库</span><span class="sxs-lookup"><span data-stu-id="1028f-111">Creating a Database</span></span>

1. <span data-ttu-id="1028f-112">单击 "Skype for Business 服务器 2015" 节点, 然后单击 "**安装数据库**"。</span><span class="sxs-lookup"><span data-stu-id="1028f-112">Click the Skype for Business Server 2015 node and then click **Install Database**.</span></span>
    
2. <span data-ttu-id="1028f-113">在 "**安装**数据库" 对话框中的 "**创建数据库**" 页面上, 选择要在其中创建新数据库的 SQL Server 应用商店的完全限定的域名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="1028f-113">In the **Install Databases** dialog box, on the **Create Database** page, select the fully qualified domain name (FQDN) of the SQL Server store where the new databases are to be created.</span></span>
    
3. <span data-ttu-id="1028f-p103">单击“**高级**”。在“**选择数据库文件位置**”对话框中，选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="1028f-p103">Click **Advanced**. In the **Select Database File Location** dialog box, select one of the following options:</span></span>
    
   - <span data-ttu-id="1028f-p104">**自动确定数据库文件位置**。如果选择此选项，拓扑生成器将使用内置算法选择数据库日志和数据文件的存储位置。</span><span class="sxs-lookup"><span data-stu-id="1028f-p104">**Automatically determine database file location**. If you select this option, Topology Builder uses a built-in algorithm to choose the storage location for the database logs and data files.</span></span>
    
   - <span data-ttu-id="1028f-118">**使用 SQL Server 实例默认值**。</span><span class="sxs-lookup"><span data-stu-id="1028f-118">**Use SQL Server instance defaults**.</span></span> <span data-ttu-id="1028f-119">如果选择此选项，将不会使用内置算法选择数据库日志和数据文件的存储位置。</span><span class="sxs-lookup"><span data-stu-id="1028f-119">If you select this option, the built-in algorithm is not used to choose the storage locations for the database logs and data files.</span></span> <span data-ttu-id="1028f-120">而是将日志和数据文件存储在 SQL Server 默认路径指定的位置 (这些路径必须由 SQL Server 管理员配置为 "高级")。</span><span class="sxs-lookup"><span data-stu-id="1028f-120">Instead, log and data files are stored in the locations specified by the SQL Server defaults path (these paths must be configured in advanced by a SQL Server administrator).</span></span> <span data-ttu-id="1028f-121">数据文件将存储在默认 SQL Server 数据文件位置，而日志文件将存储在默认 SQL Server 日志文件位置。</span><span class="sxs-lookup"><span data-stu-id="1028f-121">Data files will be stored in the default SQL Server data file location while log files will be stored in the default SQL Server log file location.</span></span>
    
4. <span data-ttu-id="1028f-122">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="1028f-122">Click **OK**.</span></span>
    
5. <span data-ttu-id="1028f-123">在“**创建数据库**”页上，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="1028f-123">On the **Create Database** page, click **Next**.</span></span>
    
6. <span data-ttu-id="1028f-124">在“**数据库创建已完成**”页上，单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="1028f-124">On the **Database Creation Complete** page, click **Finish**.</span></span>
    

