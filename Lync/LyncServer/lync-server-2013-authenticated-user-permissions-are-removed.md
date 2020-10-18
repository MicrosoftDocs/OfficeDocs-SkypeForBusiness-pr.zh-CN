---
title: Lync Server 2013：删除经过身份验证的用户权限
description: Lync Server 2013：已删除经过身份验证的用户权限。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Authenticated user permissions are removed
ms:assetid: 5fcd70a5-813a-4076-9bb6-5b0d47505038
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398425(v=OCS.15)
ms:contentKeyID: 48184304
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 59da0ec893395405010afdd0263bd6be5d646881
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573018"
---
# <a name="authenticated-user-permissions-are-removed-in-lync-server-2013"></a><span data-ttu-id="245c1-103">在 Lync Server 2013 中删除经过身份验证的用户权限</span><span class="sxs-lookup"><span data-stu-id="245c1-103">Authenticated user permissions are removed in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="245c1-104">_**上次修改的主题：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="245c1-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="245c1-105">在锁定的 Active Directory 环境中， (Ace) 的经过身份验证的用户访问控制项将从默认的 Active Directory 容器中删除，包括用户、配置或系统以及存储用户和计算机对象的组织单位 (Ou) 。</span><span class="sxs-lookup"><span data-stu-id="245c1-105">In a locked-down Active Directory environment, authenticated user access control entries (ACEs) are removed from the default Active Directory containers, including the Users, Configuration or System, and organizational units (OUs) where User and Computer objects are stored.</span></span> <span data-ttu-id="245c1-106">删除经过身份验证的用户 Ace 可防止对 Active Directory 信息进行读取访问。</span><span class="sxs-lookup"><span data-stu-id="245c1-106">Removing authenticated user ACEs prevents read access to Active Directory information.</span></span> <span data-ttu-id="245c1-107">但是，删除 Ace 会为 Lync Server 2013 创建问题，因为它依赖于这些容器的读取权限以允许用户运行域准备。</span><span class="sxs-lookup"><span data-stu-id="245c1-107">However, removing the ACEs creates issues for Lync Server 2013 because it depends on read permissions to these containers to allow users to run domain preparation.</span></span>

<span data-ttu-id="245c1-108">在这种情况下，域管理员组中的成员身份（若要运行域准备、服务器激活和池创建）不再授予对存储在默认容器中的 Active Directory 信息的读取权限。</span><span class="sxs-lookup"><span data-stu-id="245c1-108">In this situation, membership in the Domain Admins group, which is required to run domain preparation, server activation, and pool creation, no longer grants read access to Active Directory information stored in the default containers.</span></span> <span data-ttu-id="245c1-109">您必须手动授予对林根域中各个容器的读取访问权限，以检查先决条件林准备过程是否已完成。</span><span class="sxs-lookup"><span data-stu-id="245c1-109">You must manually grant read-access permissions on various containers in the forest root domain to check that the prerequisite forest preparation procedure is complete.</span></span>

<span data-ttu-id="245c1-110">若要使用户能够在任何非林根域上运行域准备、服务器激活或池创建，您可以选择以下选项：</span><span class="sxs-lookup"><span data-stu-id="245c1-110">To enable a user to run domain preparation, server activation, or pool creation on any non-forest root domain, you have the following options:</span></span>

  - <span data-ttu-id="245c1-111">使用作为 Enterprise Admins 组成员的帐户来运行域准备。</span><span class="sxs-lookup"><span data-stu-id="245c1-111">Use an account that is a member of the Enterprise Admins group to run domain preparation.</span></span>

  - <span data-ttu-id="245c1-112">使用属于 Domain Admins 组成员的帐户，并为此帐户授予对林根域中以下每个容器的读取访问权限：</span><span class="sxs-lookup"><span data-stu-id="245c1-112">Use an account that is a member of the Domain Admins group and grant this account read-access permissions on each of the following containers in the forest root domain:</span></span>
    
      - <span data-ttu-id="245c1-113">域</span><span class="sxs-lookup"><span data-stu-id="245c1-113">Domain</span></span>
    
      - <span data-ttu-id="245c1-114">配置或系统</span><span class="sxs-lookup"><span data-stu-id="245c1-114">Configuration or System</span></span>

<span data-ttu-id="245c1-115">如果不想使用作为 Enterprise Admins 组成员的帐户来运行域准备或其他安装任务，请明确授予要在林根的相关容器上使用 "读取" 访问权限的帐户。</span><span class="sxs-lookup"><span data-stu-id="245c1-115">If you do not want to use an account that is a member of the Enterprise Admins group to run domain preparation or other Setup tasks, explicitly grant the account you want to use read access on the relevant containers in the forest root.</span></span>

<div>

## <a name="to-give-users-read-access-permissions-on-containers-in-the-forest-root-domain"></a><span data-ttu-id="245c1-116">向用户授予对林根域中容器的读取访问权限</span><span class="sxs-lookup"><span data-stu-id="245c1-116">To give users read-access permissions on containers in the forest root domain</span></span>

1.  <span data-ttu-id="245c1-117">使用作为林根域的 Domain Admins 组成员的帐户登录加入到林根域的计算机。</span><span class="sxs-lookup"><span data-stu-id="245c1-117">Log on to the computer joined to the forest root domain with an account that is a member of the Domain Admins group for the forest root domain.</span></span>

2.  <span data-ttu-id="245c1-118">为林根域运行 adsiedit。</span><span class="sxs-lookup"><span data-stu-id="245c1-118">Run adsiedit.msc for the forest root domain.</span></span>
    
    <span data-ttu-id="245c1-119">如果从域、配置或系统容器中删除了经过身份验证的用户 Ace，则必须向容器授予只读权限，如以下步骤所述。</span><span class="sxs-lookup"><span data-stu-id="245c1-119">If authenticated user ACEs were removed from the Domain, Configuration, or System container, you must grant read-only permissions to the container, as described in the following steps.</span></span>

3.  <span data-ttu-id="245c1-120">右键单击容器，然后单击 " **属性**"。</span><span class="sxs-lookup"><span data-stu-id="245c1-120">Right-click the container, and then click **Properties**.</span></span>

4.  <span data-ttu-id="245c1-121">单击“安全”选项卡。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="245c1-121">Click the **Security** tab.</span></span>

5.  <span data-ttu-id="245c1-122">单击“**高级**”。</span><span class="sxs-lookup"><span data-stu-id="245c1-122">Click **Advanced**.</span></span>

6.  <span data-ttu-id="245c1-123">在“**权限**”选项卡上，单击“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="245c1-123">On the **Permissions** tab, click **Add**.</span></span>

7.  <span data-ttu-id="245c1-124">使用以下格式键入接收权限的用户或组的名称： `domain\account name` ，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="245c1-124">Type the name of the user or group receiving permissions by using the following format: `domain\account name`, and then click **OK**.</span></span>

8.  <span data-ttu-id="245c1-125">在 " **对象** " 选项卡上的 " **应用**于" 中，单击 " **仅此对象**"。</span><span class="sxs-lookup"><span data-stu-id="245c1-125">On the **Objects** tab, in **Applies To**, click **This Object Only**.</span></span>

9.  <span data-ttu-id="245c1-126">在 " **权限**" 中，通过单击 " **允许** 列： **列表内容**"、" **读取所有属性**" 和 " **读取权限**"，选择以下允许 ace。</span><span class="sxs-lookup"><span data-stu-id="245c1-126">In **Permissions**, select the following Allow ACEs by clicking the **Allow** column: **List Content**, **Read All Properties**, and **Read Permissions**.</span></span>

10. <span data-ttu-id="245c1-127">单击“**确定**”两次。</span><span class="sxs-lookup"><span data-stu-id="245c1-127">Click **OK** twice.</span></span>

11. <span data-ttu-id="245c1-128">对步骤2中列出的任何相关容器重复这些步骤。</span><span class="sxs-lookup"><span data-stu-id="245c1-128">Repeat these steps for any of the relevant containers listed in Step 2.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

