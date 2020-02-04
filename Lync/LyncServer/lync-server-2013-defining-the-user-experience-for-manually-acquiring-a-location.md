---
title: 定义手动获取位置的用户体验
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining the user experience for manually acquiring a location
ms:assetid: d37f67d3-e248-483b-b64c-3986559ef357
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398912(v=OCS.15)
ms:contentKeyID: 48185435
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46b5913547ab7d5030ca40070de36b4deb1f6a89
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728322"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-the-user-experience-for-manually-acquiring-a-location-in-lync-server-2013"></a><span data-ttu-id="a5776-102">定义在 Lync Server 2013 中手动获取位置的用户体验</span><span class="sxs-lookup"><span data-stu-id="a5776-102">Defining the user experience for manually acquiring a location in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a5776-103">_**主题上次修改时间：** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="a5776-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="a5776-p101">如果某个客户端位于网络外部或未定义的子网中，则用户可手动输入一个位置。但在紧急呼叫期间，呼叫将首先路由到国家/地区 E9-1-1 紧急呼叫响应中心 (ECRC) 调度程序，然后再路由到公共安全应答点 (PSAP)。ECRC 将口头询问呼叫者的位置，然后根据提供的信息将呼叫转接给相应的 PSAP。</span><span class="sxs-lookup"><span data-stu-id="a5776-p101">If a client is located outside the network, or in an undefined subnet, the user can manually enter a location. But during an emergency call, the call will first be routed to a national/regional E9-1-1 Emergency Call Response Center (ECRC) dispatcher before being routed to a Public Safety Answering Point (PSAP). The ECRC will verbally query the caller for a location and then forward the call to the appropriate PSAP, based on the information provided.</span></span>

  - <span data-ttu-id="a5776-107">**如果用户不是位置信息服务自动提供的位置，是否应提示用户输入一个位置？**</span><span class="sxs-lookup"><span data-stu-id="a5776-107">**Should users be prompted to enter a location when one is not automatically provided by the Location Information service?**</span></span>  
    <span data-ttu-id="a5776-108">例如，如果客户端位于未定义子网中、家中、酒店中或网络外的任何其他地方，是否应要求用户输入位置？</span><span class="sxs-lookup"><span data-stu-id="a5776-108">For example, if a client is located in an undefined subnet, at home, in a hotel, or anywhere else outside the network, should the user be required to enter a location?</span></span>
    
    <span data-ttu-id="a5776-p102">可以在位置策略中配置“**所需位置**”设置，从而定义客户端行为。将该值设为“否”表示不会提示用户输入位置。将该值设为“是”表示将提示用户输入位置，但可以消除提示。将该值设为“免责声明”表示将提示用户输入位置，并在用户试图消除提示时显示免责声明。在所有情况下，用户均可以像往常一样继续使用客户端。</span><span class="sxs-lookup"><span data-stu-id="a5776-p102">You can configure the **Location Required** setting in the location policy to define the client behavior. Setting this value to No means that the user will not be prompted for a location. Setting this value to Yes means that the user will be prompted for a location, but can dismiss the prompt. Setting this value to Disclaimer means that the user will be prompted for a location, and will be shown a disclaimer if they try to dismiss the prompt. In all cases, the user can continue to use the client as usual.</span></span>

<span data-ttu-id="a5776-114">当用户手动输入一个位置时，会将该位置映射到客户端网络的默认网关的 MAC 地址，并将其存储到位于客户端上的每用户表中。</span><span class="sxs-lookup"><span data-stu-id="a5776-114">When a user manually enters a location, the location is mapped to the MAC address of the default gateway of the client’s network, and is stored in a per-user table located on the client.</span></span> <span data-ttu-id="a5776-115">当用户返回到任何以前存储的位置时，Lync 客户端会自动将自己设置到该位置。</span><span class="sxs-lookup"><span data-stu-id="a5776-115">When the user returns to any previously stored location, the Lync client automatically sets itself to that location.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="a5776-116">虽然只能修改客户端的当前位置，但还可以删除本地用户表中存储的任何位置。</span><span class="sxs-lookup"><span data-stu-id="a5776-116">You can modify only the current location of your client, but you can also delete any location stored in the local user’s table.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

