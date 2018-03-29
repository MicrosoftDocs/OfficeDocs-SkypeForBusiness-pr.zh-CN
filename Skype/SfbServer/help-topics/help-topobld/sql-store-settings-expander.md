---
title: SQL 存储设置扩展器
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.SqlStoreSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bd269d52-6f87-4433-b9b0-2b543fea845d
description: 若要编辑属性的 SQL Server 数据库，则必须更改 SQL Server 数据库实例。 不能使用编辑属性对话框中执行任务的存档服务器数据库从一台计算机移动到另一个。 此外，不能用于编辑属性对话框中更改的 SQL Server 实例承载中央管理存储。
ms.openlocfilehash: 2a1fc051e3dc848272a7cad539eaa749ff95d9b9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="sql-store-settings-expander"></a><span data-ttu-id="64007-105">SQL 存储设置扩展器</span><span class="sxs-lookup"><span data-stu-id="64007-105">SQL Store Settings Expander</span></span>
 
<span data-ttu-id="64007-106">若要编辑属性的 SQL Server 数据库，则必须更改 SQL Server 数据库实例。</span><span class="sxs-lookup"><span data-stu-id="64007-106">To edit the properties of a SQL Server database, you must change the SQL Server database instance.</span></span> <span data-ttu-id="64007-107">不能使用**编辑属性**对话框中执行任务的存档服务器数据库从一台计算机移动到另一个。</span><span class="sxs-lookup"><span data-stu-id="64007-107">You cannot use the **Edit Properties** dialog box to perform tasks such as moving your Archiving Server database from one computer to another.</span></span> <span data-ttu-id="64007-108">此外，不能用于**编辑属性**对话框中更改的 SQL Server 实例承载中央管理存储。</span><span class="sxs-lookup"><span data-stu-id="64007-108">In addition, you cannot use the **Edit Properties** dialog box to change the instance of SQL Server that hosts the Central Management store.</span></span>
  
## <a name="editing-the-properties-of-a-sql-server-database"></a><span data-ttu-id="64007-109">编辑 SQL Server 数据库的属性</span><span class="sxs-lookup"><span data-stu-id="64007-109">Editing the Properties of a SQL Server Database</span></span>

<span data-ttu-id="64007-110">若要更改由中央管理存储任何数据库的 SQL Server 的实例，完成拓扑生成器中的以下步骤：</span><span class="sxs-lookup"><span data-stu-id="64007-110">To change the instance of SQL Server that is used by any database other than the Central Management store, complete the following procedure in Topology Builder:</span></span>
  
### <a name="to-modify-an-instance-of-sql-server"></a><span data-ttu-id="64007-111">若要修改的 SQL Server 实例</span><span class="sxs-lookup"><span data-stu-id="64007-111">To modify an instance of SQL Server</span></span>

1. <span data-ttu-id="64007-112">选择在**SQL 存储**节点下，相应的数据库，然后单击**编辑属性**。</span><span class="sxs-lookup"><span data-stu-id="64007-112">Select the appropriate database under the **SQL stores** node, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="64007-113">在**编辑属性**对话框中，执行以下任一操作：</span><span class="sxs-lookup"><span data-stu-id="64007-113">In the **Edit Properties** dialog box, do one of the following:</span></span>
    
  - <span data-ttu-id="64007-114">若要使用默认的 SQL Server 实例，选择**默认实例**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="64007-114">To use the default SQL Server instance, select **Default Instance** and then click **OK**.</span></span>
    
  - <span data-ttu-id="64007-115">若要使用已命名的数据库实例，选择**命名实例**、 在文本框中，输入实例名称，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="64007-115">To use a named database instance, select **Named Instance**, enter the instance name in the text box, and then click **OK**.</span></span> <span data-ttu-id="64007-116">应输入只有实例名称 (例如，ArchivingInstance)，并不是整个 SQL Server 路径。</span><span class="sxs-lookup"><span data-stu-id="64007-116">You should enter only the instance name (for example, ArchivingInstance), and not the entire SQL Server path.</span></span>
    
<span data-ttu-id="64007-117">当您在使用**编辑属性**对话框中时，拓扑生成器不会验证您输入的数据库实例是有效的实例。</span><span class="sxs-lookup"><span data-stu-id="64007-117">When you are working in the **Edit Properties** dialog box, Topology Builder will not verify that the database instance that you have entered is a valid instance.</span></span> <span data-ttu-id="64007-118">例如，如果您无意中的 typeArchivingInstanec 作为实例名称，然后单击**确定**，拓扑生成器将接受该无效的实例。</span><span class="sxs-lookup"><span data-stu-id="64007-118">For example, if you inadvertently typeArchivingInstanec as the instance name and then click **OK**, Topology Builder will accept that invalid instance.</span></span> <span data-ttu-id="64007-119">发布此拓扑之前，您必须更正此错误： 如果找不到一个 SQL Server 实例，拓扑生成器不会为您创建该实例。</span><span class="sxs-lookup"><span data-stu-id="64007-119">Before you can publish this topology, you must correct this mistake: if a SQL Server instance cannot be found, Topology Builder will not create that instance for you.</span></span>
  

