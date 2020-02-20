---
title: Lync Server 2013：分支站点恢复功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Branch-site resiliency features
ms:assetid: 8e3feda5-9a38-4e3c-b808-af29f19c5eb9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398715(v=OCS.15)
ms:contentKeyID: 48184765
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5787f0fd07afcf0ca70a9c3b0f7c21e3525cfae7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150721"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="branch-site-resiliency-features-in-lync-server-2013"></a><span data-ttu-id="ea09e-102">Lync Server 2013 中的分支站点恢复功能</span><span class="sxs-lookup"><span data-stu-id="ea09e-102">Branch-site resiliency features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ea09e-103">_**上次修改的主题：** 2014-02-10_</span><span class="sxs-lookup"><span data-stu-id="ea09e-103">_**Topic Last Modified:** 2014-02-10_</span></span>

<span data-ttu-id="ea09e-104">如果提供分支站点恢复能力，当分支站点到中央站点的 WAN 连接出现故障，或者当中央站点无法访问时，以下语音功能应该仍然可用：</span><span class="sxs-lookup"><span data-stu-id="ea09e-104">If you provide branch-site resiliency, if a branch site’s WAN connection to a central site fails or if the central site is unreachable, the following voice features should continue to be available:</span></span>

<div>


  - <span data-ttu-id="ea09e-105">入站和出站公用电话交换网 (PSTN) 呼叫</span><span class="sxs-lookup"><span data-stu-id="ea09e-105">Inbound and outbound public switched telephone network (PSTN) calls</span></span>

  - <span data-ttu-id="ea09e-106">同一站点的用户间和两个不同站点的用户间的企业呼叫</span><span class="sxs-lookup"><span data-stu-id="ea09e-106">Enterprise calls between users at both the same site and between two different sites</span></span>

  - <span data-ttu-id="ea09e-107">基本呼叫处理功能（包括呼叫保持、取回和转接）</span><span class="sxs-lookup"><span data-stu-id="ea09e-107">Basic call handling, including call hold, retrieval, and transfer</span></span>

  - <span data-ttu-id="ea09e-108">双方即时消息</span><span class="sxs-lookup"><span data-stu-id="ea09e-108">Two-party instant messaging</span></span>

  - <span data-ttu-id="ea09e-109">呼叫转接、终结点同时响铃、呼叫委派和团队呼叫服务，但前提是在同一站点配置代理程序和代理人（例如，经理和经理的管理员）或所有团队成员</span><span class="sxs-lookup"><span data-stu-id="ea09e-109">Call forwarding, simultaneous ringing of endpoints, call delegation, and team call services, but only if the delegator and delegate (for example, a manager and the manager’s administrator), or all team members, are configured at the same site</span></span>

  - <span data-ttu-id="ea09e-110">呼叫详细信息记录 (CDR)</span><span class="sxs-lookup"><span data-stu-id="ea09e-110">Call detail records (CDRs)</span></span>

  - <span data-ttu-id="ea09e-111">使用会议自动助理的 PSTN 电话拨入式会议</span><span class="sxs-lookup"><span data-stu-id="ea09e-111">PSTN dial-in conferencing with Conferencing Auto-Attendant</span></span>

  - <span data-ttu-id="ea09e-112">语音邮件功能（如果配置了语音邮件重新路由设置）。</span><span class="sxs-lookup"><span data-stu-id="ea09e-112">Voice mail capabilities, if you configure voice mail rerouting settings.</span></span> <span data-ttu-id="ea09e-113">（有关详细信息，请参阅[Lync Server 2013 的分支站点恢复要求](lync-server-2013-branch-site-resiliency-requirements.md)。）</span><span class="sxs-lookup"><span data-stu-id="ea09e-113">(For details, see [Branch-site resiliency requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).)</span></span>

  - <span data-ttu-id="ea09e-114">用户身份验证和授权</span><span class="sxs-lookup"><span data-stu-id="ea09e-114">User authentication and authorization</span></span>

<span data-ttu-id="ea09e-115">仅当您的恢复解决方案是分支站点的完全规模的 Lync 服务器部署时，以下功能才可用：</span><span class="sxs-lookup"><span data-stu-id="ea09e-115">The following features will be available only if your resiliency solution is a full-scale Lync Server deployment at the branch site:</span></span>

  - <span data-ttu-id="ea09e-116">IM、Web 会议和 A/V 会议</span><span class="sxs-lookup"><span data-stu-id="ea09e-116">IM, web, and A/V conferencing</span></span>

  - <span data-ttu-id="ea09e-117">基于状态和请勿打扰 (DND) 的路由（其中将阻止呼叫在已激活 DND 的分机上响铃）</span><span class="sxs-lookup"><span data-stu-id="ea09e-117">Presence and Do Not Disturb (DND)-based routing (where calls are prevented from ringing on extensions that have DND activated)</span></span>

  - <span data-ttu-id="ea09e-118">更新呼叫转接设置</span><span class="sxs-lookup"><span data-stu-id="ea09e-118">Updating call forwarding settings</span></span>

  - <span data-ttu-id="ea09e-119">响应组应用程序和呼叫寄存应用程序</span><span class="sxs-lookup"><span data-stu-id="ea09e-119">Response Group application and Call Park application</span></span>

  - <span data-ttu-id="ea09e-120">设置新的电话和客户端，但仅在分支站点上存在 Active Directory 域服务时。</span><span class="sxs-lookup"><span data-stu-id="ea09e-120">Provisioning new phones and clients, but only if Active Directory Domain Services is present at the branch site.</span></span>

  - <span data-ttu-id="ea09e-121">增强型 9-1-1 (E9-1-1)</span><span class="sxs-lookup"><span data-stu-id="ea09e-121">Enhanced 9-1-1 (E9-1-1)</span></span>
    
    <span data-ttu-id="ea09e-122">如果已部署 E9-1-1，并且中心站点上的 SIP 中继因 WAN 链路断开而不可用，则 Survivable 分支设备会将 E9-1-1 呼叫路由到本地分支网关。</span><span class="sxs-lookup"><span data-stu-id="ea09e-122">If E9-1-1 is deployed, and the SIP trunk at the central site is not available because the WAN link is down, then the Survivable Branch Appliance will route E9-1-1 calls to the local branch gateway.</span></span> <span data-ttu-id="ea09e-123">要启用该功能，分支站点用户的语音策略应在 WAN 出现故障时将呼叫路由到本地网关。</span><span class="sxs-lookup"><span data-stu-id="ea09e-123">To enable this feature, the branch-site users’ voice policies should route calls to the local gateway in the event of WAN failure.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ea09e-124">XMPP 不支持 SBA （survivable branch office）。</span><span class="sxs-lookup"><span data-stu-id="ea09e-124">SBA (survivable branch office) is not supported for XMPP.</span></span> <span data-ttu-id="ea09e-125">驻留在 SBA 配置中的用户将无法使用 XMPP 联系人发送即时消息或查看状态。</span><span class="sxs-lookup"><span data-stu-id="ea09e-125">Users homed in a SBA configurations will not be able to send IMs or see Presence with XMPP contacts.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

