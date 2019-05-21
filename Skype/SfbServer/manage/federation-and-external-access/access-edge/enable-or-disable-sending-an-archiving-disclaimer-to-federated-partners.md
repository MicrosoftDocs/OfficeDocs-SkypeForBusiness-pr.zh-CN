---
title: 启用或禁用向联盟伙伴发送存档免责声明
ms.reviewer: ''
ms:assetid: c8e9a2fa-9dc1-4e4d-919f-56ece8004864
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182584(v=OCS.15)
ms:contentKeyID: 48185391
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: c2f64a617cae938ffe64ec8db313402785413c49
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280213"
---
# <a name="enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners-in-skype-for-business-server"></a>在 Skype for business 服务器中启用或禁用向联盟合作伙伴发送存档免责声明

在部署你的边缘服务器并为你的组织启用联盟后, 你应该已指定是否要将存档免责声明自动发送给联盟伙伴。 如果您存档外部通信, 则应启用发送存档免责声明。 使用本主题中的过程更改该配置。

> [!NOTE]
> 以下过程假定你已为你的组织启用联盟。 有关启用联盟的详细信息, 请参阅[启用或禁用远程用户访问](enable-or-disable-remote-user-access.md)。


## <a name="to-enable-or-disable-sending-of-an-archiving-disclaimer-to-federated-partners"></a>启用或禁用向联盟伙伴发送存档免责声明

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口, 然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。 

3.  在左侧导航栏中, 单击 "**外部用户访问**", 然后单击 "**访问边缘配置**"。

4.  在“**访问边缘配置**”选项卡上，单击“**全局**”，再单击“**编辑**”，然后单击“**显示详细信息**”。

5.  在 "**编辑访问边缘配置**" 下的 "**启用与联盟用户的通信**" 下, 选中或清除 "**将存档声明发送给联盟伙伴**" 复选框以启用或禁用自动发送存档免责声明.

6.  单击“**提交**”。

若要使联盟用户能够与 Skype for Business Server 部署中的用户进行协作, 你必须也配置了至少一个外部访问策略来支持联合用户访问。 有关控制特定联盟域的访问权限的详细信息, 请参阅[配置对允许的外部域的支持](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)。


## <a name="enabling-or-disabling-the-archiving-disclaimer-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell cmdlet 启用或禁用存档放弃声明

可使用 Windows PowerShell 和 CsAccessEdgeConfiguration cmdlet 管理存档否认使用。 此 cmdlet 既可以从 Skype for Business 服务器管理外壳运行, 也可以从 Windows PowerShell 的远程会话运行。 

## <a name="to-enable-the-archiving-disclaimer"></a>启用存档免责声明

  - 要启用存档免责声明，请将 **EnableArchivingDisclaimer** 属性的值设置为 True ($True)：
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True

## <a name="to-disable-the-archiving-disclaimer"></a>禁用存档放弃声明

  - 要禁用存档免责声明，请将 **EnableArchivingDisclaimer** 属性的值设置为 False ($False)：
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False


