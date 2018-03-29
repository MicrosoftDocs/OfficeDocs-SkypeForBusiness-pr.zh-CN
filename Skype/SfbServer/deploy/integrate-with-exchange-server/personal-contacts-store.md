---
title: 在客户端计算机上为 Skype for Business Server 2015 配置个人联系人存储
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
description: 摘要： 配置使用 Exchange Server 2016年或 Exchange Server 2013年和 Skype 业务服务器 2015年个人联系人存储库。
ms.openlocfilehash: 6d6c34a196e418d66708418ff8805caf19d39cfe
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="configure-the-personal-contacts-store-on-client-computers-for-skype-for-business-server-2015"></a><span data-ttu-id="e004c-103">在客户端计算机上为 Skype for Business Server 2015 配置个人联系人存储</span><span class="sxs-lookup"><span data-stu-id="e004c-103">Configure the personal contacts store on client computers for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="e004c-104">**摘要：**配置使用 Exchange Server 2016年或 Exchange Server 2013年和 Skype 业务服务器 2015年个人联系人存储库。</span><span class="sxs-lookup"><span data-stu-id="e004c-104">**Summary:** Configure the personal contact store used by Exchange Server 2016 or Exchange Server 2013 and Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="e004c-105">如果您正在集成 Skype 业务服务器 2015年和 Exchange Server 2016年或 Exchange Server 2013年，应将个人联系人存储库配置运行 Skype 业务的所有客户端计算机上。</span><span class="sxs-lookup"><span data-stu-id="e004c-105">If you are integrating Skype for Business Server 2015 and Exchange Server 2016 or Exchange Server 2013, then you should configure the personal contact store on any client computers running Skype for Business.</span></span> <span data-ttu-id="e004c-106">特别是，您应该配置 Skype 为企业与个人的联系人存储库，使用 Exchange，并在同一时间，确保用户将不能重写该决定。</span><span class="sxs-lookup"><span data-stu-id="e004c-106">In particular, you should configure Skype for Business to use Exchange as the personal contact store, and, at the same time, ensure that users are not able to override that decision.</span></span> <span data-ttu-id="e004c-107">这可以通过在各客户端计算机上创建和配置注册表值来完成。</span><span class="sxs-lookup"><span data-stu-id="e004c-107">This can be done by creating and configuring a Registry value on each client computer.</span></span>
  
<span data-ttu-id="e004c-108">请注意，这不需要运行业务的 Skype 的计算机上。</span><span class="sxs-lookup"><span data-stu-id="e004c-108">Note that this is not required on computers running Skype for Business.</span></span>
  
<span data-ttu-id="e004c-109">要在单个计算机上配置此值，请完成下列过程：</span><span class="sxs-lookup"><span data-stu-id="e004c-109">To configure this value on a single computer, complete the following procedure:</span></span>
  
1. <span data-ttu-id="e004c-110">在客户端计算机上，单击“**开始**”，然后单击“**运行**”。</span><span class="sxs-lookup"><span data-stu-id="e004c-110">On the client computer, click **Start** and then click **Run**.</span></span>
    
2. <span data-ttu-id="e004c-111">在“**运行**”对话框中，键入“regedit”，然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="e004c-111">In the **Run** dialog box, type regedit and then press ENTER.</span></span>
    
3. <span data-ttu-id="e004c-112">在注册表编辑器中，依次展开“**HKEY_LOCAL_MACHINE**”、“**Software**”、“**Policies**”、“**Microsoft**”和“**Communicator**”。</span><span class="sxs-lookup"><span data-stu-id="e004c-112">In Registry Editor, expand **HKEY_LOCAL_MACHINE**, expand **Software**, expand **Policies**, expand **Microsoft**, and then expand **Communicator**.</span></span>
    
4. <span data-ttu-id="e004c-113">右键单击“**Communicator**”，指向“**新建**”，然后单击“**DWORD（32 位）值**”。</span><span class="sxs-lookup"><span data-stu-id="e004c-113">Right-click **Communicator**, point to **New**, and then click **DWORD (32-bit) Value**.</span></span>
    
5. <span data-ttu-id="e004c-114">在创建新值之后，键入 PersonalContactStoreOverride，然后按 enter 键以便重命名值。</span><span class="sxs-lookup"><span data-stu-id="e004c-114">After the new value is created, type PersonalContactStoreOverride and then press ENTER to rename the value.</span></span>
    
6. <span data-ttu-id="e004c-115">验证将 PersonalContactStoreOverride 的值设置为 0，然后关闭注册表编辑器。</span><span class="sxs-lookup"><span data-stu-id="e004c-115">Verify that the value of PersonalContactStoreOverride is set to 0 and then close Registry Editor.</span></span>
    
<span data-ttu-id="e004c-116">如果您要在多台计算机上执行相同的更改，则可以通过创建自定义组策略对象执行此操作。</span><span class="sxs-lookup"><span data-stu-id="e004c-116">If you need to make this same change on multiple computers you can do so by creating a custom Group Policy object.</span></span> <span data-ttu-id="e004c-117">有关详细信息，请参阅组策略文档，网址[https://go.microsoft.com/fwlink/p/?LinkId=268543](https://go.microsoft.com/fwlink/p/?LinkId=268543)。</span><span class="sxs-lookup"><span data-stu-id="e004c-117">For details, see the Group Policy documentation at [https://go.microsoft.com/fwlink/p/?LinkId=268543](https://go.microsoft.com/fwlink/p/?LinkId=268543).</span></span>
  

