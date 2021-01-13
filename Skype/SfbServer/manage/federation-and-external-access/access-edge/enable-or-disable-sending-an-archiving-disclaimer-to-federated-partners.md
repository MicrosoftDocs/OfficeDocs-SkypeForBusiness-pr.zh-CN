---
title: 启用或禁用向联盟伙伴发送存档免责声明
ms.reviewer: ''
ms:assetid: c8e9a2fa-9dc1-4e4d-919f-56ece8004864
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182584(v=OCS.15)
ms:contentKeyID: 48185391
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: ''
ms.openlocfilehash: 1f0238e177e74dc1263208f9a6a350158825d825
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817352"
---
# <a name="enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners-in-skype-for-business-server"></a>在 Skype for Business Server 中启用或禁用向联盟伙伴发送存档免责声明

在部署边缘服务器并为组织启用联盟时，应该已经指定了是否自动向联盟伙伴发送存档免责声明。如果要对外部通信进行存档，应启用发送存档免责声明。使用本主题中的过程更改此配置。

> [!NOTE]
> 以下过程假定您已为组织启用联盟。 有关启用联盟的详细信息，请参阅["启用或禁用远程用户访问"。](enable-or-disable-remote-user-access.md)


## <a name="to-enable-or-disable-sending-of-an-archiving-disclaimer-to-federated-partners"></a>启用或禁用向联盟伙伴发送存档免责声明

1.  从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或已分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。 

3.  在左侧导航栏中，单击“外部用户访问”，然后单击“访问边缘配置”。

4.  在“访问边缘配置”选项卡上，单击“全局”，再单击“编辑”，然后单击“显示详细信息”。

5.  在“编辑访问边缘配置”的“启用与联盟用户的通信”下，选中或清除“向联盟伙伴发送存档免责声明”复选框以启用或禁用自动发送存档免责声明。

6.  单击“提交”。

若要使联盟用户能够与 Skype for Business Server 部署中的用户进行协作，还必须配置至少一个外部访问策略以支持联盟用户访问。 有关控制特定联盟域的访问的详细信息，请参阅配置 [对允许的外部域的支持](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)。


## <a name="enabling-or-disabling-the-archiving-disclaimer-by-using-windows-powershell-cmdlets"></a>使用 cmdlet 启用或禁用Windows PowerShell免责声明

存档免责声明的使用可通过使用 Windows PowerShell 和 Set-CsAccessEdgeConfiguration cmdlet 进行管理。 此 cmdlet 可以从 Skype for Business Server 命令行管理程序运行，也可以从远程会话Windows PowerShell。 

## <a name="to-enable-the-archiving-disclaimer"></a>启用存档免责声明

  - 要启用存档免责声明，请将 **EnableArchivingDisclaimer** 属性的值设置为 True ($True)：
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True

## <a name="to-disable-the-archiving-disclaimer"></a>禁用存档免责声明

  - 要禁用存档免责声明，请将 **EnableArchivingDisclaimer** 属性的值设置为 False ($False)：
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False


