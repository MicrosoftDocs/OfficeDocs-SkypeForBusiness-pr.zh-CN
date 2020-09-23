---
title: SQL 存储设置扩展器
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
- ms.lync.tb.SqlStoreSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bd269d52-6f87-4433-b9b0-2b543fea845d
description: 若要编辑 SQL Server 数据库的属性，您必须更改 SQL Server 数据库实例。 无法使用“编辑属性”对话框执行诸如将存档服务器数据库从一台计算机移到另一台计算机等任务。 此外，不能使用 "编辑属性" 对话框更改承载中央管理存储的 SQL Server 实例。
ms.openlocfilehash: e3b16d8c6eab4f4918ef39b3c4f1ab4d0c6fc057
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2020
ms.locfileid: "48219607"
---
# <a name="sql-store-settings-expander"></a><span data-ttu-id="72c07-105">SQL 存储设置扩展器</span><span class="sxs-lookup"><span data-stu-id="72c07-105">SQL Store Settings Expander</span></span>
 
<span data-ttu-id="72c07-106">若要编辑 SQL Server 数据库的属性，您必须更改 SQL Server 数据库实例。</span><span class="sxs-lookup"><span data-stu-id="72c07-106">To edit the properties of a SQL Server database, you must change the SQL Server database instance.</span></span> <span data-ttu-id="72c07-107">无法使用“编辑属性”\*\*\*\* 对话框执行诸如将存档服务器数据库从一台计算机移到另一台计算机等任务。</span><span class="sxs-lookup"><span data-stu-id="72c07-107">You cannot use the **Edit Properties** dialog box to perform tasks such as moving your Archiving Server database from one computer to another.</span></span> <span data-ttu-id="72c07-108">此外，不能使用 " **编辑属性** " 对话框更改承载中央管理存储的 SQL Server 实例。</span><span class="sxs-lookup"><span data-stu-id="72c07-108">In addition, you cannot use the **Edit Properties** dialog box to change the instance of SQL Server that hosts the Central Management store.</span></span>
  
## <a name="editing-the-properties-of-a-sql-server-database"></a><span data-ttu-id="72c07-109">编辑 SQL Server 数据库的属性</span><span class="sxs-lookup"><span data-stu-id="72c07-109">Editing the Properties of a SQL Server Database</span></span>

<span data-ttu-id="72c07-110">若要更改除中央管理存储之外的任何数据库所使用的 SQL Server 实例，请在拓扑生成器中完成以下过程：</span><span class="sxs-lookup"><span data-stu-id="72c07-110">To change the instance of SQL Server that is used by any database other than the Central Management store, complete the following procedure in Topology Builder:</span></span>
  
### <a name="to-modify-an-instance-of-sql-server"></a><span data-ttu-id="72c07-111">修改 SQL Server 实例</span><span class="sxs-lookup"><span data-stu-id="72c07-111">To modify an instance of SQL Server</span></span>

1. <span data-ttu-id="72c07-112">在“SQL 存储”\*\*\*\* 节点下选择相应的数据库，然后单击“编辑属性”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="72c07-112">Select the appropriate database under the **SQL stores** node, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="72c07-113">在“编辑属性”\*\*\*\* 对话框中，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="72c07-113">In the **Edit Properties** dialog box, do one of the following:</span></span>
    
   - <span data-ttu-id="72c07-114">若要使用默认的 SQL Server 实例，请选择 " **默认实例** "，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="72c07-114">To use the default SQL Server instance, select **Default Instance** and then click **OK**.</span></span>
    
   - <span data-ttu-id="72c07-115">要使用命名数据库实例，请选择 **“命名实例”**，在文本框中输入实例名称，然后单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="72c07-115">To use a named database instance, select **Named Instance**, enter the instance name in the text box, and then click **OK**.</span></span> <span data-ttu-id="72c07-116">应仅输入实例名称 (例如，ArchivingInstance) ，而不是整个 SQL Server 路径。</span><span class="sxs-lookup"><span data-stu-id="72c07-116">You should enter only the instance name (for example, ArchivingInstance), and not the entire SQL Server path.</span></span>
    
<span data-ttu-id="72c07-117">当您在 " **编辑属性** " 对话框中工作时，拓扑生成器将不会验证您输入的数据库实例是否为有效的实例。</span><span class="sxs-lookup"><span data-stu-id="72c07-117">When you are working in the **Edit Properties** dialog box, Topology Builder will not verify that the database instance that you have entered is a valid instance.</span></span> <span data-ttu-id="72c07-118">例如，如果您无意中 typeArchivingInstanec 作为实例名称，然后单击 **"确定"**，拓扑生成器将接受无效的实例。</span><span class="sxs-lookup"><span data-stu-id="72c07-118">For example, if you inadvertently typeArchivingInstanec as the instance name and then click **OK**, Topology Builder will accept that invalid instance.</span></span> <span data-ttu-id="72c07-119">必须更正此错误，然后才能发布此拓扑：如果找不到 SQL Server 实例，拓扑生成器将不会为您创建该实例。</span><span class="sxs-lookup"><span data-stu-id="72c07-119">Before you can publish this topology, you must correct this mistake: if a SQL Server instance cannot be found, Topology Builder will not create that instance for you.</span></span>
  

