---
title: 中介服务设置扩展器
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.FeMediationServiceSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 142c1acd-cdaa-4922-8379-aa1bdf56a964
description: 对于“中介服务器”，可以指定以下内容：
ms.openlocfilehash: 4535698552b918c57a8c76741ffaaef2c1b66b48
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/28/2018
ms.locfileid: "23253793"
---
# <a name="mediation-service-settings-expander"></a><span data-ttu-id="c429a-103">中介服务设置扩展器</span><span class="sxs-lookup"><span data-stu-id="c429a-103">Mediation Service Settings Expander</span></span>

<span data-ttu-id="c429a-104">对于“**中介服务器**”，可以指定以下内容：</span><span class="sxs-lookup"><span data-stu-id="c429a-104">For **Mediation Server**, you can specify the following:</span></span>

<span data-ttu-id="c429a-105">如果您并置中介服务器上的前端池或 Standard Edition server，选择**并置中介服务器已启用**复选框。</span><span class="sxs-lookup"><span data-stu-id="c429a-105">If you are collocating the Mediation Server onto the Front End pool or the Standard Edition server, select the check box **Collocated Mediation Server enabled**.</span></span> <span data-ttu-id="c429a-106">如果您选择将中介服务器并置，没有在此部分可定义设置。</span><span class="sxs-lookup"><span data-stu-id="c429a-106">If you choose not to collocate the Mediation Server, there are no definable settings in this section.</span></span>

<span data-ttu-id="c429a-107">如果已启用并置的中介服务器，您需要在服务器上的传输层安全性 (TLS) 定义的侦听端口范围。</span><span class="sxs-lookup"><span data-stu-id="c429a-107">If you have enabled the collocation of the Mediation Server, you need to define the listening port range on the server for Transport Layer Security (TLS).</span></span> <span data-ttu-id="c429a-108">默认情况下，此端口为 5067。</span><span class="sxs-lookup"><span data-stu-id="c429a-108">By default, this port is 5067.</span></span> <span data-ttu-id="c429a-109">如果选择“**启用 TCP 端口**”，则必须为并置的中介服务器定义传输控制协议 (TCP) 端口。</span><span class="sxs-lookup"><span data-stu-id="c429a-109">If you select **Enable TCP port**, you must define a Transmission Control Protocol (TCP) port for the collocated Mediation Server.</span></span> <span data-ttu-id="c429a-110">这是一个可选设置，您应该参考网关要求或公用电话交换网 (PSTN) 要求以确定是否需要此设置。</span><span class="sxs-lookup"><span data-stu-id="c429a-110">This is an optional setting, and you should refer to the requirements of your gateway or public switched telephone network (PSTN) requirements to determine if you need this.</span></span> <span data-ttu-id="c429a-111">默认情况下，TCP 端口值为 5068。</span><span class="sxs-lookup"><span data-stu-id="c429a-111">By default, the TCP port value is 5068.</span></span>

<span data-ttu-id="c429a-112">定义与并置的中介服务器关联的 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="c429a-112">You define PSTN gateways that are associated with the collocated Mediation Server.</span></span> <span data-ttu-id="c429a-113">如果已定义网关，它们将可用于与中介服务器相关联。</span><span class="sxs-lookup"><span data-stu-id="c429a-113">If you have already defined gateways, they will be available to associate with the Mediation Server.</span></span>

<span data-ttu-id="c429a-114">如果您有多个网关与中介服务器相关联，关联的第一个网关将默认网关。</span><span class="sxs-lookup"><span data-stu-id="c429a-114">If you have more than one gateway associated with a Mediation Server, the first gateway associated will be the default gateway.</span></span> <span data-ttu-id="c429a-115">如果需要选择其他网关作为默认网关，请选择要设为默认值的网关，然后单击“**设为默认值**”。</span><span class="sxs-lookup"><span data-stu-id="c429a-115">If you need to choose another gateway as the default gateway, select the gateway that you want to make the default, and click **Make Default**.</span></span> <span data-ttu-id="c429a-116">若要取消选择网关作为默认网关，请单击“**取消设为默认值**”。</span><span class="sxs-lookup"><span data-stu-id="c429a-116">To unselect the gateway as the default, click **Unmake Default**.</span></span>

<span data-ttu-id="c429a-117">有关定义和配置设置的 Enterprise Edition 前端池或 Standard Edition server 的详细信息，请参阅[Defining and Configuring the Topology](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx)和[Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx)。</span><span class="sxs-lookup"><span data-stu-id="c429a-117">For details about defining and configuring the settings for the Enterprise Edition Front End pool or Standard Edition server, see [Defining and Configuring the Topology](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) and [Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).</span></span>


