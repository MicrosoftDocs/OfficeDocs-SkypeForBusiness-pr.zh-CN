---
title: Lync Server 2013：为托管 Exchange UM 创建联系人对象
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create contact objects for hosted Exchange UM
ms:assetid: a39be52f-488a-4523-ad5f-ce1f0d681959
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412765(v=OCS.15)
ms:contentKeyID: 48185045
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 07b363c3f52abe2e62955d456f9d708393e4574b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152014"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-contact-objects-for-hosted-exchange-um-in-lync-server-2013"></a><span data-ttu-id="a1255-102">在 Lync Server 2013 中为托管 Exchange UM 创建联系人对象</span><span class="sxs-lookup"><span data-stu-id="a1255-102">Create contact objects for hosted Exchange UM in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a1255-103">_**上次修改的主题：** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="a1255-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="a1255-104">以下过程介绍如何为托管 Exchange 统一消息 (UM) 创建自动助理 (AA) 或订阅者访问 (SA) 联系人对象。</span><span class="sxs-lookup"><span data-stu-id="a1255-104">The following procedure explains how to create Auto Attendant (AA) or Subscriber Access (SA) contact objects for hosted Exchange Unified Messaging (UM).</span></span>

<span data-ttu-id="a1255-105">有关详细信息，请参阅规划文档中的在[Lync Server 2013 中托管 Exchange 联系人对象管理](lync-server-2013-hosted-exchange-contact-object-management.md)。</span><span class="sxs-lookup"><span data-stu-id="a1255-105">For details, see [Hosted Exchange Contact object management in Lync Server 2013](lync-server-2013-hosted-exchange-contact-object-management.md) in the Planning documentation.</span></span>

<span data-ttu-id="a1255-106">有关配置 contact 对象的详细信息，请参阅 Lync Server 命令行管理程序文档中的以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="a1255-106">For details about configuring contact objects, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="a1255-107">新 CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="a1255-107">New-CsExUmContact</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsExUmContact)

  - [<span data-ttu-id="a1255-108">CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="a1255-108">Set-CsExUmContact</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsExUmContact)

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="a1255-109">在 Lync Server 2013 中可以为托管 Exchange UM 启用联系人对象之前，必须部署适用于这些对象的托管语音邮件策略。</span><span class="sxs-lookup"><span data-stu-id="a1255-109">Before Lync Server 2013 contact objects can be enabled for hosted Exchange UM, a hosted voice mail policy that applies to them must be deployed.</span></span> <span data-ttu-id="a1255-110">有关详细信息，请参阅<A href="lync-server-2013-hosted-voice-mail-policies.md">Lync Server 2013 中的托管语音邮件策略</A>。</span><span class="sxs-lookup"><span data-stu-id="a1255-110">For details, see <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted voice mail policies in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-create-aa-or-sa-contact-objects-for-hosted-exchange-um"></a><span data-ttu-id="a1255-111">为托管 Exchange UM 创建 AA 或 SA 联系人对象</span><span class="sxs-lookup"><span data-stu-id="a1255-111">To create AA or SA contact objects for hosted Exchange UM</span></span>

1.  <span data-ttu-id="a1255-112">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a1255-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="a1255-p102">运行 New-CsExUmContact cmdlet 创建部署所需的任何联系人对象。例如，运行以下命令创建 AA 和 SA 联系人对象：</span><span class="sxs-lookup"><span data-stu-id="a1255-p102">Run the New-CsExUmContact cmdlet to create any contact objects required for your deployment. For example, run the following to create an AA and an SA contact object:</span></span>
    
       ```powershell
        New-CsExUmContact -SipAddress "sip:exumaa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101" -AutoAttendant $True
       ```
    
       ```powershell
        New-CsExUmContact -SipAddress "sip:exumsa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101"
       ```
    
    <span data-ttu-id="a1255-115">这些示例设置了以下参数：</span><span class="sxs-lookup"><span data-stu-id="a1255-115">These examples set the following parameters:</span></span>
    
      - <span data-ttu-id="a1255-116">**SipAddress** 指定联系人对象的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="a1255-116">**SipAddress** specifies the SIP address of the contact object.</span></span> <span data-ttu-id="a1255-117">该地址必须是尚未在 Active Directory 域服务中用于配置用户或联系人对象的地址。</span><span class="sxs-lookup"><span data-stu-id="a1255-117">This must be an address that has not already been used to configure a user or contact object in Active Directory Domain Services.</span></span> <span data-ttu-id="a1255-118">此值必须采用 "sip：\<*sip 地址*\>" 的格式，如前面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="a1255-118">This value must be in the format “sip:\<*SIP address*\>“ as shown in the previous examples.</span></span>
    
      - <span data-ttu-id="a1255-119">**RegistrarPool** 指定运行 Registrar 服务的池的完全限定域名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="a1255-119">**RegistrarPool** specifies the fully qualified domain name (FQDN) of the pool on which the Registrar service is running.</span></span>
        
        <div class=" ">
        

        > [!NOTE]  
        > <span data-ttu-id="a1255-120">在 Lync Server 2013 之前，不能将 Exchange UM 联系人对象移到作为 Lync Server 2013 部署一部分的池。</span><span class="sxs-lookup"><span data-stu-id="a1255-120">Exchange UM contact objects cannot be moved to pools that are part of Lync Server 2013 deployments prior to Lync Server 2013.</span></span>

        
        </div>
    
      - <span data-ttu-id="a1255-121">**OU** 指定此联系人对象将位于的 Active Directory 组织单位。</span><span class="sxs-lookup"><span data-stu-id="a1255-121">**OU** specifies the Active Directory organizational unit where this contact object will be located.</span></span>
    
      - <span data-ttu-id="a1255-p104">**DisplayNumber** 指定联系人对象的电话号码。每个联系人对象的电话号码必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="a1255-p104">**DisplayNumber** specifies the telephone number of the contact object. The phone number for each contact object must be unique.</span></span>
    
      - <span data-ttu-id="a1255-p105">**AutoAttendant** 指定联系人对象是否为自动助理。自动助理提供了一组语音提示，允许呼叫者导航电话系统并最终到达他们要联系的一方。为此参数指定 **False** 值（默认值）指示对象为订阅者访问联系人对象。</span><span class="sxs-lookup"><span data-stu-id="a1255-p105">**AutoAttendant** specifies whether the Contact object is an Auto Attendant. Auto Attendant provides a set of voice prompts that allow callers to navigate the phone system and reach the party that they want to contact. A value of **False** (the default) for this parameter indicates a Subscriber Access contact object.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

