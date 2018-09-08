---
title: 在 Skype for Business Server 中配置的辅助位置信息服务
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
description: 为业务 Server 企业语音的 E9-1-1 在 Skype 配置辅助位置源 （另外） 数据库。
ms.openlocfilehash: e811062bbec9e3b6caf368e010b751e496c1b305
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23885120"
---
# <a name="configure-a-secondary-location-information-service-in-skype-for-business-server"></a><span data-ttu-id="90c6d-103">在 Skype for Business Server 中配置的辅助位置信息服务</span><span class="sxs-lookup"><span data-stu-id="90c6d-103">Configure a secondary Location Information service in Skype for Business Server</span></span>
 
<span data-ttu-id="90c6d-104">为业务 Server 企业语音的 E9-1-1 在 Skype 配置辅助位置源 （另外） 数据库。</span><span class="sxs-lookup"><span data-stu-id="90c6d-104">Configure a secondary location source (SLS) database for E9-1-1 in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="90c6d-105">Skype 业务服务器提供了可用于指向辅助位置源 （另外） 数据库的位置信息服务的 web 服务接口。</span><span class="sxs-lookup"><span data-stu-id="90c6d-105">Skype for Business Server provides a web service interface that you can use to point the Location Information service to a Secondary Location Source (SLS) database.</span></span> <span data-ttu-id="90c6d-106">连接到另外数据库的 web 服务界面必须符合位置信息服务 WSDL。</span><span class="sxs-lookup"><span data-stu-id="90c6d-106">The web service interface that connects to the SLS database must conform to Location Information service WSDL.</span></span> <span data-ttu-id="90c6d-107">如果配置位置数据库和辅助位置数据库，位置信息服务将首先查询位置数据库，并如果未找到匹配，请从客户端发送位置请求，另外数据库。</span><span class="sxs-lookup"><span data-stu-id="90c6d-107">If both a location database and secondary location database are configured, the Location Information service first queries the location database, and if no match is found, sends the location request from the client to the SLS database.</span></span> <span data-ttu-id="90c6d-108">如果位置存在于另外，位置信息服务然后向客户端发送位置。</span><span class="sxs-lookup"><span data-stu-id="90c6d-108">If the location exists in the SLS, the Location Information service then sends the location back to the client.</span></span> 
  
### <a name="to-configure-a-secondary-location-database"></a><span data-ttu-id="90c6d-109">配置辅助位置数据库</span><span class="sxs-lookup"><span data-stu-id="90c6d-109">To configure a Secondary Location database</span></span>

1. <span data-ttu-id="90c6d-110">启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。</span><span class="sxs-lookup"><span data-stu-id="90c6d-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="90c6d-111">运行以下 cmdlet 为辅助位置数据库位置配置 URL。</span><span class="sxs-lookup"><span data-stu-id="90c6d-111">Run the following cmdlet to configure the URL for the location of the secondary location database.</span></span> 
    
   ```
   Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 
   ```

## <a name="see-also"></a><span data-ttu-id="90c6d-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="90c6d-112">See also</span></span>

[<span data-ttu-id="90c6d-113">通过 Set-cswebserviceconfiguration</span><span class="sxs-lookup"><span data-stu-id="90c6d-113">Set-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

