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
description: 若要验证架构扩展已在 Active Directory 域服务林中成功复制，请执行以下操作：
ms.openlocfilehash: a5628e369ffc796affe9984cef8ecb1ba044ec8a
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2018
---
# <a name="verify-replication-of-schema-partition"></a><span data-ttu-id="ea29a-103">验证架构分区的复制</span><span class="sxs-lookup"><span data-stu-id="ea29a-103">Verify Replication of Schema Partition</span></span>
 
<span data-ttu-id="ea29a-104">若要验证架构扩展已在 Active Directory 域服务林中成功复制，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ea29a-104">To verify that the schema extension have been successfully replicated in your Active Directory Domain Services forest, do the following:</span></span>
  
1. <span data-ttu-id="ea29a-105">在您的 Active Directory 域服务林，其中的架构扩展已应用的 Enterprise Admins 组成员身份登录到域控制器 （而非保留架构主机角色的域控制器）。</span><span class="sxs-lookup"><span data-stu-id="ea29a-105">Log on to a domain controller (other than the domain controller that holds the schema master role) in your Active Directory Domain Services forest, where the schema extensions were applied as a member of the Enterprise Admins group.</span></span>
    
2. <span data-ttu-id="ea29a-106">打开 ADSI Edit： 单击**开始**，单击**管理工具**，然后单击**ADSI 编辑**。</span><span class="sxs-lookup"><span data-stu-id="ea29a-106">Open ADSI Edit: Click **Start**, click **Administrative Tools**, and then click **ADSI Edit**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="ea29a-107">或者，单击**开始**，然后单击**运行**键入**adsiedit.msc**来启动 ADSI Edit。</span><span class="sxs-lookup"><span data-stu-id="ea29a-107">Alternatively, click **Start**, then click **Run**, type **adsiedit.msc** to start ADSI Edit.</span></span>
  
3. <span data-ttu-id="ea29a-108">在 Microsoft 管理控制台 (MMC) 树中，如果尚未选择它，则单击 ADSI 编辑。</span><span class="sxs-lookup"><span data-stu-id="ea29a-108">In the Microsoft Management Console (MMC) tree, if it is not already selected, click ADSI Edit.</span></span>
    
4. <span data-ttu-id="ea29a-109">在“**操作**”菜单上，单击“**连接到**”。</span><span class="sxs-lookup"><span data-stu-id="ea29a-109">On the **Action** menu, click **Connect to**.</span></span>
    
5. <span data-ttu-id="ea29a-110">在“**连接设置**”对话框中的“**选择一个已知命名上下文**”下，选择“**架构**”，然后单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="ea29a-110">In the **Connection Settings** dialog box under **Select a well known Naming Context**, select **Schema**, and then click **OK**.</span></span>
    
6. <span data-ttu-id="ea29a-111">在架构容器中下, 搜索 CN = ms RTC SIP SchemaVersion。</span><span class="sxs-lookup"><span data-stu-id="ea29a-111">Under the schema container, search for CN=ms-RTC-SIP-SchemaVersion.</span></span> <span data-ttu-id="ea29a-112">如果此对象存在，并且**rangeUpper**属性的值为 1150年， **rangeLower**属性的值为 3，然后架构已成功更新和复制。</span><span class="sxs-lookup"><span data-stu-id="ea29a-112">If this object exists, and the value of the **rangeUpper** attribute is 1150 and the value of the **rangeLower** attribute is 3, then the schema was successfully updated and replicated.</span></span> <span data-ttu-id="ea29a-113">如果此对象不存在，或**rangeUpper**和**rangeLower**属性的值不为指定，然后架构未经过修改或尚未复制。</span><span class="sxs-lookup"><span data-stu-id="ea29a-113">If this object does not exist or if the values of the **rangeUpper** and **rangeLower** attributes are not as specified, then the schema was not modified or has not replicated.</span></span>
    
> [!NOTE]
> <span data-ttu-id="ea29a-114">如果架构的复制您复选尚未不显示成功复制，等待约为 15 分钟，然后再次检查。</span><span class="sxs-lookup"><span data-stu-id="ea29a-114">If your check of the replication of the schema does not yet show a successful replication, wait approximately 15 minutes and then check again.</span></span> <span data-ttu-id="ea29a-115">Active Directory 复制是基于松散一致性模型和一些复制延迟可能发生，根据多种因素的服务器和基础结构中。</span><span class="sxs-lookup"><span data-stu-id="ea29a-115">Active Directory replication is based on a loose consistency model and some replication latency can occur, based on a number of factors in the server and infrastructure.</span></span> 
  

