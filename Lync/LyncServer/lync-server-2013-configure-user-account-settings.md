---
title: Lync Server 2013：配置用户帐户设置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure user account settings
ms:assetid: b7c74ecc-b924-4efc-8a56-3a5f94a9ef13
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412896(v=OCS.15)
ms:contentKeyID: 48185200
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b4d06405d2f80aef5decb69d564ae399401d4328
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837303"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-user-account-settings-in-lync-server-2013"></a><span data-ttu-id="0f8ab-102">在 Lync Server 2013 中配置用户帐户设置</span><span class="sxs-lookup"><span data-stu-id="0f8ab-102">Configure user account settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0f8ab-103">_**主题上次修改时间:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="0f8ab-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="0f8ab-104">拨入用户输入其电话号码或分机号和 PIN，即可以经过身份验证的用户身份加入会议。</span><span class="sxs-lookup"><span data-stu-id="0f8ab-104">Dial-in users enter their phone number or extension and a PIN to join conferences as authenticated users.</span></span> <span data-ttu-id="0f8ab-105">需要在 Lync Server 用户帐户上指定的电话**线路 URI**才能进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="0f8ab-105">The telephony **Line URI** specified on Lync Server user accounts is required for authentication.</span></span>

<span data-ttu-id="0f8ab-106">本主题中的过程介绍如何为单个用户帐户分配“**线路 URI**”。</span><span class="sxs-lookup"><span data-stu-id="0f8ab-106">The procedure in this topic describes how to assign a **Line URI** for a single user account.</span></span> <span data-ttu-id="0f8ab-107">如果需要为多个用户帐户分配“**线路 URI**”，则可以创建使用 **Set-CsUser** cmdlet 的脚本。</span><span class="sxs-lookup"><span data-stu-id="0f8ab-107">If you need to assign a **Line URI** for multiple user accounts, you can create a script that uses the **Set-CsUser** cmdlet.</span></span> <span data-ttu-id="0f8ab-108">有关使用示例脚本为多个用户帐户分配**行 URI**的详细信息, 请参阅 "为多个用户分配行 uri [http://go.microsoft.com/fwlink/p/?linkId=196945](http://go.microsoft.com/fwlink/p/?linkid=196945)"。</span><span class="sxs-lookup"><span data-stu-id="0f8ab-108">For details about using a sample script to assign **Line URI** to multiple user accounts, see "Assign Line URIs to Multiple Users" at [http://go.microsoft.com/fwlink/p/?linkId=196945](http://go.microsoft.com/fwlink/p/?linkid=196945).</span></span>

<div>

## <a name="to-configure-user-account-settings"></a><span data-ttu-id="0f8ab-109">配置用户帐户设置</span><span class="sxs-lookup"><span data-stu-id="0f8ab-109">To configure user account settings</span></span>

1.  <span data-ttu-id="0f8ab-110">以 RTCUniversalServerAdmins 组成员或者 **Cs-UserAdministrator** 或 **CsAdministrator** 角色成员的身份登录计算机。</span><span class="sxs-lookup"><span data-stu-id="0f8ab-110">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-UserAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="0f8ab-111">打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="0f8ab-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="0f8ab-112">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="0f8ab-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="0f8ab-113">在左导航栏中，单击“用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0f8ab-113">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="0f8ab-114">在搜索字段中，键入要为其配置电话拨入式会议的用户的名称，或单击“**添加筛选器**”以指定搜索字段，然后单击“**查找**”。</span><span class="sxs-lookup"><span data-stu-id="0f8ab-114">In the search field, type the name of the user you want to configure for dial-in conferencing or click **Add filter** to specify search fields, and then click **Find**.</span></span>

5.  <span data-ttu-id="0f8ab-115">双击该用户名以打开 "**编辑 Lync Server 用户**" 对话框。</span><span class="sxs-lookup"><span data-stu-id="0f8ab-115">Double-click the user name to open the **Edit Lync Server User** dialog box.</span></span>

6.  <span data-ttu-id="0f8ab-116">在“**电话**”下的“**线路 URI**”字段中，键入唯一的规范化电话号码（例如，tel:+14255550200）。</span><span class="sxs-lookup"><span data-stu-id="0f8ab-116">Under **Telephony**, in the **Line URI** field, type a unique, normalized phone number (for example, tel:+14255550200).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0f8ab-117">仅当将“<STRONG>电话</STRONG>”设置为“<STRONG>仅限 PC 到 PC</STRONG>”、“<STRONG>企业语音</STRONG>”、“<STRONG>远程呼叫控制</STRONG>”或“<STRONG>仅远程呼叫控制</STRONG>”时，才可以指定“<STRONG>线路 URI</STRONG>”。</span><span class="sxs-lookup"><span data-stu-id="0f8ab-117">You can specify <STRONG>Line URI</STRONG> only if <STRONG>Telephony</STRONG> is set to <STRONG>PC-to-PC only</STRONG>, <STRONG>Enterprise Voice</STRONG>, <STRONG>Remote call control</STRONG> or <STRONG>Remote call control only</STRONG>.</span></span>

    
    </div>

7.  <span data-ttu-id="0f8ab-118">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="0f8ab-118">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

