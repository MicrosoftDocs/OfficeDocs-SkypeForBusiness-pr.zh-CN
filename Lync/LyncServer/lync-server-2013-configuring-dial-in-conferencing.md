---
title: Lync Server 2013：配置拨入式会议
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring dial-in conferencing
ms:assetid: 79a98c5d-a0a8-4729-828d-b9166842432c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398600(v=OCS.15)
ms:contentKeyID: 48184587
ms.date: 10/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ca8b82fe77e578f1ac513d00583c42dd56162a1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837262"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="ae691-102">在 Lync Server 2013 中配置拨入式会议</span><span class="sxs-lookup"><span data-stu-id="ae691-102">Configuring dial-in conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ae691-103">_**主题上次修改时间:** 2014-10-03_</span><span class="sxs-lookup"><span data-stu-id="ae691-103">_**Topic Last Modified:** 2014-10-03_</span></span>

<span data-ttu-id="ae691-104">本部分将指导你完成 Lync Server 2013 拨入式会议的配置。</span><span class="sxs-lookup"><span data-stu-id="ae691-104">This section guides you through the configuration of Lync Server 2013 dial-in conferencing.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ae691-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="ae691-105">In This Section</span></span>

  - [<span data-ttu-id="ae691-106">Lync Server 2013 中电话拨入式会议配置的先决条件和权限</span><span class="sxs-lookup"><span data-stu-id="ae691-106">Dial-in conferencing configuration prerequisites and permissions in Lync Server 2013</span></span>](lync-server-2013-dial-in-conferencing-configuration-prerequisites-and-permissions.md)

  - [<span data-ttu-id="ae691-107">Lync Server 2013 中的电话拨入式会议的部署清单</span><span class="sxs-lookup"><span data-stu-id="ae691-107">Deployment checklist for dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-dial-in-conferencing.md)

  - [<span data-ttu-id="ae691-108">在 Lync Server 2013 中配置电话拨入式会议的拨号计划</span><span class="sxs-lookup"><span data-stu-id="ae691-108">Configure dial plans for dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md)

  - [<span data-ttu-id="ae691-109">确保拨号计划 Lync Server 2013 已分配区域</span><span class="sxs-lookup"><span data-stu-id="ae691-109">Make sure dial plans Lync Server 2013 have assigned regions</span></span>](lync-server-2013-make-sure-dial-plans-have-assigned-regions.md)

  - [<span data-ttu-id="ae691-110">（可选）在 Lync Server 2013 中验证 PIN 策略设置</span><span class="sxs-lookup"><span data-stu-id="ae691-110">(Optional) Verify PIN policy settings in Lync Server 2013</span></span>](lync-server-2013-optional-verify-pin-policy-settings.md)

  - [<span data-ttu-id="ae691-111">在 Lync Server 2013 中配置电话拨入式会议策略</span><span class="sxs-lookup"><span data-stu-id="ae691-111">Configure conferencing policy for dial-in in Lync Server 2013</span></span>](lync-server-2013-configure-conferencing-policy-for-dial-in.md)

  - [<span data-ttu-id="ae691-112">在 Lync Server 2013 中配置电话拨入式会议访问号码</span><span class="sxs-lookup"><span data-stu-id="ae691-112">Configure dial-in conferencing access numbers in Lync Server 2013</span></span>](lync-server-2013-configure-dial-in-conferencing-access-numbers.md)

  - [<span data-ttu-id="ae691-113">（可选）在 Lync Server 2013 中验证电话拨入式会议设置</span><span class="sxs-lookup"><span data-stu-id="ae691-113">(Optional) Verify dial-in conferencing settings in Lync Server 2013</span></span>](lync-server-2013-optional-verify-dial-in-conferencing-settings.md)

  - [<span data-ttu-id="ae691-114">（可选）在 Lync Server 2013 中修改 DTMF 命令的键映射</span><span class="sxs-lookup"><span data-stu-id="ae691-114">(Optional) Modify key mapping for DTMF commands in Lync Server 2013</span></span>](lync-server-2013-optional-modify-key-mapping-for-dtmf-commands.md)

  - [<span data-ttu-id="ae691-115">（可选）在 Lync Server 2013 中启用和禁用会议加入和离开通知</span><span class="sxs-lookup"><span data-stu-id="ae691-115">(Optional) Enable and disable conference join and leave announcements in Lync Server 2013</span></span>](lync-server-2013-optional-enable-and-disable-conference-join-and-leave-announcements.md)

  - [<span data-ttu-id="ae691-116">（可选）在 Lync Server 2013 中验证电话拨入式会议</span><span class="sxs-lookup"><span data-stu-id="ae691-116">(Optional) Verify dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-optional-verify-dial-in-conferencing.md)

  - [<span data-ttu-id="ae691-117">部署 Lync 2013 的联机会议加载项</span><span class="sxs-lookup"><span data-stu-id="ae691-117">Deploy the Online Meeting Add-in for Lync 2013</span></span>](lync-server-2013-deploy-the-online-meeting-add-in-for-lync-2013.md)

  - [<span data-ttu-id="ae691-118">在 Lync Server 2013 中配置用户帐户设置</span><span class="sxs-lookup"><span data-stu-id="ae691-118">Configure user account settings in Lync Server 2013</span></span>](lync-server-2013-configure-user-account-settings.md)

  - [<span data-ttu-id="ae691-119">(Recommended) Create Conference Directories</span><span class="sxs-lookup"><span data-stu-id="ae691-119">(Recommended) Create Conference Directories</span></span>](recommended-create-conference-directories.md)

  - [<span data-ttu-id="ae691-120">（可选）在 Lync Server 2013 中欢迎用户参加电话拨入式会议</span><span class="sxs-lookup"><span data-stu-id="ae691-120">(Optional) Welcome users to dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-optional-welcome-users-to-dial-in-conferencing.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="ae691-121">相关部分</span><span class="sxs-lookup"><span data-stu-id="ae691-121">Related Sections</span></span>

[<span data-ttu-id="ae691-122">部署 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ae691-122">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

