---
title: Lync Server 2013：将 Lync Server 2013 配置为在 Microsoft Exchange Server 上使用统一消息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Lync Server 2013 to work with Unified Messaging on Microsoft Exchange Server
ms:assetid: 1098ae4d-f57f-44f3-804e-39889d9fc14e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398193(v=OCS.15)
ms:contentKeyID: 48183430
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0dc8bc60f87b981a18f351df8ddd163d1b080be
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197695"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server"></a><span data-ttu-id="39c94-102">配置 Lync Server 2013 以使用 Microsoft Exchange Server 上的统一消息</span><span class="sxs-lookup"><span data-stu-id="39c94-102">Configure Lync Server 2013 to work with Unified Messaging on Microsoft Exchange Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span data-ttu-id="39c94-103">_**上次修改的主题：** 2013-04-03_</span><span class="sxs-lookup"><span data-stu-id="39c94-103">_**Topic Last Modified:** 2013-04-03_</span></span>

<span data-ttu-id="39c94-104">此步骤需要使用 Exchange UM 集成实用程序 (OcsUmUtil.exe)。</span><span class="sxs-lookup"><span data-stu-id="39c94-104">This step requires the Exchange UM Integration Utility (OcsUmUtil.exe).</span></span> <span data-ttu-id="39c94-105">此工具位于中的 Lync Server 2013 服务器上。。\\程序文件\\： Microsoft\\Lync Server 2013\\支持文件夹的常见文件。</span><span class="sxs-lookup"><span data-stu-id="39c94-105">This tool is located on the Lync Server 2013 server in the ..\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Support folder.</span></span>

<div>

## <a name="running-the-exchange-um-integration-utility"></a><span data-ttu-id="39c94-106">运行 Exchange UM 集成实用程序</span><span class="sxs-lookup"><span data-stu-id="39c94-106">Running the Exchange UM Integration Utility</span></span>

<span data-ttu-id="39c94-107">必须通过具有以下特征的用户帐户运行 Exchange UM 集成实用程序：</span><span class="sxs-lookup"><span data-stu-id="39c94-107">The Exchange UM Integration Utility must be run from a user account with the following characteristics:</span></span>

  - <span data-ttu-id="39c94-108">RTCUniversalServerAdmins 和 RtcUniversalUserAdmins 组中的成员身份（包含读取 Exchange Server 统一消息设置的权限）。</span><span class="sxs-lookup"><span data-stu-id="39c94-108">Membership in the RTCUniversalServerAdmins and RtcUniversalUserAdmins groups (which includes permission to read Exchange Server Unified Messaging settings).</span></span>

  - <span data-ttu-id="39c94-109">域中的用户权限，用于在指定的组织单位（OU）容器中创建联系人对象。</span><span class="sxs-lookup"><span data-stu-id="39c94-109">User rights within the domain to create contact objects in the specified organizational unit (OU) container.</span></span>

<span data-ttu-id="39c94-110">运行 Exchange UM 集成实用程序时，该实用程序将执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="39c94-110">When you run the Exchange UM Integration Utility, it performs the following tasks:</span></span>

  - <span data-ttu-id="39c94-111">为要由企业语音用户使用的每个自动助理和订阅者访问号码创建联系人对象。</span><span class="sxs-lookup"><span data-stu-id="39c94-111">Creates contact objects for each auto-attendant and subscriber access number to be used by Enterprise Voice users.</span></span>

  - <span data-ttu-id="39c94-112">验证每个企业语音拨号计划的名称是否与其对应的统一消息（UM）拨号计划电话上下文相匹配。</span><span class="sxs-lookup"><span data-stu-id="39c94-112">Verifies that the name of each Enterprise Voice dial plan matches its corresponding unified messaging (UM) dial plan phone context.</span></span> <span data-ttu-id="39c94-113">仅当 UM 拨号计划运行在 exchange 2010 Service Pack 1 （SP1）*之前*的 exchange 版本上时，此匹配才是必需的。</span><span class="sxs-lookup"><span data-stu-id="39c94-113">This matching is necessary only if the UM dial plan is running on a version of Exchange *earlier* than Exchange 2010 Service Pack 1 (SP1).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="39c94-114">在运行 Exchange UM 集成实用工具之前，请确保已完成以下操作：</span><span class="sxs-lookup"><span data-stu-id="39c94-114">Before running the Exchange UM Integration Utility, be sure that you have done the following:</span></span>
> <ul>
> <li><p><span data-ttu-id="39c94-115">创建一个或多个 Exchange UM 拨号计划，如 Exchange 产品文档中所述。</span><span class="sxs-lookup"><span data-stu-id="39c94-115">Create one or more Exchange UM dial plans, as described in the Exchange product documentation.</span></span></p>
> <p><span data-ttu-id="39c94-116">有关 Microsoft Exchange Server 2010，请&quot;参阅在上<a href="https://go.microsoft.com/fwlink/p/?linkid=186177">https://go.microsoft.com/fwlink/p/?linkId=186177</a>创建 UM&quot;拨号计划。</span><span class="sxs-lookup"><span data-stu-id="39c94-116">For Microsoft Exchange Server 2010, see &quot;Create a UM Dial Plan&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=186177">https://go.microsoft.com/fwlink/p/?linkId=186177</a>.</span></span></p>
> <p><span data-ttu-id="39c94-117">对于 Microsoft Exchange Server 2007 Service Pack 1 （SP1），请&quot;参阅如何在<a href="https://go.microsoft.com/fwlink/p/?linkid=185771">https://go.microsoft.com/fwlink/p/?linkId=185771</a>中创建统一消息 SIP URI 拨号&quot;计划。</span><span class="sxs-lookup"><span data-stu-id="39c94-117">For Microsoft Exchange Server 2007 Service Pack 1 (SP1), see &quot;How to Create a Unified Messaging SIP URI Dial Plan&quot; at <a href="https://go.microsoft.com/fwlink/p/?linkid=185771">https://go.microsoft.com/fwlink/p/?linkId=185771</a>.</span></span></p></li>
> <li><p><span data-ttu-id="39c94-118">按照在<a href="lync-server-2013-create-a-dial-plan.md">Lync server 2013 中创建拨号计划</a>中所述，创建一个或多个相应的 Lync server 拨号计划。</span><span class="sxs-lookup"><span data-stu-id="39c94-118">Create one or more corresponding Lync Server dial plans, as described in <a href="lync-server-2013-create-a-dial-plan.md">Create a dial plan in Lync Server 2013</a>.</span></span></p></li>
> <ul><li><span data-ttu-id="39c94-119">如果使用的是早于 Microsoft Exchange Server 2010 SP1 的 Exchange 版本，则必须在 "Lync Server 2013 拨号计划<STRONG>简单名称</STRONG>" 字段中输入相应 Exchange 统一消息（UM） SIP 拨号计划的完全限定域名（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="39c94-119">If you are using a version of Exchange that is earlier than Microsoft Exchange Server 2010 SP1, you must enter the fully qualified domain name (FQDN) of the corresponding Exchange Unified Messaging (UM) SIP dial plan in the Lync Server 2013 dial plan <STRONG>Simple name</STRONG> field.</span></span> <span data-ttu-id="39c94-120">如果使用的是 Microsoft Exchange Server 2010 SP1 或最新的 service pack，则不需要此拨号计划名称匹配。</span><span class="sxs-lookup"><span data-stu-id="39c94-120">If you are using Microsoft Exchange Server 2010 SP1 or latest service pack, this dial plan name matching is not necessary.</span></span></li></ul>
> <li><span data-ttu-id="39c94-121">创建自动助理，并确保订阅者访问号码和自动助理号码的格式为 E.164。</span><span class="sxs-lookup"><span data-stu-id="39c94-121">Create an auto-attendant and make sure that both the subscriber access number and auto-attendant number are in E.164 format.</span></span></li></ul>


<div>

## <a name="to-run-the-exchange-um-integration-utility"></a><span data-ttu-id="39c94-122">运行 Exchange UM 集成实用程序</span><span class="sxs-lookup"><span data-stu-id="39c94-122">To run the Exchange UM Integration Utility</span></span>

1.  <span data-ttu-id="39c94-123">在前端服务器上，打开命令提示符并键入**cd% CommonProgramFiles%\\Microsoft Lync Server 2013\\支持**，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="39c94-123">On a Front End Server, open a command prompt and type **cd %CommonProgramFiles%\\Microsoft Lync Server 2013\\Support**, and then press ENTER.</span></span>

2.  <span data-ttu-id="39c94-124">键入 **OcsUmUtil.exe**，然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="39c94-124">Type **OcsUmUtil.exe**, and then press ENTER.</span></span>

3.  <span data-ttu-id="39c94-125">单击 **“加载数据”** 以查找所有受信任的 Exchange 林。</span><span class="sxs-lookup"><span data-stu-id="39c94-125">Click **Load Data** to find all trusted Exchange forests.</span></span>

4.  <span data-ttu-id="39c94-126">在 **“SIP 拨号计划”** 列表中，选择要为其创建联系人对象的 UM SIP 拨号计划，然后单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="39c94-126">In the **SIP Dial Plans** list, select a UM SIP dial plan for which you want to create contact objects, and then click **Add**.</span></span>

5.  <span data-ttu-id="39c94-p104">在 **“联系人”** 框中接受默认的组织单位，或单击 **“浏览”**，从而启动 **“OU 选取器”**。在 **“OU 选取器”** 框中，可以选择 OU 并单击 **“确定”**，也可以单击 **“新建 OU”**，在域中的根或任何其他 OU 下创建新的组织单位（例如“OU=RTC Special Accounts,DC=fourthcoffee,DC=com”），然后单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="39c94-p104">In the **Contact** box, accept the default organizational unit, or click **Browse** to start the **OU Picker**. In the **OU Picker** box, you can select an OU and click **OK**, or you can click **Make New OU** to create a new organizational unit under the root or any other OU in the domain (for example, "OU=RTC Special Accounts,DC=fourthcoffee,DC=com"), and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="39c94-129">已选择或创建的 OU 的可分辨名称 (DN) 此时将显示在<STRONG>“组织单位”</STRONG>框中。</span><span class="sxs-lookup"><span data-stu-id="39c94-129">The distinguished name (DN) of the OU that you have selected or created is now displayed in the <STRONG>Organizational Unit</STRONG> box.</span></span>

    
    </div>

6.  <span data-ttu-id="39c94-130">在 **“名称”** 框中接受默认的拨号计划名称，或为要创建的联系人对象键入新的显示名称。</span><span class="sxs-lookup"><span data-stu-id="39c94-130">In the **Name** box, either accept the default dial plan name or type a new display name for the contact object that you are creating.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="39c94-131">例如，如果要创建订阅者访问联系人对象，则可能只需简单地将其命名为“订阅者访问”。</span><span class="sxs-lookup"><span data-stu-id="39c94-131">For example, if you are creating a subscriber access contact object, you might simply name it Subscriber Access.</span></span>

    
    </div>

7.  <span data-ttu-id="39c94-132">在 **“SIP 地址”** 框中，接受默认 SIP 地址或键入新的 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="39c94-132">In the **SIP Address** box, either accept the default SIP address or type a new SIP address.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="39c94-133">如果键入新的 SIP 地址，该地址必须以 <STRONG>SIP:</STRONG> 开头（即“SIP:”，包括冒号）。</span><span class="sxs-lookup"><span data-stu-id="39c94-133">If you type a new SIP address, it must begin with <STRONG>SIP:</STRONG> (that is, "SIP:" including the colon).</span></span>

    
    </div>

8.  <span data-ttu-id="39c94-134">在 "**服务器或池**" 列表中，选择要在其中启用 contact 对象的 Standard Edition Server 或前端池。</span><span class="sxs-lookup"><span data-stu-id="39c94-134">In the **Server or Pool** list, select the Standard Edition server or Front End pool in which the contact object is to be enabled.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="39c94-135">选择的池最好是部署启用了企业语音和 Exchange UM 的用户的同一个池。</span><span class="sxs-lookup"><span data-stu-id="39c94-135">Preferably, the pool you select is the same one pool where users enabled for Enterprise Voice and Exchange UM are deployed.</span></span>

    
    </div>

9.  <span data-ttu-id="39c94-136">在 **“电话号码”** 列表中，选择 **“输入电话号码”** 或 **“从 Exchange UM 中使用此引导号”**，然后输入电话号码。</span><span class="sxs-lookup"><span data-stu-id="39c94-136">In the **Phone Number** list, select either **Enter phone number** or **Use this pilot number from Exchange UM** and then enter a phone number.</span></span>

10. <span data-ttu-id="39c94-137">在 **“联系人类型”** 列表中，选择要创建的联系人类型，然后单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="39c94-137">In the **Contact Type** list, select the contact type that you want to create, and then click **OK**.</span></span>

11. <span data-ttu-id="39c94-138">对于要创建的其他联系人对象，重复步骤 1 到 10。</span><span class="sxs-lookup"><span data-stu-id="39c94-138">Repeat steps 1 through 10 for additional contact objects that you want to create.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="39c94-p105">为每个自动助理应至少创建一个联系人。如果希望允许外部访问，还需要一个订阅者访问联系人并指定外线直拨分机 (DID) 号码。</span><span class="sxs-lookup"><span data-stu-id="39c94-p105">You should create at least one contact for each auto attendant. If you want external access, you also need a Subscriber Access contact and to specify Direct Inward Dial (DID) numbers.</span></span>

    
    </div>

</div>

<span data-ttu-id="39c94-p106">要验证是否已创建联系人对象，请打开“Active Directory 用户和计算机”，并选择在其中创建对象的 OU。联系人对象应在详细信息窗格中出现。</span><span class="sxs-lookup"><span data-stu-id="39c94-p106">To verify that the contact objects have been created, open Active Directory Users and Computers and select the OU in which the objects were created. The contact objects should appear in the details pane.</span></span>

<span data-ttu-id="39c94-143"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="39c94-143"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

