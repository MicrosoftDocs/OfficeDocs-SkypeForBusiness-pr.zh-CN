---
title: 配置电话拨入式会议个人识别号（PIN）规则
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure dial-in conferencing personal identification number (PIN) rules
ms:assetid: 27b79fb1-e2dc-4f71-bc82-b6eb61be2b16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520967(v=OCS.15)
ms:contentKeyID: 48183668
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6aef41f14b37d2a21fa747bb14132bd6e9ba93ad
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735002"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dial-in-conferencing-personal-identification-number-pin-rules-in-lync-server-2013"></a><span data-ttu-id="bc431-102">在 Lync Server 2013 中配置电话拨入式会议个人识别号（PIN）规则</span><span class="sxs-lookup"><span data-stu-id="bc431-102">Configure dial-in conferencing personal identification number (PIN) rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bc431-103">_**主题上次修改时间：** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="bc431-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="bc431-104">在你的组织中拥有 Active Directory 域服务（AD DS）凭据的 Lync Server 2013 用户可以使用个人识别码（PIN）将电话拨入式会议作为已验证用户加入电话拨入式会议。</span><span class="sxs-lookup"><span data-stu-id="bc431-104">Lync Server 2013 users who have Active Directory Domain Services (AD DS) credentials in your organization can join dial-in conferences as authenticated users by using a personal identification number (PIN).</span></span> <span data-ttu-id="bc431-105">PIN 策略定义电话拨入式会议 PIN 工作方式的规则。</span><span class="sxs-lookup"><span data-stu-id="bc431-105">PIN policy defines the rules for how dial-in conferencing PINs work.</span></span>

<span data-ttu-id="bc431-106">如果要将特定策略应用于某个站点或某个用户组，可以创建新的 PIN 策略。</span><span class="sxs-lookup"><span data-stu-id="bc431-106">You can create a new PIN policy if you want a specific policy to apply to a site or to a certain group of users.</span></span> <span data-ttu-id="bc431-107">如果要在整个组织中使用相同的 PIN 策略，则可以使用全局 PIN 策略并根据需要对其进行修改。</span><span class="sxs-lookup"><span data-stu-id="bc431-107">If you want to use the same PIN policy for your entire organization, you can use the global PIN policy and modify it as needed.</span></span> <span data-ttu-id="bc431-108">PIN 策略既可以应用于少数用户，也可以应用于众多用户。</span><span class="sxs-lookup"><span data-stu-id="bc431-108">PIN policies apply to users from the narrowest scope to the widest scope.</span></span> <span data-ttu-id="bc431-109">如果为用户分配用户级别的 PIN 策略，则优先应用这些设置。</span><span class="sxs-lookup"><span data-stu-id="bc431-109">If you assign a user-level PIN policy to a user, those settings take precedence.</span></span> <span data-ttu-id="bc431-110">如果没有分配用户策略，则将应用站点级别的 PIN 策略（如果存在）。</span><span class="sxs-lookup"><span data-stu-id="bc431-110">If you do not assign a user policy, the site-level PIN policy applies, if it exists.</span></span> <span data-ttu-id="bc431-111">如果未应用用户策略或站点策略，则全局 PIN 策略会提供默认设置。</span><span class="sxs-lookup"><span data-stu-id="bc431-111">If no user or site policies apply, global PIN policy provides the default settings.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="bc431-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="bc431-112">In This Section</span></span>

  - [<span data-ttu-id="bc431-113">在 Lync Server 2013 中修改默认电话拨入式会议 PIN 设置</span><span class="sxs-lookup"><span data-stu-id="bc431-113">Modify the default dial-in conferencing PIN settings in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-dial-in-conferencing-pin-settings.md)

  - [<span data-ttu-id="bc431-114">在 Lync Server 2013 中创建或修改站点或用户组的电话拨入式会议 PIN 设置</span><span class="sxs-lookup"><span data-stu-id="bc431-114">Create or modify dial-in conferencing PIN settings in Lync Server 2013 for a site or group of users</span></span>](lync-server-2013-create-or-modify-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md)

  - [<span data-ttu-id="bc431-115">在 Lync Server 2013 中删除一个网站或一组用户的电话拨入式会议 PIN 设置</span><span class="sxs-lookup"><span data-stu-id="bc431-115">Delete dial-in conferencing PIN settings for a site or group of users in Lync Server 2013</span></span>](lync-server-2013-delete-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

