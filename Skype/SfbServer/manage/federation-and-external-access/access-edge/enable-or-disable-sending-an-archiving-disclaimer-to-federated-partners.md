---
title: 启用或禁用向联盟伙伴发送存档免责声明
ms:assetid: c8e9a2fa-9dc1-4e4d-919f-56ece8004864
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182584(v=OCS.15)
ms:contentKeyID: 48185391
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: 3e076e1044a65c45a8fc72d0e7d54369d4c3196f
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222777"
---
# <a name="enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners-in-skype-for-business-server"></a>启用或禁用业务服务器向 Skype 中的联盟伙伴发送存档免责声明

次部署边缘服务器和启用联盟组织中，您应具有指定是否自动向联盟伙伴发送存档免责声明。 如果存档外部通信，您应启用发送存档免责声明。 使用本主题中的过程来更改的配置。

> [!NOTE]
> 下面的过程假定您已为您的组织中启用了联盟。 有关启用联合身份验证的详细信息，请参阅[启用或禁用远程用户访问](enable-or-disable-remote-user-access.md)。


## <a name="to-enable-or-disable-sending-of-an-archiving-disclaimer-to-federated-partners"></a>启用或禁用向联盟伙伴发送存档免责声明

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。 

3.  在左侧的导航栏中，单击**外部用户访问**，单击**访问边缘配置**。

4.  在“**访问边缘配置**”选项卡上，单击“**全局**”，再单击“**编辑**”，然后单击“**显示详细信息**”。

5.  在**编辑访问边缘配置**下**启用与联盟用户的通信**，请选中或清除**向联盟伙伴发送存档免责声明**复选框以启用或禁用自动发送存档免责声明。

6.  单击“**提交**”。

若要启用联盟的用户与您 Skype 业务服务器部署中的用户进行协作，您必须还配置至少一个外部访问策略以支持联盟的用户访问。 有关控制对特定联盟域访问的详细信息，请参阅[支持的允许的外部域的配置](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)。


## <a name="enabling-or-disabling-the-archiving-disclaimer-by-using-windows-powershell-cmdlets"></a>启用或禁用存档免责声明，通过使用 Windows PowerShell cmdlet

使用 Windows PowerShell 和 Set-csaccessedgeconfiguration cmdlet 可以管理存档免责声明的使用。 从业务 Server 命令行管理程序 Skype 或 Windows PowerShell 远程会话，则可以运行此 cmdlet。 

## <a name="to-enable-the-archiving-disclaimer"></a>若要启用存档免责声明

  - 要启用存档免责声明，请将 **EnableArchivingDisclaimer** 属性的值设置为 True ($True)：
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True

## <a name="to-disable-the-archiving-disclaimer"></a>若要禁用存档免责声明

  - 要禁用存档免责声明，请将 **EnableArchivingDisclaimer** 属性的值设置为 False ($False)：
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False


