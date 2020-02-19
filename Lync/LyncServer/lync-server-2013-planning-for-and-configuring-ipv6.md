---
title: Lync Server 2013：规划和配置 IPv6
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for and configuring IPv6
ms:assetid: 01f77196-38f4-4292-9480-2e2fbd57eabe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204624(v=OCS.15)
ms:contentKeyID: 48183236
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 478b2c52013dce5aeb655f6de37bd41aa91e0a7a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139935"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-and-configuring-ipv6-in-lync-server-2013"></a><span data-ttu-id="cf1e8-102">在 Lync Server 2013 中规划和配置 IPv6</span><span class="sxs-lookup"><span data-stu-id="cf1e8-102">Planning for and configuring IPv6 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cf1e8-103">_**上次修改的主题：** 2012-06-14_</span><span class="sxs-lookup"><span data-stu-id="cf1e8-103">_**Topic Last Modified:** 2012-06-14_</span></span>

<span data-ttu-id="cf1e8-104">Lync Server 2013 包括对 IP 版本6（IPv6）地址的支持，以及对 IP 版本4（IPv4）地址的连续支持。</span><span class="sxs-lookup"><span data-stu-id="cf1e8-104">Lync Server 2013 includes support for IP version 6 (IPv6) addresses, along with continued support of IP version 4 (IPv4) addresses.</span></span> <span data-ttu-id="cf1e8-105">IPv4 地址是 32 位地址，允许计算机通过 Internet 进行通信。</span><span class="sxs-lookup"><span data-stu-id="cf1e8-105">IPv4 addresses are 32-bit addresses that allow a computer to communicate over the Internet.</span></span> <span data-ttu-id="cf1e8-106">由于世界范围内的设备数量不断增加，可用的 IPv4 地址已用完。因此，许多新设备将移动到使用 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="cf1e8-106">Due to the increasing number of devices worldwide, the available IPv4 addresses have run out. Because of this, many new devices are moving to using IPv6 addresses.</span></span> <span data-ttu-id="cf1e8-107">IPv6 地址执行与 IPv4 地址相同的功能（另外还有一些附加功能），但 IPv6 地址不仅使用 32 位，而且还使用 128 位。</span><span class="sxs-lookup"><span data-stu-id="cf1e8-107">IPv6 addresses perform the same function as IPv4 addresses (with some additional features), but instead of using only 32-bits, IPv6 addresses use 128-bits.</span></span> <span data-ttu-id="cf1e8-108">这不仅提供了一组新的地址，而且数量远远超过原来的地址集。</span><span class="sxs-lookup"><span data-stu-id="cf1e8-108">This provides not only a new set of addresses, but also a much larger number of them.</span></span> <span data-ttu-id="cf1e8-109">传统 IPv4 地址看起来类似于：192.0.2.235，而 IPv6 地址看起来类似于：2001:0db8:85a3:0000:0000:8a2e:0370:7334。</span><span class="sxs-lookup"><span data-stu-id="cf1e8-109">A typical IPv4 address looks something like this: 192.0.2.235, whereas an IPv6 address looks like this: 2001:0db8:85a3:0000:0000:8a2e:0370:7334.</span></span> <span data-ttu-id="cf1e8-110">在使用 IPv6 地址的设备的格式和功能方面的更改需要在 Lync Server 2013 安装中进行几个部署和配置注意事项。</span><span class="sxs-lookup"><span data-stu-id="cf1e8-110">The change in formatting and functionality for devices that use IPv6 addresses requires several deployment and configuration considerations in your Lync Server 2013 installation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="cf1e8-111">本部分内容</span><span class="sxs-lookup"><span data-stu-id="cf1e8-111">In This Section</span></span>

  - [<span data-ttu-id="cf1e8-112">Lync Server 2013 的 IP 地址类型概述</span><span class="sxs-lookup"><span data-stu-id="cf1e8-112">Overview of IP address types for Lync Server 2013</span></span>](lync-server-2013-overview-of-ip-address-types.md)

  - [<span data-ttu-id="cf1e8-113">Lync Server 2013 中 IPv6 的技术要求</span><span class="sxs-lookup"><span data-stu-id="cf1e8-113">Technical requirements for IPv6 in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-ipv6.md)

  - [<span data-ttu-id="cf1e8-114">Lync Server 2013 中 IPv6 的迁移和共存注意事项</span><span class="sxs-lookup"><span data-stu-id="cf1e8-114">Migration and coexistence considerations for IPv6 in Lync Server 2013</span></span>](lync-server-2013-migration-and-coexistence-considerations-for-ipv6.md)

  - [<span data-ttu-id="cf1e8-115">在 Lync Server 2013 中配置 IP 地址类型</span><span class="sxs-lookup"><span data-stu-id="cf1e8-115">Configure IP address types in Lync Server 2013</span></span>](lync-server-2013-configure-ip-address-types.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

