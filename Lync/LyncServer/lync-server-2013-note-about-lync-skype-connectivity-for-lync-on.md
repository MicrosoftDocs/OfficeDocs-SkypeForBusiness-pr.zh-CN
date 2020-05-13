---
title: Lync Server 2013：有关 lync 的 Lync-Skype 连接的说明
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Note about Lync-Skype connectivity for Lync On
ms:assetid: 1d0f5c1a-74c6-468f-9877-ad2b1ddf355f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440169(v=OCS.15)
ms:contentKeyID: 57793359
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8535c2a3d4f3d5f1cae8ec443283c1a3db8c8c45
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221546"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="note-about-lync-skype-connectivity-in-lync-server-2013-for-lync-online-customers"></a><span data-ttu-id="dbaed-102">有关 lync Online 客户的 Lync Server 2013 中的 Lync-Skype 连接说明</span><span class="sxs-lookup"><span data-stu-id="dbaed-102">Note about Lync-Skype connectivity in Lync Server 2013 for Lync Online customers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dbaed-103">_**上次修改的主题：** 2013-09-23_</span><span class="sxs-lookup"><span data-stu-id="dbaed-103">_**Topic Last Modified:** 2013-09-23_</span></span>

<span data-ttu-id="dbaed-104">本文档旨在帮助 Lync Server 本地管理员设置 Lync-Skype 连接。</span><span class="sxs-lookup"><span data-stu-id="dbaed-104">This document was written to help Lync Server on-premise administrators set up Lync-Skype connectivity.</span></span><span data-ttu-id="dbaed-105">Lync-Skype 连接也是 Lync Online 的一项功能，它是 Office 365 和 Microsoft 365 的一部分。</span><span class="sxs-lookup"><span data-stu-id="dbaed-105">  Lync-Skype connectivity is also a feature of Lync Online, which is part of Office 365 and Microsoft 365.</span></span> <span data-ttu-id="dbaed-106">您可以从管理中心内的 Lync 管理中心启用 Lync-Skype 连接功能。</span><span class="sxs-lookup"><span data-stu-id="dbaed-106">You can enable the Lync-Skype connectivity feature from the Lync Administration Center within the admin center.</span></span>

<span data-ttu-id="dbaed-107">对于 Microsoft 365 中型企业版、Office 365 企业版、Microsoft 365 教育版和 Office 365 for 政府版：登录 Office 365 门户或 Microsoft 365 管理中心，导航到**Lync 管理中心**。</span><span class="sxs-lookup"><span data-stu-id="dbaed-107">For Microsoft 365 Midsize Business, Office 365 Enterprise, Microsoft 365 Education, and Office 365 for Government: Sign in to the Office 365 portal or Microsoft 365 admin center and navigate to the **Lync Administration Center**.</span></span> <span data-ttu-id="dbaed-108">转到 "**外部通信**"。</span><span class="sxs-lookup"><span data-stu-id="dbaed-108">Go to **External Communications**.</span></span> <span data-ttu-id="dbaed-109">在 "**公共 IM 服务提供商**" 下，单击 "**启用**"。</span><span class="sxs-lookup"><span data-stu-id="dbaed-109">Under **Public IM Service Providers**, click **Enable**.</span></span> <span data-ttu-id="dbaed-110">如果要控制单个用户对 Lync-Skype 连接的访问权限，您可以通过编辑单个用户的外部通信设置来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="dbaed-110">If you want to control individual user access to Lync-Skype Connectivity, you can do so by editing individual users’ External Communications settings.</span></span>

<span data-ttu-id="dbaed-111">对于 Microsoft 365 小型企业高级版：登录到 Microsoft 365，然后转到 "**管理 \> 服务设置 \> 即时消息、会议和会议"**。</span><span class="sxs-lookup"><span data-stu-id="dbaed-111">For Microsoft 365 Small Business Premium: Sign in to Microsoft 365, and go to **Admin \> Service Settings \> Instant messaging, meetings and conferencing**.</span></span> <span data-ttu-id="dbaed-112">打开外部通信。</span><span class="sxs-lookup"><span data-stu-id="dbaed-112">Turn on External communications.</span></span> <span data-ttu-id="dbaed-113">外部通信开关同时打开 Lync Skype 连接和与使用 Lync 的其他组织的通信。</span><span class="sxs-lookup"><span data-stu-id="dbaed-113">The External communications switch turns on both Lync-Skype connectivity and communications with other organizations that use Lync.</span></span> <span data-ttu-id="dbaed-114">根据开始使用 Lync Online 的时间，处于 "打开" 状态的外部通信开关可能最初仅指示与其他 Lync 组织的通信处于激活状态。</span><span class="sxs-lookup"><span data-stu-id="dbaed-114">Depending on when you started using Lync Online, the External communications switch in an "on" state may initially indicate only that communications with other Lync organizations is activated.</span></span> <span data-ttu-id="dbaed-115">若要打开 Lync-Skype 连接，只需关闭交换机，然后再重新打开即可。</span><span class="sxs-lookup"><span data-stu-id="dbaed-115">To turn on Lync-Skype Connectivity, simply toggle the switch off and then back on again.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

