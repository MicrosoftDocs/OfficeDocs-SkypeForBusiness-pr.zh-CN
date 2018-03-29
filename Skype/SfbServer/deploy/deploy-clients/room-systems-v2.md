---
title: 部署 Skype 会议室系统 v2
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/6/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
description: 阅读本主题以了解有关 Skype 的空间系统 v2 和如何将其集成与交换和 Skype 的业务服务器 2015年。
ms.openlocfilehash: 54dc3d42d406fea2bdefcac5eb726dd77fde078f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-skype-room-systems-v2"></a>部署 Skype 会议室系统 v2
 
阅读本主题以了解有关 Skype 的空间系统 v2 和如何将其集成与交换和 Skype 的业务服务器 2015年。
  
本主题介绍如何创建帐户的业务服务器 2015年使用 Microsoft Exchange 和 Skype 的 Skype 的空间系统 v2。 [Skype 的空间系统 v2 控制台配置](console.md)中介绍了 Skype 的空间系统 v2 设备的部署说明。 你的基础结构很可能属于以下配置之一：
  
- 联机部署： 完全在 Office 365 上部署您的组织环境。 有关详细信息，请参阅[部署 Skype 的空间系统 v2 与 Office 365](with-office-365.md)。
    
- 内部部署： 它控制，您的组织有承载 Active Directory、 交换和业务服务器 2015年的 Skype。 有关详细信息，请参阅[部署 Skype 的空间系统具有的业务服务器 2015 Skype 的 v2](with-skype-for-business-server-2015.md)
    
- 混合部署： 您的组织有一些位于内部部署和联机寄宿通过 Office 365 提供一些服务，混合。 与 Skype 的空间系统 v2 支持下面的混合方案： 
    
  - Exchange 联机使用内部部署的业务服务器 2015年的 Skype。 有关详细信息，请参阅[部署 Skype 的空间系统 v2 使用 Exchange Online （混合）](with-exchange-online.md)。
    
  - 在线业务交换在与 Skype 的场所。 有关详细信息，请参阅[部署 Skype 的空间系统 v2 交换在场所 （混合）](with-exchange-on-premises.md)。
    
你所拥有的配置类型将影响设备设置的准备方式。
  
Skype 的空间系统 v2 需要分配一个"用户帐户"在 Active Directory、 交换和业务的 Skype。 此帐户用于访问其会议日历，并建立 Skype 业务连接性。 用户可通过使用此帐户安排会议来预订此帐户。 Skype 的空间系统 v2 将能够参加该会议并向与会者提供各种功能。
  
> [!IMPORTANT]
> 如果没有用户帐户，所有功能都将不能使用。 
  
每个用户帐户是唯一的一个 Skype 的空间系统 v2 设备，并且需要一些设置：
  
- 必须对用户帐户进行正确配置。
    
- 您的基础结构必须被配置为允许 Skype 的空间系统 v2 来验证用户帐户，并达到相应的 Microsoft 服务。
    
> [!IMPORTANT]
> 强烈建议你在实际安装硬件之前完成帐户创建。 理想情况下，应在安装之前两至三周开始帐户准备工作。 
  
可以是用户帐户看作人作为大会文件室或会议空间的帐户识别资源帐户。 当你要使用该会议室安排会议时，可邀请帐户加入该会议。 为了最有效地使用 Skype 的空间系统 v2，则执行相同的操作使用分配给每个用户帐户。
  
如果您已经有资源邮箱帐户设置为位置安装 Skype 的空间系统 v2 的会议空间，可该资源帐户更改为用户帐户。 完成后，所有您需要做是将用户帐户添加到 Skype 的空间系统 v2 设备。 请参阅下面提供的用户帐户设置示例。
  
与其他配置，远程管理是可能使用 Microsoft 操作管理套件 (OMS)，所述[计划 Skype 的空间系统 OMS v2 管理](../../plan-your-deployment/clients-and-devices/oms-management.md)、[部署 Skype 的空间系统 v2 管理与 OMS](with-oms.md)和[管理Skype 的空间系统 OMS 的 v2 设备](../../manage/skype-room-systems-v2/oms.md)。 
  
## <a name="basic-configuration"></a>基本配置

这些属性表示为用户帐户以使用 Skype 的空间系统 v2 的最低配置。 你的用户帐户可能需要进行更多设置。
  
|**属性**|**目的**|
|:-----|:-----|
|Exchange 邮箱 (Exchange 2013 SP1 或更高版本，或者 Exchange Online)  <br/> |启用 Exchange 邮箱的帐户为用户帐户提供能力来接收和发送邮件和会议要求，并在 Skype 的空间系统 v2 设备上显示会议日历。 Skype 的空间系统 v2 邮箱必须会议室邮箱。  <br/> |
|为业务 Skype 已启用  <br/> |Skype 业务必须启用才能使用各种会议功能，如视频电话、 IM 和屏幕共享。 Skype 的在线业务和 Skype 业务服务器的支持。  <br/> |
|已启用密码  <br/> |必须启用用户帐户有密码保护，或者它不能与 Exchange 或 Skype 业务服务器的身份验证。  <br/> |
   
## <a name="advanced-configuration"></a>高级配置

属性时基本配置将允许用户帐户设置在简单的环境中，很可能您的环境必须满足为 Skype 的空间系统 v2，为了能够成功使用的目录帐户上有其他限制用户帐户。
  
|**属性**|**目的**|
|:-----|:-----|
|基于证书的身份验证  <br/> |用于交换和 Skype 业务服务器可能需要使用证书。 要部署证书，可以在以管理员身份登录时加载它们。  <br/> |
   
设置用户帐户的最佳方法是使用远程 Windows PowerShell 配置。 [Microsoft 提供的脚本](https://go.microsoft.com/fwlink/?linkid=870105)将帮助创建新的用户帐户，或验证现有资源帐户可以帮助您将它们转换为兼容的 Skype 的空间系统 v2 用户帐户。
  
如果您希望在 Windows PowerShell cmdlet 使用 Office 365 用户界面，可以手动执行一些步骤。 请参阅[创建设备帐户使用 Office 365](https://technet.microsoft.com/en-us/itpro/surface-hub/create-a-device-account-using-office-365)。
  
## <a name="see-also"></a>另请参阅

#### 

[Skype 的空间规划系统 v2](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[配置控制台，Skype 的空间系统 v2](console.md)
  
[Skype 的机房管理系统 v2](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

