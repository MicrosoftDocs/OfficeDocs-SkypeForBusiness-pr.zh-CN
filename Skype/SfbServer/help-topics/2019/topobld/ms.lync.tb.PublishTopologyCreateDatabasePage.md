---
title: 创建数据库
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PublishTopologyCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d391619-1cab-4265-ae8a-2519993705bc
ROBOTS: NOINDEX, NOFOLLOW
description: 拓扑生成器提供了一种在数据库存储中安装SQL Server的方法。 当您使用拓扑生成器安装数据库时，应用程序会从拓扑中读取信息，然后将所需数据库安装在指定的 SQL Server 或 SQL Server 群集上。 这是唯一可以使用拓扑生成器进行的数据库安装类型。 如果需要在特定的计算机上安装特定数据库，或者必须安装并排的数据库，则必须改为使用 Windows PowerShell 命令行接口和 Install-CsDatabase cmdlet。
ms.openlocfilehash: 1092840305d1a455aa094776ae757cf074f7e89a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822282"
---
# <a name="create-database"></a><span data-ttu-id="e0e43-106">创建数据库</span><span class="sxs-lookup"><span data-stu-id="e0e43-106">Create Database</span></span>
 
<span data-ttu-id="e0e43-107">拓扑生成器提供了一种在数据库存储中安装SQL Server的方法。</span><span class="sxs-lookup"><span data-stu-id="e0e43-107">Topology Builder provides a way to install databases on a SQL Server store.</span></span> <span data-ttu-id="e0e43-108">当您使用拓扑生成器安装数据库时，应用程序会从拓扑中读取信息，然后将所需数据库安装在指定的 SQL Server 或 SQL Server 群集上。</span><span class="sxs-lookup"><span data-stu-id="e0e43-108">When you install databases by using Topology Builder, the application reads information from the topology and then installs the required databases on the specified SQL Server computer or SQL Server cluster.</span></span> <span data-ttu-id="e0e43-109">这是唯一可以使用拓扑生成器进行的数据库安装类型。</span><span class="sxs-lookup"><span data-stu-id="e0e43-109">This is the only type of database installation available by using Topology Builder.</span></span> <span data-ttu-id="e0e43-110">如果需要在特定的计算机上安装特定数据库，或者必须安装并排的数据库，则必须改为使用 Windows PowerShell 命令行接口和 [Install-CsDatabase](https://docs.microsoft.com/powershell/module/skype/install-csdatabase?view=skype-ps) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e0e43-110">If you need to install a specific database on a specific computer, or if you must install a collocated database, you must use Windows PowerShell command-line interface and the [Install-CsDatabase](https://docs.microsoft.com/powershell/module/skype/install-csdatabase?view=skype-ps) cmdlet instead.</span></span>
  
### <a name="creating-a-database"></a><span data-ttu-id="e0e43-111">创建数据库</span><span class="sxs-lookup"><span data-stu-id="e0e43-111">Creating a Database</span></span>

1. <span data-ttu-id="e0e43-112">单击 Skype for Business Server 节点，然后单击"**安装数据库"。**</span><span class="sxs-lookup"><span data-stu-id="e0e43-112">Click the Skype for Business Server node and then click **Install Database**.</span></span>
    
2. <span data-ttu-id="e0e43-113">在"安装数据库"对话框中的"创建数据库"页上，选择要创建新数据库的 SQL Server 存储的完全限定域名 (FQDN) 。</span><span class="sxs-lookup"><span data-stu-id="e0e43-113">In the **Install Databases** dialog box, on the **Create Database** page, select the fully qualified domain name (FQDN) of the SQL Server store where the new databases are to be created.</span></span>
    
3. <span data-ttu-id="e0e43-p103">单击“高级”。在“选择数据库文件位置”对话框中，选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="e0e43-p103">Click **Advanced**. In the **Select Database File Location** dialog box, select one of the following options:</span></span>
    
   - <span data-ttu-id="e0e43-p104">**自动确定数据库文件位置**。如果选择此选项，拓扑生成器将使用内置算法选择数据库日志和数据文件的存储位置。</span><span class="sxs-lookup"><span data-stu-id="e0e43-p104">**Automatically determine database file location**. If you select this option, Topology Builder uses a built-in algorithm to choose the storage location for the database logs and data files.</span></span>
    
   - <span data-ttu-id="e0e43-118">**使用 SQL Server 实例默认值**。</span><span class="sxs-lookup"><span data-stu-id="e0e43-118">**Use SQL Server instance defaults**.</span></span> <span data-ttu-id="e0e43-119">如果选择此选项，将不会使用内置算法选择数据库日志和数据文件的存储位置。</span><span class="sxs-lookup"><span data-stu-id="e0e43-119">If you select this option, the built-in algorithm is not used to choose the storage locations for the database logs and data files.</span></span> <span data-ttu-id="e0e43-120">日志和数据文件将存储在由 SQL Server 默认路径（SQL Server 管理员必须提前配置好这些路径）指定的位置。</span><span class="sxs-lookup"><span data-stu-id="e0e43-120">Instead, log and data files are stored in the locations specified by the SQL Server defaults path (these paths must be configured in advanced by a SQL Server administrator).</span></span> <span data-ttu-id="e0e43-121">数据文件将存储在默认 SQL Server 数据文件位置，而日志文件将存储在默认 SQL Server 日志文件位置。</span><span class="sxs-lookup"><span data-stu-id="e0e43-121">Data files will be stored in the default SQL Server data file location while log files will be stored in the default SQL Server log file location.</span></span>
    
4. <span data-ttu-id="e0e43-122">单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="e0e43-122">Click **OK**.</span></span>
    
5. <span data-ttu-id="e0e43-123">在“创建数据库”页上，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="e0e43-123">On the **Create Database** page, click **Next**.</span></span>
    
6. <span data-ttu-id="e0e43-124">在“数据库创建已完成”页上，单击“完成”。</span><span class="sxs-lookup"><span data-stu-id="e0e43-124">On the **Database Creation Complete** page, click **Finish**.</span></span>
    

