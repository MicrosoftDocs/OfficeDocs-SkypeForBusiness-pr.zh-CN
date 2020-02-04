---
title: 验证架构分区的复制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployMainVerifySchemaPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0357f230-6d0c-41f1-942c-e14f76e55d31
ROBOTS: NOINDEX, NOFOLLOW
description: 若要验证架构扩展是否已成功复制到你的 Active Directory 域服务林中，请执行下列操作：
ms.openlocfilehash: 2d739bece89d43d5d3be289be55c90c2a63b49fe
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41705337"
---
# <a name="verify-replication-of-schema-partition"></a><span data-ttu-id="50bd9-103">验证架构分区的复制</span><span class="sxs-lookup"><span data-stu-id="50bd9-103">Verify Replication of Schema Partition</span></span>
 
<span data-ttu-id="50bd9-104">若要验证架构扩展是否已成功复制到你的 Active Directory 域服务林中，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="50bd9-104">To verify that the schema extension have been successfully replicated in your Active Directory Domain Services forest, do the following:</span></span>
  
1. <span data-ttu-id="50bd9-105">在 Active Directory 域服务林中登录到作为企业管理员组成员应用的架构扩展的域控制器（不包含架构主机角色的域控制器除外）。</span><span class="sxs-lookup"><span data-stu-id="50bd9-105">Log on to a domain controller (other than the domain controller that holds the schema master role) in your Active Directory Domain Services forest, where the schema extensions were applied as a member of the Enterprise Admins group.</span></span>
    
2. <span data-ttu-id="50bd9-106">打开 "ADSI 编辑"：单击 "**开始**"，单击 "**管理工具**"，然后单击 " **ADSI 编辑**"。</span><span class="sxs-lookup"><span data-stu-id="50bd9-106">Open ADSI Edit: Click **Start**, click **Administrative Tools**, and then click **ADSI Edit**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="50bd9-107">或者，单击 "**开始**"，然后单击 "**运行**"，键入 " **ADSIEDIT** " 以启动 "ADSI 编辑"。</span><span class="sxs-lookup"><span data-stu-id="50bd9-107">Alternatively, click **Start**, then click **Run**, type **adsiedit.msc** to start ADSI Edit.</span></span>
  
3. <span data-ttu-id="50bd9-108">在 Microsoft 管理控制台（MMC）树中，如果尚未选中它，请单击 "ADSI 编辑"。</span><span class="sxs-lookup"><span data-stu-id="50bd9-108">In the Microsoft Management Console (MMC) tree, if it is not already selected, click ADSI Edit.</span></span>
    
4. <span data-ttu-id="50bd9-109">在“**操作**”菜单上，单击“**连接到**”。</span><span class="sxs-lookup"><span data-stu-id="50bd9-109">On the **Action** menu, click **Connect to**.</span></span>
    
5. <span data-ttu-id="50bd9-110">在“**连接设置**”对话框中的“**选择一个已知命名上下文**”下，选择“**架构**”，然后单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="50bd9-110">In the **Connection Settings** dialog box under **Select a well known Naming Context**, select **Schema**, and then click **OK**.</span></span>
    
6. <span data-ttu-id="50bd9-111">在架构容器下，搜索“CN=ms-RTC-SIP-SchemaVersion”。</span><span class="sxs-lookup"><span data-stu-id="50bd9-111">Under the schema container, search for CN=ms-RTC-SIP-SchemaVersion.</span></span> <span data-ttu-id="50bd9-112">如果此对象存在，并且**rangeUpper**属性的值为1150，并且**rangeLower**属性的值为3，则架构已成功更新和复制。</span><span class="sxs-lookup"><span data-stu-id="50bd9-112">If this object exists, and the value of the **rangeUpper** attribute is 1150 and the value of the **rangeLower** attribute is 3, then the schema was successfully updated and replicated.</span></span> <span data-ttu-id="50bd9-113">如果此对象不存在，或者**rangeUpper**和**rangeLower**属性的值不是指定的，则架构未被修改或未复制。</span><span class="sxs-lookup"><span data-stu-id="50bd9-113">If this object does not exist or if the values of the **rangeUpper** and **rangeLower** attributes are not as specified, then the schema was not modified or has not replicated.</span></span>
    
> [!NOTE]
> <span data-ttu-id="50bd9-114">如果检查架构的复制尚未显示成功复制，请等待大约15分钟，然后再次检查。</span><span class="sxs-lookup"><span data-stu-id="50bd9-114">If your check of the replication of the schema does not yet show a successful replication, wait approximately 15 minutes and then check again.</span></span> <span data-ttu-id="50bd9-115">Active Directory 复制基于松散一致性模型，并且可能会发生某些复制延迟，具体取决于服务器和基础结构中的多种因素。</span><span class="sxs-lookup"><span data-stu-id="50bd9-115">Active Directory replication is based on a loose consistency model and some replication latency can occur, based on a number of factors in the server and infrastructure.</span></span> 
  

