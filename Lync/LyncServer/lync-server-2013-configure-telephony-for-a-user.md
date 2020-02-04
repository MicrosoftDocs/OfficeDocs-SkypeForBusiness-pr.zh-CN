---
title: Lync Server 2013：为用户配置电话服务
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure telephony for a user
ms:assetid: 4546432e-c839-4517-a2c5-bc0d4d8c6a03
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520988(v=OCS.15)
ms:contentKeyID: 48183987
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d57c4799c0fe9bb9dc698c3e0e74a9d73cbde524
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740002"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-telephony-for-a-user-in-lync-server-2013"></a><span data-ttu-id="8e845-102">在 Lync Server 2013 中为用户配置电话服务</span><span class="sxs-lookup"><span data-stu-id="8e845-102">Configure telephony for a user in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8e845-103">_**主题上次修改时间：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="8e845-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="8e845-104">电话设置是用户帐户的一些个人设置，可在 Lync Server 控制面板 for 用户（即，如果个人用户已启用 Lync Server 2013 且组织支持电话服务）中进行配置。</span><span class="sxs-lookup"><span data-stu-id="8e845-104">Telephony settings are some of the individual settings of a user account that can be configured in Lync Server Control Panel for the user (that is, if the individual user has been enabled for Lync Server 2013 and the organization supports telephony).</span></span>

<span data-ttu-id="8e845-105">Lync Server 用户电话选项包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="8e845-105">Lync Server user telephony options include the following:</span></span>

  - <span data-ttu-id="8e845-106">**音频/视频已禁用**   用户无法使用音频和视频进行呼叫。</span><span class="sxs-lookup"><span data-stu-id="8e845-106">**Audio/video disabled**   The user cannot make calls with audio and video.</span></span>

  - <span data-ttu-id="8e845-107">**仅限**   pc 至 pc 用户只能进行 pc 到 pc 的音频或视频通话。</span><span class="sxs-lookup"><span data-stu-id="8e845-107">**PC-to-PC only**   The user can make only PC-to-PC audio or video calls.</span></span>

  - <span data-ttu-id="8e845-108">**企业语音**   用户可以使用 Lync Server 2013 基础结构路由所有传入和传出呼叫。</span><span class="sxs-lookup"><span data-stu-id="8e845-108">**Enterprise Voice**   The user can use the Lync Server 2013 infrastructure to route all incoming and outgoing calls.</span></span> <span data-ttu-id="8e845-109">用户还可以进行 PC 到 PC 呼叫。</span><span class="sxs-lookup"><span data-stu-id="8e845-109">The user can also make PC-to-PC calls.</span></span>

  - <span data-ttu-id="8e845-110">**远程呼叫控制**   用户可以使用 Lync Server 2013 控制桌面电话，也可以进行 pc 到 pc 呼叫。</span><span class="sxs-lookup"><span data-stu-id="8e845-110">**Remote call control**   The user can use Lync Server 2013 to control the desktop phone, and can also make PC-to-PC calls.</span></span>

<span data-ttu-id="8e845-111">有关为组织配置电话的详细信息，请参阅在部署文档中[为 Lync server 2013 中的用户配置电话](lync-server-2013-configure-telephony-for-a-user.md)和[在 lync Server 2013 中部署企业语音](lync-server-2013-deploying-enterprise-voice.md)。</span><span class="sxs-lookup"><span data-stu-id="8e845-111">For details about configuring telephony for an organization, see [Configure telephony for a user in Lync Server 2013](lync-server-2013-configure-telephony-for-a-user.md) and [Deploying Enterprise Voice in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) in the Deployment documentation.</span></span>

<div>

## <a name="to-configure-telephony-for-a-specific-user-account"></a><span data-ttu-id="8e845-112">为特定用户帐户配置电话服务</span><span class="sxs-lookup"><span data-stu-id="8e845-112">To configure telephony for a specific user account</span></span>

1.  <span data-ttu-id="8e845-113">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="8e845-113">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8e845-114">打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="8e845-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8e845-115">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="8e845-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="8e845-116">在左导航栏中，单击“用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8e845-116">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="8e845-117">在 "**搜索用户**" 框中，键入所需用户帐户的所有或第一部分的显示名称、名字、姓氏、安全帐户管理器（SAM）帐户名称、SIP 地址或行统一资源标识符（URI），然后单击 "**查找**"。</span><span class="sxs-lookup"><span data-stu-id="8e845-117">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span>

5.  <span data-ttu-id="8e845-118">在表中，单击要修改的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="8e845-118">In the table, click the user account that you want to modify.</span></span>

6.  <span data-ttu-id="8e845-119">在 "**编辑**" 菜单上，单击 "**修改**"。</span><span class="sxs-lookup"><span data-stu-id="8e845-119">On the **Edit** menu, click **Modify**.</span></span>

7.  <span data-ttu-id="8e845-120">在**电话服务**中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="8e845-120">In **Telephony**, do the following:</span></span>
    
      - <span data-ttu-id="8e845-121">若要为用户禁用音频和视频呼叫，请单击 "**音频/视频已禁用**"。</span><span class="sxs-lookup"><span data-stu-id="8e845-121">To disable audio and video calls for the user, click **Audio/video disabled**.</span></span>
    
      - <span data-ttu-id="8e845-122">若要为用户启用 PC 至 PC 音频通信，但不支持远程呼叫控制或企业语音，请单击 "**仅 pc 到 pc**"。</span><span class="sxs-lookup"><span data-stu-id="8e845-122">To enable PC-to-PC audio communications for the user, but not remote call control or Enterprise Voice, click **PC-to-PC only**.</span></span> <span data-ttu-id="8e845-123">为用户用于 PC 到 PC 音频通信的电话指定**行 URI**的值。</span><span class="sxs-lookup"><span data-stu-id="8e845-123">Specify a value for **Line URI** for the telephone that the user uses for PC-to-PC audio communications.</span></span>
    
      - <span data-ttu-id="8e845-124">若要根据服务策略类别（包括 PC 到 PC 音频通信）使用 Lync Server 2010 基础结构路由用户的电话呼叫，请单击 "**企业语音**"。</span><span class="sxs-lookup"><span data-stu-id="8e845-124">To route the user's phone calls by using the Lync Server 2010 infrastructure in accordance with the class of service policy, including PC-to-PC audio communication, click **Enterprise Voice**.</span></span> <span data-ttu-id="8e845-125">在 "**行 URI**" 中，指定企业语音的电话号码。</span><span class="sxs-lookup"><span data-stu-id="8e845-125">In **Line URI**, specify the telephone number for Enterprise Voice.</span></span> <span data-ttu-id="8e845-126">在 "**拨号计划策略**" 和 "**语音策略**" 中，为用户指定适当的策略。</span><span class="sxs-lookup"><span data-stu-id="8e845-126">In **Dial plan policy** and **Voice policy**, specify the appropriate policies for the user.</span></span> <span data-ttu-id="8e845-127">若要指定将用户拨打的电话号码转换为电子164格式的规范化规则，请在 "**位置策略**" 中选择相应的位置配置文件。</span><span class="sxs-lookup"><span data-stu-id="8e845-127">To specify the normalization rules for translating phone numbers dialed by the user to the E.164 format, select the appropriate location profile in **Location policy**.</span></span>
    
      - <span data-ttu-id="8e845-128">若要启用 "远程呼叫控制"，使用户能够从 Lync Server 2013 控制其桌面电话线路，以进行 PC 到 PC 呼叫和 PC 至电话呼叫，请单击 "**远程呼叫控制**"。</span><span class="sxs-lookup"><span data-stu-id="8e845-128">To enable remote call control, which enables users to control their desktop phone line from Lync Server 2013 to make PC-to-PC calls and PC-to-phone calls, click **Remote call control**.</span></span> <span data-ttu-id="8e845-129">在 "**行 URI**" 中，指定远程呼叫控制的电话号码。</span><span class="sxs-lookup"><span data-stu-id="8e845-129">In **Line URI**, specify the telephone number for remote call control.</span></span> <span data-ttu-id="8e845-130">用户必须具有桌面电话和专用分支 exchange （PBX）连接才能使用呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="8e845-130">The user must have a desktop phone and private branch exchange (PBX) connection for call routing.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8e845-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8e845-131">See Also</span></span>


[<span data-ttu-id="8e845-132">在 Lync Server 2013 中修改用户帐户属性</span><span class="sxs-lookup"><span data-stu-id="8e845-132">Modifying user account properties in Lync Server 2013</span></span>](lync-server-2013-modifying-user-account-properties.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

