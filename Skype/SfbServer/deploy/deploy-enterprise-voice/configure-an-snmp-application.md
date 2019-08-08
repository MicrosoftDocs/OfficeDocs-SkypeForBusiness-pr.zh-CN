---
title: 在 Skype for Business 服务器中配置 SNMP 应用程序
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
description: 在 Skype for business Server Enterprise Voice 中配置 SNMP 应用程序以使用 E9-1。
ms.openlocfilehash: 2462c7af4473f8c29cf0e068ddc86b391d7e1df2
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233719"
---
# <a name="configure-an-snmp-application-in-skype-for-business-server"></a><span data-ttu-id="54fc3-103">在 Skype for Business 服务器中配置 SNMP 应用程序</span><span class="sxs-lookup"><span data-stu-id="54fc3-103">Configure an SNMP application in Skype for Business Server</span></span>
 
<span data-ttu-id="54fc3-104">在 Skype for business Server Enterprise Voice 中配置 SNMP 应用程序以使用 E9-1。</span><span class="sxs-lookup"><span data-stu-id="54fc3-104">Configure an SNMP application to work with E9-1-1 in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="54fc3-105">Skype for Business 服务器包括一个标准的 web 服务接口, 可用于将 Location 信息服务连接到与端口和交换机信息相匹配的 MAC 地址的简单网络管理协议 (SNMP) 应用程序。</span><span class="sxs-lookup"><span data-stu-id="54fc3-105">Skype for Business Server includes a standard web service interface that you can use to connect the Location Information service to Simple Network Management Protocol (SNMP) applications that match MAC addresses with port and switch information.</span></span> 
  
<span data-ttu-id="54fc3-106">如果已安装 SNMP 应用程序, 并且位置信息服务无法在位置数据库中找到匹配项, 则位置信息服务将使用客户端提供的 MAC 地址自动查询应用程序。</span><span class="sxs-lookup"><span data-stu-id="54fc3-106">If an SNMP application is installed and the Location Information service fails to find a match in the location database, the Location Information service automatically queries the application by using the MAC address provided by the client.</span></span> <span data-ttu-id="54fc3-107">然后, 位置信息服务使用 SNMP 应用程序返回的端口和交换信息再次查询位置数据库。</span><span class="sxs-lookup"><span data-stu-id="54fc3-107">The Location Information service then uses the port and switch information returned by the SNMP application to query the location database again.</span></span>
  
> [!NOTE]
> <span data-ttu-id="54fc3-108">MAC 地址在运行 Windows 8 的计算机上不可用。</span><span class="sxs-lookup"><span data-stu-id="54fc3-108">MAC addresses are not available on computers running Windows 8.</span></span> 
  
### <a name="to-configure-the-snmp-application-url"></a><span data-ttu-id="54fc3-109">配置 SNMP 应用程序 URL</span><span class="sxs-lookup"><span data-stu-id="54fc3-109">To configure the SNMP application URL</span></span>

1.  <span data-ttu-id="54fc3-110">启动 Skype for Business Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\* 和“Skype for Business 2015”\*\*\*\*，然后单击“Skype for Business Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="54fc3-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="54fc3-111">运行以下 cmdlet 为 SNMP 应用程序配置 URL。</span><span class="sxs-lookup"><span data-stu-id="54fc3-111">Run the following cmdlet to configure the URL for the SNMP application.</span></span> 
    
   ```
   Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 
   ```

## <a name="see-also"></a><span data-ttu-id="54fc3-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="54fc3-112">See also</span></span>

[<span data-ttu-id="54fc3-113">Set-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="54fc3-113">Set-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

