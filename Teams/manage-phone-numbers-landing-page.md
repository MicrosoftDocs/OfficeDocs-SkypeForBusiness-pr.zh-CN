---
title: 管理组织的电话号码
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: davlick, roykuntz, jenstr
ms.topic: conceptual
ms.assetid: 6b61cb3c-361c-48a8-a9ef-d81bddde27bb
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.voice.phonenumbers.overview
- ms.teamsadmincenter.voice.searchandacquire.PSTNpartner
- ms.lync.lac.NewNumberManualAcquisitionOpenSupportTicket
- ms.lync.lac.VASAMissingGeoCodes
- Calling Plans
- seo-marvel-apr2020
description: 了解如何为组织获取和管理用户 (订阅者) 和服务 (收费和免费) 电话号码。
ms.openlocfilehash: 52069029e7dca69f5df9520ad1491464bf6b9aa9
ms.sourcegitcommit: cbcf37f395832bed871fe709b87c6eecb1fdfd72
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2022
ms.locfileid: "68584232"
---
# <a name="manage-telephone-numbers-for-your-organization"></a>管理组织的电话号码

目前，Microsoft 支持两种电话号码类型： 

- [**用户号码**](#user-telephone-numbers)（也称为订阅者号码）可以分配给组织中的用户。

- [**服务号码**](#service-telephone-numbers)，分配给服务，如 [音频会议](deploy-audio-conferencing-teams-landing-page.md)、 [自动助理](plan-auto-attendant-call-queue.md)或 [呼叫队列](plan-auto-attendant-call-queue.md)。

Microsoft 正在努力简化数字类型，但目前需要决定：

- 哪些用户位置需要 Microsoft 提供新的电话号码？
- 我需要哪种类型的电话号码 (订阅者或服务) ？
- 如何实现将现有电话号码移植到 Teams？

获取和管理电话号码方式因公共交换电话网络 (PSTN) 连接选项而异。

- 有关管理 Microsoft 通话套餐的电话号码的信息，请参阅 [管理通话套餐的电话号码](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。

- 有关为 Operator Connect 管理电话号码的信息，请参阅 [使用 Operator Connect 设置电话号码](operator-connect-configure.md#set-up-phone-numbers)。

- 有关管理 Teams Phone Mobile 的电话号码的信息，请参阅 [使用 Teams Phone Mobile 设置电话号码](operator-connect-mobile-configure.md#set-up-phone-numbers)。

- 有关管理直接路由的电话号码的信息，请参阅 [配置电话号码并启用企业语音](direct-routing-enable-users.md#configure-the-phone-number-and-enable-enterprise-voice)。




> [!NOTE]
> 如果需要其他或其他号码类型（Microsoft Teams 管理中心中显示的号码除外），可以向 [电话号码服务中心](https://pstnsd.powerappsportals.com/)提交电话号码请求。

## <a name="user-telephone-numbers"></a>用户电话号码

有两种类型的用户电话号码，可以分配给组织中的用户：  
    
- **地理数字** 与地理区域有关系，是最常见的。 例如，大多数情况下，地理电话号码只能在该国的特定地址、城市、州或区域内使用。
    
- **非地理数字** 称为国家数字，有时称为 VoIP 数字。 这些数字与国家/地区的地理区域没有关系。 例如，从国家/地区中的任意位置调用号码时，非地理号码的成本通常相同。 此外，一些国家，如丹麦，只有非地理数字可用。


## <a name="service-telephone-numbers"></a>服务电话号码  

本部分介绍许可中包含的 Microsoft 提供的服务号码。 有关操作员连接或直接路由提供的服务号码的信息，请联系提供商。 

Microsoft 提供的两种服务电话号码（收费和免费）可分配给音频会议、自动助理或呼叫队列等服务。 服务号码的并发呼叫容量高于用户号码。 服务号码可用性因国家/地区而异， (是收费号码还是免费号码) 。 Microsoft 在每个国家/地区的电话许可证决定了可以使用的数字。
    
 - **收费服务号码** - 有两种类型的收费服务号码，这可能会给调用方带来通行费：
    
   - **地理数字** 地理数字与地理区域有关系。 例如，大多数情况下，地理电话号码只能在该国的特定地址、城市、州或区域内使用。
        
   - **非地理数字** 非地理数字是与国家/地区内的地理区域没有关系的国家数字。 例如，从国家/地区中的任意位置调用号码时，非地理号码的成本通常相同。
   
- **免费服务号码** - 这些服务号码通常不会给调用方产生收费费用。 Teams 在 60 多个国家/地区提供全国免费号码。
    
    > [!CAUTION]
    > 某些国家/地区和源号码类型（例如来自移动电话的呼叫）在某些情况下可能会给呼叫者带来费用。 

## <a name="where-phone-numbers-are-managed"></a>在其中管理电话号码

数字的托管位置和方式取决于 PSTN 连接选项：

- Microsoft 呼叫计划和操作员连接电话号码只能在 Microsoft 365 中进行管理。

- 可在本地 Active Directory或 Microsoft 365 中管理直接路由电话号码，如以下部分所述。

### <a name="direct-routing-numbers-managed-in-an-on-premises-active-directory"></a>在本地 Active Directory中管理的直接路由编号

如果已Skype for Business Server混合部署，则本地 Active Directory很可能与 Microsoft 365 同步。 这意味着用户和资源帐户上的目录属性在本地 Active Directory中进行管理并同步到 Microsoft 365。

如果直接路由电话号码是在本地 Active Directory中的用户或资源帐户上管理的，则帐户上的 msRTCSIP-Line 参数包含一个值。 可以使用 ADSI 编辑等工具查看在本地 Active Directory中分配了直接路由电话号码的用户或资源帐户的 msRTCSIP-Line 参数。   

通过 (Azure AD Connect) 的目录同步过程自动将此参数同步到 Microsoft 365 中的用户或资源帐户后，可以通过查看 [Get-CsOnlineUser](/powershell/module/skype/get-csonlineuser) cmdlet 输出中的 OnPremLineURi 参数来查看电话号码。

| Where | 参数 | 值 |
| :------------| :-------| :---------|
| 本地 AD | msRTCSIP-Line | tel：+14255551234 |
| Microsoft 365 | OnPremLineURi | tel：+14255551234 |

### <a name="direct-routing-numbers-managed-in-microsoft-365"></a>在 Microsoft 365 中管理的直接路由号码

如果未在本地 Active Directory中管理直接路由电话号码，则在 Microsoft 365 中对其进行管理。 由于电话号码未同步到 Microsoft 365，因此在用户或资源帐户运行的Get-CsOnlineUser cmdlet 的输出中，这些电话号码在 OnPremLineUri 参数中不可见。

### <a name="direct-routing-numbers-managed-in-both-an-on-premises-active-directory-and-microsoft-365"></a>在 本地 Active Directory 和 Microsoft 365 中管理的直接路由号码

可以管理 Microsoft 365 中其他帐户的本地 Active Directory和直接路由电话号码中某些用户和资源帐户的直接路由电话号码。 此功能取决于是否在本地 Active Directory中的用户或资源帐户上设置了属性 msRTCSIP-Line。    

### <a name="change-where-direct-routing-phone-numbers-are-managed"></a>更改管理直接路由电话号码的位置

若要更改直接路由电话号码的托管位置，需要从本地 Active Directory中的用户或资源帐户上的 msRTCSIP-Line 属性中删除电话号码。   

有关详细信息，请参阅 [Active Directory 中所有本地用户的 Clear Skype for Business 属性](/skypeforbusiness/hybrid/cloud-consolidation-managing-attributes#method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory.md)。 请注意，需要将电话号码重新分配给 Microsoft 365 中的用户或资源帐户。

删除同步到 Microsoft 365 后，用户或资源帐户上Get-CsOnlineUser输出中的 OnPremLineUri 属性将为空。 

