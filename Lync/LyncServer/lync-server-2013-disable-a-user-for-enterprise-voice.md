---
title: Lync Server 2013：禁用企业语音用户
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disable a user for Enterprise Voice
ms:assetid: 462002d8-21df-4d77-bf7f-4d059d6a4bb2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688043(v=OCS.15)
ms:contentKeyID: 49733635
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f89b40a7398f35efab418fac7be92536ec17270
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762210"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disable-a-user-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="1f78c-102">在 Lync Server 2013 中禁用企业语音用户</span><span class="sxs-lookup"><span data-stu-id="1f78c-102">Disable a user for Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1f78c-103">_**主题上次修改时间：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="1f78c-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="1f78c-104">使用以下过程为已启用 Lync Server 2013 的用户帐户禁用企业语音。</span><span class="sxs-lookup"><span data-stu-id="1f78c-104">Use the following procedure to disable Enterprise Voice for a user account that is enabled for Lync Server 2013.</span></span>

<div>

## <a name="to-disable-a-user-account-for-enterprise-voice"></a><span data-ttu-id="1f78c-105">禁用企业语音的用户帐户</span><span class="sxs-lookup"><span data-stu-id="1f78c-105">To disable a user account for Enterprise Voice</span></span>

1.  <span data-ttu-id="1f78c-106">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="1f78c-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1f78c-107">打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="1f78c-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1f78c-108">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="1f78c-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1f78c-109">在左导航栏中，单击“用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1f78c-109">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="1f78c-110">在“搜索用户”\*\*\*\* 框中，键入要启用的用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“查找”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1f78c-110">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>

5.  <span data-ttu-id="1f78c-111">在表中，单击要为企业语音启用的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="1f78c-111">In the table, click the user account that you want to enable for Enterprise Voice.</span></span>

6.  <span data-ttu-id="1f78c-112">在“编辑”\*\*\*\* 菜单上，单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1f78c-112">On the **Edit** menu, click **Show details**.</span></span>

7.  <span data-ttu-id="1f78c-113">在 "**编辑 Lync Server 用户**" 页面上的 "**电话服务**" 下，单击除**企业语音**之外的任何选项。</span><span class="sxs-lookup"><span data-stu-id="1f78c-113">On the **Edit Lync Server User** page, under **Telephony**, click any option except **Enterprise Voice**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1f78c-114">若要限制用户使用 Lync 进行音频或视频呼叫，请在 "<STRONG>电话服务</STRONG>" 下，单击 "<STRONG>音频/视频已禁用</STRONG>"。</span><span class="sxs-lookup"><span data-stu-id="1f78c-114">To restrict a user from making audio or video calls by using Lync, under <STRONG>Telephony</STRONG>, click <STRONG>Audio/video disabled</STRONG>.</span></span>

    
    </div>

8.  <span data-ttu-id="1f78c-115">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="1f78c-115">Click **Commit**.</span></span>

<span data-ttu-id="1f78c-116">用户现在无法使用企业语音功能。</span><span class="sxs-lookup"><span data-stu-id="1f78c-116">The user is now unable to use the Enterprise Voice feature.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1f78c-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1f78c-117">See Also</span></span>


[<span data-ttu-id="1f78c-118">在 Lync Server 2013 中启用企业语音用户</span><span class="sxs-lookup"><span data-stu-id="1f78c-118">Enable users for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-enable-users-for-enterprise-voice.md)  


[<span data-ttu-id="1f78c-119">在 Lync Server 2013 中管理用户的企业语音语音</span><span class="sxs-lookup"><span data-stu-id="1f78c-119">Managing Enterprise Voice for users in Lync Server 2013</span></span>](lync-server-2013-managing-enterprise-voice-for-users.md)  
[<span data-ttu-id="1f78c-120">Lync Server 2013 命令行管理程序</span><span class="sxs-lookup"><span data-stu-id="1f78c-120">Lync Server 2013 Management Shell</span></span>](lync-server-2013-lync-server-management-shell.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

