---
title: "在 Office 365 中部署 Skype for Business 客户端"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/21/2017
ms.audience: Admin
ms.topic: get-started-article
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
- httpsfix
- LeftNav_IT_O365
ms.assetid: 8c563b81-22c9-4024-9efe-9fe28c7bbc96
description: "Learn how to plan and deploy Skype for Business in small, medium, and large organizations and making it available to your users. "
---

# 在 Office 365 中部署 Skype for Business 客户端

> [!IMPORTANT]
> 本文是由机器翻译的，请参阅[免责声明](8c563b81-22c9-4024-9efe-9fe28c7bbc96.md#MT_Footer)。请在 [此处](https://support.office.com/en-us/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96) 中查找本文的英文版本以便参考。
  
本文介绍作为 **[在 Office 365 中分配管理员角色](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)** 的你为你的组织内的用户部署 Skype for Business 应用的方法。
  
您将Skype for Business部署到您的用户之前，请确保您已完成文章[设置 Skype for Business Online](set-up-skype-for-business-online.md)中的步骤 1-3。这种方式， Skype for Business将设置与您的域，每个人都将其许可证，并且您将已配置即时消息和[在 Skype for Business Online 中配置状态](configure-presence-in-skype-for-business-online.md)为您的组织。
  
> [!NOTE]
> 为用户安装Skype for Business应用程序，他们需要在其计算机或设备上的本地管理员。或者，他们将需要可以在其计算机或设备安装的应用程序的本地组的一部分。如果您的用户不允许使用的设备上安装软件，您需要安装Skype for Business应用程序。 
  
## 对于大多数中小型企业

 **分步安装说明：** 如果您有小型企业版或中型企业版，我们建议您只需让用户在其 PC 上安装Skype for Business应用程序。指导他们访问这些说明：[安装 Skype for Business](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb)。如果他们使用的 Mac，指向这些[为 Office 365 设置 Lync for Mac 2011](https://support.office.com/article/ae3ebd0e-a1a7-48cf-9350-36b144dc5f88)。从 Office 应用程序的其余部分单独安装了Skype for Business应用。
  
 **Office 365 专业增强订阅版客户：** 如果您的企业使用的 Office 365 计划，如 E3 计划包括 Office 365 ProPlus， Skype for Business安装了应用，同时您的用户下载和安装 Word、 Excel、 PowerPoint 等。这也意味着他们不能卸载Skype for Business ，除非他们卸载所有 Office。
  
### 选择是否将 Skype for Business 提供给用户使用

作为[在 Office 365 中分配管理员角色](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)，您可以选择是否要为您的用户提供Skype for Business应用程序。
  
- **可以控制是否在您的公司中的每个人都可获取软件** ： 登录在到Office 365 管理中心，转到 **安装软件**，然后选择所需为可供用户的软件。
    
    ![Choose the software you want to make available to the people in your company.](../images/5eb9e9d4-6ea2-4cc1-a61d-8a1af5a7c121.png)
  
- **若要控制是否在您的公司中的特定人员获取软件** ： 登录到Office 365 管理中心中，转到 **用户**> **活动用户**，选择您想要授予对该软件，访问权限的人员，然后单击 **旁边的编辑产品许可证**和打开或关闭许可证。
    
    ![Choose which software you want the user to access.](../images/91f6f422-2c85-4afd-944f-0021b2f6f109.png)
  
> [!NOTE]
> 如果需要您可以看到哪种计划分配给您的组织中的用户登录到新Office 365 管理中心 > **用户**> **活动用户**。从列表中选择的人员，然后在 **产品许可证**下查找。如果您使用的经典Office 365 管理中心，查看在 **分配的许可证**下。 
  
### 手动为用户部署 Skype for Business
<a name="bkmk_manual_1"> </a>

如果您希望用户从您的网络而不是从 Internet 上的某个位置安装Skype for Business应用程序，您可以下载安装文件。为此，请转到Office 365 管理中心的 **手动部署用户软件**部分。然后，您可以选择 **安装**并设置.exe 文件保存到网络位置。
  
另一种选择是下载Skype for Business基本应用为您的用户。您可以下载[Microsoft Skype for Business 基本 （32 或 64 位）](https://www.microsoft.com/en-us/download/details.aspx?id=49440)。
  
两个的完整和基本Skype for Business应用程序，您下载安装文件时后，您将需要手动 （例如，在电子邮件） 的网络路径向用户发送使其可以运行安装程序在其计算机上安装应用程序。
  
你也可以使用这些下载通过现有软件部署工具和过程为用户部署 Skype for Business 应用。
  
## 对于较大和企业组织

> [!NOTE]
>  本节仅适用于通过 Office 365 计划提供的 Skype for Business 应用。如果你的组织使用的是 Skype for Business 应用的批量许可版本（其基于 Windows Installer (MSI)），请参阅[自定义 Skype for Business Server 2015 中的客户端安装](https://technet.microsoft.com/zh-cn/library/jj204934.aspx)。 
  
在许多企业或大型组织，不允许用户在其计算机上安装软件。相反，IT 部门部署到用户的计算机所需的软件。IT 部门也可能希望控制的 Internet 或网络带宽使用在其组织中，以便他们想要从附近的位置，而不是从其网络上安装软件，通过 Internet 或在公司网络。
  
使用 Office 365，您有几个选项用于部署Skype for Business应用程序，如果您想要控制从安装位置。这些选项的一些包括：
  
- 下载Skype for Business应用到您的本地网络Office 365 管理中心，从[手动部署到您的用户的商业版的 Skype](8c563b81-22c9-4024-9efe-9fe28c7bbc96.md#bkmk_manual)中所述。
    
- 使用 **[Office 部署工具](https://go.microsoft.com/fwlink/p/?LinkID=626065)** 下载到您的本地网络的 Office 365 专业增强订阅版或Skype for Business应用程序。然后，使用 Office 部署工具部署到您的用户的应用程序。Office 部署工具使您能够控制部署中，如语言和版本 （32 位或 64 位） 的某些方面。
    
- 使用您的现有软件部署工具和流程，如系统中心配置管理器中，将 Office 365 专业增强订阅版或Skype for Business应用部署到您的用户。使用[Office 部署工具](https://go.microsoft.com/fwlink/p/?LinkID=626065)或从Office 365 管理中心已下载的软件，您可以使用您现有的工具和流程。
    
### 有关使用 Office 部署工具的更多信息

有关下载 Office 部署工具的详细信息和有关安装 Skype for Business 应用和其他 Office 365 客户端应用的更多信息，请参阅[在 Office 365 中管理用户软件](https://support.office.com/article/365-c13051e6-f75c-4737-bc0d-7685dcedf360.aspx)。
  
下面是使用 Office 部署工具部署应用程序所涉及的步骤概述：
  
1. 从 Microsoft 下载中心 **[下载最新的 Office 部署工具](https://go.microsoft.com/fwlink/p/?LinkID=626065)** 。
    
2. 创建要与 Office 部署工具结合使用并且包含所需客户端应用设置的 configuration.xml 文件，例如，安装的版本（32 位或 64 位）、安装语言等等。
    
3. 使用 Office 部署工具和 configuration.xml 文件以从 Office 内容传递网络 (CDN) 将安装文件下载到本地或内部网络。
    
4. 使用 Office 部署工具和 configuration.xml 安装 Office 客户端应用程序，包括Skype for Business应用程序。
    
有关使用 Office 部署工具和 configuration.xml 文件的详细信息，请参阅以下文章：
  
- [Office 部署工具概述](https://technet.microsoft.com/library/jj219422.aspx)
    
- [Configuration.xml 设置](https://technet.microsoft.com/library/jj219426.aspx)
    
### 使用系统中心配置管理器的详细信息

您可以使用您的现有软件部署工具和流程，如系统中心配置管理器部署Skype for Business应用程序。使用任一软件从Office 365 管理中心下载或使用 Office 部署工具，可以使用这些工具和流程。
  
有关使用配置管理器部署软件的详细信息，请参阅下列文章：
  
- [如何在 Configuration Manager 中创建应用程序](https://technet.microsoft.com/zh-cn/library/gg682159.aspx)
    
- [如何在 Configuration Manager 中部署应用程序](https://technet.microsoft.com/zh-cn/library/gg682082.aspx)
    
如果您正在部署Skype for Business应用作为一部分的部署 Office 365 专业增强订阅版，请参阅[部署 Office 365 专业增强订阅版使用系统中心配置管理器](https://technet.microsoft.com/en-us/library/dn708063.aspx)。
  
## 规划 Skype for Business 应用的更新

作为部署Skype for Business应用程序的一部分，您需要考虑要如何在安装 Skype for Business 之后获取更新。新增功能、 安全更新或非安全更新，如提供稳定性和性能改进的更新，则可以包括这些更新。需要考虑的两个主要方面是：
  
- 要在其中获取的更新
    
- 要获取功能更新频率
    
时您可以控制您在哪里获取的更新和获取功能更新的频率，您无法选择哪个特定的安全更新或您收到的非安全更新。
  
 **从哪里获得更新**
  
默认情况下， Skype for Business应用安装后，更新将自动下载来自 Internet 时可从 Microsoft。如果需要更多的控制上方时进行更新，或从安装更新后的位置，您可以使用 Office 部署工具或组策略配置的。
  
例如，许多组织希望测试在整个组织部署之前的一组用户的更新。您可以通过使用 Office 部署工具或组策略配置Skype for Business应用程序自动从 Internet 获取而不是从您的网络上的特定位置的更新来执行此操作。然后，您可以使用 Office 部署工具以将每个月的更新下载到您的本地网络。
  
有关 Office 365 的软件更新如何工作的详细信息，请参阅以下文章：
  
- [Office 365 专业增强订阅版更新过程概述](https://technet.microsoft.com/library/dn761709.aspx)。
    
- [选择如何管理 Office 365 专业增强订阅版的更新](https://technet.microsoft.com/en-us/library/dn761707.aspx)
    
- [配置 Office 365 专业增强订阅版的更新设置](https://technet.microsoft.com/zh-cn/library/dn761708.aspx)
    
 **获取功能更新的频率**
  
除了您在哪里获取的更新，您可以控制频率的 Skype for Business 客户端中获取新功能。两个选择如下所示：
  
- 获取功能更新每个月，如果有新功能
    
- 获取功能更新每六个月
    
对于某些组织，他们想要以测试新功能，以便他们想要以获取功能更新仅两次，而不是每月一年的时间。
  
您可以控制通过使用 Office 部署工具或组策略配置更新通道来获取功能更新的频率。每月通道为您的功能更新每月 （大约），同时半年通道为您提供了功能每六个月的更新。有关通道的详细信息，请参阅[为 Office 365 专业增强订阅版更新通道概述](https://support.office.com/article/9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4)。
  
## 相关主题

[设置 Skype for Business Online](set-up-skype-for-business-online.md)
  
[Skype for Business 和 Microsoft 团队许可加载项](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **机器翻译免责声明**：本文是由无人工介入的计算机系统翻译的。Microsoft 提供机器翻译是为了帮助非英语国家/地区用户方便阅读有关 Microsoft 产品、服务和技术的内容。由于机器翻译的原因，本文可能包含词汇、语法或文法方面的错误。 
  

