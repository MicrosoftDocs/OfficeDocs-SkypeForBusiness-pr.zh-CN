---
title: 验证是否已从旧版池中删除所有 Exchange UM 联系人对象
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify that all Exchange UM Contact objects are removed from the legacy pool
ms:assetid: 5a813169-0ed7-4f84-a242-ed2cd4ea5c43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688068(v=OCS.15)
ms:contentKeyID: 49733664
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 72e18e63dbbc5b64ca61baf9c5635717fc7f3fff
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147835"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-that-all-exchange-um-contact-objects-are-removed-from-the-legacy-pool"></a><span data-ttu-id="a1ac2-102">验证是否已从旧版池中删除所有 Exchange UM 联系人对象</span><span class="sxs-lookup"><span data-stu-id="a1ac2-102">Verify that all Exchange UM Contact objects are removed from the legacy pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a1ac2-103">_**上次修改的主题：** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="a1ac2-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="a1ac2-104">使用**ocsumutil.exe**工具或**CsExumContact** cmdlet 验证 Exchange UM contact 对象是否已从旧版 Office 通信服务器 2007 R2 池中删除。</span><span class="sxs-lookup"><span data-stu-id="a1ac2-104">Use either the **OCSUmUtil** tool or the **Get-CsExumContact** cmdlet to verify that Exchange UM contact objects have been removed from the legacy Office Communications Server 2007 R2 pool.</span></span> <span data-ttu-id="a1ac2-105">**OCSUmUtil** 位于以下文件夹中：</span><span class="sxs-lookup"><span data-stu-id="a1ac2-105">**OCSUmUtil** is located in the following folder:</span></span>

<span data-ttu-id="a1ac2-106">% Program Files%\\常用文件\\Lync Server 2013\\支持\\ocsumutil.exe</span><span class="sxs-lookup"><span data-stu-id="a1ac2-106">%Program Files%\\Common Files\\Lync Server 2013\\Support\\OcsUMUtil.exe</span></span>

<span data-ttu-id="a1ac2-107">**OCSUmUtil** 必须从具有以下权限的用户帐户运行：</span><span class="sxs-lookup"><span data-stu-id="a1ac2-107">**OCSUmUtil** must be run from a user account that has:</span></span>

  - <span data-ttu-id="a1ac2-108">RTCUniversalServerAdmins 和 RTCUniversalUserAdmins 组中的成员身份（包括读取 Exchange Server 统一消息设置的权限）</span><span class="sxs-lookup"><span data-stu-id="a1ac2-108">Membership in the RTCUniversalServerAdmins and RTCUniversalUserAdmins group (which includes rights to read Exchange Server Unified Messaging settings)</span></span>

  - <span data-ttu-id="a1ac2-109">在指定的组织单位 (OU) 容器中创建联系对象的域权限</span><span class="sxs-lookup"><span data-stu-id="a1ac2-109">Domain rights to create contact objects in the specified organizational unit (OU) container</span></span>

<span data-ttu-id="a1ac2-110">有关使用**CsExumContact** cmdlet 的详细信息，请参阅 Lync Server 命令行管理程序文档中的[CsExumContact](https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact) 。</span><span class="sxs-lookup"><span data-stu-id="a1ac2-110">For details about using the **Get-CsExumContact** cmdlet, see [Get-CsExUmContact](https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact) in the Lync Server Management Shell documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

