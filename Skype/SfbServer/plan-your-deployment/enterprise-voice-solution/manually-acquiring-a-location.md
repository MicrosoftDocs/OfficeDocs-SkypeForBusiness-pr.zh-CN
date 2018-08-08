---
title: 定义手动获取业务服务器的 Skype 中的位置的用户体验
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d37f67d3-e248-483b-b64c-3986559ef357
description: 规划漫游业务 Server 企业语音的 Skype 中使用 SIP 中继提供商，E9-1-1 部署中的用户。
ms.openlocfilehash: 0b439cc52a5724f5642bd8c61288cededefe754c
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20988477"
---
# <a name="define-the-user-experience-for-manually-acquiring-a-location-in-skype-for-business-server"></a><span data-ttu-id="6a822-103">定义手动获取业务服务器的 Skype 中的位置的用户体验</span><span class="sxs-lookup"><span data-stu-id="6a822-103">Define the user experience for manually acquiring a location in Skype for Business Server</span></span>
 
<span data-ttu-id="6a822-104">规划漫游业务 Server 企业语音的 Skype 中使用 SIP 中继提供商，E9-1-1 部署中的用户。</span><span class="sxs-lookup"><span data-stu-id="6a822-104">Planning for roaming users in an E9-1-1 deployment using SIP trunking providers, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="6a822-p101">如果某个客户端位于网络外部或未定义的子网中，则用户可手动输入一个位置。但在紧急呼叫期间，呼叫将首先路由到国家/地区 E9-1-1 紧急呼叫响应中心 (ECRC) 调度程序，然后再路由到公共安全应答点 (PSAP)。ECRC 将口头询问呼叫者的位置，然后根据提供的信息将呼叫转接给相应的 PSAP。</span><span class="sxs-lookup"><span data-stu-id="6a822-p101">If a client is located outside the network, or in an undefined subnet, the user can manually enter a location. But during an emergency call, the call will first be routed to a national/regional E9-1-1 Emergency Call Response Center (ECRC) dispatcher before being routed to a Public Safety Answering Point (PSAP). The ECRC will verbally query the caller for a location and then forward the call to the appropriate PSAP, based on the information provided.</span></span> 
  
<span data-ttu-id="6a822-108">**应提示用户输入位置时未自动提供位置信息服务？**</span><span class="sxs-lookup"><span data-stu-id="6a822-108">**Should users be prompted to enter a location when one is not automatically provided by the Location Information service?**</span></span>
  
<span data-ttu-id="6a822-109">例如，如果客户端位于未定义子网中、家中、酒店中或网络外的任何其他地方，是否应要求用户输入位置？</span><span class="sxs-lookup"><span data-stu-id="6a822-109">For example, if a client is located in an undefined subnet, at home, in a hotel, or anywhere else outside the network, should the user be required to enter a location?</span></span>
    
<span data-ttu-id="6a822-p102">可以在位置策略中配置“**所需位置**”设置，从而定义客户端行为。将该值设为“否”表示不会提示用户输入位置。将该值设为“是”表示将提示用户输入位置，但可以消除提示。将该值设为“免责声明”表示将提示用户输入位置，并在用户试图消除提示时显示免责声明。在所有情况下，用户均可以像往常一样继续使用客户端。</span><span class="sxs-lookup"><span data-stu-id="6a822-p102">You can configure the **Location Required** setting in the location policy to define the client behavior. Setting this value to No means that the user will not be prompted for a location. Setting this value to Yes means that the user will be prompted for a location, but can dismiss the prompt. Setting this value to Disclaimer means that the user will be prompted for a location, and will be shown a disclaimer if they try to dismiss the prompt. In all cases, the user can continue to use the client as usual.</span></span>
    
<span data-ttu-id="6a822-115">当用户手动输入位置时，位置映射到客户端的网络的默认网关的 MAC 地址和存储在客户端上位于每个用户表中。</span><span class="sxs-lookup"><span data-stu-id="6a822-115">When a user manually enters a location, the location is mapped to the MAC address of the default gateway of the client's network, and is stored in a per-user table located on the client.</span></span> <span data-ttu-id="6a822-116">当用户返回到以前存储的任何位置时，业务客户端 Skype 自动将自身设置为该位置。</span><span class="sxs-lookup"><span data-stu-id="6a822-116">When the user returns to any previously stored location, the Skype for Business client automatically sets itself to that location.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="6a822-117">您可以修改仅您的客户端的当前位置，但您也可以删除本地用户表中存储的任何位置。</span><span class="sxs-lookup"><span data-stu-id="6a822-117">You can modify only the current location of your client, but you can also delete any location stored in the local user's table.</span></span> 
  

