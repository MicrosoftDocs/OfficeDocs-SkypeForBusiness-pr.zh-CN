---
title: Lync Server 2013：运行综合事务
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running synthetic transactions
ms:assetid: 2b56c7bd-8956-4fa1-8232-1876b959b258
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720911(v=OCS.15)
ms:contentKeyID: 63969593
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 297e1ee6416fb534791a2459e10acaa87f86e205
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511089"
---
# <a name="running-synthetic-transactions-in-lync-server-2013"></a><span data-ttu-id="b462f-102">在 Lync Server 2013 中运行综合事务</span><span class="sxs-lookup"><span data-stu-id="b462f-102">Running synthetic transactions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b462f-103">_**上次修改的主题：** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="b462f-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="b462f-104">通常通过两种方式执行综合事务。</span><span class="sxs-lookup"><span data-stu-id="b462f-104">Synthetic transactions are typically conducted in two ways.</span></span> <span data-ttu-id="b462f-105">您可以使用 CsHealthMonitoringConfiguration cmdlet 为每个注册器池设置测试用户。</span><span class="sxs-lookup"><span data-stu-id="b462f-105">You can use the CsHealthMonitoringConfiguration cmdlets to set up test users for each of their Registrar pools.</span></span> <span data-ttu-id="b462f-106">这些测试用户是已预配置为与综合事务一起使用的一对用户。</span><span class="sxs-lookup"><span data-stu-id="b462f-106">These test users are a pair of users who were preconfigured for use with synthetic transactions.</span></span> <span data-ttu-id="b462f-107"> (通常是测试帐户，而不是属于实际用户的帐户。 ) 在配置了池的测试用户的情况下，可以对该池运行综合事务，而无需指定 (的标识，并提供用于) 测试中所涉及的用户帐户的凭据。</span><span class="sxs-lookup"><span data-stu-id="b462f-107">(Typically these are test accounts and not accounts that belong to actual users.) With test users configured for a pool, you can run a synthetic transaction against that pool without having to specify the identities of (and supply the credentials for) the user accounts involved in the test.</span></span>

<span data-ttu-id="b462f-108">或者，您可以使用实际用户帐户运行综合事务。</span><span class="sxs-lookup"><span data-stu-id="b462f-108">Or, you can run a synthetic transaction by using actual user accounts.</span></span> <span data-ttu-id="b462f-109">例如，如果两个用户不能交换即时消息，则可以使用这两个用户帐户运行一个综合事务 (而不是一对测试帐户) ，然后尝试诊断并解决该问题。</span><span class="sxs-lookup"><span data-stu-id="b462f-109">For example, if two users cannot exchange instant messages, you could run a synthetic transaction using those two user accounts (instead of a pair of test accounts), and then try to diagnose and resolve the issue.</span></span> <span data-ttu-id="b462f-110">如果您决定使用实际用户帐户执行综合事务，则必须为每个用户提供登录名和密码。</span><span class="sxs-lookup"><span data-stu-id="b462f-110">If you decide to conduct a synthetic transaction using actual user accounts, you must supply the logon names and passwords for each user.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="b462f-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b462f-111">See Also</span></span>


[<span data-ttu-id="b462f-112">在 Lync Server 2013 中配置观察程序节点测试用户和配置设置</span><span class="sxs-lookup"><span data-stu-id="b462f-112">Configuring watcher node test users and configuration settings in Lync Server 2013</span></span>](lync-server-2013-configuring-watcher-node-test-users-and-configuration-settings.md)  
[<span data-ttu-id="b462f-113">Lync Server 2013 中的综合事务的特殊设置说明</span><span class="sxs-lookup"><span data-stu-id="b462f-113">Special setup instructions for synthetic transactions in Lync Server 2013</span></span>](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

