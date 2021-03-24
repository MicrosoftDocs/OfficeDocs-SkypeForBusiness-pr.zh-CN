---
title: 将 Skype for Business Server 与 Exchange Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 795dc1c6-524f-4012-8b66-103b55198044
description: 摘要：查看 Exchange Server 2016 或 Exchange Server 2013 和 Skype for Business Server 的集成步骤。
ms.openlocfilehash: b19aa73e62b12674551690b716144fb67b4cd715
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104848"
---
# <a name="integrate-skype-for-business-server-with-exchange-server"></a><span data-ttu-id="0a9a4-103">将 Skype for Business Server 与 Exchange Server</span><span class="sxs-lookup"><span data-stu-id="0a9a4-103">Integrate Skype for Business Server with Exchange Server</span></span>

<span data-ttu-id="0a9a4-104">**摘要：** 查看 Exchange Server 2013 或更高版本和 Skype for Business Server 的集成步骤。</span><span class="sxs-lookup"><span data-stu-id="0a9a4-104">**Summary:** Review integration steps for Exchange Server 2013 or later and Skype for Business Server.</span></span>

<span data-ttu-id="0a9a4-105">Exchange Server 2013 或更高版本与 Skype for Business Server 兼容且集成良好。</span><span class="sxs-lookup"><span data-stu-id="0a9a4-105">Exchange Server 2013 or later and Skype for Business Server are compatible and integrate well.</span></span> <span data-ttu-id="0a9a4-106">例如，Skype for Business 用户状态信息可以在 Microsoft Outlook 中报告;同样，Skype for Business 可以访问用户的 Outlook 日历，注意用户已安排会议，并且会议期间将用户状态显示为忙碌。</span><span class="sxs-lookup"><span data-stu-id="0a9a4-106">For example, Skype for Business user presence information can be reported in Microsoft Outlook; likewise, Skype for Business can access a user's Outlook calendar, notice the user has a meeting scheduled, and show the user's presence as Busy during the meeting.</span></span> <span data-ttu-id="0a9a4-107">尽管不需要运行 Exchange Server 运行 Skype for Business Server (反之亦然) 这两种产品一起增强彼此的用户体验。</span><span class="sxs-lookup"><span data-stu-id="0a9a4-107">Although you do not have to run Exchange Server in order to run Skype for Business Server (or vice-versa) the two products together enhance each other's user experience.</span></span>

<span data-ttu-id="0a9a4-108">本文档提供了有关集成 Skype for Business Server 和 Exchange Server 2016 或 Exchange Server 2013 的信息，但它假定这两种产品的初始安装和配置已经发生。</span><span class="sxs-lookup"><span data-stu-id="0a9a4-108">This documentation provides information on integrating Skype for Business Server and Exchange Server 2016 or Exchange Server 2013, but it assumes the initial setup and configuration of these two products has already happened.</span></span> <span data-ttu-id="0a9a4-109">有关部署 Skype for Business Server 的详细信息，请参阅 [Skype for Business Server 技术中心](../../../Hub/index.yml)。</span><span class="sxs-lookup"><span data-stu-id="0a9a4-109">For details about deploying Skype for Business Server see the [Skype for Business Server Tech Center](../../../Hub/index.yml).</span></span> <span data-ttu-id="0a9a4-110">有关部署 exchange Exchange Server请参阅 Exchange 版本的部署文档。</span><span class="sxs-lookup"><span data-stu-id="0a9a4-110">For details about deploying Exchange Server see the deployment documentation for your version of Exchange.</span></span>

<span data-ttu-id="0a9a4-111">如果要将 Skype for Business Server 本地安装与 Microsoft Exchange Online 集成，请参阅配置本地 Skype for Business Server 与 Outlook Web App [之间的集成](outlook-web-app.md)。</span><span class="sxs-lookup"><span data-stu-id="0a9a4-111">If you are integrating an on premises installation of Skype for Business Server with Microsoft Exchange Online, see [Configure integration between on-premises Skype for Business Server and Outlook Web App](outlook-web-app.md).</span></span>

<span data-ttu-id="0a9a4-112">如果要将 Skype for Business Online 与本地Exchange Server集成，请参阅在 Skype for Business Online 和本地 Exchange 之间[配置 OAuth。](oauth-with-online-and-on-premises.md)</span><span class="sxs-lookup"><span data-stu-id="0a9a4-112">If you are integrating Skype for Business Online with Exchange Server on premises, see [Configure OAuth between Skype for Business Online and Exchange on premises](oauth-with-online-and-on-premises.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="0a9a4-113">本节内容</span><span class="sxs-lookup"><span data-stu-id="0a9a4-113">In this section</span></span>

[<span data-ttu-id="0a9a4-114">在 Skype for Business Server 和 Exchange Server</span><span class="sxs-lookup"><span data-stu-id="0a9a4-114">Configure partner applications in Skype for Business Server and Exchange Server</span></span>](configure-partner-applications.md)

[<span data-ttu-id="0a9a4-115">配置 Skype for Business Server 以使用Exchange Server存档</span><span class="sxs-lookup"><span data-stu-id="0a9a4-115">Configure Skype for Business Server to use Exchange Server archiving</span></span>](use-exchange-archiving.md)

[<span data-ttu-id="0a9a4-116">配置 SharePoint Server 以搜索存档的 Skype for Business 数据</span><span class="sxs-lookup"><span data-stu-id="0a9a4-116">Configure SharePoint Server to search for archived Skype for Business data</span></span>](sharepoint-to-search-for-archived-data.md)

[<span data-ttu-id="0a9a4-117">配置 Skype for Business Server 以使用统一的联系人存储</span><span class="sxs-lookup"><span data-stu-id="0a9a4-117">Configure Skype for Business Server to use the unified contact store</span></span>](use-the-unified-contact-store.md)

[<span data-ttu-id="0a9a4-118">在 Skype for Business Server 中配置高分辨率照片的使用</span><span class="sxs-lookup"><span data-stu-id="0a9a4-118">Configure the use of high-resolution photos in Skype for Business Server</span></span>](high-resolution-photos.md)

[<span data-ttu-id="0a9a4-119">为Exchange Server Skype for Business Server 语音邮件配置统一消息</span><span class="sxs-lookup"><span data-stu-id="0a9a4-119">Configure Exchange Server Unified Messaging for Skype for Business Server voice mail</span></span>](exchangeunified-messaging-for-voice-mail.md)

<span data-ttu-id="0a9a4-120">[集成 Skype for Business Server 和 Microsoft Outlook Web App 2013](/previous-versions/office/communications/jj688055(v=ocs.16))</span><span class="sxs-lookup"><span data-stu-id="0a9a4-120">[Integrating Skype for Business Server and Microsoft Outlook Web App 2013](/previous-versions/office/communications/jj688055(v=ocs.16))</span></span>

[<span data-ttu-id="0a9a4-121">为 Skype for Business Server 配置客户端计算机上的个人联系人存储</span><span class="sxs-lookup"><span data-stu-id="0a9a4-121">Configure the personal contacts store on client computers for Skype for Business Server</span></span>](personal-contacts-store.md)

## <a name="see-also"></a><span data-ttu-id="0a9a4-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0a9a4-122">See also</span></span>

[<span data-ttu-id="0a9a4-123">计划集成 Skype for Business 和 Exchange</span><span class="sxs-lookup"><span data-stu-id="0a9a4-123">Plan to integrate Skype for Business and Exchange</span></span>](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)