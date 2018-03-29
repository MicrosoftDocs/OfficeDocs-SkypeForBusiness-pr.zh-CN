---
title: 在 Skype for Business 中配置 IP 地址类型
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 7/22/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 17e756c0-6652-4cd5-b185-4b25929e3a42
description: 摘要： Skype 实现业务服务器 2015年前检查 IP 地址类型下面的注意事项。
ms.openlocfilehash: facfff432cfcde74af737b5a7c5db87d36f3eb41
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="configure-ip-address-types-in-skype-for-business"></a>在 Skype for Business 中配置 IP 地址类型
 
**摘要：**Skype 实现业务服务器 2015年之前，请查看下面的 IP 地址类型注意事项。
  
您可以通过使用配置拓扑生成器中的拓扑结构设置部署的 IP 地址类型。 本部分介绍如何部署前端服务器、 中介服务器和边缘服务器上的 IP 地址类型。
  
## <a name="deploy-ip-address-types-on-a-front-end-server"></a>在前端服务器上部署 IP 地址类型

使用拓扑生成器，在下面的过程来部署前端服务器的 IP 地址类型中执行的步骤。
  
### <a name="to-deploy-ip-address-types-on-a-front-end-server"></a>在前端服务器上部署 IP 地址类型

1. 在“**Enterprise Edition 前端池**”下，右键单击池中的服务器，然后选择“**编辑属性**”。（也可以选择服务器，然后单击“**操作**”菜单中的“**编辑属性**”。）
    
2. 在“**编辑属性**”对话框中，选择您要配置的 IP 地址类型。对于双协议栈配置，则选择“**启用 IPv4**”和“**启用 IPv6**”，如下图所示。
    
   **编辑为前端服务器池的属性对话框**

  - **使用所有配置 IP 地址**。如果您希望允许使用计算机上定义的任何 IP 地址，请选择此选项。 
    
    > [!NOTE]
    > 这是针对 IP 版本 6 (IPv6) 配置的建议选项。 
  
  - **将服务用途限制为所选 IP 地址**。选择此选项可指定要在新服务器上使用的特定地址。如果选择此选项，则必须输入“**主 IP 地址**”的值。
    
  - **主 IP 地址**。输入用于除公用电话交换网 (PSTN) 之外的所有通信的 IP 地址。所输入的 IP 地址必须符合选择的地址类型的格式。
    
  - **PSTN IP 地址**。在前端服务器上并置中介服务器时定义一个 PSTN IP 地址。该地址必须符合选择的地址类型的格式。
    
    > [!NOTE]
    > 不支持安装的附加网络接口卡 (Nic) 在前端服务器上支持的 PSTN IP 地址配置。 有关所支持的 Skype 业务服务器的 NIC 配置的详细信息，请参阅[Lync Server 2013 的服务器硬件平台](http://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx)。 
  
## <a name="deploy-ip-address-types-on-a-mediation-server"></a>在中介服务器上部署 IP 地址类型

使用拓扑生成器，在下面的过程来部署中介服务器的 IP 地址类型中执行的步骤。
  
### <a name="to-deploy-ip-address-types-on-a-mediation-server"></a>在中介服务器上部署 IP 地址类型

- 在拓扑生成器中，在**中介池**，右键单击在池中的服务器，然后选择**编辑属性**。 （或者，选择服务器，然后从**操作**菜单上单击**编辑属性**。）
    
- 在“**编辑属性**”对话框中，选择您要配置的 IP 地址类型。对于双协议栈配置，则选择“**启用 IPv4**”和“**启用 IPv6**”，如下图所示。
    
   **编辑为中介服务器池的属性对话框**

  - **使用所有配置 IP 地址**。如果您希望允许使用计算机上定义的任何 IP 地址，请选择此选项。 
    
    > [!NOTE]
    > 这是针对 IP 版本 6 (IPv6) 配置的建议选项。 
  
  - **将服务用途限制为所选 IP 地址**。选择此选项可指定要在新服务器上使用的特定地址。如果选择此选项，则必须输入主 IP 地址的值。
    
  - **主 IP 地址**。输入用于除公用电话交换网 (PSTN) 之外的所有通信的 IP 地址。所输入的 IP 地址必须符合选择的地址类型的格式。
    
  - **PSTN IP 地址**。在前端服务器上并置中介服务器时定义一个 PSTN IP 地址。该地址必须符合选择的地址类型的格式。
    
    > [!NOTE]
    > 不支持其他 Nic 在独立的中介服务器上支持的 PSTN IP 地址配置的安装。 有关所支持的 Skype 业务服务器的 NIC 配置的详细信息，请参阅[Lync Server 2013 的服务器硬件平台](http://technet.microsoft.com/library/c964c1c0-0153-472b-88ad-a38866e0df0c.aspx)。 
  
## <a name="deploy-ip-address-types-on-a-edge-server"></a>在边缘服务器上部署 IP 地址类型

使用拓扑生成器，在下面的过程来部署边缘服务器上的 IP 地址类型中执行的步骤。
  
### <a name="to-deploy-ip-address-types-on-an-edge-server"></a>在边缘服务器上部署 IP 地址类型

1. 在拓扑生成器中，在**边缘池**，右键单击在池中的服务器，然后选择**编辑属性**。 （或者，选择服务器，然后从**操作**菜单上单击**编辑属性**。）
    
2. 在“**编辑属性**”窗口中，选择要支持的 IP 地址配置。下图显示用于内部接口和外部接口的双协议栈配置。
    
   **双堆积边缘服务器的内部接口**

   **双堆积的边缘服务器外部接口**

3. 对于您选择的每个地址类型，必须提供适当的内部和外部地址。
    

