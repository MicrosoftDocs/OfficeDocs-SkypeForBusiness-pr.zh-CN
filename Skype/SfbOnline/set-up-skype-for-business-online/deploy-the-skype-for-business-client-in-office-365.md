---
title: 在 Office 365 中部署 Skype for Business 客户端
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 8c563b81-22c9-4024-9efe-9fe28c7bbc96
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: '了解如何在小型、中型和大型组织中规划和部署 Skype for Business, 并让你的用户可以使用它。 '
ms.openlocfilehash: b6895a45f59de2c73e445c7c26345f3b3d191a5f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34285281"
---
# <a name="deploy-the-skype-for-business-client-in-office-365"></a>在 Office 365 中部署 Skype for Business 客户端

本文介绍**[管理员](https://support.office.com/en-us/article/eac4d046-1afd-4f1a-85fc-8219c79e1504?ui=en-US&rs=en-US&ad=US)** 可如何将 Skype for business 应用部署到组织中的人员的选项。
  
在将 Skype for business 部署到你的用户之前, 请确保在本文[设置 skype For Business Online](set-up-skype-for-business-online.md)中执行了步骤1-3。 这样, 将为您的域设置 Skype for business, 每个人都将拥有自己的许可证, 并且您将在您的组织的[Skype for Business Online 中](configure-presence-in-skype-for-business-online.md)配置了 IM 并配置状态。
  
> [!NOTE]
> 对于要安装 Skype for Business 应用的用户, 他们需要在其 PC 或设备上是本地管理员。 或者, 它们必须是可在其电脑或设备上安装应用的本地组的一部分。 如果你的用户不能在其设备上安装软件, 你需要为其安装 Skype for Business 应用。 
  
## <a name="for-most-small-and-medium-sized-businesses"></a>适用于大多数小型企业和中等规模的企业

 **分步安装说明:** 如果您有小型企业或中型企业版, 我们建议您只需让用户在其 PC 上安装 Skype for Business 应用程序。 请点击以下说明:[安装 Skype For business](https://support.office.com/en-us/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb?ui=en-US&rs=en-US&ad=US)。 如果他们使用 Mac, 请将其指向为[Office 365 设置 Lync For Mac 2011](https://support.office.com/en-us/article/ae3ebd0e-a1a7-48cf-9350-36b144dc5f88?ui=en-US&rs=en-US&ad=US)。 Skype for Business 应用与其余 Office 应用分开安装。
  
 **Office 365 专业增强版客户:** 如果你的企业使用包含 Office 365 专业增强版的 Office 365 计划 (如 E3 计划), 则在你的用户下载和安装 Word、Excel、PowerPoint 等的同时安装 Skype for Business 应用。这还意味着他们无法卸载 Skype for Business, 除非他们卸载了所有的 Office。
  
### <a name="choose-whether-to-make-skype-for-business-available-to-your-users"></a>选择是否让你的用户可以使用 Skype for Business

作为[管理员](https://support.office.com/en-us/article/eac4d046-1afd-4f1a-85fc-8219c79e1504?ui=en-US&rs=en-US&ad=US), 你可以选择是否将 Skype for business 应用程序提供给你的用户。
  
- **控制公司中的每个人是否获取软件**: 登录到 Office 365 管理中心, 请转到 "**安装我的软件**", 然后选择要供用户使用的软件。
    
    ![选择您希望为公司中的人员提供的软件。](../images/5eb9e9d4-6ea2-4cc1-a61d-8a1af5a7c121.png)
  
- **若要控制贵公司中的特定人员是否获取软件**, 请执行以下操作: 登录到 Office 365 管理中心, 转到 "**用户** > **活动用户**", 选择要向其授予软件访问权限的人员, 然后单击 "**编辑**"在 "**产品许可证**" 旁边, 打开或关闭许可证。
    
    ![选择希望用户访问的软件。](../images/91f6f422-2c85-4afd-944f-0021b2f6f109.png)
  
> [!NOTE]
> 如果需要查看为组织中的人员分配了哪些计划, 请登录到新的 Office 365 管理中心 >**用户** > **活动用户**。 从列表中选择人员, 然后在 "**产品许可证**" 下查看。 如果您使用的是经典 Office 365 管理中心, 请在 "**分配的许可证**" 下查看。 
  
### <a name="manually-deploying-skype-for-business-to-your-users"></a>手动为用户部署 Skype for Business
<a name="bkmk_manual_1"> </a>

如果希望用户从网络上的某个位置 (而不是从 Internet) 安装 Skype for Business 应用, 可以下载安装程序文件。 若要执行此操作, 请转到 Office 365 管理中心的 "**手动部署用户软件**" 部分。 然后, 您可以选择 "**安装**并将 setup.exe 文件保存到网络位置"。
  
另一种方法是为你的用户下载 Skype for Business Basic 应用。 您可以下载[Microsoft Skype For Business Basic (32 或64位)](https://www.microsoft.com/en-us/download/details.aspx?id=49440)。
  
对于完整版和基本版 Skype for business 应用, 在下载安装程序文件之后, 你需要手动发送 (例如, 在电子邮件中) 用户的网络路径, 以便他们可以运行安装程序以在其计算机上安装该应用。
  
你还可以使用这些下载将 Skype for Business 应用部署到你的用户, 方法是使用现有软件部署工具和进程。
  
## <a name="for-larger-and-enterprise-organizations"></a>对于大型企业组织

> [!NOTE]
> 本部分仅适用于通过 Office 365 计划提供的 Skype for Business 应用。 如果你的组织使用的是基于 Windows Installer (MSI) 的 Skype for business 应用批量许可版本, 请参阅[在 Skype For Business Server 2015 中自定义客户端安装](https://technet.microsoft.com/en-us/library/jj204934.aspx)。 
  
在许多企业或大型组织中, 不允许用户在其计算机上安装软件。 相反, IT 部门将必要的软件部署到用户的计算机。 IT 部门还可能希望控制组织中使用的 Internet 或网络带宽量, 以便他们可以从网络上的附近位置 (而不是通过 Internet 或整个企业网络) 安装软件。
  
使用 Office 365, 如果要控制安装 Skype for Business 应用的位置, 则可以使用多个选项来部署 Skype for Business 应用。 其中一些选项包括以下内容:
  
- 将 Skype for Business 应用从 Office 365 管理中心下载到您的本地网络, 如[手动向用户部署 Skype for](deploy-the-skype-for-business-client-in-office-365.md#bkmk_manual_1)business 中所述。
    
- 使用**[Office 部署工具](https://go.microsoft.com/fwlink/p/?LinkID=626065)** 将 Office 365 专业增强版或 Skype for business 应用下载到您的本地网络。 然后, 使用 Office 部署工具将应用部署到你的用户。 Office 部署工具使你能够控制部署的某些方面, 例如语言和版本 (32 位或64位)。
    
- 使用现有软件部署工具和进程 (如 System Center Configuration Manager) 将 Office 365 专业增强版或 Skype for Business 应用部署到你的用户。 你可以将现有工具和进程与[Office 部署工具](https://go.microsoft.com/fwlink/p/?LinkID=626065)或从 office 365 管理中心下载的软件结合使用。
    
### <a name="more-info-on-using-the-office-deployment-tool"></a>有关使用 Office 部署工具的详细信息

有关下载 Office 部署工具的详细信息以及有关安装 Skype for Business 应用和其他 Office 365 客户端应用的详细信息, 请参阅[管理 Office 365 中的用户软件](https://support.office.com/en-us/article/c13051e6-f75c-4737-bc0d-7685dcedf360)。
  
下面概述了使用 Office 部署工具部署应用时所涉及的步骤:
  
1. 从 Microsoft 下载中心**[下载最新的 Office 部署工具](https://www.microsoft.com/en-us/download/details.aspx?id=49117)**。
    
2. 创建要与 Office 部署工具一起使用的 config.xml 文件, 该工具具有所需的客户端应用程序设置, 如设置版本 (32 位或64位)、安装语言等。
    
3. 使用 Office 部署工具和配置 .xml 文件, 从 Office 内容交付网络 (CDN) 将安装文件下载到本地或内部网络。
    
4. 使用 Office 部署工具和配置 .xml 安装 Office 客户端应用, 包括 Skype for Business 应用。
    
有关使用 Office 部署工具和配置 .xml 文件的详细信息, 请参阅以下文章:
  
- [Office 部署工具概述](https://technet.microsoft.com/library/jj219422.aspx)
    
- [配置 xml 设置](https://technet.microsoft.com/library/jj219426.aspx)
    
### <a name="more-info-on-using-system-center-configuration-manager"></a>有关使用 System Center Configuration Manager 的详细信息

你可以使用现有软件部署工具和进程 (如 System Center Configuration Manager) 部署 Skype for Business 应用。 你可以将这些工具和进程与从 Office 365 管理中心或 Office 部署工具下载的软件配合使用。
  
有关使用 Configuration Manager 部署软件的详细信息, 请参阅以下文章:
  
- [如何在 Configuration Manager 中创建应用程序](https://technet.microsoft.com/en-us/library/gg682159.aspx)
    
- [如何在 Configuration Manager 中部署应用程序](https://technet.microsoft.com/en-us/library/gg682082.aspx)
    
如果你要在部署 Office 365 专业增强版时部署 Skype for Business 应用, 请参阅[使用 System Center Configuration Manager 部署 office 365 专业增强版](https://technet.microsoft.com/en-us/library/dn708063.aspx)。
  
## <a name="planning-for-updates-to-the-skype-for-business-app"></a>规划 Skype for Business 应用更新

作为部署 Skype for Business 应用的一部分, 你需要考虑在安装 Skype for Business 后你希望如何获取更新。 这些更新可以包括新功能、安全更新或非安全更新, 例如提供稳定性或性能改进的更新。 需要考虑的两个主要方面是:
  
- 您希望从何处获取更新
    
- 你希望多长时间获取一项功能更新
    
虽然你可以控制从何处获取更新以及获取功能更新的频率, 但你无法选择获取哪些特定安全更新或非安全更新。
  
 **从何处获取更新**
  
默认情况下, 在安装 Skype for Business 应用后, 当 Microsoft 提供更新时, 将从 Internet 自动下载更新。 如果你希望更好地控制何时发生更新或安装更新的位置, 可以使用 Office 部署工具或组策略来配置。
  
例如, 许多组织希望先对一组用户测试更新, 然后再在整个组织中部署这些更新。 你可以通过使用 Office 部署工具或组策略将 Skype for Business 应用配置为从网络上的特定位置 (而不是从 Internet 自动) 获取更新来执行此操作。 然后, 你可以使用 Office 部署工具将每月的更新下载到本地网络。
  
有关 Office 365 软件的更新如何工作的详细信息, 请参阅以下文章:
  
- [Office 365 专业增强版更新流程概述](https://technet.microsoft.com/en-us/library/dn761709.aspx)
    
- [选择如何管理 Office 365 的更新专业增强版](https://technet.microsoft.com/en-us/library/dn761707.aspx)
    
- [配置 Office 365 的更新设置专业增强版](https://technet.microsoft.com/en-us/library/dn761708.aspx)
    
  **获取功能更新的频率**
  
除了从中获取更新的位置, 还可以控制为 Skype for business 客户端获取新功能的频率。 这两个选项如下所示:
  
- 如果有新功能, 则每月获取功能更新
    
- 获取功能每六个月更新一次
    
对于某些组织, 他们希望使用时间测试新功能, 以便他们只需一年的两次 (而不是每个月) 获取功能更新。
  
你可以通过使用 Office 部署工具或组策略配置更新通道来控制获取功能更新的频率。 每月频道为您提供每月 (大约) 的功能更新, 而半年度频道每六个月提供一次功能更新。 有关频道的详细信息, 请参阅[Office 365 专业增强版更新频道概述](https://support.office.com/article/9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4)。
  
## <a name="related-topics"></a>相关主题

[设置 Skype for Business Online](set-up-skype-for-business-online.md)
  
[Skype for Business 和 Microsoft Teams 外接程序许可](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
 
