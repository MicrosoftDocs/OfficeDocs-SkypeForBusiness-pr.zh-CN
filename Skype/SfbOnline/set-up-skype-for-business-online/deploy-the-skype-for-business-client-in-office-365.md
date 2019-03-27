---
title: 部署 Office 365 中的商业客户端 Skype
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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: '了解如何规划和部署 Skype for Business 中小型、 中型和大型组织，并使其可供您的用户。 '
ms.openlocfilehash: 6dccd022d82519c1dfdce13f767e5b0a2531eb10
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30896790"
---
# <a name="deploy-the-skype-for-business-client-in-office-365"></a>部署 Office 365 中的商业客户端 Skype

本文介绍如何**[管理](https://support.office.com/en-us/article/eac4d046-1afd-4f1a-85fc-8219c79e1504?ui=en-US&rs=en-US&ad=US)**，您可以业务应用程序 Skype 的人在组织中部署的选项。
  
在部署 Skype 的业务给用户，请确保之前您已完成[设置业务 online Skype](set-up-skype-for-business-online.md)一文中的步骤 1-3。 这种方式，Skype for Business 将设置与您的域、 每个人都将其许可证，并且您将已配置 IM 和[Skype 业务 online 中的 Configure 状态](configure-presence-in-skype-for-business-online.md)为您的组织。
  
> [!NOTE]
> 对于安装 Skype 业务应用程序的用户，他们需要在其计算机或设备上的本地管理员。 或，他们将需要是可以在其计算机或设备安装应用程序的本地组的一部分。 如果不允许用户在其设备上安装软件，您将需要这些安装业务应用程序 Skype。 
  
## <a name="for-most-small-and-medium-sized-businesses"></a>对于大多数小型和中型企业

 **分步安装说明：** 如果您有小型或中型企业，我们建议您只要求用户在 PC 上安装 Skype 业务应用程序。 其指向以下说明：[安装 for Business 的 Skype](https://support.office.com/en-us/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb?ui=en-US&rs=en-US&ad=US)。 如果他们使用的 Mac，其指向[Lync for Mac 2011 for Office 365 设置](https://support.office.com/en-us/article/ae3ebd0e-a1a7-48cf-9350-36b144dc5f88?ui=en-US&rs=en-US&ad=US)。 为业务应用程序 Skype 是 Office 应用程序的其余单独进行安装。
  
 **Office 365 ProPlus 客户：** 如果您的业务使用的包含 Office 365 ProPlus，如 E3 计划的 Office 365 计划，业务应用程序 Skype 安装在同一时间用户下载并安装 Word、 Excel、 PowerPoint 等。这也意味着他们不能卸载 for Business 的 Skype，除非他们卸载所有 Office。
  
### <a name="choose-whether-to-make-skype-for-business-available-to-your-users"></a>选择是否向用户提供 Skype for Business

作为[管理员](https://support.office.com/en-us/article/eac4d046-1afd-4f1a-85fc-8219c79e1504?ui=en-US&rs=en-US&ad=US)，则可以选择是否向用户提供 Skype 业务应用程序。
  
- **控制是否贵公司中的每个人获取本软件**： 登录到 Office 365 管理中心，转到**安装我软件**，然后选择您需要为可供用户的软件。
    
    ![选择您想要向您的公司内的人员提供的软件。](../images/5eb9e9d4-6ea2-4cc1-a61d-8a1af5a7c121.png)
  
- **若要控制是否贵公司中的特定人员获取本软件**： 登录到 Office 365 管理中心，转到**用户** > **活动用户**中，选择您想要授予对软件，访问权限的人员，然后单击**编辑****产品许可证**旁边和打开或关闭的许可证。
    
    ![选择希望用户访问的软件。](../images/91f6f422-2c85-4afd-944f-0021b2f6f109.png)
  
> [!NOTE]
> 如果您需要以查看哪些计划已分配给您的组织中的人员，登录到新的 Office 365 admin center >**用户** > **活动用户**。 从列表中选择联系人，然后在**产品许可证**下查看。 如果您使用的经典的 Office 365 管理中心，查看**已分配许可证**下。 
  
### <a name="manually-deploying-skype-for-business-to-your-users"></a>手动部署到您的用户的 Skype for Business
<a name="bkmk_manual_1"> </a>

如果您希望用户从您网络，而不是从 Internet 上的某个位置安装 Skype 业务应用程序，您可以下载安装程序文件。 为此，请转到 Office 365 管理中心的**手动部署用户软件**部分。 然后，您可以选择**安装**，并将安装程序.exe 文件保存到网络位置。
  
另一种选择是下载 Skype 为您的用户的基本业务应用程序。 您可以下载[Microsoft Skype 的业务基本 （32 或 64 位）](https://www.microsoft.com/en-us/download/details.aspx?id=49440)。
  
为这两个完整和基本 Skype 业务应用程序，您已下载的安装文件之后, 您将需要手动 （例如，在电子邮件） 的网络路径向用户发送使其可以运行安装程序在其计算机上安装的应用程序。
  
您可以使用这些下载到您的用户的企业应用程序的 Skype 部署通过使用您现有软件部署工具和过程。
  
## <a name="for-larger-and-enterprise-organizations"></a>对于较大和企业组织

> [!NOTE]
> 本节仅适用于企业应用程序可以通过 Office 365 计划的 Skype。 如果您的组织使用 Skype 的批量许可版本的业务应用程序，它是基于 Windows Installer (MSI)，请参阅[中的业务服务器 2015 Skype 的自定义客户端安装](https://technet.microsoft.com/en-us/library/jj204934.aspx)。 
  
在很多企业或大型组织，不允许用户在其计算机上安装软件。 相反，IT 部门将必需的软件部署到用户的计算机。 IT 部门还可能希望控制在其组织中，使用，因此他们想要从附近位置而不是从其网络上安装软件，通过 Internet 或在公司网络的 Internet 或网络带宽量。
  
与 Office 365，您必须部署企业应用程序的 Skype，如果您希望控制从安装了多个选项。 一些这些选项包括：
  
- 为业务应用程序 Skype 到本地网络从下载 Office 365 管理中心中，[手动部署到您的用户的业务的 Skype](deploy-the-skype-for-business-client-in-office-365.md#bkmk_manual_1)中所述。
    
- 使用**[Office 部署工具](https://go.microsoft.com/fwlink/p/?LinkID=626065)** 下载 Office 365 ProPlus 或业务应用程序 Skype 到本地网络。 然后，使用 Office 部署工具部署到您的用户的应用程序。 Office 部署工具使您能够控制的部署，如语言和版本 （32 位或 64 位） 的某些方面。
    
- 使用现有软件部署工具和流程，例如 System Center Configuration Manager 中，向用户部署 Office 365 ProPlus 或企业应用程序的 Skype。 与[Office 部署工具](https://go.microsoft.com/fwlink/p/?LinkID=626065)或已从 Office 365 管理中心下载软件，您可以使用您现有的工具和流程。
    
### <a name="more-info-on-using-the-office-deployment-tool"></a>使用 Office 部署工具的详细信息

有关下载 Office 部署工具和安装 Skype 业务应用程序和其他 Office 365 客户端应用程序的详细信息的详细信息，请参阅[Office 365 中的管理用户软件](https://support.office.com/en-us/article/c13051e6-f75c-4737-bc0d-7685dcedf360)。
  
下面是使用 Office 部署工具部署应用程序所涉及的步骤概述：
  
1. Microsoft 下载中心**[下载最新的 Office 部署工具](https://www.microsoft.com/en-us/download/details.aspx?id=49117)**。
    
2. 创建将与 Office 部署工具的客户端应用程序需要的设置，例如设置版本 （32 位或 64 位）、 安装语言等一起使用的 configuration.xml 文件。
    
3. 使用 Office 部署工具和 configuration.xml 文件下载到您的本地域或内部网络从 Office 内容交付网络 (CDN) 的安装程序文件。
    
4. 使用 Office 部署工具和 configuration.xml 安装 Office 客户端应用程序，包括企业应用程序的 Skype。
    
有关使用 Office 部署工具和 configuration.xml 文件的详细信息，请参阅以下文章：
  
- [Office 部署工具概述 （英文)](https://technet.microsoft.com/library/jj219422.aspx)
    
- [Configuration.xml 设置](https://technet.microsoft.com/library/jj219426.aspx)
    
### <a name="more-info-on-using-system-center-configuration-manager"></a>使用 System Center Configuration Manager 的详细信息

您可以使用您现有软件部署工具和流程，例如 System Center Configuration Manager 中，部署 Skype 业务应用程序。 与您从 Office 365 管理中心下载的任一软件或 Office 部署工具，可以使用这些工具和流程。
  
有关使用 Configuration Manager 部署软件的详细信息，请参阅以下文章：
  
- [如何创建在配置管理器中的应用程序](https://technet.microsoft.com/en-us/library/gg682159.aspx)
    
- [如何部署应用程序在配置管理器](https://technet.microsoft.com/en-us/library/gg682082.aspx)
    
如果您正在部署一部分的业务应用程序 Skype 的部署 Office 365 ProPlus，请参阅[部署 Office 365 ProPlus 使用 System Center Configuration Manager](https://technet.microsoft.com/en-us/library/dn708063.aspx)。
  
## <a name="planning-for-updates-to-the-skype-for-business-app"></a>规划企业应用程序的 Skype 更新

作为部署业务应用程序 Skype 的一部分，您需要考虑希望如何获取更新之后安装 for Business 的 Skype。 新功能、 安全更新或非安全更新，例如提供稳定性或性能改进更新，则可以包括这些更新。 是您需要考虑的两个主要方面：
  
- 要在其中获取从更新
    
- 要获取功能更新频率如何
    
尽管您可以控制您在哪里找到来自更新和获取功能更新的频率，不能选择哪个特定安全更新或您获取的非安全更新。
  
 **获取从更新的位置**
  
默认情况下安装 Skype 业务应用程序后，更新将自动下载来自 Internet 时 Microsoft 提供的。 如果需要更多控制通过更新发生时，或者如果已从安装这些更新，您可以使用 Office 部署工具或组策略来配置它。
  
例如，许多组织希望在整个组织中部署它们之前测试更新一组用户。 您可以通过使用 Office 部署工具或组策略配置为业务应用程序 Skype，若要从 Internet 自动而不是获取来自您的网络上的特定位置更新来执行此操作。 然后，可以使用 Office 部署工具将每月更新下载到本地网络。
  
有关 Office 365 的软件更新的工作原理的详细信息，请参阅以下文章：
  
- [Office 365 ProPlus 的更新过程的概述](https://technet.microsoft.com/en-us/library/dn761709.aspx)
    
- [选择如何管理对 Office 365 ProPlus 的更新](https://technet.microsoft.com/en-us/library/dn761707.aspx)
    
- [配置 Office 365 ProPlus 的更新设置](https://technet.microsoft.com/en-us/library/dn761708.aspx)
    
  **如何通常来获取功能更新**
  
除了其中收到来自更新，您还可以控制的新功能获得业务客户端 Skype 频率。 两个选项如下所示：
  
- 获取功能更新每个月，如果有新功能
    
- 获取功能更新每个六个月
    
对于某些组织，他们希望测试新功能，以便他们想要获取功能更新仅两次而不是每月一年的时间。
  
您可以控制通过使用 Office 部署工具或组策略配置更新通道获取功能更新频率。 每月通道提供您的功能更新每月 （大约），而半年通道为您提供了功能更新每个六个月。 有关通道的详细信息，请参阅[Overview of Office 365 ProPlus 的更新通道](https://support.office.com/article/9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4)。
  
## <a name="related-topics"></a>相关主题

[设置 Skype for Business Online](set-up-skype-for-business-online.md)
  
[Skype for Business 和 Microsoft Teams 外接程序许可](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
 
