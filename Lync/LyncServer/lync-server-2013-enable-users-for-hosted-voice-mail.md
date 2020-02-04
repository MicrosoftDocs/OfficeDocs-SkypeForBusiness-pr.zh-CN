---
title: Lync Server 2013：为用户启用托管语音邮件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable users for hosted voice mail
ms:assetid: fa559f8f-ef99-43a1-b580-9e998b95efb8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413062(v=OCS.15)
ms:contentKeyID: 48185919
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8e0ce9ee4da6ee0a36e5e5f0028371aab8af523f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735994"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-users-for-hosted-voice-mail-in-lync-server-2013"></a><span data-ttu-id="67da5-102">在 Lync Server 2013 中为用户启用托管语音邮件</span><span class="sxs-lookup"><span data-stu-id="67da5-102">Enable users for hosted voice mail in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="67da5-103">_**主题上次修改时间：** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="67da5-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="67da5-104">按照在托管 Exchange 统一消息（UM）服务上为语音邮件启用 Lync Server 2013 用户的过程进行操作。</span><span class="sxs-lookup"><span data-stu-id="67da5-104">Follow the procedure to enable Lync Server 2013 users for voice mail on a hosted Exchange Unified Messaging (UM) service.</span></span>

<span data-ttu-id="67da5-105">有关详细信息，请参阅规划文档中的[Lync Server 2013 中的 "托管 Exchange 用户管理](lync-server-2013-hosted-exchange-user-management.md)"。</span><span class="sxs-lookup"><span data-stu-id="67da5-105">For details, see [Hosted Exchange user management in Lync Server 2013](lync-server-2013-hosted-exchange-user-management.md) in the Planning documentation.</span></span>

<span data-ttu-id="67da5-106">有关[move-csuser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) cmdlet 的详细信息，请参阅 Lync Server Management Shell 文档。</span><span class="sxs-lookup"><span data-stu-id="67da5-106">For details about the [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) cmdlet, see the Lync Server Management Shell documentation.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="67da5-107">在 Lync Server 2013 用户可启用托管语音邮件之前，必须部署适用于其用户帐户的托管语音邮件策略。</span><span class="sxs-lookup"><span data-stu-id="67da5-107">Before a Lync Server 2013 user can be enabled for hosted voice mail, a hosted voice mail policy that applies to their user account must be deployed.</span></span> <span data-ttu-id="67da5-108">有关详细信息，请参阅<A href="lync-server-2013-hosted-voice-mail-policies.md">Lync Server 2013 中的托管语音邮件策略</A>。</span><span class="sxs-lookup"><span data-stu-id="67da5-108">For details, see <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted voice mail policies in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-enable-users-for-hosted-voice-mail"></a><span data-ttu-id="67da5-109">为用户启用托管语音邮件</span><span class="sxs-lookup"><span data-stu-id="67da5-109">To enable users for hosted voice mail</span></span>

1.  <span data-ttu-id="67da5-110">启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="67da5-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="67da5-111">运行 Move-csuser cmdlet 以配置托管语音邮件的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="67da5-111">Run the Set-CsUser cmdlet to configure the user account for hosted voice mail.</span></span> <span data-ttu-id="67da5-112">例如，运行：</span><span class="sxs-lookup"><span data-stu-id="67da5-112">For example, run:</span></span>
    
        Set-CsUser -HostedVoiceMail $True -Identity "contoso\kenmyer"
    
    <span data-ttu-id="67da5-113">上述示例设置了以下参数：</span><span class="sxs-lookup"><span data-stu-id="67da5-113">The preceding example sets the following parameters:</span></span>
    
      - <span data-ttu-id="67da5-114">**HostedVoiceMail**使用户的语音邮件呼叫能够路由到托管 Exchange UM。</span><span class="sxs-lookup"><span data-stu-id="67da5-114">**HostedVoiceMail** enables a user’s voice mail calls to be routed to hosted Exchange UM.</span></span> <span data-ttu-id="67da5-115">它还会向 Microsoft Lync 2013 发出信号，以突出 "呼叫语音邮件" 指示器。</span><span class="sxs-lookup"><span data-stu-id="67da5-115">It also signals Microsoft Lync 2013 to light up the “call voice mail” indicator.</span></span>
    
      - <span data-ttu-id="67da5-116">**标识**指定要修改的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="67da5-116">**Identity** specifies the user account to be modified.</span></span> <span data-ttu-id="67da5-117">可以使用以下任意格式指定标识值：</span><span class="sxs-lookup"><span data-stu-id="67da5-117">The Identity value can be specified using any of the following formats:</span></span>
        
          - <span data-ttu-id="67da5-118">用户的 SIP 地址</span><span class="sxs-lookup"><span data-stu-id="67da5-118">The user's SIP address</span></span>
        
          - <span data-ttu-id="67da5-119">用户的 Active Directory 用户主体-名称</span><span class="sxs-lookup"><span data-stu-id="67da5-119">The user's Active Directory User-Principal-Name</span></span>
        
          - <span data-ttu-id="67da5-120">用户的域\\登录名（例如，contoso\\kenmyer）</span><span class="sxs-lookup"><span data-stu-id="67da5-120">The user's domain\\logon name (for example, contoso\\kenmyer)</span></span>
        
          - <span data-ttu-id="67da5-121">用户的 Active Directory 域服务显示名称（如 Ken Myer）。</span><span class="sxs-lookup"><span data-stu-id="67da5-121">The user's Active Directory Domain Services Display-Name (for example, Ken Myer).</span></span> <span data-ttu-id="67da5-122">如果使用显示名称作为标识值，则可以使用星号（\*）通配符。</span><span class="sxs-lookup"><span data-stu-id="67da5-122">If using the Display-Name as the Identity value, you can use the asterisk (\*) wildcard character.</span></span> <span data-ttu-id="67da5-123">例如，标识 "\* smith" 将返回具有以字符串值 "smith" 结尾的显示名称的所有用户。</span><span class="sxs-lookup"><span data-stu-id="67da5-123">For example, the Identity "\* Smith" returns all the users who have a Display-Name that ends with the string value "Smith".</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="67da5-124">用户的 Active Directory SAM-帐户名称不能用作标识值，因为 SAM 帐户名称不一定在林中唯一。</span><span class="sxs-lookup"><span data-stu-id="67da5-124">The user’s Active Directory SAM-Account-Name cannot be used as the Identity value because the SAM-Account-Name is not necessarily unique in the forest.</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

