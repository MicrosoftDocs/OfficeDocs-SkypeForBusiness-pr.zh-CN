---
title: 在 Skype for Business Server 2015 中配置 SNMP 应用程序
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
description: 配置 SNMP 应用程序以使用 E9-1-1 在 Skype 业务 Server 企业语音。
ms.openlocfilehash: 4d864d8617f679867e514f3cc74ae4fe0201a989
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="configure-an-snmp-application-in-skype-for-business-server-2015"></a><span data-ttu-id="e9b28-103">在 Skype for Business Server 2015 中配置 SNMP 应用程序</span><span class="sxs-lookup"><span data-stu-id="e9b28-103">Configure an SNMP application in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="e9b28-104">配置 SNMP 应用程序以使用 E9-1-1 在 Skype 业务 Server 企业语音。</span><span class="sxs-lookup"><span data-stu-id="e9b28-104">Configure an SNMP application to work with E9-1-1 in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="e9b28-105">Skype 业务服务器包括可用于连接到简单网络管理协议 (SNMP) 应用程序匹配 MAC 地址与端口和交换机信息的位置信息服务的标准 web 服务接口。</span><span class="sxs-lookup"><span data-stu-id="e9b28-105">Skype for Business Server includes a standard web service interface that you can use to connect the Location Information service to Simple Network Management Protocol (SNMP) applications that match MAC addresses with port and switch information.</span></span> 
  
<span data-ttu-id="e9b28-106">如果安装 SNMP 应用程序和位置信息服务未能找到匹配项的位置数据库中，位置信息服务自动使用客户端提供的 MAC 地址查询应用程序。</span><span class="sxs-lookup"><span data-stu-id="e9b28-106">If an SNMP application is installed and the Location Information service fails to find a match in the location database, the Location Information service automatically queries the application by using the MAC address provided by the client.</span></span> <span data-ttu-id="e9b28-107">位置信息服务然后使用 SNMP 应用程序返回的端口和交换机信息重新查询位置数据库。</span><span class="sxs-lookup"><span data-stu-id="e9b28-107">The Location Information service then uses the port and switch information returned by the SNMP application to query the location database again.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e9b28-108">MAC 地址不在运行 Windows 8 的计算机上可用。</span><span class="sxs-lookup"><span data-stu-id="e9b28-108">MAC addresses are not available on computers running Windows 8.</span></span> 
  
### <a name="to-configure-the-snmp-application-url"></a><span data-ttu-id="e9b28-109">配置 SNMP 应用程序 URL</span><span class="sxs-lookup"><span data-stu-id="e9b28-109">To configure the SNMP application URL</span></span>

1.  <span data-ttu-id="e9b28-110">启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。</span><span class="sxs-lookup"><span data-stu-id="e9b28-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="e9b28-111">运行以下 cmdlet 为 SNMP 应用程序配置 URL。</span><span class="sxs-lookup"><span data-stu-id="e9b28-111">Run the following cmdlet to configure the URL for the SNMP application.</span></span> 
    
   ```
   Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 
   ```

## <a name="see-also"></a><span data-ttu-id="e9b28-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e9b28-112">See also</span></span>

#### 

[<span data-ttu-id="e9b28-113">通过 Set-cswebserviceconfiguration</span><span class="sxs-lookup"><span data-stu-id="e9b28-113">Set-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

