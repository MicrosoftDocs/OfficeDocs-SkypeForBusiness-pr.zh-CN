---
title: Lync Server 2013：配置电话拨入式会议
description: Lync Server 2013：配置电话拨入式会议。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring dial-in conferencing
ms:assetid: 79a98c5d-a0a8-4729-828d-b9166842432c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398600(v=OCS.15)
ms:contentKeyID: 48184587
ms.date: 10/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9c3353caa1344b717b0f64c271149f078f194e5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557938"
---
# <a name="configuring-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="e1df5-103">在 Lync Server 2013 中配置电话拨入式会议</span><span class="sxs-lookup"><span data-stu-id="e1df5-103">Configuring dial-in conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e1df5-104">_**上次修改的主题：** 2014-10-03_</span><span class="sxs-lookup"><span data-stu-id="e1df5-104">_**Topic Last Modified:** 2014-10-03_</span></span>

<span data-ttu-id="e1df5-105">本部分将指导您完成 Lync Server 2013 电话拨入式会议的配置。</span><span class="sxs-lookup"><span data-stu-id="e1df5-105">This section guides you through the configuration of Lync Server 2013 dial-in conferencing.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e1df5-106">本部分内容</span><span class="sxs-lookup"><span data-stu-id="e1df5-106">In This Section</span></span>

  - [<span data-ttu-id="e1df5-107">Lync Server 2013 中的电话拨入式会议配置先决条件和权限</span><span class="sxs-lookup"><span data-stu-id="e1df5-107">Dial-in conferencing configuration prerequisites and permissions in Lync Server 2013</span></span>](lync-server-2013-dial-in-conferencing-configuration-prerequisites-and-permissions.md)

  - [<span data-ttu-id="e1df5-108">Lync Server 2013 中的电话拨入式会议的部署清单</span><span class="sxs-lookup"><span data-stu-id="e1df5-108">Deployment checklist for dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-dial-in-conferencing.md)

  - [<span data-ttu-id="e1df5-109">在 Lync Server 2013 中配置电话拨入式会议的拨号计划</span><span class="sxs-lookup"><span data-stu-id="e1df5-109">Configure dial plans for dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md)

  - [<span data-ttu-id="e1df5-110">确保拨号计划 Lync Server 2013 已分配区域</span><span class="sxs-lookup"><span data-stu-id="e1df5-110">Make sure dial plans Lync Server 2013 have assigned regions</span></span>](lync-server-2013-make-sure-dial-plans-have-assigned-regions.md)

  - [<span data-ttu-id="e1df5-111"> (可选) 在 Lync Server 2013 中验证 PIN 策略设置</span><span class="sxs-lookup"><span data-stu-id="e1df5-111">(Optional) Verify PIN policy settings in Lync Server 2013</span></span>](lync-server-2013-optional-verify-pin-policy-settings.md)

  - [<span data-ttu-id="e1df5-112">在 Lync Server 2013 中配置电话拨入式会议策略</span><span class="sxs-lookup"><span data-stu-id="e1df5-112">Configure conferencing policy for dial-in in Lync Server 2013</span></span>](lync-server-2013-configure-conferencing-policy-for-dial-in.md)

  - [<span data-ttu-id="e1df5-113">在 Lync Server 2013 中配置电话拨入式会议访问号码</span><span class="sxs-lookup"><span data-stu-id="e1df5-113">Configure dial-in conferencing access numbers in Lync Server 2013</span></span>](lync-server-2013-configure-dial-in-conferencing-access-numbers.md)

  - [<span data-ttu-id="e1df5-114"> (可选) 在 Lync Server 2013 中验证电话拨入式会议设置</span><span class="sxs-lookup"><span data-stu-id="e1df5-114">(Optional) Verify dial-in conferencing settings in Lync Server 2013</span></span>](lync-server-2013-optional-verify-dial-in-conferencing-settings.md)

  - [<span data-ttu-id="e1df5-115"> (可选) 在 Lync Server 2013 中修改 DTMF 命令的键映射</span><span class="sxs-lookup"><span data-stu-id="e1df5-115">(Optional) Modify key mapping for DTMF commands in Lync Server 2013</span></span>](lync-server-2013-optional-modify-key-mapping-for-dtmf-commands.md)

  - [<span data-ttu-id="e1df5-116"> (可选) 在 Lync Server 2013 中启用和禁用会议加入和离开通知</span><span class="sxs-lookup"><span data-stu-id="e1df5-116">(Optional) Enable and disable conference join and leave announcements in Lync Server 2013</span></span>](lync-server-2013-optional-enable-and-disable-conference-join-and-leave-announcements.md)

  - [<span data-ttu-id="e1df5-117"> (可选) 在 Lync Server 2013 中验证电话拨入式会议</span><span class="sxs-lookup"><span data-stu-id="e1df5-117">(Optional) Verify dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-optional-verify-dial-in-conferencing.md)

  - [<span data-ttu-id="e1df5-118">部署 Lync 2013 的联机会议加载项</span><span class="sxs-lookup"><span data-stu-id="e1df5-118">Deploy the Online Meeting Add-in for Lync 2013</span></span>](lync-server-2013-deploy-the-online-meeting-add-in-for-lync-2013.md)

  - [<span data-ttu-id="e1df5-119">在 Lync Server 2013 中配置用户帐户设置</span><span class="sxs-lookup"><span data-stu-id="e1df5-119">Configure user account settings in Lync Server 2013</span></span>](lync-server-2013-configure-user-account-settings.md)

  - [<span data-ttu-id="e1df5-120"> (建议) 创建会议目录</span><span class="sxs-lookup"><span data-stu-id="e1df5-120">(Recommended) Create Conference Directories</span></span>](recommended-create-conference-directories.md)

  - [<span data-ttu-id="e1df5-121"> 在 Lync Server 2013 中 (欢迎用户加入电话拨入式会议的可选) </span><span class="sxs-lookup"><span data-stu-id="e1df5-121">(Optional) Welcome users to dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-optional-welcome-users-to-dial-in-conferencing.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="e1df5-122">相关部分</span><span class="sxs-lookup"><span data-stu-id="e1df5-122">Related Sections</span></span>

[<span data-ttu-id="e1df5-123">部署 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e1df5-123">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

