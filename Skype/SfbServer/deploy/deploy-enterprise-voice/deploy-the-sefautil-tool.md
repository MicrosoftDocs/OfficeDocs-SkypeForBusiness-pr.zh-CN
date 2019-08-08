---
title: 在 Skype for Business 中部署 SEFAUtil 工具
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
ms.assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
description: 在 Skype for Business 服务器中部署 SEFAUtil 工具。
ms.openlocfilehash: 1721f4d611a08a3054366e36b0ec9a3ebccf6c78
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245387"
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business"></a>在 Skype for Business 中部署 SEFAUtil 工具
 
在 Skype for Business 服务器中部署 SEFAUtil 工具。
  
若要部署和管理组呼叫, 您需要使用 SEFAUtil 工具的 Skype for business 服务器版本。 
  
> [!IMPORTANT]
> Microsoft 统一通信托管 API (UCMA) 5 运行时必须安装在你计划运行 SEFAUtil 工具的任何计算机上。 请在此处下载:[统一通信托管 API 5.0 运行时](https://www.microsoft.com/en-us/download/details.aspx?id=47344)。 你还可以下载 UCMA 5 SDK, 其中包括运行时, 如下所示: [UCMA 5.0 sdk](https://www.microsoft.com/en-us/download/details.aspx?id=47345)。
  
你可以在部署的任何前端池中运行 SEFAUtil 工具。 若要运行 SEFAUtil 工具, 必须从受信任的应用程序计算机上的 "Skype for Business 部署" 向导中运行步骤1、2和3。 SEFAUtil 要求存在本地配置存储以及证书。
  
> [!NOTE]
> 有关运行 SEFAUtil 的更多详细信息, 请参阅博客文章 "[如何获取 SEFAUtil 运行？](https://go.microsoft.com/fwlink/?LinkId=278940)"。 
  
### <a name="to-deploy-sefautil"></a>部署 SEFAUtil

1. 登录到将 Skype for Business Server Management Shell 作为 RTCUniversalServerAdmins 组的成员或必要的用户权限 (如 "**委派设置权限**" 中所述) 进行安装的计算机。
    
2. 启动 Skype for Business Server 命令行管理程序：依次单击“开始”****、“所有程序”**** 和“Skype for Business 2015”****，然后单击“Skype for Business Server 命令行管理程序”****。
    
3. SEFAUtil 工具只能在属于受信任应用程序池的一部分的计算机上运行。 如果需要, 请为计划运行 SEFAUtil 的前端池定义受信任的应用程序池。 在命令行中运行：
    
   ```
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```
    > [!NOTE]
    > 池 FQDN: 将托管 SEFAUtil 应用程序 (通常是 Skype for business 前端服务器或池) 的服务器或池的 FQDN。
    > 池注册机构 FQDN: 与此应用程序池关联的 Skype for business 前端服务器或池的 FQDN。
    > 池网站: 此池所驻留的网站的网站 ID。

4. 将 SEFAUtil 工具定义为受信任应用程序。在命令行中运行：
    
   ```
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
   ```

    > [!NOTE]
    > 如有需要，您可以使用其他端口。 
  
5. 启用包含您的更改的拓扑。在命令行中运行：
    
   ```
   Enable-CsTopology
   ```

6. 如果尚未安装, 请从[该位置](https://www.microsoft.com/en-us/download/details.aspx?id=52631)下载 SEFAUtil 工具的 Skype For business 服务器版本, 并将其安装在您在步骤3中创建的受信任的应用程序池中。
    
7. 验证 SEFAUtil 工具是否正常运行，如下所示： 
    
    a. 使用管理员权限从 Windows 命令提示符处运行该工具以在您的部署中显示用户的呼叫转接设置。
    
    b. 显示用户的呼叫转接设置。 在命令行中运行：
    
   ```
   SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
   ```

将显示用户的呼叫转接设置。
    

