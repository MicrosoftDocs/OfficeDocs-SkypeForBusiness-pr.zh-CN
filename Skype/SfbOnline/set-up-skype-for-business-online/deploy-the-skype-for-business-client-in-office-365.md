---
title: 在 Skype for Business 部署Microsoft 365客户端Office 365
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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: '了解如何在小型、中型Skype for Business组织中计划和部署客户，以及如何让用户使用。 '
ms.openlocfilehash: 3cfa319536c521ee4d0e3b297fd978071c93105d
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58589174"
---
# <a name="deploy-the-skype-for-business-client-in-microsoft-365-or-office-365"></a>在 Skype for Business 或 Office 365 中部署 Microsoft 365 客户端

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

本文介绍管理员如何向组织人员部署 Skype for Business **[](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)** 应用的选项。
  
在将 Skype for Business部署到用户之前，请确保已完成设置联机部署一文[Skype for Business 1-3。](set-up-skype-for-business-online.md) 这样，Skype for Business设置您的域，每个人都将拥有其许可证，并且您将为您的组织配置即时消息和配置 Skype for Business [Online](configure-presence-in-skype-for-business-online.md)中的状态。
  
> [!NOTE]
> 若要让用户安装 Skype for Business 应用，他们需要是电脑或设备上的本地管理员。 或者，他们需要是可以在电脑或设备上安装应用的本地组的一部分。 如果你的用户不允许在设备上安装软件，你需要为用户安装Skype for Business应用。 
  
## <a name="for-most-small-and-medium-sized-businesses"></a>适用于大多数中小型企业

 **分步安装说明：** 如果你有一家小型或中型企业，我们建议你直接要求用户Skype for Business电脑上安装该应用。 请指向以下说明：安装[Skype for Business。](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb) 如果他们使用的是 Mac，请将其指向"设置[Lync for Mac 2011 for Office 365"。](https://support.office.com/article/ae3ebd0e-a1a7-48cf-9350-36b144dc5f88) Skype for Business应用与应用的其余部分分开安装Office应用。
  
 **Microsoft 365 企业应用版客户：** 如果你的企业使用的是包含 Microsoft 365 企业应用版 的 Office 365 计划（如 E3 计划），则 Skype for Business 应用将同时安装，同时用户下载并安装 Word、Excel、PowerPoint 等。这也意味着他们无法卸载Skype for Business，除非卸载所有Office。
  
### <a name="choose-whether-to-make-skype-for-business-available-to-your-users"></a>选择是否Skype for Business用户可用

作为[管理员](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)，你可以选择是否向用户Skype for Business应用。
  
- **若要控制贵公司的每个人** 是否获取软件：登录到 Microsoft 365 管理中心，转到"安装 **我的** 软件"，然后选择希望可供用户使用的软件。
    
    ![选择要提供给公司人员的软件。](../images/5eb9e9d4-6ea2-4cc1-a61d-8a1af5a7c121.png)
  
- 要控制贵公司 **的特定** 人员是否获取软件：登录到 Microsoft 365 管理中心，转到"用户  >  **""** 活动用户"，选择要授予其软件访问权限的用户，然后单击"产品许可证"旁边的"编辑"，然后打开或关闭许可证。
    
    ![选择希望用户访问的软件。](../images/91f6f422-2c85-4afd-944f-0021b2f6f109.png)
  
> [!NOTE]
> 如果需要查看为组织人员分配了哪些计划，请登录到"用户Microsoft 365 管理中心 >  >  **活动用户"。** 从列表中选择人员，然后在"产品许可证 **"下查看**。 如果使用经典管理中心，请查找"分配的 **许可证"下**。 
  
### <a name="manually-deploying-skype-for-business-to-your-users"></a>手动将Skype for Business部署到用户
<a name="bkmk_manual_1"> </a>

如果希望用户从Skype for Business位置（而不是从 Internet）安装应用，可以下载安装文件。 为此，请转到本文的"**手动** 部署用户软件"Microsoft 365 管理中心。 然后，可以选择 **"安装** "，将安装程序.exe文件保存到网络位置。
  
另一个选项是Skype for Business基本应用。 可以下载[Microsoft Skype for Business Basic (32 或 64 位) 。 ](https://www.microsoft.com/download/details.aspx?id=49440)
  
对于完整和基本 Skype for Business 应用，下载安装文件后，需要手动发送 (，例如，在电子邮件) 中向用户发送网络路径，以便他们可以运行安装程序以将其安装在其计算机上。
  
也可使用这些下载，通过现有的软件部署工具和Skype for Business将应用部署到用户。
  
## <a name="for-larger-and-enterprise-organizations"></a>对于大型和企业组织

> [!NOTE]
> 本部分仅适用于通过Skype for Business计划Office 365应用。 如果组织使用的是 Skype for Business 应用的批量许可版本（基于安装程序的 (MSI Windows 版本) ，请参阅在 Skype for Business Server 中自定义[Windows 客户端安装](../../SfbServer/deploy/deploy-clients/customize-windows-client-installation.md)。
  
在许多企业或大型组织中，不允许用户在计算机上安装软件。 相反，IT 部门将必要的软件部署到用户的计算机。 IT 部门可能还希望控制其组织中使用的 Internet 或网络带宽量，因此他们希望从其网络中附近的位置安装软件，而不是通过 Internet 或公司网络安装软件。
  
使用 Office 365，如果要控制安装位置，Skype for Business多个选项来部署应用。 其中一些选项包括：
  
- 将 Skype for Business 应用从 Microsoft 365 管理中心 下载到本地网络，如手动将 Skype for Business[部署到用户 中所述](deploy-the-skype-for-business-client-in-office-365.md#bkmk_manual_1)。
    
- 使用 **[Office 部署工具](https://go.microsoft.com/fwlink/p/?LinkID=626065)** 将 Microsoft 365 企业应用版 或 Skype for Business 应用下载到本地网络。 然后，使用 Office 部署工具将应用部署到用户。 使用 Office 部署工具可以控制部署的某些方面，例如语言和版本 (32 位或 64 位) 。
    
- 使用现有的软件部署工具和过程（例如 Microsoft Endpoint Configuration Manager）Microsoft 365 企业应用版或 Skype for Business 应用。 可以将现有工具和过程与 Office[部署](https://go.microsoft.com/fwlink/p/?LinkID=626065)工具或从部署工具下载的软件Microsoft 365 管理中心。
    
### <a name="more-info-on-using-the-office-deployment-tool"></a>有关使用 Office 部署工具的信息

有关下载 Office 部署工具的详细信息以及安装 Skype for Business 应用和其他 Office 365 客户端应用的详细信息，请参阅在 Office 365[中管理软件下载设置](https://support.office.com/article/c13051e6-f75c-4737-bc0d-7685dcedf360)。
  
下面概述了使用 Office 部署工具部署应用时涉及的步骤：
  
1. **[从 Microsoft 下载Office](https://www.microsoft.com/download/details.aspx?id=49117)** 下载最新的部署工具。
    
2. 创建 configuration.xml 文件，该文件用于具有客户端应用设置的 Office 部署工具，例如设置 (32 位或 64 位) 版本、安装语言等。
    
3. 使用 Office 部署工具和 configuration.xml 文件将安装程序文件从本地或内部网络下载到 Office 内容分发网络 (CDN) 。
    
4. 使用 Office 部署工具和 configuration.xml 安装 Office 客户端应用，包括 Skype for Business 应用。
    
有关使用 Office 部署工具和configuration.xml的详细信息，请参阅以下文章：
  
- [Office部署工具概述](/deployoffice/overview-office-deployment-tool)
    
- [Configuration.xml设置](/deployoffice/office-deployment-tool-configuration-options)
    
### <a name="more-info-on-using-microsoft-endpoint-configuration-manager"></a>有关使用 Microsoft Endpoint Configuration Manager

可以使用现有的软件部署工具和进程（例如 Microsoft Endpoint Configuration Manager）来部署 Skype for Business 应用。 可以将这些工具和过程与从 Microsoft 365 管理中心 下载的软件一起使用，Office部署工具。
  
有关使用 Configuration Manager 部署软件的信息，请参阅以下文章：
  
- [在 Configuration Manager 中创建应用程序](/configmgr/apps/deploy-use/create-applications)
    
- [使用 Configuration Manager 部署应用程序](/configmgr/apps/deploy-use/deploy-applications)
    
如果在部署应用时Skype for Business部署 Microsoft 365 企业应用版，请参阅使用 Configuration Manager Microsoft 365 企业应用版[部署](/configmgr/sum/deploy-use/manage-office-365-proplus-updates)。
  
## <a name="planning-for-updates-to-the-skype-for-business-app"></a>计划更新 Skype for Business 应用

在部署 Skype for Business 应用时，需要考虑在安装更新后Skype for Business更新。 这些更新可能包括新功能、安全更新或非安全更新，例如提供稳定性或性能改进的更新。 需要考虑的两个主要方面是：
  
- 希望从何处获取更新
    
- 您希望多久获取一次功能更新
    
虽然你可以控制从何处获取更新以及获取功能更新的频繁性，但无法选择获取哪些特定安全更新或非安全更新。
  
 **从何处获取更新**
  
默认情况下，安装 Skype for Business应用后，更新会在 Microsoft 提供时自动从 Internet 下载。 如果希望对更新发生的时间或安装更新的安装位置进行更多控制，可以使用 Office 部署工具或组策略进行配置。
  
例如，许多组织想要在将更新部署到整个组织之前，先与一组用户一起测试更新。 为此，可以使用 Office 部署工具或组策略将 Skype for Business 应用配置为从网络的特定位置获取更新，而不是从 Internet 自动获取更新。 然后，可以使用 Office 部署工具每月将更新下载到本地网络。
  
有关更新如何适用于Office 365，请参阅以下文章：
  
- [更新过程概述Microsoft 365 企业应用版](/deployoffice/overview-update-process-microsoft-365-apps)
    
- [选择如何管理更新Microsoft 365 企业应用版](/deployoffice/choose-how-manage-updates-microsoft-365-apps)
    
- [配置更新的Microsoft 365 企业应用版](/deployoffice/configure-update-settings-microsoft-365-apps)
    
  **获取功能更新多久一次**
  
除了从何处获取更新外，还可以控制获取新客户端的新功能Skype for Business。 两个选项如下：
  
- 如果有新功能，则每月获取功能更新
    
- 每六个月获取一次功能更新
    
对于一些组织，他们希望有时间来测试新功能，因此他们希望一年只获取两次功能更新，而不是每月获取一次。
  
可以通过使用 Office 部署工具或组策略配置更新通道来控制获取功能更新的频繁时间。 每月频道每月提供功能更新， (更新) ，Semi-Annual频道每六个月提供一次功能更新。 有关频道详细信息，请参阅适用于 Microsoft 365 企业应用版[的更新频道概述](https://support.office.com/article/9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4)。
  
## <a name="related-topics"></a>相关主题

[设置 Skype for Business Online](set-up-skype-for-business-online.md)
  
[Skype for Business 和 Microsoft Teams 加载项许可](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
