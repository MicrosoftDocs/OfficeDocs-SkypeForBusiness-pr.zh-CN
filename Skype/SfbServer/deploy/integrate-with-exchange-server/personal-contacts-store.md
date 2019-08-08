---
title: 在 Lync 2010 客户端计算机上配置个人联系人存储
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/29/2019
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
description: '摘要: 配置旧版客户端使用的个人联系人存储。'
ms.openlocfilehash: 26352517ea31b5556784f6f1ea8d1ce661cfe184
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244189"
---
# <a name="configure-the-personal-contacts-store-on-lync-2010-client-computers"></a><span data-ttu-id="79185-103">在 Lync 2010 客户端计算机上配置个人联系人存储</span><span class="sxs-lookup"><span data-stu-id="79185-103">Configure the personal contacts store on Lync 2010 client computers</span></span>
  
<span data-ttu-id="79185-104">如果你要集成 Skype for Business Server 2015 和 Exchange Server 2016 或 Exchange Server 2013, 则应配置客户端使用的个人联系人存储。</span><span class="sxs-lookup"><span data-stu-id="79185-104">If you are integrating Skype for Business Server 2015 and Exchange Server 2016 or Exchange Server 2013, then you should configure the personal contact store used by the clients.</span></span> <span data-ttu-id="79185-105">尤其是, 你应该配置 Skype for Business 以将 Exchange 用作个人联系人存储, 同时确保用户无法覆盖该决策。</span><span class="sxs-lookup"><span data-stu-id="79185-105">In particular, you should configure Skype for Business to use Exchange as the personal contact store, and, at the same time, ensure that users are not able to override that decision.</span></span> <span data-ttu-id="79185-106">这可以通过在各客户端计算机上创建和配置注册表值来完成。</span><span class="sxs-lookup"><span data-stu-id="79185-106">This can be done by creating and configuring a Registry value on each client computer.</span></span>
  
> [!NOTE]
> <span data-ttu-id="79185-107">仅对于使用 Lync 2010 客户端或更早版本的客户端, 以下过程才是必需的。</span><span class="sxs-lookup"><span data-stu-id="79185-107">The following procedure is only necessary for clients using the Lync 2010 client or earlier.</span></span> <span data-ttu-id="79185-108">Lync 2013 客户端和所有 Skype for business 客户端将无法选择替代联系人存储设置。</span><span class="sxs-lookup"><span data-stu-id="79185-108">The Lync 2013 client and all Skype for Business clients will not have the option of overriding the contact store settings.</span></span>
  
<span data-ttu-id="79185-109">要在单个计算机上配置此值，请完成下列过程：</span><span class="sxs-lookup"><span data-stu-id="79185-109">To configure this value on a single computer, complete the following procedure:</span></span>
  
1. <span data-ttu-id="79185-110">在客户端计算机上，单击“**开始**”，然后单击“**运行**”。</span><span class="sxs-lookup"><span data-stu-id="79185-110">On the client computer, click **Start** and then click **Run**.</span></span>
2. <span data-ttu-id="79185-111">在“**运行**”对话框中，键入“regedit”，然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="79185-111">In the **Run** dialog box, type regedit and then press ENTER.</span></span>
3. <span data-ttu-id="79185-112">在注册表编辑器中，依次展开“**HKEY_LOCAL_MACHINE**”、“**Software**”、“**Policies**”、“**Microsoft**”和“**Communicator**”。</span><span class="sxs-lookup"><span data-stu-id="79185-112">In Registry Editor, expand **HKEY_LOCAL_MACHINE**, expand **Software**, expand **Policies**, expand **Microsoft**, and then expand **Communicator**.</span></span>
4. <span data-ttu-id="79185-113">右键单击“**Communicator**”，指向“**新建**”，然后单击“**DWORD（32 位）值**”。</span><span class="sxs-lookup"><span data-stu-id="79185-113">Right-click **Communicator**, point to **New**, and then click **DWORD (32-bit) Value**.</span></span>
5. <span data-ttu-id="79185-114">创建新值后，键入 PersonalContactStoreOverride，然后按 Enter 来重命名该值。</span><span class="sxs-lookup"><span data-stu-id="79185-114">After the new value is created, type PersonalContactStoreOverride and then press ENTER to rename the value.</span></span>
6. <span data-ttu-id="79185-115">验证将 PersonalContactStoreOverride 的值设置为 0，然后关闭注册表编辑器。</span><span class="sxs-lookup"><span data-stu-id="79185-115">Verify that the value of PersonalContactStoreOverride is set to 0 and then close Registry Editor.</span></span>

<span data-ttu-id="79185-116">如果您要在多台计算机上执行相同的更改，则可以通过创建自定义组策略对象执行此操作。</span><span class="sxs-lookup"><span data-stu-id="79185-116">If you need to make this same change on multiple computers you can do so by creating a custom Group Policy object.</span></span> <span data-ttu-id="79185-117">有关在 Windows 10 中执行此操作的详细信息, 请参阅[创建组策略对象一](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)文。</span><span class="sxs-lookup"><span data-stu-id="79185-117">For details on doing this in Windows 10, see the [Create a Group Policy Object](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/create-a-group-policy-object) article.</span></span>
  
