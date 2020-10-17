---
title: Lync Server 2013：将 Survivable 分支设备添加到 Active Directory
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add a Survivable Branch Appliance to Active Directory
ms:assetid: 3e63507c-d60b-40ec-8bbe-586b1d707c3e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425906(v=OCS.15)
ms:contentKeyID: 48183938
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f52d9c5e88e88665f530d6d7ace06a07c4814b4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529559"
---
# <a name="add-a-survivable-branch-appliance-to-active-directory-in-lync-server-2013"></a><span data-ttu-id="e1886-102">在 Lync Server 2013 中将 Survivable 分支设备添加到 Active Directory</span><span class="sxs-lookup"><span data-stu-id="e1886-102">Add a Survivable Branch Appliance to Active Directory in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e1886-103">_**上次修改的主题：** 2012-09-23_</span><span class="sxs-lookup"><span data-stu-id="e1886-103">_**Topic Last Modified:** 2012-09-23_</span></span>

<span data-ttu-id="e1886-104">如果您计划部署 Survivable 分支设备，则必须将 Survivable 分支设备添加到 Active Directory 域服务中。</span><span class="sxs-lookup"><span data-stu-id="e1886-104">If you plan to deploy a Survivable Branch Appliance, you must add the Survivable Branch Appliance to Active Directory Domain Services.</span></span> <span data-ttu-id="e1886-105">请在中央站点执行此过程。</span><span class="sxs-lookup"><span data-stu-id="e1886-105">Perform this procedure at the central site.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e1886-106">仅在部署 Survivable 分支设备时执行此过程。</span><span class="sxs-lookup"><span data-stu-id="e1886-106">Perform this procedure only if you are deploying a Survivable Branch Appliance.</span></span> <span data-ttu-id="e1886-107">如果要部署 Survivable 分支服务器，则不要执行此操作。</span><span class="sxs-lookup"><span data-stu-id="e1886-107">Do not perform it if you are deploying a Survivable Branch Server.</span></span>



</div>

<div>

## <a name="to-add-an-survivable-branch-appliance-to-active-directory-domain-services"></a><span data-ttu-id="e1886-108">将 Survivable Branch Appliance 添加到 Active Directory 域服务</span><span class="sxs-lookup"><span data-stu-id="e1886-108">To add an Survivable Branch Appliance to Active Directory Domain Services</span></span>

1.  <span data-ttu-id="e1886-109">以 Enterprise Admins 组成员的身份登录到成员服务器。</span><span class="sxs-lookup"><span data-stu-id="e1886-109">Log on to a member server as a member of the Enterprise Admins group.</span></span>

2.  <span data-ttu-id="e1886-110">依次单击“开始”\*\*\*\*、“管理工具”\*\*\*\*、“Active Directory 用户和计算机”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e1886-110">Click **Start**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>

3.  <span data-ttu-id="e1886-111">在“操作”\*\*\*\* 菜单上，单击“新建”\*\*\*\*，然后单击“计算机”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e1886-111">On the **Actions** menu, click **New** and then click **Computer**.</span></span>

4.  <span data-ttu-id="e1886-112">在 " **新建对象-计算机** " 对话框中，键入 Survivable Branch 装置 Computer 对象的名称 (例如，BranchOffice1) ，然后单击 " **更改**"。</span><span class="sxs-lookup"><span data-stu-id="e1886-112">In the **New Object-Computer** dialog box, type in a name for the Survivable Branch Appliance computer object (for example, BranchOffice1), and then click **Change**.</span></span>

5.  <span data-ttu-id="e1886-113">在“选择用户或组”\*\*\*\* 对话框中，添加 RTCUniversalSBATechnicians 组，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e1886-113">In the **Select User or Group** dialog box, add the RTCUniversalSBATechnicians group and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e1886-114">分支站点中 RTCUniversalSBATechnicians 组的成员稍后会将此设备添加到域。</span><span class="sxs-lookup"><span data-stu-id="e1886-114">A member of the RTCUniversalSBATechnicians group at the branch site will add this device to the domain later.</span></span>

    
    </div>

6.  <span data-ttu-id="e1886-115">单击 **"确定"** 以保存 Survivable 分支装置计算机对象。</span><span class="sxs-lookup"><span data-stu-id="e1886-115">Click **OK** to save the Survivable Branch Appliance computer object.</span></span>

7.  <span data-ttu-id="e1886-116">单击“开始”\*\*\*\*，再单击“管理工具”\*\*\*\*，然后单击“ADSI Edit”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e1886-116">Click **Start**, click **Administrative Tools**, and then click **ADSI Edit**.</span></span>

8.  <span data-ttu-id="e1886-117">在“ADSI Edit”\*\*\*\* 中，右键单击之前步骤中创建的计算机对象，然后单击“属性”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e1886-117">In **ADSI Edit**, right-click the computer object that you created in the previous steps, and then click **Properties**.</span></span>

9.  <span data-ttu-id="e1886-118">在属性列表中，单击“servicePrincipalName”\*\*\*\*，然后单击“编辑”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e1886-118">In the attribute list, click **servicePrincipalName**, and then click **Edit**.</span></span>

10. <span data-ttu-id="e1886-119">在 " **要添加的值** " 字段中，键入 HOST/ \<SBA FQDN\> Where \<SBA FQDN\> 是 Survivable 分支设备的完全限定的域名 (FQDN) 。</span><span class="sxs-lookup"><span data-stu-id="e1886-119">In the **Value to add** field, type HOST/\<SBA FQDN\> where \<SBA FQDN\> is the fully qualified domain name (FQDN) of your Survivable Branch Appliance.</span></span> <span data-ttu-id="e1886-120">例如，键入 **HOST/BranchOffice1.contoso.com**。</span><span class="sxs-lookup"><span data-stu-id="e1886-120">For example, type **HOST/BranchOffice1.contoso.com**.</span></span>

11. <span data-ttu-id="e1886-121">单击“确定”\*\*\*\* 保存“servicePrincipalName”\*\*\*\* 属性设置，然后单击“确定”\*\*\*\* 保存计算机对象属性。</span><span class="sxs-lookup"><span data-stu-id="e1886-121">Click **OK** to save the **servicePrincipalName** attribute setting, and then click **OK** to save the computer object properties.</span></span>

12. <span data-ttu-id="e1886-122">在“Active Directory 用户和计算机”\*\*\*\* 中，右键单击“用户”\*\*\*\*，再单击“新建”\*\*\*\*，然后单击“用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e1886-122">In **Active Directory Users and Computers**, right-click **Users**, click **New**, and then click **User**.</span></span>

13. <span data-ttu-id="e1886-123">在向导中输入信息，以创建 Survivable 分支机构技术人员的域用户帐户。</span><span class="sxs-lookup"><span data-stu-id="e1886-123">Enter information into the wizard to create a domain user account for a Survivable Branch Appliance technician.</span></span>

14. <span data-ttu-id="e1886-124">在“Active Directory 用户和计算机”\*\*\*\* 中，单击“用户”\*\*\*\*，右键单击用户对象，然后单击“添加到组”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e1886-124">In **Active Directory Users and Computers**, click **Users**, right-click the user object, and then click **Add to a group**.</span></span>

15. <span data-ttu-id="e1886-125">在“输入要选择的对象名称”\*\*\*\* 中，键入 **RTCUniversalSBATechnicians**，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e1886-125">In **Enter the object names to select**, type **RTCUniversalSBATechnicians**, and then click **OK**.</span></span>

16. <span data-ttu-id="e1886-126">为每个分支站点技术人员重复步骤 12 至 15。</span><span class="sxs-lookup"><span data-stu-id="e1886-126">Repeat Steps 12-15 for each branch site technician.</span></span>

<span data-ttu-id="e1886-127">**下一步**： [在 Lync Server 2013 中向拓扑添加分支站点](lync-server-2013-add-branch-sites-to-your-topology.md)</span><span class="sxs-lookup"><span data-stu-id="e1886-127">**Next step**: [Add branch sites to your topology in Lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

