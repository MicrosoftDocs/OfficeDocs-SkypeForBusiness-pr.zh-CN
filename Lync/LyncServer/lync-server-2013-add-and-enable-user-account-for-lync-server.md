---
title: 'Lync Server 2013: 为 Lync Server 添加和启用用户帐户'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Add and enable user account for Lync Server
ms:assetid: 1edd1c1c-307d-450b-abea-33aaf56bdf13
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520961(v=OCS.15)
ms:contentKeyID: 48183578
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0fc52e76d480e323669b88c1ee461eeccf9aef38
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837951"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-and-enable-user-account-for-lync-server-2013"></a><span data-ttu-id="fe450-102">为 Lync Server 2013 添加和启用用户帐户</span><span class="sxs-lookup"><span data-stu-id="fe450-102">Add and enable user account for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fe450-103">_**主题上次修改时间:** 2012-11-02_</span><span class="sxs-lookup"><span data-stu-id="fe450-103">_**Topic Last Modified:** 2012-11-02_</span></span>

<span data-ttu-id="fe450-104">启用 Active Directory 用户和计算机中的用户帐户后, 您可以使用 Lync Server 控制面板通过将 Active Directory 用户添加到 Lync Server 来创建和启用新的 Lync Server 2013 用户帐户。</span><span class="sxs-lookup"><span data-stu-id="fe450-104">After enabling a user account in Active Directory Users and Computers, you can use Lync Server Control Panel to create and enable new Lync Server 2013 user accounts by adding an Active Directory user to Lync Server.</span></span>

<div>

## <a name="to-add-and-enable-a-new-lync-server-user"></a><span data-ttu-id="fe450-105">添加和启用新的 Lync 服务器用户</span><span class="sxs-lookup"><span data-stu-id="fe450-105">To add and enable a new Lync Server user</span></span>

1.  <span data-ttu-id="fe450-106">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="fe450-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="fe450-107">打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="fe450-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="fe450-108">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="fe450-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="fe450-109">在左导航栏中，单击“用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="fe450-109">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="fe450-110">单击 "**启用用户**"。</span><span class="sxs-lookup"><span data-stu-id="fe450-110">Click **Enable users**.</span></span>

5.  <span data-ttu-id="fe450-111">在 "**新建 Lync Server 用户**" 对话框中, 单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="fe450-111">On the **New Lync Server User** dialog, click **Add**.</span></span>

6.  <span data-ttu-id="fe450-112">在 "**搜索用户**" 框中, 键入所需的 Active Directory 用户帐户的所有或第一部分名称、显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名称、电子邮件地址、用户主体名称 (UPN) 或电话号码, 然后单击 "**查找**"。</span><span class="sxs-lookup"><span data-stu-id="fe450-112">In the **Search users** box, type all or the first portion of the name, display name, first name, last name, Security Accounts Manager (SAM) account name, email address, User Principal Name (UPN), or phone number of the Active Directory user account that you want, and then click **Find**.</span></span>

7.  <span data-ttu-id="fe450-113">在表中, 选择要添加到 Lync Server 的帐户, 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="fe450-113">In the table, select the account you want to add to Lync Server, and then click **OK**.</span></span>

8.  <span data-ttu-id="fe450-114">将用户分配到池, 指定任何其他详细信息, 并将策略分配给所需的用户, 然后单击 "**启用**"。</span><span class="sxs-lookup"><span data-stu-id="fe450-114">Assign the user to a pool, specify any additional details, and assign the policies to the user you want, and then click **Enable**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fe450-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fe450-115">See Also</span></span>


[<span data-ttu-id="fe450-116">禁用或重新启用 Lync Server 2013 的用户帐户</span><span class="sxs-lookup"><span data-stu-id="fe450-116">Disable or re-enable user account for Lync Server 2013</span></span>](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  
[<span data-ttu-id="fe450-117">从 Lync Server 2013 中删除用户帐户</span><span class="sxs-lookup"><span data-stu-id="fe450-117">Remove a user account from Lync Server 2013</span></span>](lync-server-2013-remove-a-user-account-from-lync-server.md)  


[<span data-ttu-id="fe450-118">启用和禁用 Lync Server 2013 的用户</span><span class="sxs-lookup"><span data-stu-id="fe450-118">Enabling and disabling users for Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

