---
title: Lync 2010 客户端计算机上配置个人联系人存储
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/29/2019
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
description: 摘要： 配置旧客户端使用的个人联系人存储。
ms.openlocfilehash: b817ae3c7e4e8d54a06d497d91ca83d2b8715e8d
ms.sourcegitcommit: 5cf9b45ad87aebfd46d3f1f757786c01804143ed
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "29635704"
---
# <a name="configure-the-personal-contacts-store-on-lync-2010-client-computers"></a><span data-ttu-id="97bc7-103">Lync 2010 客户端计算机上配置个人联系人存储</span><span class="sxs-lookup"><span data-stu-id="97bc7-103">Configure the personal contacts store on Lync 2010 client computers</span></span>
  
<span data-ttu-id="97bc7-104">如果要集成 Skype 业务服务器 2015年和 Exchange Server 2016 或 Exchange Server 2013，您应配置客户端使用的个人联系人存储。</span><span class="sxs-lookup"><span data-stu-id="97bc7-104">If you are integrating Skype for Business Server 2015 and Exchange Server 2016 or Exchange Server 2013, then you should configure the personal contact store used by the clients.</span></span> <span data-ttu-id="97bc7-105">具体而言，应配置 Skype for Business 的个人联系人存储库，为使用 Exchange，并在同一时间中，确保用户将不能重写该决定。</span><span class="sxs-lookup"><span data-stu-id="97bc7-105">In particular, you should configure Skype for Business to use Exchange as the personal contact store, and, at the same time, ensure that users are not able to override that decision.</span></span> <span data-ttu-id="97bc7-106">这可以通过在各客户端计算机上创建和配置注册表值来完成。</span><span class="sxs-lookup"><span data-stu-id="97bc7-106">This can be done by creating and configuring a Registry value on each client computer.</span></span>
  
> [!NOTE]
> <span data-ttu-id="97bc7-107">下面的过程才需要使用 Lync 2010 客户端的客户端或更早版本。</span><span class="sxs-lookup"><span data-stu-id="97bc7-107">The following procedure is only necessary for clients using the Lync 2010 client or earlier.</span></span> <span data-ttu-id="97bc7-108">Lync 2013 客户端和所有 Skype 业务客户端不会覆盖的联系人存储库设置的选项。</span><span class="sxs-lookup"><span data-stu-id="97bc7-108">The Lync 2013 client and all Skype for Business clients will not have the option of overriding the contact store settings.</span></span>
  
<span data-ttu-id="97bc7-109">要在单个计算机上配置此值，请完成下列过程：</span><span class="sxs-lookup"><span data-stu-id="97bc7-109">To configure this value on a single computer, complete the following procedure:</span></span>
  
1. <span data-ttu-id="97bc7-110">在客户端计算机上，单击“**开始**”，然后单击“**运行**”。</span><span class="sxs-lookup"><span data-stu-id="97bc7-110">On the client computer, click **Start** and then click **Run**.</span></span>
2. <span data-ttu-id="97bc7-111">在“**运行**”对话框中，键入“regedit”，然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="97bc7-111">In the **Run** dialog box, type regedit and then press ENTER.</span></span>
3. <span data-ttu-id="97bc7-112">在注册表编辑器中，依次展开“**HKEY_LOCAL_MACHINE**”、“**Software**”、“**Policies**”、“**Microsoft**”和“**Communicator**”。</span><span class="sxs-lookup"><span data-stu-id="97bc7-112">In Registry Editor, expand **HKEY_LOCAL_MACHINE**, expand **Software**, expand **Policies**, expand **Microsoft**, and then expand **Communicator**.</span></span>
4. <span data-ttu-id="97bc7-113">右键单击“**Communicator**”，指向“**新建**”，然后单击“**DWORD（32 位）值**”。</span><span class="sxs-lookup"><span data-stu-id="97bc7-113">Right-click **Communicator**, point to **New**, and then click **DWORD (32-bit) Value**.</span></span>
5. <span data-ttu-id="97bc7-114">创建新值后，键入 PersonalContactStoreOverride，然后按 Enter 来重命名该值。</span><span class="sxs-lookup"><span data-stu-id="97bc7-114">After the new value is created, type PersonalContactStoreOverride and then press ENTER to rename the value.</span></span>
6. <span data-ttu-id="97bc7-115">验证将 PersonalContactStoreOverride 的值设置为 0，然后关闭注册表编辑器。</span><span class="sxs-lookup"><span data-stu-id="97bc7-115">Verify that the value of PersonalContactStoreOverride is set to 0 and then close Registry Editor.</span></span>

<span data-ttu-id="97bc7-116">如果您要在多台计算机上执行相同的更改，则可以通过创建自定义组策略对象执行此操作。</span><span class="sxs-lookup"><span data-stu-id="97bc7-116">If you need to make this same change on multiple computers you can do so by creating a custom Group Policy object.</span></span> <span data-ttu-id="97bc7-117">有关此操作 Windows 10 中的详细信息，请参阅[创建组策略对象](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)文章。</span><span class="sxs-lookup"><span data-stu-id="97bc7-117">For details on doing this in Windows 10, see the [Create a Group Policy Object](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/create-a-group-policy-object) article.</span></span>
  