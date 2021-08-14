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
description: 打开或关闭向联盟伙伴发送存档免责声明Skype for Business Server。
ms.openlocfilehash: a44643d5a46d796e253a0fe444a45bdf610bd572
ms.sourcegitcommit: 97c2faab08ec9b8fc9967827883308733ec162ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/13/2021
ms.locfileid: "58235077"
---
# <a name="enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners-in-skype-for-business-server"></a>启用或禁用向联盟伙伴发送存档免责声明Skype for Business Server

在部署边缘服务器并为组织启用联盟时，应该已经指定了是否自动向联盟伙伴发送存档免责声明。如果要对外部通信进行存档，应启用发送存档免责声明。使用本主题中的过程更改此配置。

> [!NOTE]
> 以下过程假定您已为组织启用联盟。 有关启用联盟的详细信息，请参阅 [启用或禁用远程用户访问](enable-or-disable-remote-user-access.md)。


## <a name="to-enable-or-disable-sending-of-an-archiving-disclaimer-to-federated-partners"></a>启用或禁用向联盟伙伴发送存档免责声明

1.  从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。 

3.  在左侧导航栏中，单击“外部用户访问”，然后单击“访问边缘配置”。

4.  在“访问边缘配置”选项卡上，单击“全局”，再单击“编辑”，然后单击“显示详细信息”。

5.  在“编辑访问边缘配置”的“启用与联盟用户的通信”下，选中或清除“向联盟伙伴发送存档免责声明”复选框以启用或禁用自动发送存档免责声明。

6.  单击“提交”。

若要使联盟用户能够与 Skype for Business Server 部署中的用户进行协作，还必须至少配置一个外部访问策略以支持联盟用户访问。 有关控制特定联盟域的访问的详细信息，请参阅配置 [对允许的外部域的支持](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)。


## <a name="enabling-or-disabling-the-archiving-disclaimer-by-using-windows-powershell-cmdlets"></a>使用 cmdlet 启用或禁用Windows PowerShell免责声明

存档免责声明的使用可通过使用 Windows PowerShell 和 Set-CsAccessEdgeConfiguration cmdlet 进行管理。 可以从命令行管理程序或 Skype for Business Server远程会话运行此 cmdlet Windows PowerShell。 

## <a name="to-enable-the-archiving-disclaimer"></a>启用存档免责声明

  - 要启用存档免责声明，请将 **EnableArchivingDisclaimer** 属性的值设置为 True ($True)：<br/><br/>Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True

## <a name="to-disable-the-archiving-disclaimer"></a>禁用存档免责声明

  - 要禁用存档免责声明，请将 **EnableArchivingDisclaimer** 属性的值设置为 False ($False)：<br/><br/>Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False

