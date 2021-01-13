---
title: 在 Skype for Business Server 中配置 SNMP 应用程序
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
ms.assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
description: 将 SNMP 应用程序配置为与 Skype for Business Server 企业语音 中的 E9-1-1 一企业语音。
ms.openlocfilehash: eb1947f24968dccc6f45b6d8ea3a7df42282a58f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804152"
---
# <a name="configure-an-snmp-application-in-skype-for-business-server"></a><span data-ttu-id="de53c-103">在 Skype for Business Server 中配置 SNMP 应用程序</span><span class="sxs-lookup"><span data-stu-id="de53c-103">Configure an SNMP application in Skype for Business Server</span></span>
 
<span data-ttu-id="de53c-104">将 SNMP 应用程序配置为与 Skype for Business Server 企业语音 中的 E9-1-1 一企业语音。</span><span class="sxs-lookup"><span data-stu-id="de53c-104">Configure an SNMP application to work with E9-1-1 in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="de53c-105">Skype for Business Server 包括一个标准 Web 服务接口，可用于将位置信息服务连接到与 MAC 地址与端口和交换机信息匹配的简单网络管理协议 (SNMP) 应用程序。</span><span class="sxs-lookup"><span data-stu-id="de53c-105">Skype for Business Server includes a standard web service interface that you can use to connect the Location Information service to Simple Network Management Protocol (SNMP) applications that match MAC addresses with port and switch information.</span></span> 
  
<span data-ttu-id="de53c-106">如果安装了 SNMP 应用程序，而位置信息服务在位置数据库中找不到匹配项，则位置信息服务将自动使用客户端提供的 MAC 地址查询该应用程序。</span><span class="sxs-lookup"><span data-stu-id="de53c-106">If an SNMP application is installed and the Location Information service fails to find a match in the location database, the Location Information service automatically queries the application by using the MAC address provided by the client.</span></span> <span data-ttu-id="de53c-107">然后，位置信息服务使用 SNMP 应用程序返回的端口和交换机信息再次查询位置数据库。</span><span class="sxs-lookup"><span data-stu-id="de53c-107">The Location Information service then uses the port and switch information returned by the SNMP application to query the location database again.</span></span>
  
> [!NOTE]
> <span data-ttu-id="de53c-108">MAC 地址在运行 Windows 8 的计算机上不可用。</span><span class="sxs-lookup"><span data-stu-id="de53c-108">MAC addresses are not available on computers running Windows 8.</span></span> 
  
### <a name="to-configure-the-snmp-application-url"></a><span data-ttu-id="de53c-109">配置 SNMP 应用程序 URL</span><span class="sxs-lookup"><span data-stu-id="de53c-109">To configure the SNMP application URL</span></span>

1.  <span data-ttu-id="de53c-110">启动 Skype for Business Server命令行管理程序：单击"开始"，**单击"所有** 程序"，再单击 **"Skype for Business 2015"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**</span><span class="sxs-lookup"><span data-stu-id="de53c-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="de53c-111">运行以下 cmdlet 为 SNMP 应用程序配置 URL。</span><span class="sxs-lookup"><span data-stu-id="de53c-111">Run the following cmdlet to configure the URL for the SNMP application.</span></span> 
    
   ```powershell
   Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 
   ```

## <a name="see-also"></a><span data-ttu-id="de53c-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="de53c-112">See also</span></span>

[<span data-ttu-id="de53c-113">Set-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="de53c-113">Set-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

