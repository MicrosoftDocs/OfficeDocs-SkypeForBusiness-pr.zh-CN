---
title: Lync Server 2010 的中介服务设置扩展器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.MediationServiceSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 230e0a08-9e16-4bbd-b550-1f04bad8ddbc
description: 通过定义以下属性编辑中介服务的属性：
ms.openlocfilehash: d5f46fb269925ace53a317caec4d9b75b3c4bbe4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819564"
---
# <a name="mediation-service-settings-expander-for-lync-server-2010"></a><span data-ttu-id="13536-103">Lync Server 2010 的中介服务设置扩展器</span><span class="sxs-lookup"><span data-stu-id="13536-103">Mediation Service Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="13536-104">通过定义以下属性编辑中介服务的属性：</span><span class="sxs-lookup"><span data-stu-id="13536-104">You edit the properties of the Mediation service by defining the following properties:</span></span>
  
- <span data-ttu-id="13536-p101">**侦听端口**：定义中介服务将侦听的 **TLS** 端口。默认情况下，该端口值为使用传输层安全性 (TLS) 的 TCP 5067</span><span class="sxs-lookup"><span data-stu-id="13536-p101">**Listening ports**: Define the **TLS** port that the Mediation service will listen on. By default, the port value is TCP 5067 over transport layer security (TLS)</span></span>
    
    <span data-ttu-id="13536-p102">或者，定义一个 **TCP** 端口值。默认情况下，该值为 TCP 5068。</span><span class="sxs-lookup"><span data-stu-id="13536-p102">Optionally, you define a **TCP** port value. By default, the value is TCP 5068.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="13536-p103">可通过选择“**启用 TCP 端口**”来启用 TCP 端口值设置。有关与中介服务通信所需的端口设置要求，请参阅公用电话交换网 (PSTN) 网关或 Internet 协议专用交换机 (IP-PBX) 的相关文档。</span><span class="sxs-lookup"><span data-stu-id="13536-p103">The TCP port value setting is enabled by selecting **Enable TCP port**. You should refer to the documentation for your Public Switched Telephone Network (PSTN) Gateway or Internet Protocol Private Branch Exchange (IP-PBX) for the requirements for the port settings required to communicate with the Mediation service.</span></span> 
  
- <span data-ttu-id="13536-111">“**启用 TCP 端口**”定义来自 PSTN 网关或 IP-PBX 的 TCP 通信的端口值。</span><span class="sxs-lookup"><span data-stu-id="13536-111">You **Enable TCP port** to define the port value for TCP communications from your PSTN gateway or IP-PBX.</span></span>
    
- <span data-ttu-id="13536-112">当前关联的和现有的“**中继**”（即会话初始协议 (SIP) 中继）、“**网关**”（PSTN 网关或 IP-PBX）和“**站点**”（针对中继和网关配置的站点）的列表。</span><span class="sxs-lookup"><span data-stu-id="13536-112">A listing of currently associated and existing **Trunk** (that is, Session Initiation Protocol (SIP) Trunks), **Gateway** (PSTN gateway or IP-PBX) and **Site** (configured site for the trunk and gateway).</span></span>
    
- <span data-ttu-id="13536-p104">选择一个中继、网关和站点并单击“**设为默认值**”以将选择设置为此中介服务的默认值。选择当前的默认值并单击“**取消设为默认值**”以取消将选择设置为当前默认值。然后选择一个新的默认值并单击“**设为默认值**”。</span><span class="sxs-lookup"><span data-stu-id="13536-p104">You select a Trunk, Gateway and Site and click **Make Default** to set the selection as the default for this Mediation service. You select the current default and click **Unmake Default** to remove the selection as the current default. You then select a new default and click **Make Default**.</span></span>
    
  <span data-ttu-id="13536-116">**确定** 接受更改并通过对话框提交更改。</span><span class="sxs-lookup"><span data-stu-id="13536-116">**OK** Accepts and commits changes to the dialog.</span></span>
  
  <span data-ttu-id="13536-117">**取消** 放弃更改并关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="13536-117">**Cancel** Discards changes and closes the dialog.</span></span>
  
  <span data-ttu-id="13536-118">**帮助** 显示此帮助屏幕。</span><span class="sxs-lookup"><span data-stu-id="13536-118">**Help** Displays this help screen.</span></span>
  

