---
title: Lync Server 2013：远程呼叫控制和电话号码规范化
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
ms.openlocfilehash: 6eff9fb48e9730549d67638c69d8655d8f04d710
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724372"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remote-call-control-and-phone-number-normalization-in-lync-server-2013"></a><span data-ttu-id="e81de-102">Lync Server 2013 中的远程呼叫控制和电话号码规范化</span><span class="sxs-lookup"><span data-stu-id="e81de-102">Remote call control and phone number normalization in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e81de-103">_**主题上次修改时间：** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="e81de-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="e81de-104">Lync 客户端会下载电话号码规范化规则，作为通讯簿服务（ABS）文件下载的一部分。</span><span class="sxs-lookup"><span data-stu-id="e81de-104">Lync clients download phone number normalization rules as part of the Address Book Service (ABS) file download.</span></span> <span data-ttu-id="e81de-105">在远程呼叫控制方案中，通讯簿服务电话号码规范化规则同时应用于传入和传出远程呼叫控制调用。</span><span class="sxs-lookup"><span data-stu-id="e81de-105">In remote call control scenarios, Address Book Service phone number normalization rules are applied to both incoming and outgoing remote call control calls.</span></span> <span data-ttu-id="e81de-106">对于启用了远程呼叫控制的用户的传入呼叫，呼叫方的电话号码首先通过 SIP/CSTA 网关或专用分支交换（PBX）规范化为 E-164 格式。</span><span class="sxs-lookup"><span data-stu-id="e81de-106">For incoming calls to a remote call control-enabled user, the phone number of the caller is first normalized to E.164 format by either the SIP/CSTA gateway or private branch exchange (PBX).</span></span> <span data-ttu-id="e81de-107">当 Lync Server 2013 从网关接收呼叫时，将对呼叫者的电话号码执行反向号码查找（RNL），对被呼叫者的 Microsoft Office Outlook 联系人列表或全局地址列表（GAL）中存储的标准化号码通讯簿服务。</span><span class="sxs-lookup"><span data-stu-id="e81de-107">When Lync Server 2013 receives the call from the gateway, it performs reverse number lookup (RNL) on the phone number of the caller against the normalized number in the callee’s Microsoft Office Outlook Contacts list or the global address list (GAL) that is stored in the Address Book Service.</span></span> <span data-ttu-id="e81de-108">如果 "反向号码查找" 成功找到匹配项，则呼叫者将按名称在传入呼叫通知中标识。</span><span class="sxs-lookup"><span data-stu-id="e81de-108">If reverse number lookup successfully finds a match, the caller is identified by name in the incoming call notification.</span></span>

<span data-ttu-id="e81de-109">对于传出的远程呼叫控制呼叫，在将呼叫路由到 SIP/CSTA 网关之前，Lync 会将通讯簿服务电话号码规范化规则应用到已拨打的号码。</span><span class="sxs-lookup"><span data-stu-id="e81de-109">For outgoing remote call control calls, Lync applies the Address Book Service phone number normalization rules to the dialed number before routing the call to the SIP/CSTA gateway.</span></span>

<span data-ttu-id="e81de-110">有关为远程呼叫控制创建电话号码规范化规则的详细信息，请参阅规划文档中的[Lync Server 2013 中的 "拨号计划和规范规则](lync-server-2013-dial-plans-and-normalization-rules.md)"。</span><span class="sxs-lookup"><span data-stu-id="e81de-110">For details about creating phone number normalization rules for remote call control, see [Dial plans and normalization rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) in the Planning documentation.</span></span>

<div>

## <a name="migrating-phone-number-normalization-rules"></a><span data-ttu-id="e81de-111">迁移电话号码规范化规则</span><span class="sxs-lookup"><span data-stu-id="e81de-111">Migrating Phone Number Normalization Rules</span></span>

<span data-ttu-id="e81de-112">如果你正在迁移以前为远程呼叫控制启用的用户，请参阅迁移文档中的以下主题：</span><span class="sxs-lookup"><span data-stu-id="e81de-112">If you are migrating users previously enabled for remote call control, see the following topics in the Migration documentation:</span></span>

  - <span data-ttu-id="e81de-113">对于 Lync Server 2010，请参阅迁移文档中的 "[迁移通讯簿](migrate-address-book.md)"。</span><span class="sxs-lookup"><span data-stu-id="e81de-113">For Lync Server 2010, see [Migrate Address Book](migrate-address-book.md) in the Migration documentation.</span></span>

  - <span data-ttu-id="e81de-114">有关通信服务器 2007 R2 的详细说明，请参阅迁移文档中的 "[迁移通讯簿](migrate-address-book_1.md)"。</span><span class="sxs-lookup"><span data-stu-id="e81de-114">For Communications Server 2007 R2, see [Migrate Address Book](migrate-address-book_1.md) in the Migration documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

