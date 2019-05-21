---
title: 将 Skype for Business 服务器与 Exchange Server 集成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 795dc1c6-524f-4012-8b66-103b55198044
description: '摘要: 查看 Exchange Server 2016 或 Exchange Server 2013 和 Skype for business 服务器的集成步骤。'
ms.openlocfilehash: 25b2260805cf4e42bc15d1ae5607baa3f830fba6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277984"
---
# <a name="integrate-skype-for-business-server-with-exchange-server"></a><span data-ttu-id="7565d-103">将 Skype for Business 服务器与 Exchange Server 集成</span><span class="sxs-lookup"><span data-stu-id="7565d-103">Integrate Skype for Business Server with Exchange Server</span></span>

<span data-ttu-id="7565d-104">**摘要:** 查看 Exchange Server 2013 或更高版本以及 Skype for business 服务器的集成步骤。</span><span class="sxs-lookup"><span data-stu-id="7565d-104">**Summary:** Review integration steps for Exchange Server 2013 or later and Skype for Business Server.</span></span>

<span data-ttu-id="7565d-105">Exchange Server 2013 或更高版本以及 Skype for business 服务器兼容并良好集成。</span><span class="sxs-lookup"><span data-stu-id="7565d-105">Exchange Server 2013 or later and Skype for Business Server are compatible and integrate well.</span></span> <span data-ttu-id="7565d-106">例如, 可以在 Microsoft Outlook 中报告 Skype for Business 用户状态信息。同样, Skype for Business 可以访问用户的 Outlook 日历, 请注意用户安排了会议, 并在会议期间将用户的状态显示为 "忙碌"。</span><span class="sxs-lookup"><span data-stu-id="7565d-106">For example, Skype for Business user presence information can be reported in Microsoft Outlook; likewise, Skype for Business can access a user's Outlook calendar, notice the user has a meeting scheduled, and show the user's presence as Busy during the meeting.</span></span> <span data-ttu-id="7565d-107">虽然您不必运行 Exchange Server 即可运行 Skype for Business 服务器 (反之亦然), 但这两个产品一起增强了用户体验。</span><span class="sxs-lookup"><span data-stu-id="7565d-107">Although you do not have to run Exchange Server in order to run Skype for Business Server (or vice-versa) the two products together enhance each other's user experience.</span></span>

<span data-ttu-id="7565d-108">本文档提供有关集成 Skype for Business Server 和 Exchange Server 2016 或 Exchange Server 2013 的信息, 但假定这两种产品的初始设置和配置已经发生。</span><span class="sxs-lookup"><span data-stu-id="7565d-108">This documentation provides information on integrating Skype for Business Server and Exchange Server 2016 or Exchange Server 2013, but it assumes the initial setup and configuration of these two products has already happened.</span></span> <span data-ttu-id="7565d-109">有关部署 Skype for Business 服务器的详细信息, 请参阅[Skype for Business Server 技术中心](https://go.microsoft.com/fwlink/p/?LinkId=246127)。</span><span class="sxs-lookup"><span data-stu-id="7565d-109">For details about deploying Skype for Business Server see the [Skype for Business Server Tech Center](https://go.microsoft.com/fwlink/p/?LinkId=246127).</span></span> <span data-ttu-id="7565d-110">有关部署 Exchange Server 的详细信息, 请参阅 Exchange 版本的部署文档。</span><span class="sxs-lookup"><span data-stu-id="7565d-110">For details about deploying Exchange Server see the deployment documentation for your version of Exchange.</span></span>

<span data-ttu-id="7565d-111">如果你要将 Skype for business Server 的内部部署安装与 Microsoft Exchange Online 集成, 请参阅[配置本地 skype for Business 服务器和 Outlook Web App 之间的集成](outlook-web-app.md)。</span><span class="sxs-lookup"><span data-stu-id="7565d-111">If you are integrating an on premises installation of Skype for Business Server with Microsoft Exchange Online, see [Configure integration between on-premises Skype for Business Server and Outlook Web App](outlook-web-app.md).</span></span>

<span data-ttu-id="7565d-112">如果你要将 Skype for Business Online 与内部部署 Exchange Server 集成, 请参阅[在 skype For Business online 和 Exchange Online 之间配置 OAuth](oauth-with-online-and-on-premises.md)。</span><span class="sxs-lookup"><span data-stu-id="7565d-112">If you are integrating Skype for Business Online with Exchange Server on premises, see [Configure OAuth between Skype for Business Online and Exchange on premises](oauth-with-online-and-on-premises.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="7565d-113">本节内容</span><span class="sxs-lookup"><span data-stu-id="7565d-113">In this section</span></span>

[<span data-ttu-id="7565d-114">在 Skype for Business Server 和 Exchange Server 中配置合作伙伴应用程序</span><span class="sxs-lookup"><span data-stu-id="7565d-114">Configure partner applications in Skype for Business Server and Exchange Server</span></span>](configure-partner-applications.md)

[<span data-ttu-id="7565d-115">配置 Skype for Business 服务器以使用 Exchange Server 存档</span><span class="sxs-lookup"><span data-stu-id="7565d-115">Configure Skype for Business Server to use Exchange Server archiving</span></span>](use-exchange-archiving.md)

[<span data-ttu-id="7565d-116">配置 SharePoint Server 以搜索存档的 Skype for Business 数据</span><span class="sxs-lookup"><span data-stu-id="7565d-116">Configure SharePoint Server to search for archived Skype for Business data</span></span>](sharepoint-to-search-for-archived-data.md)

[<span data-ttu-id="7565d-117">配置 Skype for Business Server 以使用统一联系人存储</span><span class="sxs-lookup"><span data-stu-id="7565d-117">Configure Skype for Business Server to use the unified contact store</span></span>](use-the-unified-contact-store.md)

[<span data-ttu-id="7565d-118">在 Skype for Business 服务器中配置高分辨率照片的使用</span><span class="sxs-lookup"><span data-stu-id="7565d-118">Configure the use of high-resolution photos in Skype for Business Server</span></span>](high-resolution-photos.md)

[<span data-ttu-id="7565d-119">为 Skype for Business Server 语音邮件配置 Exchange Server 统一消息</span><span class="sxs-lookup"><span data-stu-id="7565d-119">Configure Exchange Server Unified Messaging for Skype for Business Server voice mail</span></span>](exchangeunified-messaging-for-voice-mail.md)

[<span data-ttu-id="7565d-120">集成 Skype for Business 服务器和 Microsoft Outlook Web App 2013</span><span class="sxs-lookup"><span data-stu-id="7565d-120">Integrating Skype for Business Server and Microsoft Outlook Web App 2013</span></span>](https://technet.microsoft.com/library/513d4cc7-aa87-4f68-b99d-d58b63bdf242.aspx)

[<span data-ttu-id="7565d-121">在客户端计算机上为 Skype for Business 服务器配置个人联系人存储</span><span class="sxs-lookup"><span data-stu-id="7565d-121">Configure the personal contacts store on client computers for Skype for Business Server</span></span>](personal-contacts-store.md)

## <a name="see-also"></a><span data-ttu-id="7565d-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7565d-122">See also</span></span>

[<span data-ttu-id="7565d-123">计划集成 Skype for Business 和 Exchange</span><span class="sxs-lookup"><span data-stu-id="7565d-123">Plan to integrate Skype for Business and Exchange</span></span>](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)
