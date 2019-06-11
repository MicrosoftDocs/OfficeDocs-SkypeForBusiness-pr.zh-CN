---
title: 'Lync Server 2013: 配置增强的状态隐私模式'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring enhanced presence privacy mode
ms:assetid: e7a6b873-486d-4dfb-a967-c48f61f237f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399028(v=OCS.15)
ms:contentKeyID: 48185664
ms.date: 12/09/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 878691cd7b39d893b416a128f937d2aad1e561b1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837263"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-enhanced-presence-privacy-mode-in-lync-server-2013"></a><span data-ttu-id="cc65a-102">在 Lync Server 2013 中配置增强的联机状态隐私模式</span><span class="sxs-lookup"><span data-stu-id="cc65a-102">Configuring enhanced presence privacy mode in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cc65a-103">_**主题上次修改时间:** 2014-12-08_</span><span class="sxs-lookup"><span data-stu-id="cc65a-103">_**Topic Last Modified:** 2014-12-08_</span></span>

<span data-ttu-id="cc65a-104">通过 "增强状态隐私" 模式, 用户可以限制其状态信息, 使其仅对 Lync 2013 联系人列表中列出的联系人可见。</span><span class="sxs-lookup"><span data-stu-id="cc65a-104">With enhanced presence privacy mode, users can restrict their presence information so that it is visible only to the contacts listed in their Lync 2013 Contacts list.</span></span> <span data-ttu-id="cc65a-105">**CsPrivacyConfiguration** 和**CsPrivacyConfiguration** cmdlet 具有 EnablePrivacyMode 参数, 该参数控制此选项。</span><span class="sxs-lookup"><span data-stu-id="cc65a-105">The **New-CsPrivacyConfiguration** and **Set-CsPrivacyConfiguration** cmdlets have an EnablePrivacyMode parameter controls this option.</span></span> <span data-ttu-id="cc65a-106">当 EnablePrivacyMode 设置为 True 时, 将 "Lync 2013 状态" 选项中的 "限制联系人的状态信息" 选项变为可用。</span><span class="sxs-lookup"><span data-stu-id="cc65a-106">When EnablePrivacyMode is set to True, the option to restrict presence information to contacts becomes available in the Lync 2013 Status options.</span></span> <span data-ttu-id="cc65a-107">当 EnablePrivacyMode 设置为 False 时, 用户可以选择始终允许所有人查看其状态信息, 或遵循管理员对隐私模式所做的任何未来更改。</span><span class="sxs-lookup"><span data-stu-id="cc65a-107">When EnablePrivacyMode is set to False, users can choose either to always allow everyone to see their presence information or to adhere to any future changes the administrator makes to the privacy mode.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="cc65a-108">Lync 2013 和 Lync 2010 隐私设置不会被以前的版本 (Microsoft Office Communicator 2007 R2 或 Microsoft Office Communicator 2007) 所认可。</span><span class="sxs-lookup"><span data-stu-id="cc65a-108">Lync 2013 and Lync 2010 privacy settings are not honored by previous versions (Microsoft Office Communicator 2007 R2 or Microsoft Office Communicator 2007).</span></span> <span data-ttu-id="cc65a-109">如果允许以前版本的 Office Communicator 登录, 则 Lync 2013 用户的状态、联系人信息或图片可由未经授权查看的人员查看。</span><span class="sxs-lookup"><span data-stu-id="cc65a-109">If previous versions of Office Communicator are allowed to sign in, a Lync 2013 user’s status, contact information, or picture could be viewed by someone who has not been authorized to view it.</span></span> <span data-ttu-id="cc65a-110">此外, 如果用户稍后使用 Communicator 的早期版本登录, 则将重置 Lync 2013 用户的隐私设置。</span><span class="sxs-lookup"><span data-stu-id="cc65a-110">Additionally, a Lync 2013 user’s privacy settings are reset if he or she later signs in with previous version of Communicator.</span></span><BR><span data-ttu-id="cc65a-111">因此, 在迁移方案中, 在启用 "增强状态隐私模式" 之前, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="cc65a-111">For these reasons, in a migration scenario, before you enable enhanced presence privacy mode:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="cc65a-112">确保每位用户安装了 Lync 2013。</span><span class="sxs-lookup"><span data-stu-id="cc65a-112">Ensure that every user has Lync 2013 installed.</span></span></P>
> <LI>
> <P><span data-ttu-id="cc65a-113">定义客户端版本策略规则以阻止以前版本的 Communicator 登录。</span><span class="sxs-lookup"><span data-stu-id="cc65a-113">Define a client version policy rule to prevent previous versions of Communicator from signing in.</span></span></P></LI></UL>



</div>

<div>

## <a name="to-enable-enhanced-presence-privacy-mode"></a><span data-ttu-id="cc65a-114">启用 "增强状态隐私模式"</span><span class="sxs-lookup"><span data-stu-id="cc65a-114">To enable enhanced presence privacy mode</span></span>

1.  <span data-ttu-id="cc65a-115">启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="cc65a-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="cc65a-116">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="cc65a-116">Run the following command:</span></span>
    
        Get-CsPrivacyConfiguration | Set-CsPrivacyConfiguration -EnablePrivacyMode $True
    
    <span data-ttu-id="cc65a-117">此命令将为组织中当前使用的所有隐私配置设置启用隐私模式。</span><span class="sxs-lookup"><span data-stu-id="cc65a-117">This command enables privacy mode for all the privacy configuration settings currently in use in the organization.</span></span> <span data-ttu-id="cc65a-118">有关 Lync Server 增强状态隐私模式策略配置如何管理 Lync 2013 客户端的联系人状态的详细信息, 请参阅 Microsoft 知识库文章[启用 Lync Server 增强状态隐私模式会更新状态某些 Lync 联系人的状态为 "不可用"](http://support.microsoft.com/kb/3020057)。</span><span class="sxs-lookup"><span data-stu-id="cc65a-118">For more information about how the Lync Server enhanced presence privacy mode policy configurations manages contact presence for the Lync 2013 client, see the Microsoft KB article [Enabling Lync Server enhanced presence privacy mode updates the presence status of some Lync contacts to "unavailable"](http://support.microsoft.com/kb/3020057).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="cc65a-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cc65a-119">See Also</span></span>


[<span data-ttu-id="cc65a-120">CsPrivacyConfiguration</span><span class="sxs-lookup"><span data-stu-id="cc65a-120">Get-CsPrivacyConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsPrivacyConfiguration)  
[<span data-ttu-id="cc65a-121">新-CsPrivacyConfiguration</span><span class="sxs-lookup"><span data-stu-id="cc65a-121">New-CsPrivacyConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsPrivacyConfiguration)  
[<span data-ttu-id="cc65a-122">Set-CsPrivacyConfiguration</span><span class="sxs-lookup"><span data-stu-id="cc65a-122">Set-CsPrivacyConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsPrivacyConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

