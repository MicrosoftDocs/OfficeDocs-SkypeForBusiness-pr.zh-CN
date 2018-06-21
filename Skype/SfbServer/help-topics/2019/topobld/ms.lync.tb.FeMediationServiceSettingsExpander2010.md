---
title: Lync Server 2010 的前端中介服务设置扩展器
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.FeMediationServiceSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 37166b87-8a43-42a6-a2aa-5a45bed8a6f3
description: 编辑此对话框中的中介服务器 PSTN 网关设置的属性。 定义以下设置：
ms.openlocfilehash: 7343fb4e2876ffa23fa7d37a8669f9b0c25f428b
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/20/2018
ms.locfileid: "19979769"
---
# <a name="front-end-mediation-service-settings-expander-for-lync-server-2010"></a><span data-ttu-id="f2286-104">Lync Server 2010 的前端中介服务设置扩展器</span><span class="sxs-lookup"><span data-stu-id="f2286-104">Front End Mediation Service Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="f2286-105">编辑此对话框中的**中介服务器 PSTN 网关**设置的属性。</span><span class="sxs-lookup"><span data-stu-id="f2286-105">You edit the properties of the **Mediation Server PSTN gateway** settings in this dialog.</span></span> <span data-ttu-id="f2286-106">定义以下设置：</span><span class="sxs-lookup"><span data-stu-id="f2286-106">You define the following settings:</span></span>
  
- <span data-ttu-id="f2286-107">如果您想要将并置中介服务器与此前端服务器或前端池，请选择**并置中介服务器已启用**。</span><span class="sxs-lookup"><span data-stu-id="f2286-107">Select the **Collocated Mediation Server enabled** if you want to collocate the Mediation Server with this Front End Server or Front End pools.</span></span>
    
- <span data-ttu-id="f2286-108">**侦听端口**： 定义中介服务器将侦听的端口。</span><span class="sxs-lookup"><span data-stu-id="f2286-108">**Listening ports**: Define the ports that the Mediation Server will listen on.</span></span> <span data-ttu-id="f2286-109">您可以定义用于**TLS**或传输层安全性或**TCP**的端口或传输控制协议。</span><span class="sxs-lookup"><span data-stu-id="f2286-109">You can define a port for **TLS** or transport layer security, or **TCP**, or transport control protocol.</span></span> <span data-ttu-id="f2286-110">可用的 tcp 端口条目，您必须为**启用 TCP 端口**选择复选框。</span><span class="sxs-lookup"><span data-stu-id="f2286-110">For the port entry for TCP to be available, you must select the check box for **Enable TCP port**.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="f2286-111">请参阅确定如果您需要启用并定义端口值 TLS、 TCP 或同时公用电话交换网 (pstn) 网关的文档和配置设置。</span><span class="sxs-lookup"><span data-stu-id="f2286-111">Refer to the documentation and configuration settings for your public switched telephone network (PSTN) gateway to determine if you need to enable and define port values TLS, TCP or both.</span></span> <span data-ttu-id="f2286-112">TLS 是一种更安全协议证书用于对中介服务器和 PSTN 网关之间的通信进行加密。</span><span class="sxs-lookup"><span data-stu-id="f2286-112">TLS is a more secure protocol, using certificates to encrypt the traffic between the Mediation Server and the PSTN gateway.</span></span> <span data-ttu-id="f2286-113">并非所有 PSTN 网关都支持 TLS。</span><span class="sxs-lookup"><span data-stu-id="f2286-113">Not all PSTN gateways support TLS.</span></span> 
  
- <span data-ttu-id="f2286-114">当前关联的和现有的“**中继**”（即会话初始协议 (SIP) 中继）、“**网关**”（PSTN 网关或 IP-PBX）和“**站点**”（针对中继和网关配置的站点）的列表。</span><span class="sxs-lookup"><span data-stu-id="f2286-114">A listing of currently associated and existing **Trunk** (that is, Session Initiation Protocol (SIP) Trunks), **Gateway** (PSTN gateway or IP-PBX) and **Site** (configured site for the trunk and gateway).</span></span>
    
- <span data-ttu-id="f2286-p105">选择一个中继、网关和站点并单击“**设为默认值**”以将选择设置为此中介服务的默认值。选择当前的默认值并单击“**取消设为默认值**”以取消将选择设置为当前默认值。然后选择一个新的默认值并单击“**设为默认值**”。</span><span class="sxs-lookup"><span data-stu-id="f2286-p105">You select a Trunk, Gateway and Site and click **Make Default** to set the selection as the default for this Mediation service. You select the current default and click **Unmake Default** to remove the selection as the current default. You then select a new default and click **Make Default**.</span></span>
    
 <span data-ttu-id="f2286-118">**确定** 接受更改并通过对话框提交更改。</span><span class="sxs-lookup"><span data-stu-id="f2286-118">**OK** Accepts and commits changes to the dialog.</span></span>
  
 <span data-ttu-id="f2286-119">**取消** 放弃更改并关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="f2286-119">**Cancel** Discards changes and closes the dialog.</span></span>
  
 <span data-ttu-id="f2286-120">**帮助** 显示此帮助屏幕。</span><span class="sxs-lookup"><span data-stu-id="f2286-120">**Help** Displays this help screen.</span></span>
  

