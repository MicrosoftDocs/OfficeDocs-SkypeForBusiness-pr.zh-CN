---
title: 删除网站或用户组的电话拨入式会议 PIN 设置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete dial-in conferencing PIN settings for a site or group of users
ms:assetid: 15a9faee-d024-4c0e-b2a0-fe7e7dc00589
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520955(v=OCS.15)
ms:contentKeyID: 48183498
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a4174a0c84f4e297159cefa7408544c102acc9b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154434"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users-in-lync-server-2013"></a><span data-ttu-id="728fe-102">删除 Lync Server 2013 中某一网站或一组用户的电话拨入式会议 PIN 设置</span><span class="sxs-lookup"><span data-stu-id="728fe-102">Delete dial-in conferencing PIN settings for a site or group of users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="728fe-103">_**上次修改的主题：** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="728fe-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="728fe-104">按照以下步骤删除用户级别或站点级别的 PIN 策略。</span><span class="sxs-lookup"><span data-stu-id="728fe-104">Follow these steps to delete a user-level or a site-level PIN policy.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="728fe-105">无法删除全局 PIN 策略。</span><span class="sxs-lookup"><span data-stu-id="728fe-105">You cannot delete the global PIN policy.</span></span>



</div>

<div>

## <a name="to-delete-a-user-or-site-pin-policy"></a><span data-ttu-id="728fe-106">删除用户或站点 PIN 策略</span><span class="sxs-lookup"><span data-stu-id="728fe-106">To delete a user or site PIN policy</span></span>

1.  <span data-ttu-id="728fe-107">从作为 RTCUniversalServerAdmins 组成员的用户帐户（或具有等效的用户权限）或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户，登录到您在其中部署了 Lync Server 2013 的网络中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="728fe-107">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="728fe-108">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="728fe-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="728fe-109">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="728fe-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="728fe-110">在左侧导航栏中，单击“会议”\*\*\*\*，然后单击“PIN 策略”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="728fe-110">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>

4.  <span data-ttu-id="728fe-111">在“PIN 策略”\*\*\*\* 页上的搜索字段中，键入要删除的策略的全部或部分名称。</span><span class="sxs-lookup"><span data-stu-id="728fe-111">On the **PIN Policy** page, in the search field, type all or part of the name of the policy you want to delete.</span></span>

5.  <span data-ttu-id="728fe-112">在策略列表中，单击所需的策略，再单击“编辑”\*\*\*\*，然后单击“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="728fe-112">In the list of policies, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>

6.  <span data-ttu-id="728fe-113">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="728fe-113">Click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

