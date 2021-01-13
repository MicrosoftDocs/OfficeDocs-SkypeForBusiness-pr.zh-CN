---
title: 将前端与 AV MCU 关联
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AssociateFrontEndWithAvMcuPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 314e3b0b-9ca7-423b-9c8e-80eb6013d36f
description: A/V 会议在用户间启用实时音频和视频通信（前提是用户有相应的客户端设备，如用于音频会议的耳麦和用于视频会议的网络摄像机）。 如果您的部署支持会议并且您启用了 Web 会议和 A/V 会议，则可以将 A/V 会议服务器与前端服务器并置，或部署一个或多个独立的 A/V 会议服务器（A/V 会议池）。 如果选择部署独立 A/V 会议服务器的选项，则必须在拓扑生成器中定义它。
ms.openlocfilehash: 247212a163535b6e8ab0124a68d95c938a6160da
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818492"
---
# <a name="associate-front-end-with-av-mcu"></a><span data-ttu-id="71333-105">将前端与 AV MCU 关联</span><span class="sxs-lookup"><span data-stu-id="71333-105">Associate Front End With AV MCU</span></span>
 
<span data-ttu-id="71333-106">A/V 会议在用户间启用实时音频和视频通信（前提是用户有相应的客户端设备，如用于音频会议的耳麦和用于视频会议的网络摄像机）。</span><span class="sxs-lookup"><span data-stu-id="71333-106">A/V Conferencing enables real-time audio and video communications between your users (that is, if they have appropriate client devices, such as headsets for audio conferences, and webcams for video conferences).</span></span> <span data-ttu-id="71333-107">如果您的部署支持会议并且您启用了 Web 会议和 A/V 会议，则可以将 A/V 会议服务器与前端服务器并置，或部署一个或多个独立的 A/V 会议服务器（A/V 会议池）。</span><span class="sxs-lookup"><span data-stu-id="71333-107">If your deployment supports conferencing and you enable both web conferencing and A/V Conferencing, you can collocate the A/V Conferencing Server with the Front End Server), or you can deploy one or more stand-alone A/V Conferencing Servers (A/V Conferencing pool).</span></span> <span data-ttu-id="71333-108">如果选择部署独立 A/V 会议服务器的选项，则必须在拓扑生成器中定义它。</span><span class="sxs-lookup"><span data-stu-id="71333-108">If you choose the option to deploy a stand-alone A/V Conferencing Server, you must define it in Topology Builder.</span></span>
  
<span data-ttu-id="71333-109">站点的所有池和多个中央站点的池可以使用同一个 A/V 会议服务器（如果使用率不超过 A/V 会议服务器的容量）。</span><span class="sxs-lookup"><span data-stu-id="71333-109">All pools at a site and the pools of multiple central sites can use the same A/V Conferencing Server, if usage does not exceed the capacity of the A/V Conferencing Server.</span></span> 
  

