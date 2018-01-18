---
title: "部署 Office 365 中的业务客户端的 Skype"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 8c563b81-22c9-4024-9efe-9fe28c7bbc96
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: Setup
description: "了解如何规划和部署业务的 Skype 在小型、 中型和大型企业，并将它们提供给您的用户。 "
ms.openlocfilehash: bbcbc632110ea466d6a3fdf566c6f3498e3bd751
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/15/2017
---
# <a name="deploy-the-skype-for-business-client-in-office-365"></a>部署 Office 365 中的业务客户端的 Skype

本文介绍了如何，**[管理](https://support.office.com/en-us/article/eac4d046-1afd-4f1a-85fc-8219c79e1504?ui=en-US&rs=en-US&ad=US)**，部署业务应用程序为 Skype 的人在组织中的选项。
  
对于业务用户，请确保部署 Skype 之前所做的[设置 Skype 业务在线](set-up-skype-for-business-online.md)文章中的步骤 1-3。 这样一来，Skype 业务将设置为与您的域，每个人都将拥有其许可证，并且您将已配置即时消息和[Skype 的在线业务中的配置状态](configure-presence-in-skype-for-business-online.md)为您的组织。
  
> [!NOTE]
> 对于安装 Skype 的业务应用程序的用户，他们需要将其 PC 或设备上的本地管理员。 或者他们需要将可以在他们的 PC 或设备安装应用程序的本地组的一部分。 如果您的用户不会允许在其设备上安装软件，您需要为它们安装 Skype 的业务应用程序。 
  
## <a name="for-most-small-and-medium-sized-businesses"></a>对于大多数小型和中型企业

 **的逐步安装说明：**如果您有小型或中等规模的业务，我们建议您只需要求用户在其 PC 上安装 Skype 的业务应用程序。 其指向这些说明：[企业安装 Skype](https://support.office.com/en-us/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb?ui=en-US&rs=en-US&ad=US)。 如果他们使用的 Mac，其指向[设置 Office 365 的 Mac 2011 的 Lync](https://support.office.com/en-us/article/ae3ebd0e-a1a7-48cf-9350-36b144dc5f88?ui=en-US&rs=en-US&ad=US)。 Skype 的业务应用程序是 Office 应用程序的其余部分分开安装。
  
 **Office 365 ProPlus 的客户：**如果您的业务使用例如 E3 计划包括 Office 365 ProPlus Office 365 计划，Skype 的业务应用程序被安装在同一时间，您的用户下载和安装 Word、 Excel、 PowerPoint 等。这也意味着他们不能卸载 Skype 的业务，除非它们卸载所有办公室。
  
### <a name="choose-whether-to-make-skype-for-business-available-to-your-users"></a>选择是否要让用户 Skype 业务

[管理员](https://support.office.com/en-us/article/eac4d046-1afd-4f1a-85fc-8219c79e1504?ui=en-US&rs=en-US&ad=US)可以选择是否让用户 Skype 为业务应用程序。
  
- **控制是否在公司中的每个人都获取软件**： 登录到 Office 365 管理中心，转至**安装软件**，然后选择您想要为用户提供的软件。
    
    ![选择您想要向您的公司中的人员提供的软件。](../images/5eb9e9d4-6ea2-4cc1-a61d-8a1af5a7c121.png)
  
- **控制是否在您公司的特定人员获取软件**： 登录到 Office 365 管理的中心，请转到**用户** > **活动用户**，选择您想要让软件，访问者，然后单击**编辑****产品许可证**旁边并打开或关闭该许可证。
    
    ![选择您希望用户可以访问哪些软件。](../images/91f6f422-2c85-4afd-944f-0021b2f6f109.png)
  
> [!NOTE]
> 如果您需要查看分配给组织中的人员方面有何计划，登录到新的 Office 365 管理中心 >**用户** > **活动的用户**。 从列表中选择此人然后看看下面的**产品许可证**。 如果您使用的经典的 Office 365 管理中心，看下**分配许可证**。 
  
### <a name="manually-deploying-skype-for-business-to-your-users"></a>手动部署到您的用户的 Skype 业务
<a name="bkmk_manual_1"> </a>

如果您希望用户从互联网而不是您的网络上的某个位置安装 Skype 的业务应用程序，您可以下载安装程序文件。 为此，请转到 Office 365 管理中心**手动部署用户软件**部分。 然后可以选择**安装**，并将安装程序.exe 文件保存到网络位置。
  
另一种方法是下载 Skype 业务基本应用程序为您的用户。 您可以下载[Microsoft Skype 的基本业务 （32 或 64 位）](https://www.microsoft.com/en-us/download/details.aspx?id=49440)。
  
为两个完整和基本 Skype 的业务应用程序，您下载的安装文件之后, 您需要手动发送 （例如，电子邮件） 中的网络路径的用户使其可以运行安装程序以在其计算机上安装该应用程序。
  
这些下载内容还可用于使用您现有的软件部署工具和流程部署到您的用户 Skype 为业务应用程序。
  
## <a name="for-larger-and-enterprise-organizations"></a>对于较大和企业公司

> [!NOTE]
> 此部分仅适用于为业务应用程序可通过 Office 365 计划 Skype。 如果您的组织使用的业务应用程序，它是基于 Windows 安装程序 (MSI)，Skype 的批量许可版本，请参阅[自定义客户端安装在商业服务器 2015年的 Skype](https://technet.microsoft.com/en-us/library/jj204934.aspx)。 
  
在很多企业或大型组织，不允许用户在其计算机上安装软件。 相反，IT 部门将所需的软件部署到用户的计算机。 IT 部门还可能需要控制互联网或网络使用的带宽量在其组织中，因此他们希望通过 Internet 或企业网络，从附近而不是从其网络位置安装软件。
  
与 Office 365 可以几个用于部署业务应用程序的 Skype，如果您想要控制从何处安装的选项。 这些选项包括：
  
- 下载 Skype 的业务应用程序到您的本地网络从 Office 365 管理中心，[手动部署业务用户的 Skype](deploy-the-skype-for-business-client-in-office-365.md#bkmk_manual_1)所述。
    
- 使用**[Office 部署工具](https://go.microsoft.com/fwlink/p/?LinkID=626065)**将 Office 365 ProPlus 或 Skype 的业务应用程序下载到您的本地网络。 然后，使用 Office 部署工具来将应用程序部署到您的用户。 Office 部署工具使您能够控制部署，如语言和版本 （32 位或 64 位） 的某些方面。
    
- 使用您的现有软件部署工具和进程，例如系统中心配置管理器中，可以将 Office 365 ProPlus 或 Skype 的业务应用程序部署到您的用户。 与[Office 部署工具](https://go.microsoft.com/fwlink/p/?LinkID=626065)或从 Office 365 管理中心已经下载的软件，可以使用您现有的工具和流程。
    
### <a name="more-info-on-using-the-office-deployment-tool"></a>有关使用 Office 部署工具的详细信息

有关下载 Office 部署工具和安装 Skype 业务应用程序和其他 Office 365 的客户端应用程序的详细信息的详细信息，请参阅[在 Office 365 管理用户软件](https://support.office.com/en-us/article/c13051e6-f75c-4737-bc0d-7685dcedf360)。
  
下面是使用 Office 部署工具来部署应用程序所涉及的步骤概述：
  
1. 从 Microsoft 下载中心**[下载最新的 Office 部署工具](https://www.microsoft.com/en-us/download/details.aspx?id=49117)**。
    
2. 创建 configuration.xml 文件用于 Office 部署工具中包含客户端应用程序所需的设置，如设置的版本 （32 位或 64 位）、 安装语言，等等。
    
3. 使用 Office 部署工具和 configuration.xml 文件将安装文件下载到您的本地或内部网络从 Office 内容传递网络 (CDN)。
    
4. 使用 Office 部署工具和 configuration.xml 安装 Office 客户端应用程序，包括 Skype 的业务应用程序。
    
有关使用 Office 部署工具和 configuration.xml 文件的详细信息，请参阅下列文章：
  
- [Office 部署工具概述](https://technet.microsoft.com/library/jj219422.aspx)
    
- [Configuration.xml 设置](https://technet.microsoft.com/library/jj219426.aspx)
    
### <a name="more-info-on-using-system-center-configuration-manager"></a>有关使用系统中心配置管理器的详细信息

您可以使用您现有的软件部署工具和流程，如系统中心配置管理器中，部署业务应用程序为 Skype。 与从 Office 365 管理中心下载的任何软件或 Office 部署工具，可以使用这些工具和进程。
  
有关使用配置管理器部署软件的详细信息，请参阅下列文章：
  
- [如何创建配置管理器中的应用](https://technet.microsoft.com/en-us/library/gg682159.aspx)
    
- [如何部署应用程序在配置管理器](https://technet.microsoft.com/en-us/library/gg682082.aspx)
    
如果您正在部署业务应用程序一部分的 Skype 的部署 Office 365 ProPlus，请参阅[部署 Office 365 ProPlus 使用系统中心配置管理器](https://technet.microsoft.com/en-us/library/dn708063.aspx)。
  
## <a name="planning-for-updates-to-the-skype-for-business-app"></a>规划对 Skype 的业务应用程序的更新

作为部署 Skype 的业务应用程序的一部分，您需要考虑要如何获取更新后安装 Skype 业务。 这些更新可以包括新功能、 安全更新、 与安全无关的更新，如提供稳定性和性能改进的更新。 您需要考虑的两个主要方面是：
  
- 要获得更新的位置
    
- 要获取功能更新频率如何
    
您可以控制您从何处获取更新和获取功能更新的频率，而不能选择的特定安全更新或您获得的非安全更新。
  
 **从何处获取更新**
  
默认情况下，安装 Skype 的业务应用程序之后，更新将自动下载从互联网时可从 Microsoft。 如果需要更多的控制通过更新发生时或在从已安装这些更新，可以使用 Office 部署工具或组策略来配置它。
  
例如，许多组织都希望在整个组织部署之前测试的一组用户更新。 您可以使用 Office 部署工具或组策略配置为业务应用程序自动从 Internet 获取而不是从您的网络上的特定位置更新 Skype 来执行此操作。 然后，可以使用 Office 部署工具将每月更新下载到您的本地网络。
  
有关 Office 365 提供软件更新如何工作的详细信息，请参阅下列文章：
  
- [对于 Office 365 ProPlus 更新过程概述](https://technet.microsoft.com/en-us/library/dn761709.aspx)
    
- [选择如何管理对 Office 365 ProPlus 更新](https://technet.microsoft.com/en-us/library/dn761707.aspx)
    
- [配置更新设置 Office 365 ProPlus](https://technet.microsoft.com/en-us/library/dn761708.aspx)
    
 **如何经常获取功能更新**
  
除了哪里您获取更新，您还可以控制新功能获得 Skype 业务客户端的频率。 两个选项如下所示：
  
- 获取功能更新每个月，如果有新功能
    
- 获取功能更新每六个月
    
对于一些组织来说，他们想要测试新的功能，所以他们想要获取功能更新只每年两次而不是每个月的时间。
  
您可以控制通过使用 Office 部署工具或组策略来配置更新通道获取功能更新的频率。 您的功能更新每月 （大约），而半年通道为您提供了每月一次通道使功能更新每六个月。 有关通道的详细信息，请参阅[Office 365 ProPlus 更新通道的概述](https://support.office.com/article/9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4)。
  
## <a name="related-topics"></a>相关主题

[设置 Skype for Business Online](set-up-skype-for-business-online.md)
  
[Skype 的附加业务和 Microsoft 小组授权](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  

