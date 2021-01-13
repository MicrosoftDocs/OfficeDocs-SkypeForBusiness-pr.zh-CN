---
title: SQL 存储设置扩展器
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.SqlStoreSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bd269d52-6f87-4433-b9b0-2b543fea845d
ROBOTS: NOINDEX, NOFOLLOW
description: 若要编辑数据库SQL Server，必须更改SQL Server实例。 无法使用“编辑属性”对话框执行诸如将存档服务器数据库从一台计算机移到另一台计算机等任务。 此外，不能使用"编辑属性"对话框更改承载中央管理存储SQL Server实例。
ms.openlocfilehash: 96eeb4302bd904fe3622e7135d34d374f56766e4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805512"
---
# <a name="sql-store-settings-expander"></a><span data-ttu-id="73c29-105">SQL 存储设置扩展器</span><span class="sxs-lookup"><span data-stu-id="73c29-105">SQL Store Settings Expander</span></span>
 
<span data-ttu-id="73c29-106">若要编辑数据库SQL Server，必须更改SQL Server实例。</span><span class="sxs-lookup"><span data-stu-id="73c29-106">To edit the properties of a SQL Server database, you must change the SQL Server database instance.</span></span> <span data-ttu-id="73c29-107">无法使用“编辑属性”对话框执行诸如将存档服务器数据库从一台计算机移到另一台计算机等任务。</span><span class="sxs-lookup"><span data-stu-id="73c29-107">You cannot use the **Edit Properties** dialog box to perform tasks such as moving your Archiving Server database from one computer to another.</span></span> <span data-ttu-id="73c29-108">此外，不能使用"编辑属性"对话框更改承载中央管理存储SQL Server实例。</span><span class="sxs-lookup"><span data-stu-id="73c29-108">In addition, you cannot use the **Edit Properties** dialog box to change the instance of SQL Server that hosts the Central Management store.</span></span>
  
## <a name="editing-the-properties-of-a-sql-server-database"></a><span data-ttu-id="73c29-109">编辑数据库SQL Server属性</span><span class="sxs-lookup"><span data-stu-id="73c29-109">Editing the Properties of a SQL Server Database</span></span>

<span data-ttu-id="73c29-110">若要更改由中央SQL Server存储外的任何数据库使用的数据库的实例，请完成拓扑生成器中的以下过程：</span><span class="sxs-lookup"><span data-stu-id="73c29-110">To change the instance of SQL Server that is used by any database other than the Central Management store, complete the following procedure in Topology Builder:</span></span>
  
### <a name="to-modify-an-instance-of-sql-server"></a><span data-ttu-id="73c29-111">修改实例SQL Server</span><span class="sxs-lookup"><span data-stu-id="73c29-111">To modify an instance of SQL Server</span></span>

1. <span data-ttu-id="73c29-112">在“SQL 存储”节点下选择相应的数据库，然后单击“编辑属性”。</span><span class="sxs-lookup"><span data-stu-id="73c29-112">Select the appropriate database under the **SQL stores** node, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="73c29-113">在“编辑属性”对话框中，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="73c29-113">In the **Edit Properties** dialog box, do one of the following:</span></span>
    
   - <span data-ttu-id="73c29-114">若要使用默认SQL Server实例，请选择 **"默认实例**"，然后单击"**确定"。**</span><span class="sxs-lookup"><span data-stu-id="73c29-114">To use the default SQL Server instance, select **Default Instance** and then click **OK**.</span></span>
    
   - <span data-ttu-id="73c29-115">要使用命名数据库实例，请选择 **“命名实例”**，在文本框中输入实例名称，然后单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="73c29-115">To use a named database instance, select **Named Instance**, enter the instance name in the text box, and then click **OK**.</span></span> <span data-ttu-id="73c29-116">应仅输入实例名称 (例如 ArchivingInstance) ，而不是整个SQL Server路径。</span><span class="sxs-lookup"><span data-stu-id="73c29-116">You should enter only the instance name (for example, ArchivingInstance), and not the entire SQL Server path.</span></span>
    
<span data-ttu-id="73c29-117">当您在"编辑属性"对话框中操作时，拓扑生成器不会验证您输入的数据库实例是否有效。</span><span class="sxs-lookup"><span data-stu-id="73c29-117">When you are working in the **Edit Properties** dialog box, Topology Builder will not verify that the database instance that you have entered is a valid instance.</span></span> <span data-ttu-id="73c29-118">例如，如果无意中键入ArchivingInstanec 作为实例名称，然后单击"确定"，拓扑生成器将接受该无效实例。</span><span class="sxs-lookup"><span data-stu-id="73c29-118">For example, if you inadvertently typeArchivingInstanec as the instance name and then click **OK**, Topology Builder will accept that invalid instance.</span></span> <span data-ttu-id="73c29-119">在发布此拓扑之前，必须更正此错误：如果找不到SQL Server实例，拓扑生成器将不会创建该实例。</span><span class="sxs-lookup"><span data-stu-id="73c29-119">Before you can publish this topology, you must correct this mistake: if a SQL Server instance cannot be found, Topology Builder will not create that instance for you.</span></span>
  

