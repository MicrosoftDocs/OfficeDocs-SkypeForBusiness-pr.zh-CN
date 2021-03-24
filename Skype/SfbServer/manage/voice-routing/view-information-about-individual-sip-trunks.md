---
title: 查看有关 Skype for Business Server 中单个 SIP 中继的信息
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 在 Skype for Business Server 中，可以将多个中继分配给一个 PSTN 网关;这意味着网关和中继不同，管理员必须使用 Get-CsTrunk cmdlet 查看有关单个 SIP 中继的信息。
ms.openlocfilehash: eebba2982a6f574ca2af99609f19ba5426139acb
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102998"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a><span data-ttu-id="74e7a-103">查看有关 Skype for Business Server 中单个 SIP 中继的信息</span><span class="sxs-lookup"><span data-stu-id="74e7a-103">View information about individual SIP trunks in Skype for Business Server</span></span>

<span data-ttu-id="74e7a-104">在 Skype for Business Server 中，可以将多个中继分配给一个 PSTN 网关;这意味着网关和中继不是一个相同的，并且管理员必须使用 [Get-CsTrunk](/powershell/module/skype/Get-CsTrunk) cmdlet 查看有关单个 SIP 中继的信息。</span><span class="sxs-lookup"><span data-stu-id="74e7a-104">In Skype for Business Server, multiple trunks can be assigned to a single PSTN gateway; this means that gateways and trunks are not one and the same, and that administrators must use the [Get-CsTrunk](/powershell/module/skype/Get-CsTrunk) cmdlet to view information about an individual SIP trunk.</span></span>

<span data-ttu-id="74e7a-105">该Get-CsTrunk cmdlet 可以从 Skype for Business Server 命令行管理程序或远程会话运行Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="74e7a-105">The Get-CsTrunk cmdlet can be run either from the  Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span>

<span data-ttu-id="74e7a-106">**查看所有 SIP 中继的信息**</span><span class="sxs-lookup"><span data-stu-id="74e7a-106">**To view information for all your SIP trunks**</span></span>

<span data-ttu-id="74e7a-107">以下命令返回有关组织使用的所有 SIP 中继的信息：</span><span class="sxs-lookup"><span data-stu-id="74e7a-107">The following command returns information about all the SIP trunks in use in your organization:</span></span>

`Get-CsTrunk`

<span data-ttu-id="74e7a-108">**查看特定 SIP 中继的信息**</span><span class="sxs-lookup"><span data-stu-id="74e7a-108">**To view information for a specific SIP trunk**</span></span>

<span data-ttu-id="74e7a-109">此命令仅返回标识为 PstnGateway：192.168.0.240 的 SIP 中继的信息：</span><span class="sxs-lookup"><span data-stu-id="74e7a-109">This command returns information only for the SIP trunk with the Identity PstnGateway:192.168.0.240:</span></span>

`Get-CsTrunk -Identity "PstnGateway:192.168.0.240"`

<span data-ttu-id="74e7a-110">**查看分配给池的所有 SIP 中继的信息**</span><span class="sxs-lookup"><span data-stu-id="74e7a-110">**Viewing Information for All the SIP Trunks Assigned to a Pool**</span></span>

<span data-ttu-id="74e7a-111">此示例返回分配给池池的所有 SIP 中继 atl-cs-001.litwareinc.com：</span><span class="sxs-lookup"><span data-stu-id="74e7a-111">In this example, information is returned for all the SIP trunks assigned to the pool atl-cs-001.litwareinc.com:</span></span>

`Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"`