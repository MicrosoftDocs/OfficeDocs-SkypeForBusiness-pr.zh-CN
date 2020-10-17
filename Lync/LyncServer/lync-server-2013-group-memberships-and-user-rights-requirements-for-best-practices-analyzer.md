---
title: 最佳实践分析工具的组成员身份和用户权限要求
description: 最佳实践分析工具的组成员身份和用户权限要求。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Group memberships and user rights requirements for Best Practices Analyzer
ms:assetid: f812e343-8f75-454e-b7a8-1b404e32071a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591354(v=OCS.15)
ms:contentKeyID: 48185869
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 64a7d785a77701c6796488178a7cce10caf54f42
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564188"
---
# <a name="group-memberships-and-user-rights-requirements-for-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="2ee29-103">Lync Server 2013 中最佳实践分析工具的组成员身份和用户权限要求</span><span class="sxs-lookup"><span data-stu-id="2ee29-103">Group memberships and user rights requirements for Best Practices Analyzer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2ee29-104">_**上次修改的主题：** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="2ee29-104">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="2ee29-p101">要成功运行最佳做法分析器，您用于登录的用户帐户必须是本地计算机上 Administrators 组的成员。另外，要扫描您的环境，用户帐户必须是下列组的成员：</span><span class="sxs-lookup"><span data-stu-id="2ee29-p101">To successfully run Best Practices Analyzer, the user account that you use to log on must be a member of the Administrators group on the local computer. Additionally, to scan your environment, the user account must be a member of the following groups:</span></span>

  - <span data-ttu-id="2ee29-107">**域管理员**    若要枚举 Active Directory 域服务信息，并在域控制器和全局编录服务器上 (WMI) 提供程序调用 Windows Management Instrumentation。</span><span class="sxs-lookup"><span data-stu-id="2ee29-107">**Domain Admins**   To enumerate Active Directory Domain Services information and to call the Windows Management Instrumentation (WMI) providers on domain controllers and global catalog servers.</span></span>

  - <span data-ttu-id="2ee29-108">**管理员**    每个 Lync Server 2013 内部计算机和每台边缘服务器都需要调用 Windows Management Instrumentation (WMI) 提供程序，并访问注册表。</span><span class="sxs-lookup"><span data-stu-id="2ee29-108">**Administrators**   Required on each Lync Server 2013 internal computer and each Edge Server to call the Windows Management Instrumentation (WMI) providers and to access the registry.</span></span>

  - <span data-ttu-id="2ee29-109">**RTCUniversalReadOnlyAdmins**    完全或委派的只读 Lync Server 2013 管理权限。</span><span class="sxs-lookup"><span data-stu-id="2ee29-109">**RTCUniversalReadOnlyAdmins**   Full or delegated read only Lync Server 2013 administrative rights.</span></span>

  - <span data-ttu-id="2ee29-110">**Exchange 仅查看管理员**    Microsoft Exchange 组织上的 "完全" 或 "委派 Exchange" 仅查看管理员。</span><span class="sxs-lookup"><span data-stu-id="2ee29-110">**Exchange View Only Administrator**   Full or delegated Exchange View Only Administrator on the Microsoft Exchange organization.</span></span>

<span data-ttu-id="2ee29-111">如果您的用户帐户没有充分的用户权限，则您有两个选项：</span><span class="sxs-lookup"><span data-stu-id="2ee29-111">If your user account does not have sufficient user rights, you have two options:</span></span>

  - <span data-ttu-id="2ee29-112">在命令提示符下，使用 **runas** 命令在具有充分用户权限的帐户下运行该工具。</span><span class="sxs-lookup"><span data-stu-id="2ee29-112">At a command prompt, use the **runas** command to run the tool under an account that does have sufficient user rights.</span></span> <span data-ttu-id="2ee29-113">语法如下所示：</span><span class="sxs-lookup"><span data-stu-id="2ee29-113">The syntax is as follows:</span></span>
    
        runas /netonly /user:<domain>\<userName> rtcbpa.exe

  - <span data-ttu-id="2ee29-114">在“连接到 Active Directory”\*\*\*\* 页面上，为您计划用于运行最佳做法分析器的帐户设置凭据。</span><span class="sxs-lookup"><span data-stu-id="2ee29-114">On the **Connect to Active Directory** page, set the credentials for the accounts that you plan to use to run Best Practices Analyzer.</span></span> <span data-ttu-id="2ee29-115">单击“显示高级登录选项”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2ee29-115">Click **Show advanced login options**.</span></span> <span data-ttu-id="2ee29-116">您可以输入三个帐户：一个用于连接到 Active Directory 域服务，一个用于连接到 Lync Server 2013 边缘服务器，另一个用于连接到 Exchange 服务器。</span><span class="sxs-lookup"><span data-stu-id="2ee29-116">You can enter three accounts: one for connecting to Active Directory Domain Services, one for connecting to Lync Server 2013 Edge Servers, and one for connecting to the Exchange Servers.</span></span> <span data-ttu-id="2ee29-117">如果您不指定这些任何帐户，则使用用于登录和运行最佳做法分析器的帐户。</span><span class="sxs-lookup"><span data-stu-id="2ee29-117">If you do not specify any of these accounts, the user account that you used to log on and run Best Practices Analyzer is used.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

