---
title: 在 Skype for Business Server 中配置辅助位置信息服务
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
description: Configure a secondary location source (SLS) database for E9-1-1 in Skype for Business Server 企业语音.
ms.openlocfilehash: 7a81d8573ca0425d4d445dc00f257f014a39d8c6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103378"
---
# <a name="configure-a-secondary-location-information-service-in-skype-for-business-server"></a><span data-ttu-id="e6330-103">在 Skype for Business Server 中配置辅助位置信息服务</span><span class="sxs-lookup"><span data-stu-id="e6330-103">Configure a secondary Location Information service in Skype for Business Server</span></span>
 
<span data-ttu-id="e6330-104">Configure a secondary location source (SLS) database for E9-1-1 in Skype for Business Server 企业语音.</span><span class="sxs-lookup"><span data-stu-id="e6330-104">Configure a secondary location source (SLS) database for E9-1-1 in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="e6330-105">Skype for Business Server 提供了一个 Web 服务接口，可用于将位置信息服务指向 SLS 数据库 (辅助) 源。</span><span class="sxs-lookup"><span data-stu-id="e6330-105">Skype for Business Server provides a web service interface that you can use to point the Location Information service to a Secondary Location Source (SLS) database.</span></span> <span data-ttu-id="e6330-106">连接到 SLS 数据库的 Web 服务接口必须符合位置信息服务 WSDL。</span><span class="sxs-lookup"><span data-stu-id="e6330-106">The web service interface that connects to the SLS database must conform to Location Information service WSDL.</span></span> <span data-ttu-id="e6330-107">如果同时配置了位置数据库和辅助位置数据库，则位置信息服务将首先查询位置数据库，如果未找到匹配项，则从客户端向 SLS 数据库发送位置请求。</span><span class="sxs-lookup"><span data-stu-id="e6330-107">If both a location database and secondary location database are configured, the Location Information service first queries the location database, and if no match is found, sends the location request from the client to the SLS database.</span></span> <span data-ttu-id="e6330-108">如果位置存在于 SLS 中，则位置信息服务会向客户端发送回该位置。</span><span class="sxs-lookup"><span data-stu-id="e6330-108">If the location exists in the SLS, the Location Information service then sends the location back to the client.</span></span> 
  
### <a name="to-configure-a-secondary-location-database"></a><span data-ttu-id="e6330-109">配置辅助位置数据库</span><span class="sxs-lookup"><span data-stu-id="e6330-109">To configure a Secondary Location database</span></span>

1. <span data-ttu-id="e6330-110">启动 Skype for Business Server命令行管理程序：单击"开始"，单击"所有程序"，单击 **"Skype for Business 2015"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**</span><span class="sxs-lookup"><span data-stu-id="e6330-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="e6330-111">运行以下 cmdlet 为辅助位置数据库位置配置 URL。</span><span class="sxs-lookup"><span data-stu-id="e6330-111">Run the following cmdlet to configure the URL for the location of the secondary location database.</span></span> 
    
   ```powershell
   Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 
   ```

## <a name="see-also"></a><span data-ttu-id="e6330-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e6330-112">See also</span></span>

[<span data-ttu-id="e6330-113">Set-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="e6330-113">Set-CsWebServiceConfiguration</span></span>](/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)