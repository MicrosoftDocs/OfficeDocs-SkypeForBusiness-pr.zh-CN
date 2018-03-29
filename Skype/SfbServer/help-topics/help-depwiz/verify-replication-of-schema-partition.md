---
title: 验证架构分区的复制
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainVerifySchemaPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0357f230-6d0c-41f1-942c-e14f76e55d31
description: 要验证的架构扩展已被成功复制 Active Directory 域服务林中，请执行以下操作：
ms.openlocfilehash: a5628e369ffc796affe9984cef8ecb1ba044ec8a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="verify-replication-of-schema-partition"></a><span data-ttu-id="80827-103">验证架构分区的复制</span><span class="sxs-lookup"><span data-stu-id="80827-103">Verify Replication of Schema Partition</span></span>
 
<span data-ttu-id="80827-104">要验证的架构扩展已被成功复制 Active Directory 域服务林中，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="80827-104">To verify that the schema extension have been successfully replicated in your Active Directory Domain Services forest, do the following:</span></span>
  
1. <span data-ttu-id="80827-105">在 Active Directory 域服务林中，其中架构扩展应用作为企业管理员组的成员登录到域控制器 （而不是充当架构主机角色的域控制器）。</span><span class="sxs-lookup"><span data-stu-id="80827-105">Log on to a domain controller (other than the domain controller that holds the schema master role) in your Active Directory Domain Services forest, where the schema extensions were applied as a member of the Enterprise Admins group.</span></span>
    
2. <span data-ttu-id="80827-106">打开 ADSI 编辑： 单击**开始**，单击**管理工具**，然后单击**ADSI 编辑**。</span><span class="sxs-lookup"><span data-stu-id="80827-106">Open ADSI Edit: Click **Start**, click **Administrative Tools**, and then click **ADSI Edit**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="80827-107">或者，单击**开始**，然后单击**运行**类型**adsiedit.msc**启动 ADSI 编辑。</span><span class="sxs-lookup"><span data-stu-id="80827-107">Alternatively, click **Start**, then click **Run**, type **adsiedit.msc** to start ADSI Edit.</span></span>
  
3. <span data-ttu-id="80827-108">在 Microsoft 管理控制台 (MMC) 树中，如果它尚未被选中，则单击 ADSI 编辑。</span><span class="sxs-lookup"><span data-stu-id="80827-108">In the Microsoft Management Console (MMC) tree, if it is not already selected, click ADSI Edit.</span></span>
    
4. <span data-ttu-id="80827-109">在“**操作**”菜单上，单击“**连接到**”。</span><span class="sxs-lookup"><span data-stu-id="80827-109">On the **Action** menu, click **Connect to**.</span></span>
    
5. <span data-ttu-id="80827-110">在“**连接设置**”对话框中的“**选择一个已知命名上下文**”下，选择“**架构**”，然后单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="80827-110">In the **Connection Settings** dialog box under **Select a well known Naming Context**, select **Schema**, and then click **OK**.</span></span>
    
6. <span data-ttu-id="80827-111">在架构容器中下, 搜索 CN = ms RTC SIP SchemaVersion。</span><span class="sxs-lookup"><span data-stu-id="80827-111">Under the schema container, search for CN=ms-RTC-SIP-SchemaVersion.</span></span> <span data-ttu-id="80827-112">如果该对象存在，并**rangeUpper**属性的值是 1150 **rangeLower**属性的值为 3，然后架构已成功更新和复制。</span><span class="sxs-lookup"><span data-stu-id="80827-112">If this object exists, and the value of the **rangeUpper** attribute is 1150 and the value of the **rangeLower** attribute is 3, then the schema was successfully updated and replicated.</span></span> <span data-ttu-id="80827-113">如果不存在此对象，或**rangeUpper**和**rangeLower**属性的值不是作为指定，然后架构未被修改或尚未复制。</span><span class="sxs-lookup"><span data-stu-id="80827-113">If this object does not exist or if the values of the **rangeUpper** and **rangeLower** attributes are not as specified, then the schema was not modified or has not replicated.</span></span>
    
> [!NOTE]
> <span data-ttu-id="80827-114">如果复制架构的签还不会显示成功复制，等待约 15 分钟，然后再次进行检查。</span><span class="sxs-lookup"><span data-stu-id="80827-114">If your check of the replication of the schema does not yet show a successful replication, wait approximately 15 minutes and then check again.</span></span> <span data-ttu-id="80827-115">活动目录复制是基于松散一致性模型，可能会出现一些复制滞后时间，基于许多因素中的服务器和基础结构。</span><span class="sxs-lookup"><span data-stu-id="80827-115">Active Directory replication is based on a loose consistency model and some replication latency can occur, based on a number of factors in the server and infrastructure.</span></span> 
  

