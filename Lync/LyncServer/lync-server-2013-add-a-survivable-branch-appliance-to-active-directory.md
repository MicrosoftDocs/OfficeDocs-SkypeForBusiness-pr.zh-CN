---
title: Lync Server 2013：向 Active Directory 中添加 Survivable Branch Appliance
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Add a Survivable Branch Appliance to Active Directory
ms:assetid: 3e63507c-d60b-40ec-8bbe-586b1d707c3e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425906(v=OCS.15)
ms:contentKeyID: 48183938
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4dc057318a0d241a28b8529802ea9f2016a1f5b5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837956"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-a-survivable-branch-appliance-to-active-directory-in-lync-server-2013"></a><span data-ttu-id="7156b-102">在 Lync Server 2013 中向 Active Directory 中添加 Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="7156b-102">Add a Survivable Branch Appliance to Active Directory in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7156b-103">_**主题上次修改时间:** 2012-09-23_</span><span class="sxs-lookup"><span data-stu-id="7156b-103">_**Topic Last Modified:** 2012-09-23_</span></span>

<span data-ttu-id="7156b-104">如果你计划部署 Survivable 分支设备, 则必须将 Survivable 分支装置添加到 Active Directory 域服务。</span><span class="sxs-lookup"><span data-stu-id="7156b-104">If you plan to deploy a Survivable Branch Appliance, you must add the Survivable Branch Appliance to Active Directory Domain Services.</span></span> <span data-ttu-id="7156b-105">在中心站点执行此过程。</span><span class="sxs-lookup"><span data-stu-id="7156b-105">Perform this procedure at the central site.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="7156b-106">仅在部署 Survivable 分支设备时执行此过程。</span><span class="sxs-lookup"><span data-stu-id="7156b-106">Perform this procedure only if you are deploying a Survivable Branch Appliance.</span></span> <span data-ttu-id="7156b-107">如果要部署 Survivable 分支服务器, 请不要执行此操作。</span><span class="sxs-lookup"><span data-stu-id="7156b-107">Do not perform it if you are deploying a Survivable Branch Server.</span></span>



</div>

<div>

## <a name="to-add-an-survivable-branch-appliance-to-active-directory-domain-services"></a><span data-ttu-id="7156b-108">将 Survivable 分支装置添加到 Active Directory 域服务</span><span class="sxs-lookup"><span data-stu-id="7156b-108">To add an Survivable Branch Appliance to Active Directory Domain Services</span></span>

1.  <span data-ttu-id="7156b-109">作为企业管理员组的成员登录到成员服务器。</span><span class="sxs-lookup"><span data-stu-id="7156b-109">Log on to a member server as a member of the Enterprise Admins group.</span></span>

2.  <span data-ttu-id="7156b-110">单击 "**开始**", 单击 "**管理工具**", 然后单击 " **Active Directory 用户和计算机**"。</span><span class="sxs-lookup"><span data-stu-id="7156b-110">Click **Start**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>

3.  <span data-ttu-id="7156b-111">在 "**操作**" 菜单上, 单击 "**新建**", 然后单击 "**计算机**"。</span><span class="sxs-lookup"><span data-stu-id="7156b-111">On the **Actions** menu, click **New** and then click **Computer**.</span></span>

4.  <span data-ttu-id="7156b-112">在 "**新建对象-计算机**" 对话框中, 键入 Survivable 分支装置计算机对象的名称 (例如, BranchOffice1), 然后单击 "**更改**"。</span><span class="sxs-lookup"><span data-stu-id="7156b-112">In the **New Object-Computer** dialog box, type in a name for the Survivable Branch Appliance computer object (for example, BranchOffice1), and then click **Change**.</span></span>

5.  <span data-ttu-id="7156b-113">在 "**选择用户或组**" 对话框中, 添加 "RTCUniversalSBATechnicians" 组, 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="7156b-113">In the **Select User or Group** dialog box, add the RTCUniversalSBATechnicians group and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7156b-114">分支站点的 RTCUniversalSBATechnicians 组的成员将在以后将此设备添加到该域。</span><span class="sxs-lookup"><span data-stu-id="7156b-114">A member of the RTCUniversalSBATechnicians group at the branch site will add this device to the domain later.</span></span>

    
    </div>

6.  <span data-ttu-id="7156b-115">单击 **"确定"** 保存 Survivable 分支装置计算机对象。</span><span class="sxs-lookup"><span data-stu-id="7156b-115">Click **OK** to save the Survivable Branch Appliance computer object.</span></span>

7.  <span data-ttu-id="7156b-116">单击 "**开始**", 单击 "**管理工具**", 然后单击 " **ADSI 编辑**"。</span><span class="sxs-lookup"><span data-stu-id="7156b-116">Click **Start**, click **Administrative Tools**, and then click **ADSI Edit**.</span></span>

8.  <span data-ttu-id="7156b-117">在 " **ADSI 编辑**" 中, 右键单击您在前面的步骤中创建的计算机对象, 然后单击 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="7156b-117">In **ADSI Edit**, right-click the computer object that you created in the previous steps, and then click **Properties**.</span></span>

9.  <span data-ttu-id="7156b-118">在 "属性" 列表中, 单击 " **servicePrincipalName**", 然后单击 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="7156b-118">In the attribute list, click **servicePrincipalName**, and then click **Edit**.</span></span>

10. <span data-ttu-id="7156b-119">在 "**要添加的值**" 字段中,\<键入 HOST\> / \<SBA FQDN\> , 其中 SBA fqdn 是你的 Survivable 分支装置的完全限定的域名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="7156b-119">In the **Value to add** field, type HOST/\<SBA FQDN\> where \<SBA FQDN\> is the fully qualified domain name (FQDN) of your Survivable Branch Appliance.</span></span> <span data-ttu-id="7156b-120">例如, 键入**HOST/BranchOffice1**。</span><span class="sxs-lookup"><span data-stu-id="7156b-120">For example, type **HOST/BranchOffice1.contoso.com**.</span></span>

11. <span data-ttu-id="7156b-121">单击 **"确定"** 保存**servicePrincipalName**属性设置, 然后单击 **"确定"** 以保存计算机对象属性。</span><span class="sxs-lookup"><span data-stu-id="7156b-121">Click **OK** to save the **servicePrincipalName** attribute setting, and then click **OK** to save the computer object properties.</span></span>

12. <span data-ttu-id="7156b-122">在 " **Active Directory 用户和计算机**" 中, 右键单击 "**用户**", 单击 "**新建**", 然后单击 "**用户**"。</span><span class="sxs-lookup"><span data-stu-id="7156b-122">In **Active Directory Users and Computers**, right-click **Users**, click **New**, and then click **User**.</span></span>

13. <span data-ttu-id="7156b-123">在向导中输入信息, 为 Survivable 分支装置技术人员创建域用户帐户。</span><span class="sxs-lookup"><span data-stu-id="7156b-123">Enter information into the wizard to create a domain user account for a Survivable Branch Appliance technician.</span></span>

14. <span data-ttu-id="7156b-124">在 " **Active Directory 用户和计算机**" 中, 单击 "**用户**", 右键单击用户对象, 然后单击 "**添加到组**"。</span><span class="sxs-lookup"><span data-stu-id="7156b-124">In **Active Directory Users and Computers**, click **Users**, right-click the user object, and then click **Add to a group**.</span></span>

15. <span data-ttu-id="7156b-125">在 "**输入要选择的对象名称**" 中, 键入**RTCUniversalSBATechnicians**, 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="7156b-125">In **Enter the object names to select**, type **RTCUniversalSBATechnicians**, and then click **OK**.</span></span>

16. <span data-ttu-id="7156b-126">对每个分支站点技术人员重复步骤12-15。</span><span class="sxs-lookup"><span data-stu-id="7156b-126">Repeat Steps 12-15 for each branch site technician.</span></span>

<span data-ttu-id="7156b-127">**下一步**:[在 Lync Server 2013 中向拓扑添加分支站点](lync-server-2013-add-branch-sites-to-your-topology.md)</span><span class="sxs-lookup"><span data-stu-id="7156b-127">**Next step**: [Add branch sites to your topology in Lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

