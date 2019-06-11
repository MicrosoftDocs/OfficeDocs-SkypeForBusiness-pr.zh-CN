---
title: 验证是否已从旧版池中删除所有 Exchange UM 联系人对象
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Verify that all Exchange UM Contact objects are removed from the legacy pool
ms:assetid: 5a813169-0ed7-4f84-a242-ed2cd4ea5c43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688068(v=OCS.15)
ms:contentKeyID: 49733664
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0db8f4c55d863221c9a66d33a21bbe073bbc225a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845069"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-that-all-exchange-um-contact-objects-are-removed-from-the-legacy-pool"></a><span data-ttu-id="01a31-102">验证是否已从旧版池中删除所有 Exchange UM 联系人对象</span><span class="sxs-lookup"><span data-stu-id="01a31-102">Verify that all Exchange UM Contact objects are removed from the legacy pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="01a31-103">_**主题上次修改时间:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="01a31-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="01a31-104">使用**OCSUmUtil**工具或**CsExumContact** cmdlet 验证 Exchange UM 联系人对象是否已从旧版 Office 通信服务器 2007 R2 池中删除。</span><span class="sxs-lookup"><span data-stu-id="01a31-104">Use either the **OCSUmUtil** tool or the **Get-CsExumContact** cmdlet to verify that Exchange UM contact objects have been removed from the legacy Office Communications Server 2007 R2 pool.</span></span> <span data-ttu-id="01a31-105">**OCSUmUtil**位于以下文件夹中:</span><span class="sxs-lookup"><span data-stu-id="01a31-105">**OCSUmUtil** is located in the following folder:</span></span>

<span data-ttu-id="01a31-106">% 程序文件%\\常用文件\\% Lync Server\\2013\\支持 OcsUMUtil</span><span class="sxs-lookup"><span data-stu-id="01a31-106">%Program Files%\\Common Files\\Lync Server 2013\\Support\\OcsUMUtil.exe</span></span>

<span data-ttu-id="01a31-107">**OCSUmUtil**必须从具有以下内容的用户帐户运行:</span><span class="sxs-lookup"><span data-stu-id="01a31-107">**OCSUmUtil** must be run from a user account that has:</span></span>

  - <span data-ttu-id="01a31-108">RTCUniversalServerAdmins 和 RTCUniversalUserAdmins 组中的成员身份 (包括读取 Exchange Server 统一消息设置的权限)</span><span class="sxs-lookup"><span data-stu-id="01a31-108">Membership in the RTCUniversalServerAdmins and RTCUniversalUserAdmins group (which includes rights to read Exchange Server Unified Messaging settings)</span></span>

  - <span data-ttu-id="01a31-109">在指定的组织单位 (OU) 容器中创建联系人对象的域权限</span><span class="sxs-lookup"><span data-stu-id="01a31-109">Domain rights to create contact objects in the specified organizational unit (OU) container</span></span>

<span data-ttu-id="01a31-110">有关使用**CsExumContact** cmdlet 的详细信息, 请参阅 Lync Server Management Shell 文档中的[CsExumContact](https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact) 。</span><span class="sxs-lookup"><span data-stu-id="01a31-110">For details about using the **Get-CsExumContact** cmdlet, see [Get-CsExUmContact](https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact) in the Lync Server Management Shell documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

