---
title: 验证架构分区的复制
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainVerifySchemaPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 0357f230-6d0c-41f1-942c-e14f76e55d31
ROBOTS: NOINDEX, NOFOLLOW
description: 若要验证已在 Active Directory 域服务林中成功复制架构扩展，请执行下列操作：
ms.openlocfilehash: 4e4bfdf4fb50366f831f029d8f331551ba906969
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801562"
---
# <a name="verify-replication-of-schema-partition"></a><span data-ttu-id="c1f2c-103">验证架构分区的复制</span><span class="sxs-lookup"><span data-stu-id="c1f2c-103">Verify Replication of Schema Partition</span></span>
 
<span data-ttu-id="c1f2c-104">若要验证已在 Active Directory 域服务林中成功复制架构扩展，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="c1f2c-104">To verify that the schema extension have been successfully replicated in your Active Directory Domain Services forest, do the following:</span></span>
  
1. <span data-ttu-id="c1f2c-105">登录到域控制器 (在 Active Directory 域服务林中保留架构主机角色) 的域控制器，其中架构扩展已作为 Enterprise Admins 组的成员应用。</span><span class="sxs-lookup"><span data-stu-id="c1f2c-105">Log on to a domain controller (other than the domain controller that holds the schema master role) in your Active Directory Domain Services forest, where the schema extensions were applied as a member of the Enterprise Admins group.</span></span>
    
2. <span data-ttu-id="c1f2c-106">打开 ADSI Edit：依次单击“开始”、“管理工具”和“ADSI Edit”。</span><span class="sxs-lookup"><span data-stu-id="c1f2c-106">Open ADSI Edit: Click **Start**, click **Administrative Tools**, and then click **ADSI Edit**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="c1f2c-107">或者，通过单击“开始”，再单击“运行”，然后键入 **adsiedit.msc** 来启动 ADSI Edit。</span><span class="sxs-lookup"><span data-stu-id="c1f2c-107">Alternatively, click **Start**, then click **Run**, type **adsiedit.msc** to start ADSI Edit.</span></span>
  
3. <span data-ttu-id="c1f2c-108">在 Microsoft 管理控制台 (MMC) 树中，单击“ADSI Edit”（如果尚未选中）。</span><span class="sxs-lookup"><span data-stu-id="c1f2c-108">In the Microsoft Management Console (MMC) tree, if it is not already selected, click ADSI Edit.</span></span>
    
4. <span data-ttu-id="c1f2c-109">在 **“操作”** 菜单上，单击 **“连接到”**。</span><span class="sxs-lookup"><span data-stu-id="c1f2c-109">On the **Action** menu, click **Connect to**.</span></span>
    
5. <span data-ttu-id="c1f2c-110">在“连接设置”对话框中的“选择一个已知命名上下文”下，选择“架构”，然后单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="c1f2c-110">In the **Connection Settings** dialog box under **Select a well known Naming Context**, select **Schema**, and then click **OK**.</span></span>
    
6. <span data-ttu-id="c1f2c-p101">在架构容器下，搜索“CN=ms-RTC-SIP-SchemaVersion”。如果此对象存在，并且 **rangeUpper** 属性的值为 1150，**rangeLower** 属性的值为 3，则说明架构更新和复制成功。如果此对象不存在，或 **rangeUpper** 和 **rangeLower** 属性的值不是指定的值，则说明架构未经过修改或尚未复制。</span><span class="sxs-lookup"><span data-stu-id="c1f2c-p101">Under the schema container, search for CN=ms-RTC-SIP-SchemaVersion. If this object exists, and the value of the **rangeUpper** attribute is 1150 and the value of the **rangeLower** attribute is 3, then the schema was successfully updated and replicated. If this object does not exist or if the values of the **rangeUpper** and **rangeLower** attributes are not as specified, then the schema was not modified or has not replicated.</span></span>
    
> [!NOTE]
> <span data-ttu-id="c1f2c-114">如果检查架构复制时未显示复制成功，请等待大约 15 分钟，然后重新检查。</span><span class="sxs-lookup"><span data-stu-id="c1f2c-114">If your check of the replication of the schema does not yet show a successful replication, wait approximately 15 minutes and then check again.</span></span> <span data-ttu-id="c1f2c-115">Active Directory 复制基于松散的一致性模型，并且可能会发生一些复制延迟，这基于服务器和基础结构中的许多因素。</span><span class="sxs-lookup"><span data-stu-id="c1f2c-115">Active Directory replication is based on a loose consistency model and some replication latency can occur, based on a number of factors in the server and infrastructure.</span></span> 
  

