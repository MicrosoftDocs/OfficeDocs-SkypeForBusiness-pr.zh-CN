---
title: 在 Skype for Business 中部署 SEFAUtil 工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 在 Skype for Business Server 中部署 SEFAUtil 工具。
ms.openlocfilehash: 306e2ec305e9e12cd3486691b3e239e2aedfb548
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "41986807"
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business"></a>在 Skype for Business 中部署 SEFAUtil 工具
 
在 Skype for Business Server 中部署 SEFAUtil 工具。
  
若要部署和管理组呼叫应答，您需要使用 Skype for Business Server 版本的 SEFAUtil 工具。 
  
> [!IMPORTANT]
> Microsoft 统一通信托管 API （UCMA）5运行时必须安装在您计划运行 SEFAUtil 工具的任何计算机上。 请在此处下载：[统一通信托管 API 5.0 运行时](https://www.microsoft.com/download/details.aspx?id=47344)。 您还可以从以下位置下载包含运行时的 UCMA 5 SDK： [UCMA 5.0 sdk](https://www.microsoft.com/download/details.aspx?id=47345)。
  
您可以在部署中的任何前端池中运行 SEFAUtil 工具。 若要运行 SEFAUtil 工具，必须在受信任的应用程序计算机上运行 "Skype for Business 部署" 向导中的步骤1、2和3。 SEFAUtil 要求提供本地配置存储以及证书。
  
> [!NOTE]
> 有关运行 SEFAUtil 的更多详细信息，请参阅博客文章 "how[to Get SEFAUtil 正在运行？](https://go.microsoft.com/fwlink/?LinkId=278940)"。 
  
### <a name="to-deploy-sefautil"></a>部署 SEFAUtil

1. 登录到 Skype for Business Server 命令行管理程序作为 RTCUniversalServerAdmins 组的成员安装的计算机，或使用**委派安装权限**中所述的必要用户权限。
    
2. 启动 Skype for Business Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **skype for business 2015**"，然后单击 " **skype for business Server Management Shell**"。
    
3. SEFAUtil 工具只能在属于受信任应用程序池一部分的计算机上运行。 如果需要，请为计划运行 SEFAUtil 的前端池定义受信任的应用程序池。 在命令行中运行：
    
   ```powershell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```
    > [!NOTE]
    > 池 FQDN：将承载 SEFAUtil 应用程序的服务器或池的 FQDN （通常为 Skype for business 前端服务器或池）。
    > 池注册器 FQDN：与此应用程序池关联的 Skype for Business 前端服务器或池的 FQDN。
    > 池网站：此池所驻留的网站的网站 ID。

4. 将 SEFAUtil 工具定义为受信任的应用程序。 在命令行中运行：
    
   ```powershell
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
   ```

    > [!NOTE]
    > 如果需要，可以使用其他端口。 
  
5. 使用您的更改启用拓扑。 在命令行中运行：
    
   ```powershell
   Enable-CsTopology
   ```

6. 如果还没有，请从[该位置](https://www.microsoft.com/download/details.aspx?id=52631)下载 SEFAUtil 工具的 Skype For business Server 版本，并将其安装在您在步骤3中创建的受信任应用程序池。
    
7. 验证 SEFAUtil 工具是否正常运行，如下所示： 
    
    a. 从带有管理员权限的 Windows 命令提示符处运行该工具，以在部署中显示用户的呼叫转接设置。
    
    b. 显示用户的呼叫转接设置。 在命令行中运行：
    
   ```console
   SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
   ```

将显示用户的呼叫转接设置。
    

