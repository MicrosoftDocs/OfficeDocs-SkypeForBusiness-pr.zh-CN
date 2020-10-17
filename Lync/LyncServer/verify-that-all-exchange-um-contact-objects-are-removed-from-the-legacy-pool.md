---
title: 验证是否已从旧版池中删除所有 Exchange UM 联系人对象
description: 验证是否已从旧版池中删除所有 Exchange UM 联系人对象。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify that all Exchange UM Contact objects are removed from the legacy pool
ms:assetid: 5a813169-0ed7-4f84-a242-ed2cd4ea5c43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688068(v=OCS.15)
ms:contentKeyID: 49733664
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8af5dea6cf746c55d8fecf074e132f721c380de1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555508"
---
# <a name="verify-that-all-exchange-um-contact-objects-are-removed-from-the-legacy-pool"></a><span data-ttu-id="083f1-103">验证是否已从旧版池中删除所有 Exchange UM 联系人对象</span><span class="sxs-lookup"><span data-stu-id="083f1-103">Verify that all Exchange UM Contact objects are removed from the legacy pool</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="083f1-104">_**上次修改的主题：** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="083f1-104">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="083f1-105">使用 **ocsumutil.exe** 工具或 **CsExumContact** cmdlet 验证 Exchange UM contact 对象是否已从旧版 Office 通信服务器 2007 R2 池中删除。</span><span class="sxs-lookup"><span data-stu-id="083f1-105">Use either the **OCSUmUtil** tool or the **Get-CsExumContact** cmdlet to verify that Exchange UM contact objects have been removed from the legacy Office Communications Server 2007 R2 pool.</span></span> <span data-ttu-id="083f1-106">**OCSUmUtil** 位于以下文件夹中：</span><span class="sxs-lookup"><span data-stu-id="083f1-106">**OCSUmUtil** is located in the following folder:</span></span>

<span data-ttu-id="083f1-107">% Program Files% \\ 常用文件 \\ Lync Server 2013 \\ 支持 \\OcsUMUtil.exe</span><span class="sxs-lookup"><span data-stu-id="083f1-107">%Program Files%\\Common Files\\Lync Server 2013\\Support\\OcsUMUtil.exe</span></span>

<span data-ttu-id="083f1-108">**OCSUmUtil** 必须从具有以下权限的用户帐户运行：</span><span class="sxs-lookup"><span data-stu-id="083f1-108">**OCSUmUtil** must be run from a user account that has:</span></span>

  - <span data-ttu-id="083f1-109">RTCUniversalServerAdmins 和 RTCUniversalUserAdmins 组中的成员身份（包括读取 Exchange Server 统一消息设置的权限）</span><span class="sxs-lookup"><span data-stu-id="083f1-109">Membership in the RTCUniversalServerAdmins and RTCUniversalUserAdmins group (which includes rights to read Exchange Server Unified Messaging settings)</span></span>

  - <span data-ttu-id="083f1-110">在指定的组织单位 (OU) 容器中创建联系对象的域权限</span><span class="sxs-lookup"><span data-stu-id="083f1-110">Domain rights to create contact objects in the specified organizational unit (OU) container</span></span>

<span data-ttu-id="083f1-111">有关使用 **CsExumContact** cmdlet 的详细信息，请参阅 Lync Server 命令行管理程序文档中的 [CsExumContact](https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact) 。</span><span class="sxs-lookup"><span data-stu-id="083f1-111">For details about using the **Get-CsExumContact** cmdlet, see [Get-CsExUmContact](https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact) in the Lync Server Management Shell documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

