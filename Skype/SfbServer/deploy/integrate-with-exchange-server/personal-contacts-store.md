---
title: 配置个人联系人存储客户端计算机上的 Skype 业务服务器
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
description: 摘要： 配置 Exchange Server 2016 或 Exchange Server 2013 和 Skype 由用于业务服务器的个人联系人存储。
ms.openlocfilehash: 311bab825412bae79c240ddb0f923c693b97103e
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "21012898"
---
# <a name="configure-the-personal-contacts-store-on-client-computers-for-skype-for-business-server"></a><span data-ttu-id="517fc-103">配置个人联系人存储客户端计算机上的 Skype 业务服务器</span><span class="sxs-lookup"><span data-stu-id="517fc-103">Configure the personal contacts store on client computers for Skype for Business Server</span></span>
 
<span data-ttu-id="517fc-104">**摘要：** 配置用于业务服务器的 Exchange Server 2016 或 Exchange Server 2013 和 Skype 的个人联系人存储。</span><span class="sxs-lookup"><span data-stu-id="517fc-104">**Summary:** Configure the personal contact store used by Exchange Server 2016 or Exchange Server 2013 and Skype for Business Server.</span></span>
  
<span data-ttu-id="517fc-105">如果您的业务服务器和 Exchange Server 2016 或 Exchange Server 2013 集成 Skype，然后应运行 for Business 的 Skype 任何客户端计算机上配置的个人联系人存储库。</span><span class="sxs-lookup"><span data-stu-id="517fc-105">If you are integrating Skype for Business Server and Exchange Server 2016 or Exchange Server 2013, then you should configure the personal contact store on any client computers running Skype for Business.</span></span> <span data-ttu-id="517fc-106">具体而言，应配置 Skype for Business 的个人联系人存储库，为使用 Exchange，并在同一时间中，确保用户将不能重写该决定。</span><span class="sxs-lookup"><span data-stu-id="517fc-106">In particular, you should configure Skype for Business to use Exchange as the personal contact store, and, at the same time, ensure that users are not able to override that decision.</span></span> <span data-ttu-id="517fc-107">这可以通过在各客户端计算机上创建和配置注册表值来完成。</span><span class="sxs-lookup"><span data-stu-id="517fc-107">This can be done by creating and configuring a Registry value on each client computer.</span></span>
  
<span data-ttu-id="517fc-108">请注意，这不要求运行 for Business 的 Skype 的计算机上。</span><span class="sxs-lookup"><span data-stu-id="517fc-108">Note that this is not required on computers running Skype for Business.</span></span>
  
<span data-ttu-id="517fc-109">要在单个计算机上配置此值，请完成下列过程：</span><span class="sxs-lookup"><span data-stu-id="517fc-109">To configure this value on a single computer, complete the following procedure:</span></span>
  
1. <span data-ttu-id="517fc-110">在客户端计算机上，单击“**开始**”，然后单击“**运行**”。</span><span class="sxs-lookup"><span data-stu-id="517fc-110">On the client computer, click **Start** and then click **Run**.</span></span>
    
2. <span data-ttu-id="517fc-111">在“**运行**”对话框中，键入“regedit”，然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="517fc-111">In the **Run** dialog box, type regedit and then press ENTER.</span></span>
    
3. <span data-ttu-id="517fc-112">在注册表编辑器中，依次展开“**HKEY_LOCAL_MACHINE**”、“**Software**”、“**Policies**”、“**Microsoft**”和“**Communicator**”。</span><span class="sxs-lookup"><span data-stu-id="517fc-112">In Registry Editor, expand **HKEY_LOCAL_MACHINE**, expand **Software**, expand **Policies**, expand **Microsoft**, and then expand **Communicator**.</span></span>
    
4. <span data-ttu-id="517fc-113">右键单击“**Communicator**”，指向“**新建**”，然后单击“**DWORD（32 位）值**”。</span><span class="sxs-lookup"><span data-stu-id="517fc-113">Right-click **Communicator**, point to **New**, and then click **DWORD (32-bit) Value**.</span></span>
    
5. <span data-ttu-id="517fc-114">创建新值后，键入 PersonalContactStoreOverride，然后按 Enter 来重命名该值。</span><span class="sxs-lookup"><span data-stu-id="517fc-114">After the new value is created, type PersonalContactStoreOverride and then press ENTER to rename the value.</span></span>
    
6. <span data-ttu-id="517fc-115">验证将 PersonalContactStoreOverride 的值设置为 0，然后关闭注册表编辑器。</span><span class="sxs-lookup"><span data-stu-id="517fc-115">Verify that the value of PersonalContactStoreOverride is set to 0 and then close Registry Editor.</span></span>
    
<span data-ttu-id="517fc-116">如果您要在多台计算机上执行相同的更改，则可以通过创建自定义组策略对象执行此操作。</span><span class="sxs-lookup"><span data-stu-id="517fc-116">If you need to make this same change on multiple computers you can do so by creating a custom Group Policy object.</span></span> <span data-ttu-id="517fc-117">有关详细信息，请参阅组策略文档[https://go.microsoft.com/fwlink/p/?LinkId=268543](https://go.microsoft.com/fwlink/p/?LinkId=268543)。</span><span class="sxs-lookup"><span data-stu-id="517fc-117">For details, see the Group Policy documentation at [https://go.microsoft.com/fwlink/p/?LinkId=268543](https://go.microsoft.com/fwlink/p/?LinkId=268543).</span></span>
  

