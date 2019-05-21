---
title: 在 Skype for Business 服务器中配置辅助位置信息服务
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
description: 在 Skype for business Server Enterprise Voice 中为 E9 配置辅助位置源 (SLS) 数据库。
ms.openlocfilehash: 0d637b8b2b61526837be2d56b8654f40bc556064
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34288531"
---
# <a name="configure-a-secondary-location-information-service-in-skype-for-business-server"></a><span data-ttu-id="ac089-103">在 Skype for Business 服务器中配置辅助位置信息服务</span><span class="sxs-lookup"><span data-stu-id="ac089-103">Configure a secondary Location Information service in Skype for Business Server</span></span>
 
<span data-ttu-id="ac089-104">在 Skype for business Server Enterprise Voice 中为 E9 配置辅助位置源 (SLS) 数据库。</span><span class="sxs-lookup"><span data-stu-id="ac089-104">Configure a secondary location source (SLS) database for E9-1-1 in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="ac089-105">Skype for Business 服务器提供可用于将位置信息服务指向辅助位置源 (SLS) 数据库的 web 服务界面。</span><span class="sxs-lookup"><span data-stu-id="ac089-105">Skype for Business Server provides a web service interface that you can use to point the Location Information service to a Secondary Location Source (SLS) database.</span></span> <span data-ttu-id="ac089-106">连接到 SLS 数据库的 web 服务接口必须符合 Location 信息服务 WSDL。</span><span class="sxs-lookup"><span data-stu-id="ac089-106">The web service interface that connects to the SLS database must conform to Location Information service WSDL.</span></span> <span data-ttu-id="ac089-107">如果同时配置了位置数据库和辅助位置数据库, 则位置信息服务首先查询位置数据库, 如果未找到匹配项, 则将位置请求从客户端发送到 SLS 数据库。</span><span class="sxs-lookup"><span data-stu-id="ac089-107">If both a location database and secondary location database are configured, the Location Information service first queries the location database, and if no match is found, sends the location request from the client to the SLS database.</span></span> <span data-ttu-id="ac089-108">如果该位置存在于 SLS 中, 则位置信息服务随后会将该位置发送回客户端。</span><span class="sxs-lookup"><span data-stu-id="ac089-108">If the location exists in the SLS, the Location Information service then sends the location back to the client.</span></span> 
  
### <a name="to-configure-a-secondary-location-database"></a><span data-ttu-id="ac089-109">配置辅助位置数据库</span><span class="sxs-lookup"><span data-stu-id="ac089-109">To configure a Secondary Location database</span></span>

1. <span data-ttu-id="ac089-110">启动 Skype for Business Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\* 和“Skype for Business 2015”\*\*\*\*，然后单击“Skype for Business Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ac089-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="ac089-111">运行以下 cmdlet 为辅助位置数据库位置配置 URL。</span><span class="sxs-lookup"><span data-stu-id="ac089-111">Run the following cmdlet to configure the URL for the location of the secondary location database.</span></span> 
    
   ```
   Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 
   ```

## <a name="see-also"></a><span data-ttu-id="ac089-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ac089-112">See also</span></span>

[<span data-ttu-id="ac089-113">Set-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="ac089-113">Set-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

