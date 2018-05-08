---
title: 在 Skype for Business 2015 中部署 SEFAUtil 工具
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
description: 为业务 Server 部署中 Skype 的 SEFAUtil 工具。
ms.openlocfilehash: f0bb660218b761e513e120f4ea5786eb9278b12a
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business-2015"></a>在 Skype for Business 2015 中部署 SEFAUtil 工具
 
为业务 Server 部署中 Skype 的 SEFAUtil 工具。
  
部署和管理组呼叫分拣，您需要 Skype 用于业务服务器版本的 SEFAUtil 工具。 
  
> [!IMPORTANT]
> Microsoft 统一通信托管 API (UCMA) 3.0 核心 SDK 必须安装在您计划运行 SEFAUtil 工具的任何计算机上。 
  
在部署中，可以在任何前端池中运行 SEFAUtil 工具。
  
> [!NOTE]
> 有关运行 SEFAUtil，有关详细信息，请参阅 Technet 博客文章，"[如何获取 SEFAutil 运行？](https://go.microsoft.com/fwlink/?LinkId=278940)"。 
  
### <a name="to-deploy-sefautil"></a>部署 SEFAUtil

1. 登录到计算机的业务 Server Management Shell 的 Skype 或使用**Delegate Setup Permissions**中所述的必要用户权限的 RTCUniversalServerAdmins 组成员身份的安装。
    
2. 启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。
    
3. SEFAUtil 工具只能在属于受信任应用程序池的一部分的计算机上运行。 如果需要定义打算运行 SEFAUtil 的前端池的受信任应用程序池。 在命令行中运行：
    
   ```
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```

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

6. 如果尚未准备好，下载 Business Server 版 SEFAUtil 工具 Skype 从[该位置](https://www.microsoft.com/en-us/download/details.aspx?id=52631)，并安装您在步骤 3 中创建它的受信任应用程序池。
    
7. 验证 SEFAUtil 工具是否正常运行，如下所示： 
    
    a. 使用管理员权限从 Windows 命令提示符处运行该工具以在您的部署中显示用户的呼叫转接设置。
    
    b. 显示用户的呼叫转接设置。 在命令行中运行：
    
  ```
  SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
  ```

将显示用户的呼叫转接设置。
    

