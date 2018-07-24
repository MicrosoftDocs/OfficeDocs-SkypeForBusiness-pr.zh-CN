---
title: 为业务 Server 与 Exchange Server 集成 Skype
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 795dc1c6-524f-4012-8b66-103b55198044
description: 摘要： 查看业务服务器的 Exchange Server 2016 或 Exchange Server 2013 和 Skype 集成步骤。
ms.openlocfilehash: 5b4afa15401a0e19e475a12e4a47c8786c321eca
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20979795"
---
# <a name="integrate-skype-for-business-server-with-exchange-server"></a><span data-ttu-id="efc02-103">为业务 Server 与 Exchange Server 集成 Skype</span><span class="sxs-lookup"><span data-stu-id="efc02-103">Integrate Skype for Business Server with Exchange Server</span></span>
 
<span data-ttu-id="efc02-104">**摘要：** 查看 Business Server 集成步骤的 Exchange Server 2013 或更高版本和 Skype。</span><span class="sxs-lookup"><span data-stu-id="efc02-104">**Summary:** Review integration steps for Exchange Server 2013 or later and Skype for Business Server.</span></span>
  
<span data-ttu-id="efc02-105">Exchange Server 2013 或更高版本和 Skype 业务服务器兼容，并且还集成。</span><span class="sxs-lookup"><span data-stu-id="efc02-105">Exchange Server 2013 or later and Skype for Business Server are compatible and integrate well.</span></span> <span data-ttu-id="efc02-106">例如，可以在 Microsoft Outlook; 中报告 Skype 业务用户状态信息同样，for Business 的 Skype 可以访问用户的 Outlook 日历、 注意用户具有一个会议，并在会议期间显示为忙碌的用户的状态。</span><span class="sxs-lookup"><span data-stu-id="efc02-106">For example, Skype for Business user presence information can be reported in Microsoft Outlook; likewise, Skype for Business can access a user's Outlook calendar, notice the user has a meeting scheduled, and show the user's presence as Busy during the meeting.</span></span> <span data-ttu-id="efc02-107">尽管无需才能在运行 Skype 业务服务器 （或相反） 的两个产品一起运行 Exchange Server 增强彼此的用户体验。</span><span class="sxs-lookup"><span data-stu-id="efc02-107">Although you do not have to run Exchange Server in order to run Skype for Business Server (or vice-versa) the two products together enhance each other's user experience.</span></span>
  
<span data-ttu-id="efc02-108">本文档提供有关将 Skype 集成业务服务器和 Exchange Server 2016 或 Exchange Server 2013 的信息，并假定初始安装，但已经发生这两种产品的配置。</span><span class="sxs-lookup"><span data-stu-id="efc02-108">This documentation provides information on integrating Skype for Business Server and Exchange Server 2016 or Exchange Server 2013, but it assumes the initial setup and configuration of these two products has already happened.</span></span> <span data-ttu-id="efc02-109">有关部署 for Business Server Skype 的详细信息，请参阅[Business Server 技术中心的 Skype](https://go.microsoft.com/fwlink/p/?LinkId=246127)。</span><span class="sxs-lookup"><span data-stu-id="efc02-109">For details about deploying Skype for Business Server see the [Skype for Business Server Tech Center](https://go.microsoft.com/fwlink/p/?LinkId=246127).</span></span> <span data-ttu-id="efc02-110">有关部署 Exchange Server 详细信息，请参阅部署文档中为您的 Exchange 版本。</span><span class="sxs-lookup"><span data-stu-id="efc02-110">For details about deploying Exchange Server see the deployment documentation for your version of Exchange.</span></span>
  
<span data-ttu-id="efc02-111">如果要与 Microsoft Exchange Online 的业务服务器集成的 Skype 上部署安装，请参阅[Configure Business Server 和 Outlook Web App 的内部部署 Skype 集成](outlook-web-app.md)。</span><span class="sxs-lookup"><span data-stu-id="efc02-111">If you are integrating an on premises installation of Skype for Business Server with Microsoft Exchange Online, see [Configure integration between on-premises Skype for Business Server and Outlook Web App](outlook-web-app.md).</span></span>
  
<span data-ttu-id="efc02-112">如果要为 Online 与本地 Exchange 服务器上的业务集成 Skype，请参阅[业务在线和本地 Exchange 的 Skype 之间配置 OAuth](oauth-with-online-and-on-premises.md)。</span><span class="sxs-lookup"><span data-stu-id="efc02-112">If you are integrating Skype for Business Online with Exchange Server on premises, see [Configure OAuth between Skype for Business Online and Exchange on premises](oauth-with-online-and-on-premises.md).</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="efc02-113">本节内容</span><span class="sxs-lookup"><span data-stu-id="efc02-113">In this section</span></span>

[<span data-ttu-id="efc02-114">在 Skype for Business Server 和 Exchange Server 中配置合作伙伴应用程序</span><span class="sxs-lookup"><span data-stu-id="efc02-114">Configure partner applications in Skype for Business Server and Exchange Server</span></span>](configure-partner-applications.md)
  
[<span data-ttu-id="efc02-115">配置 Business Server 使用 Exchange Server 存档的 Skype</span><span class="sxs-lookup"><span data-stu-id="efc02-115">Configure Skype for Business Server to use Exchange Server archiving</span></span>](use-exchange-archiving.md)
  
[<span data-ttu-id="efc02-116">配置 SharePoint Server 以搜索存档的 Skype for Business 数据</span><span class="sxs-lookup"><span data-stu-id="efc02-116">Configure SharePoint Server to search for archived Skype for Business data</span></span>](sharepoint-to-search-for-archived-data.md)
  
[<span data-ttu-id="efc02-117">配置 Skype for Business Server 以使用统一联系人存储</span><span class="sxs-lookup"><span data-stu-id="efc02-117">Configure Skype for Business Server to use the unified contact store</span></span>](use-the-unified-contact-store.md)
  
[<span data-ttu-id="efc02-118">在 Skype for Business Server 中配置使用高分辨率照片</span><span class="sxs-lookup"><span data-stu-id="efc02-118">Configure the use of high-resolution photos in Skype for Business Server</span></span>](high-resolution-photos.md)
  
[<span data-ttu-id="efc02-119">为 Skype for Business Server 语音邮件配置 Exchange Server 统一消息</span><span class="sxs-lookup"><span data-stu-id="efc02-119">Configure Exchange Server Unified Messaging for Skype for Business Server voice mail</span></span>](exchangeunified-messaging-for-voice-mail.md)
  
[<span data-ttu-id="efc02-120">将 Skype 集成的企业服务器和 Microsoft Outlook Web App 2013</span><span class="sxs-lookup"><span data-stu-id="efc02-120">Integrating Skype for Business Server and Microsoft Outlook Web App 2013</span></span>](http://technet.microsoft.com/library/513d4cc7-aa87-4f68-b99d-d58b63bdf242.aspx)
  
[<span data-ttu-id="efc02-121">配置个人联系人存储客户端计算机上的 Skype 业务服务器</span><span class="sxs-lookup"><span data-stu-id="efc02-121">Configure the personal contacts store on client computers for Skype for Business Server</span></span>](personal-contacts-store.md)
  
## <a name="see-also"></a><span data-ttu-id="efc02-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="efc02-122">See also</span></span>

[<span data-ttu-id="efc02-123">计划集成 Skype for Business 和 Exchange</span><span class="sxs-lookup"><span data-stu-id="efc02-123">Plan to integrate Skype for Business and Exchange</span></span>](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)