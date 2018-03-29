---
title: 将 Skype for Business Server 2015 与 Exchange Server 集成
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 795dc1c6-524f-4012-8b66-103b55198044
description: 摘要： 为业务服务器 2015年查看 Exchange Server 2016年或 Exchange Server 2013年和 Skype 的集成步骤。
ms.openlocfilehash: c8cbecd6b78e3dc14ad2133a93d9fc2d1f6bb3d6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="integrate-skype-for-business-server-2015-with-exchange-server"></a><span data-ttu-id="20c0d-103">将 Skype for Business Server 2015 与 Exchange Server 集成</span><span class="sxs-lookup"><span data-stu-id="20c0d-103">Integrate Skype for Business Server 2015 with Exchange Server</span></span>
 
<span data-ttu-id="20c0d-104">**摘要：**检查集成步骤 Exchange Server 2016年或 Exchange Server 2013年和 Skype 业务服务器 2015年。</span><span class="sxs-lookup"><span data-stu-id="20c0d-104">**Summary:** Review integration steps for Exchange Server 2016 or Exchange Server 2013 and Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="20c0d-105">Exchange Server 2016年或 Exchange Server 2013年和 Skype 业务服务器 2015年的兼容，并很好地集成。</span><span class="sxs-lookup"><span data-stu-id="20c0d-105">Exchange Server 2016 or Exchange Server 2013 and Skype for Business Server 2015 are compatible and integrate well.</span></span> <span data-ttu-id="20c0d-106">例如，可以在 Microsoft Outlook; 报告 Skype 业务用户出席信息同样，Skype 业务可以访问用户的 Outlook 日历，请注意用户都有一个会议，并在会议过程中显示用户的状态显示为忙。</span><span class="sxs-lookup"><span data-stu-id="20c0d-106">For example, Skype for Business user presence information can be reported in Microsoft Outlook; likewise, Skype for Business can access a user's Outlook calendar, notice the user has a meeting scheduled, and show the user's presence as Busy during the meeting.</span></span> <span data-ttu-id="20c0d-107">尽管您不需要运行 Exchange Server 才能运行 Skype 业务服务器 （或反之亦然） 这两种产品放在一起增强彼此的用户体验。</span><span class="sxs-lookup"><span data-stu-id="20c0d-107">Although you do not have to run Exchange Server in order to run Skype for Business Server (or vice-versa) the two products together enhance each other's user experience.</span></span>
  
<span data-ttu-id="20c0d-108">本文档提供的信息，在集成业务服务器 2015年和 Exchange Server 2016年或 Exchange Server 2013，Skype 但它假定初始安装和配置这两种产品已经发生。</span><span class="sxs-lookup"><span data-stu-id="20c0d-108">This documentation provides information on integrating Skype for Business Server 2015 and Exchange Server 2016 or Exchange Server 2013, but it assumes the initial setup and configuration of these two products has already happened.</span></span> <span data-ttu-id="20c0d-109">有关部署业务服务器 2015 Skype 的详细信息请参阅[Skype 业务服务器 2015年技术中心](https://go.microsoft.com/fwlink/p/?LinkId=246127)。</span><span class="sxs-lookup"><span data-stu-id="20c0d-109">For details about deploying Skype for Business Server 2015 see the [Skype for Business Server 2015 Tech Center](https://go.microsoft.com/fwlink/p/?LinkId=246127).</span></span> <span data-ttu-id="20c0d-110">有关 Exchange Server 部署的详细信息请参阅您的 Exchange 版本部署文档。</span><span class="sxs-lookup"><span data-stu-id="20c0d-110">For details about deploying Exchange Server see the deployment documentation for your version of Exchange.</span></span>
  
<span data-ttu-id="20c0d-111">如果您正在为 Microsoft Exchange Online 具有的业务服务器 2015年集成的 Skype 在内部部署安装，请参阅[配置业务服务器 2015年和 Outlook Web App 内部 Skype 之间的集成](outlook-web-app.md)。</span><span class="sxs-lookup"><span data-stu-id="20c0d-111">If you are integrating an on premises installation of Skype for Business Server 2015 with Microsoft Exchange Online, see [Configure integration between on-premises Skype for Business Server 2015 and Outlook Web App](outlook-web-app.md).</span></span>
  
<span data-ttu-id="20c0d-112">如果您正在为与内部部署的 Exchange Server 在线的业务集成 Skype，看到[之间 Skype 的在线业务和内部部署的 Exchange 配置 OAuth](oauth-with-online-and-on-premises.md)。</span><span class="sxs-lookup"><span data-stu-id="20c0d-112">If you are integrating Skype for Business Online with Exchange Server on premises, see [Configure OAuth between Skype for Business Online and Exchange on premises](oauth-with-online-and-on-premises.md).</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="20c0d-113">本节内容</span><span class="sxs-lookup"><span data-stu-id="20c0d-113">In this section</span></span>

[<span data-ttu-id="20c0d-114">在 Skype 为业务服务器 2015年和 Exchange Server 配置合作伙伴应用程序</span><span class="sxs-lookup"><span data-stu-id="20c0d-114">Configure partner applications in Skype for Business Server 2015 and Exchange Server</span></span>](configure-partner-applications.md)
  
[<span data-ttu-id="20c0d-115">Skype 的业务服务器 2015 使用 Exchange Server 存档配置</span><span class="sxs-lookup"><span data-stu-id="20c0d-115">Configure Skype for Business Server 2015 to use Exchange Server archiving</span></span>](use-exchange-archiving.md)
  
[<span data-ttu-id="20c0d-116">将搜索业务数据的存档 Skype 的 SharePoint 服务器配置</span><span class="sxs-lookup"><span data-stu-id="20c0d-116">Configure SharePoint Server to search for archived Skype for Business data</span></span>](sharepoint-to-search-for-archived-data.md)
  
[<span data-ttu-id="20c0d-117">Skype 业务服务器 2015 使用统一的联系人存储库的配置</span><span class="sxs-lookup"><span data-stu-id="20c0d-117">Configure Skype for Business Server 2015 to use the unified contact store</span></span>](use-the-unified-contact-store.md)
  
[<span data-ttu-id="20c0d-118">在 Skype 为业务服务器 2015年配置使用的高分辨率照片</span><span class="sxs-lookup"><span data-stu-id="20c0d-118">Configure the use of high-resolution photos in Skype for Business Server 2015</span></span>](high-resolution-photos.md)
  
[<span data-ttu-id="20c0d-119">配置统一邮件的 Exchange Server 的 Skype 业务服务器 2015年语音邮件</span><span class="sxs-lookup"><span data-stu-id="20c0d-119">Configure Exchange Server Unified Messaging for Skype for Business Server 2015 voice mail</span></span>](exchangeunified-messaging-for-voice-mail.md)
  
[<span data-ttu-id="20c0d-120">集成的业务服务器 2015年和 Microsoft Outlook Web App 2013年的 Skype</span><span class="sxs-lookup"><span data-stu-id="20c0d-120">Integrating Skype for Business Server 2015 and Microsoft Outlook Web App 2013</span></span>](http://technet.microsoft.com/library/513d4cc7-aa87-4f68-b99d-d58b63bdf242.aspx)
  
[<span data-ttu-id="20c0d-121">配置个人联系人存储在客户端计算机上的 Skype 业务服务器 2015</span><span class="sxs-lookup"><span data-stu-id="20c0d-121">Configure the personal contacts store on client computers for Skype for Business Server 2015</span></span>](personal-contacts-store.md)
  
## <a name="see-also"></a><span data-ttu-id="20c0d-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="20c0d-122">See also</span></span>

#### 

[<span data-ttu-id="20c0d-123">计划以落实 Skype 业务和交换</span><span class="sxs-lookup"><span data-stu-id="20c0d-123">Plan to integrate Skype for Business and Exchange</span></span>](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)

