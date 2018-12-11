---
title: 查看 Business server Skype 中的单个 SIP 中继的信息
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 在业务服务器 Skype，多个中继可以分配给单个 PSTN 网关;这意味着，网关和中继不是同一个，并且管理员必须使用 Get-cstrunk cmdlet 可以查看有关各个 SIP 中继的信息。
ms.openlocfilehash: c8463fb23ea09167d760a1b9068235da871792c2
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222791"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a><span data-ttu-id="8573c-103">查看 Business server Skype 中的单个 SIP 中继的信息</span><span class="sxs-lookup"><span data-stu-id="8573c-103">View information about individual SIP trunks in Skype for Business Server</span></span>

<span data-ttu-id="8573c-104">在业务服务器 Skype，多个中继可以分配给单个 PSTN 网关;这意味着网关和中继不是同一个，管理员必须使用[Get-cstrunk](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunk) cmdlet 可以查看有关各个 SIP 中继的信息。</span><span class="sxs-lookup"><span data-stu-id="8573c-104">In Skype for Business Server, multiple trunks can be assigned to a single PSTN gateway; this means that gateways and trunks are not one and the same, and that administrators must use the [Get-CsTrunk](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunk) cmdlet to view information about an individual SIP trunk.</span></span>

<span data-ttu-id="8573c-105">从业务 Server 命令行管理程序 Skype 或 Windows PowerShell 远程会话，则可以运行 Get-cstrunk cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8573c-105">The Get-CsTrunk cmdlet can be run either from the  Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span>

<span data-ttu-id="8573c-106">**查看所有 SIP 中继的信息**</span><span class="sxs-lookup"><span data-stu-id="8573c-106">**To view information for all your SIP trunks**</span></span>

<span data-ttu-id="8573c-107">以下命令会返回有关您的组织中使用的所有 SIP 中继的信息：</span><span class="sxs-lookup"><span data-stu-id="8573c-107">The following command returns information about all the SIP trunks in use in your organization:</span></span>

`Get-CsTrunk`

<span data-ttu-id="8573c-108">**查看特定 SIP 中继的信息**</span><span class="sxs-lookup"><span data-stu-id="8573c-108">**To view information for a specific SIP trunk**</span></span>

<span data-ttu-id="8573c-109">此命令仅会返回 Identity 为 PstnGateway:192.168.0.240 的 SIP 中继的信息：</span><span class="sxs-lookup"><span data-stu-id="8573c-109">This command returns information only for the SIP trunk with the Identity PstnGateway:192.168.0.240:</span></span>

`Get-CsTrunk -Identity "PstnGateway:192.168.0.240"`

<span data-ttu-id="8573c-110">**查看分配给池的所有 SIP 中继的信息**</span><span class="sxs-lookup"><span data-stu-id="8573c-110">**Viewing Information for All the SIP Trunks Assigned to a Pool**</span></span>

<span data-ttu-id="8573c-111">在此示例中，将返回分配给池 atl-cs-001.litwareinc.com 的所有 SIP 中继的信息：</span><span class="sxs-lookup"><span data-stu-id="8573c-111">In this example, information is returned for all the SIP trunks assigned to the pool atl-cs-001.litwareinc.com:</span></span>

`Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"`