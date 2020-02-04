---
title: 将单个用户移动到 "引导" 池
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Move a single user to the pilot pool
ms:assetid: e9de81a8-40dd-4446-81e7-a2b810eaea50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205401(v=OCS.15)
ms:contentKeyID: 48185905
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c14c4a772ced3939d979bd8d4cd053207b0c5613
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765300"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-a-single-user-to-the-pilot-pool"></a><span data-ttu-id="50601-102">将单个用户移动到 "引导" 池</span><span class="sxs-lookup"><span data-stu-id="50601-102">Move a single user to the pilot pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="50601-103">_**主题上次修改时间：** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="50601-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="50601-104">您可以使用 Lync Server 2013 控制面板或 Lync Server 2013 命令行管理程序，将用户从 Lync Server 2010 池中移动到 Lync Server 2013 试验池。</span><span class="sxs-lookup"><span data-stu-id="50601-104">You can move a user from your Lync Server 2010 pool to your Lync Server 2013 pilot pool using Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="50601-105">在下面的示例中，在 "注册机构池" 列中， **pool01.contoso.net**是 Lync Server 2010 池，这些用户中的所有六个用户都已连接到该池。</span><span class="sxs-lookup"><span data-stu-id="50601-105">In the example below, in the Registrar pool column, **pool01.contoso.net** is the Lync Server 2010 pool, and all six of these users are connected to this pool.</span></span> <span data-ttu-id="50601-106">使用以下过程，使用 Lync Server 2013 控制面板和 Lync Server Management Shell 将用户移动到您的 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="50601-106">Use the following procedures to move a user to your Lync Server 2013 pool using Lync Server 2013 Control Panel and Lync Server Management Shell.</span></span>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-control-panel"></a><span data-ttu-id="50601-107">使用 Lync Server 2013 "控制面板" 移动用户</span><span class="sxs-lookup"><span data-stu-id="50601-107">To move a user by using the Lync Server 2013 Control Panel</span></span>

<span data-ttu-id="50601-108">**Lync Server 2013 控制面板中的用户列表**</span><span class="sxs-lookup"><span data-stu-id="50601-108">**List of users in the Lync Server 2013 Control Panel**</span></span>

<span data-ttu-id="50601-109">![Lync Server 控制面板，"移动用户" 对话框](images/JJ721870.a2bce284-0392-4db3-9bb2-9f12699738e7(OCS.15).jpg "Lync Server 控制面板，"移动用户" 对话框")</span><span class="sxs-lookup"><span data-stu-id="50601-109">![Lync Server Control Panel, Move User dialog](images/JJ721870.a2bce284-0392-4db3-9bb2-9f12699738e7(OCS.15).jpg "Lync Server Control Panel, Move User dialog")</span></span>

1.  <span data-ttu-id="50601-110">使用具有 RTCUniversalServerAdmins 组成员身份或 CsAdministrator 或 CsUserAdministrator 管理角色成员身份的帐户登录到前端服务器。</span><span class="sxs-lookup"><span data-stu-id="50601-110">Log on to the Front End Server with an account that is a member of the RTCUniversalServerAdmins group or a member of the CsAdministrator or CsUserAdministrator administrative role.</span></span>

2.  <span data-ttu-id="50601-111">打开“Lync Server 控制面板”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="50601-111">Open **Lync Server Control Panel**.</span></span>

3.  <span data-ttu-id="50601-112">依次单击“用户”\*\*\*\*、“搜索”和“查找”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="50601-112">Click **Users**, click Search, and then click **Find**.</span></span>

4.  <span data-ttu-id="50601-113">选择要移动到 Lync Server 2013 池的用户。</span><span class="sxs-lookup"><span data-stu-id="50601-113">Select a user that you want to move to the Lync Server 2013 pool.</span></span> <span data-ttu-id="50601-114">在此示例中，将移动用户 Sara Davis。</span><span class="sxs-lookup"><span data-stu-id="50601-114">In this example, we will move user Sara Davis.</span></span>

5.  <span data-ttu-id="50601-115">在“操作”\*\*\*\* 菜单中，选择“将所选用户移动到池”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="50601-115">On the **Action** menu, select **Move selected users to pool**.</span></span>

6.  <span data-ttu-id="50601-116">从下拉列表中，选择 "Lync Server 2013" 池。</span><span class="sxs-lookup"><span data-stu-id="50601-116">From the drop-down list, select the Lync Server 2013 pool.</span></span>

7.  <span data-ttu-id="50601-117">单击“操作”\*\*\*\*，然后单击“将所选用户移动到池”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="50601-117">Click **Action** and then click **Move selected users to pool**.</span></span> <span data-ttu-id="50601-118">单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="50601-118">Click **OK**.</span></span>
    
    <span data-ttu-id="50601-119">!["移动用户"、"目标注册机构池" 对话框](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png ""移动用户"、"目标注册机构池" 对话框")</span><span class="sxs-lookup"><span data-stu-id="50601-119">![Move Users, destination registrar pool dialog box](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Move Users, destination registrar pool dialog box")</span></span>  

8.  <span data-ttu-id="50601-120">验证用户的**注册池**列现在是否包含 Lync Server 2013 池，这表示用户已成功移动。</span><span class="sxs-lookup"><span data-stu-id="50601-120">Verify that the **Registrar pool** column for the user now contains the Lync Server 2013 pool, which indicates that the user has been successfully moved.</span></span>

</div>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-management-shell"></a><span data-ttu-id="50601-121">使用 Lync Server 2013 命令行管理程序移动用户</span><span class="sxs-lookup"><span data-stu-id="50601-121">To move a user by using the Lync Server 2013 Management Shell</span></span>

1.  <span data-ttu-id="50601-122">打开 Lync Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="50601-122">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="50601-123">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="50601-123">At the command line, type the following:</span></span>
    
        Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"

3.  <span data-ttu-id="50601-124">接下来，在命令行键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="50601-124">Next, at the command line, type the following:</span></span>
    
        Get-CsUser -Identity "David Pelton"

4.  <span data-ttu-id="50601-125">**RegistrarPool**标识现在指向 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="50601-125">The **RegistrarPool** identity now points to the Lync Server 2013 pool.</span></span> <span data-ttu-id="50601-126">此标识的存在可确认用户已成功移动。</span><span class="sxs-lookup"><span data-stu-id="50601-126">The presence of this identity confirms that the user has been successfully moved.</span></span>
    
    <span data-ttu-id="50601-127">![Move-csuser cmdlet 和 Identity filter 的输出](images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "Move-csuser cmdlet 和 Identity filter 的输出")</span><span class="sxs-lookup"><span data-stu-id="50601-127">![Output from Get-CsUser cmdlet with Identity filter](images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "Output from Get-CsUser cmdlet with Identity filter")</span></span>  
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="50601-128">有关<STRONG>move-csuser</STRONG> cmdlet 的详细信息，请运行： <STRONG>Get-help move-csuser-详细</STRONG>信息</span><span class="sxs-lookup"><span data-stu-id="50601-128">For details about the <STRONG>Get-CsUser</STRONG> cmdlet, run: <STRONG>Get-Help Get-CsUser –Detailed</STRONG></span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

