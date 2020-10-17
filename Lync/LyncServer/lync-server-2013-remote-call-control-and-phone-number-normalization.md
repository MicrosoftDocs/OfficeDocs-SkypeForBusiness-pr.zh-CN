---
title: Lync Server 2013：远程呼叫控制和电话号码规范化
description: Lync Server 2013：远程呼叫控制和电话号码规范化。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remote call control and phone number normalization
ms:assetid: 291d9e87-4c65-4ea2-888f-517741391de5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558630(v=OCS.15)
ms:contentKeyID: 48183696
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: edcb50678da7111aba066745bce5e356dd1ac7f3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555808"
---
# <a name="remote-call-control-and-phone-number-normalization-in-lync-server-2013"></a><span data-ttu-id="307b3-103">Lync Server 2013 中的远程呼叫控制和电话号码规范化</span><span class="sxs-lookup"><span data-stu-id="307b3-103">Remote call control and phone number normalization in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="307b3-104">_**上次修改的主题：** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="307b3-104">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="307b3-105">Lync 客户端会在通讯簿服务 (ABS) 文件下载中下载电话号码规范化规则。</span><span class="sxs-lookup"><span data-stu-id="307b3-105">Lync clients download phone number normalization rules as part of the Address Book Service (ABS) file download.</span></span> <span data-ttu-id="307b3-106">在远程呼叫控制方案中，通讯簿服务电话号码规范化规则同时适用于传入和传出远程呼叫控制呼叫。</span><span class="sxs-lookup"><span data-stu-id="307b3-106">In remote call control scenarios, Address Book Service phone number normalization rules are applied to both incoming and outgoing remote call control calls.</span></span> <span data-ttu-id="307b3-107">对于对启用了远程呼叫控制的用户的传入呼叫，呼叫者的电话号码首先通过 SIP/CSTA 网关或专用交换机 (PBX) 规范化为 E.164 格式。</span><span class="sxs-lookup"><span data-stu-id="307b3-107">For incoming calls to a remote call control-enabled user, the phone number of the caller is first normalized to E.164 format by either the SIP/CSTA gateway or private branch exchange (PBX).</span></span> <span data-ttu-id="307b3-108">当 Lync Server 2013 从网关接收呼叫时，将对呼叫者的电话号码执行反向号码查找 (RNL) 对呼叫者的 Microsoft Office Outlook 联系人列表中的规范化号码或存储在通讯簿服务中的全局地址列表 (GAL) 。</span><span class="sxs-lookup"><span data-stu-id="307b3-108">When Lync Server 2013 receives the call from the gateway, it performs reverse number lookup (RNL) on the phone number of the caller against the normalized number in the callee’s Microsoft Office Outlook Contacts list or the global address list (GAL) that is stored in the Address Book Service.</span></span> <span data-ttu-id="307b3-109">如果反向号码查找成功找到了匹配项，则通过传入呼叫通知中的名称来识别呼叫者。</span><span class="sxs-lookup"><span data-stu-id="307b3-109">If reverse number lookup successfully finds a match, the caller is identified by name in the incoming call notification.</span></span>

<span data-ttu-id="307b3-110">对于传出远程呼叫控制呼叫，Lync 会在将呼叫路由到 SIP/CSTA 网关之前，将通讯簿服务电话号码规范化规则应用于所拨打的号码。</span><span class="sxs-lookup"><span data-stu-id="307b3-110">For outgoing remote call control calls, Lync applies the Address Book Service phone number normalization rules to the dialed number before routing the call to the SIP/CSTA gateway.</span></span>

<span data-ttu-id="307b3-111">有关为远程呼叫控制创建电话号码规范化规则的详细信息，请参阅规划文档中的 [Lync Server 2013 中的拨号计划和规范化规则](lync-server-2013-dial-plans-and-normalization-rules.md) 。</span><span class="sxs-lookup"><span data-stu-id="307b3-111">For details about creating phone number normalization rules for remote call control, see [Dial plans and normalization rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) in the Planning documentation.</span></span>

<div>

## <a name="migrating-phone-number-normalization-rules"></a><span data-ttu-id="307b3-112">迁移电话号码规范化规则</span><span class="sxs-lookup"><span data-stu-id="307b3-112">Migrating Phone Number Normalization Rules</span></span>

<span data-ttu-id="307b3-113">如果要迁移以前启用了远程呼叫控制的用户，请参阅迁移文档中的以下主题：</span><span class="sxs-lookup"><span data-stu-id="307b3-113">If you are migrating users previously enabled for remote call control, see the following topics in the Migration documentation:</span></span>

  - <span data-ttu-id="307b3-114">对于 Lync Server 2010，请参阅迁移文档中的 [迁移通讯簿](migrate-address-book.md) 。</span><span class="sxs-lookup"><span data-stu-id="307b3-114">For Lync Server 2010, see [Migrate Address Book](migrate-address-book.md) in the Migration documentation.</span></span>

  - <span data-ttu-id="307b3-115">有关通信服务器 2007 R2 的详细说明，请参阅迁移文档中的 [迁移通讯簿](migrate-address-book.md) 。</span><span class="sxs-lookup"><span data-stu-id="307b3-115">For Communications Server 2007 R2, see [Migrate Address Book](migrate-address-book.md) in the Migration documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

