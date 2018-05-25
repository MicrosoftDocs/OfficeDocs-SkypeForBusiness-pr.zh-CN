---
title: 创建数据库
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.PublishTopologyCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d391619-1cab-4265-ae8a-2519993705bc
description: 拓扑生成器提供一种方法在 SQL Server 存储上安装数据库。 使用拓扑生成器安装数据库时，应用程序从拓扑中读取信息，然后将所需的数据库安装在指定的 SQL Server 计算机或 SQL Server 群集。 这是唯一可以使用拓扑生成器进行的数据库安装类型。 如果您需要在特定计算机上，安装特定数据库，或者必须安装并置的数据库，您必须改为使用 Windows PowerShell 命令行界面和的 Install-csdatabase cmdlet。
ms.openlocfilehash: 9bee333e0b56a6eeb8f4363e6657be2fabfa1ace
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2018
---
# <a name="create-database"></a><span data-ttu-id="98d7b-106">创建数据库</span><span class="sxs-lookup"><span data-stu-id="98d7b-106">Create Database</span></span>
 
<span data-ttu-id="98d7b-107">拓扑生成器提供一种方法在 SQL Server 存储上安装数据库。</span><span class="sxs-lookup"><span data-stu-id="98d7b-107">Topology Builder provides a way to install databases on a SQL Server store.</span></span> <span data-ttu-id="98d7b-108">使用拓扑生成器安装数据库时，应用程序从拓扑中读取信息，然后将所需的数据库安装在指定的 SQL Server 计算机或 SQL Server 群集。</span><span class="sxs-lookup"><span data-stu-id="98d7b-108">When you install databases by using Topology Builder, the application reads information from the topology and then installs the required databases on the specified SQL Server computer or SQL Server cluster.</span></span> <span data-ttu-id="98d7b-109">这是唯一可以使用拓扑生成器进行的数据库安装类型。</span><span class="sxs-lookup"><span data-stu-id="98d7b-109">This is the only type of database installation available by using Topology Builder.</span></span> <span data-ttu-id="98d7b-110">如果您需要在特定计算机上，安装特定数据库，或者必须安装并置的数据库，您必须改为使用 Windows PowerShell 命令行界面和的[Install-csdatabase](https://docs.microsoft.com/powershell/module/skype/install-csdatabase?view=skype-ps) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="98d7b-110">If you need to install a specific database on a specific computer, or if you must install a collocated database, you must use Windows PowerShell command-line interface and the [Install-CsDatabase](https://docs.microsoft.com/powershell/module/skype/install-csdatabase?view=skype-ps) cmdlet instead.</span></span>
  
### <a name="creating-a-database"></a><span data-ttu-id="98d7b-111">创建数据库</span><span class="sxs-lookup"><span data-stu-id="98d7b-111">Creating a Database</span></span>

1. <span data-ttu-id="98d7b-112">单击业务服务器 2015年节点 Skype，然后单击**安装数据库**。</span><span class="sxs-lookup"><span data-stu-id="98d7b-112">Click the Skype for Business Server 2015 node and then click **Install Database**.</span></span>
    
2. <span data-ttu-id="98d7b-113">在**安装数据库**对话框中，在**创建数据库**页上，选择新数据库要创建的 SQL Server 存储的完全限定的域名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="98d7b-113">In the **Install Databases** dialog box, on the **Create Database** page, select the fully qualified domain name (FQDN) of the SQL Server store where the new databases are to be created.</span></span>
    
3. <span data-ttu-id="98d7b-p103">单击“**高级**”。在“**选择数据库文件位置**”对话框中，选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="98d7b-p103">Click **Advanced**. In the **Select Database File Location** dialog box, select one of the following options:</span></span>
    
  - <span data-ttu-id="98d7b-p104">**自动确定数据库文件位置**。如果选择此选项，拓扑生成器将使用内置算法选择数据库日志和数据文件的存储位置。</span><span class="sxs-lookup"><span data-stu-id="98d7b-p104">**Automatically determine database file location**. If you select this option, Topology Builder uses a built-in algorithm to choose the storage location for the database logs and data files.</span></span>
    
  - <span data-ttu-id="98d7b-118">**使用 SQL Server 实例默认值**。</span><span class="sxs-lookup"><span data-stu-id="98d7b-118">**Use SQL Server instance defaults**.</span></span> <span data-ttu-id="98d7b-119">如果选择此选项，将不会使用内置算法选择数据库日志和数据文件的存储位置。</span><span class="sxs-lookup"><span data-stu-id="98d7b-119">If you select this option, the built-in algorithm is not used to choose the storage locations for the database logs and data files.</span></span> <span data-ttu-id="98d7b-120">而是日志和数据文件存储在 SQL Server 默认路径 （这些路径必须配置中的 SQL Server 管理员高级） 指定的位置。</span><span class="sxs-lookup"><span data-stu-id="98d7b-120">Instead, log and data files are stored in the locations specified by the SQL Server defaults path (these paths must be configured in advanced by a SQL Server administrator).</span></span> <span data-ttu-id="98d7b-121">数据文件将存储在默认 SQL Server 数据文件位置，而日志文件将存储在默认 SQL Server 日志文件位置。</span><span class="sxs-lookup"><span data-stu-id="98d7b-121">Data files will be stored in the default SQL Server data file location while log files will be stored in the default SQL Server log file location.</span></span>
    
4. <span data-ttu-id="98d7b-122">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="98d7b-122">Click **OK**.</span></span>
    
5. <span data-ttu-id="98d7b-123">在“**创建数据库**”页上，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="98d7b-123">On the **Create Database** page, click **Next**.</span></span>
    
6. <span data-ttu-id="98d7b-124">在“**数据库创建已完成**”页上，单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="98d7b-124">On the **Database Creation Complete** page, click **Finish**.</span></span>
    

