---
title: 在部署中部署 SEFAUtil Skype for Business
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
ms.assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
description: 在 Skype for Business Server 中部署 SEFAUtil Skype for Business Server。
ms.openlocfilehash: 5683dab35a51a088b89f410c11bd0713a8256496f85d11c7190d44f82528a3c9
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54331864"
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business"></a>在部署中部署 SEFAUtil Skype for Business
 
在 Skype for Business Server 中部署 SEFAUtil Skype for Business Server。
  
若要部署和管理组呼叫接听，你需要使用 Skype for Business Server SEFAUtil 工具的版本。 
  
> [!IMPORTANT]
> 必须在计划运行 SEFAUtil (的任何计算机上安装 Microsoft 统一通信托管 API) UCMA) 5 运行时。 在此处下载 [：Unified Communications Managed API 5.0 Runtime](https://www.microsoft.com/download/details.aspx?id=47344)。 也可以在此处下载 UCMA 5 SDK，其中包括运行时[：UCMA 5.0 SDK。](https://www.microsoft.com/download/details.aspx?id=47345)
  
可以在部署中的任一前端池中运行 SEFAUtil 工具。 若要运行 SEFAUtil 工具，必须在受信任的应用程序计算机上从 Skype for Business 部署向导运行步骤 1、2 和 3。 SEFAUtil 要求存在本地配置存储以及证书。
  
> [!NOTE]
> 有关运行 SEFAUtil 的更多详细信息，请参阅博客文章"[如何运行 SEFAutil？"。](/archive/blogs/jenstr/how-to-get-sefautil-running) 
  
### <a name="to-deploy-sefautil"></a>部署 SEFAUtil

1. 以 RTCUniversalServerAdmins 组的成员或必要的用户权限（如D委托安装权限中所述）登录到安装了命令行管理程序Skype for Business Server **的计算机。**
    
2. 启动命令行Skype for Business Server：单击"开始"，单击"所有程序"，单击 **"Skype for Business 2015"，** 然后单击"Skype for Business Server **命令行管理程序"。**
    
3. SEFAUtil 工具只能在作为受信任证书的一部分的计算机上应用程序池。 如果需要，请为应用程序池 SEFAUtil 的前端池定义受信任池。 在命令行中运行：
    
   ```powershell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```
    > [!NOTE]
    > 池 FQDN：将承载 SEFAUtil 应用程序的服务器或池的 FQDN (通常是Skype for Business前端服务器或池) 。
    > 池注册器 FQDN：Skype for Business前端服务器或池的 FQDN 应用程序池。
    > 池站点：此池所位于的站点的站点 ID。

4. 将 SEFAUtil 工具定义为受信任的应用程序。 在命令行中运行：
    
   ```powershell
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
   ```

    > [!NOTE]
    > 如果需要，可以使用其他端口。 
  
5. 启用包含更改的拓扑。 在命令行中运行：
    
   ```powershell
   Enable-CsTopology
   ```

6. 如果尚未下载，请从此位置下载 Skype for Business Server 版本的 SEFAUtil 工具，并安装在[](https://www.microsoft.com/download/details.aspx?id=52631)步骤 3 中创建应用程序池受信任的证书上。
    
7. 验证 SEFAUtil 工具是否正常运行，如下所示： 
    
    a. 使用管理员权限Windows命令提示符中运行该工具，以显示部署中用户的呼叫转发设置。
    
    b. 显示用户的呼叫转发设置。 在命令行中运行：
    
   ```console
   SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
   ```

将显示用户的呼叫转发设置。
