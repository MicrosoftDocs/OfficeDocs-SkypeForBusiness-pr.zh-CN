---
title: 查看 Skype for Business 服务器中单个 SIP 中继的相关信息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 在 Skype for Business 服务器中, 可以将多个中继分配给单个 PSTN 网关;这意味着网关和中继不是同一个, 并且管理员必须使用 CsTrunk cmdlet 查看有关单个 SIP 主干的信息。
ms.openlocfilehash: f9199936dd4c9580c95c8b9708df04dcac13e1e8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274875"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a><span data-ttu-id="811c9-103">查看 Skype for Business 服务器中单个 SIP 中继的相关信息</span><span class="sxs-lookup"><span data-stu-id="811c9-103">View information about individual SIP trunks in Skype for Business Server</span></span>

<span data-ttu-id="811c9-104">在 Skype for Business 服务器中, 可以将多个中继分配给单个 PSTN 网关;这意味着网关和中继不是同一个, 并且管理员必须使用[CsTrunk](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunk) cmdlet 查看有关单个 SIP 主干的信息。</span><span class="sxs-lookup"><span data-stu-id="811c9-104">In Skype for Business Server, multiple trunks can be assigned to a single PSTN gateway; this means that gateways and trunks are not one and the same, and that administrators must use the [Get-CsTrunk](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunk) cmdlet to view information about an individual SIP trunk.</span></span>

<span data-ttu-id="811c9-105">CsTrunk cmdlet 既可以从 Skype for Business 服务器管理外壳运行, 也可以从 Windows PowerShell 的远程会话运行。</span><span class="sxs-lookup"><span data-stu-id="811c9-105">The Get-CsTrunk cmdlet can be run either from the  Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span>

<span data-ttu-id="811c9-106">**查看所有 SIP 中继的信息**</span><span class="sxs-lookup"><span data-stu-id="811c9-106">**To view information for all your SIP trunks**</span></span>

<span data-ttu-id="811c9-107">以下命令会返回有关您的组织中使用的所有 SIP 中继的信息：</span><span class="sxs-lookup"><span data-stu-id="811c9-107">The following command returns information about all the SIP trunks in use in your organization:</span></span>

`Get-CsTrunk`

<span data-ttu-id="811c9-108">**查看特定 SIP 中继的信息**</span><span class="sxs-lookup"><span data-stu-id="811c9-108">**To view information for a specific SIP trunk**</span></span>

<span data-ttu-id="811c9-109">此命令仅会返回 Identity 为 PstnGateway:192.168.0.240 的 SIP 中继的信息：</span><span class="sxs-lookup"><span data-stu-id="811c9-109">This command returns information only for the SIP trunk with the Identity PstnGateway:192.168.0.240:</span></span>

`Get-CsTrunk -Identity "PstnGateway:192.168.0.240"`

<span data-ttu-id="811c9-110">**查看分配到池的所有 SIP 中继的信息**</span><span class="sxs-lookup"><span data-stu-id="811c9-110">**Viewing Information for All the SIP Trunks Assigned to a Pool**</span></span>

<span data-ttu-id="811c9-111">在此示例中，将返回分配给池 atl-cs-001.litwareinc.com 的所有 SIP 中继的信息：</span><span class="sxs-lookup"><span data-stu-id="811c9-111">In this example, information is returned for all the SIP trunks assigned to the pool atl-cs-001.litwareinc.com:</span></span>

`Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"`
