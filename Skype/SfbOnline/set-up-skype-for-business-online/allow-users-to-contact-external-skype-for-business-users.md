---
title: 允许用户联系外部 Skype for Business 用户
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: b414873a-0059-4cd5-aea1-e5d0857dbc94
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Setup
- For O365M_ShareLync
- ms.lync.lac.OrgExternalAccess
- ms.lync.lac.skypefederation
- O365E_HRCLYNC _ SipFederationSrvRecordVerified_FL312122
- O365E_ShareLync
- O365M_ShareLync
- O365P_ExternalCommDesc
- O365P_ShareLync
- LIL_Placement
description: '了解如何配置Skype for Business让用户与另一组织的用户交谈，或让外部联系人与用户交谈。 '
ms.openlocfilehash: 1a1a86dc9b2eadc1bdf70448c1f9b79870f45558
ms.sourcegitcommit: 75adb0cc163974772617c5e78a1678d9dbd9d76f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2021
ms.locfileid: "60536723"
---
# <a name="allow-users-to-contact-external-skype-for-business-users"></a>允许用户联系外部 Skype for Business 用户

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]
  
在下列情况下，请按照本文的步骤进行操作：
  
- 你的用户在企业内的不同域中。例如，Rob@ContosoEast.com 和 Ann@ContosoWest.com。

- 希望你组织的人员使用 Skype for Business 联系你组织外特定企业中的人员。

- 您希望世界上使用 Skype for Business的其他人能够使用您的电子邮件地址找到您并与您联系。 如果你和他们都使用默认的 Skype for Business 设置，此功能会自动运行。 如果他们更改了默认设置，他们需要确认其配置没有阻止你的域。

## <a name="enable-business-to-business-communications-for-your-users"></a>为你的用户启用企业到企业通信

<a name="bk_preview"> </a>

必须拥有[两个组织Microsoft 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)管理员Office 365或管理员权限才能进行此通信。

 **使用 Teams 管理中心**
  
1. 使用管理员帐户或Microsoft 365 Office 365登录。

2. 在管理中心中，转到"**管理中心**  >  **Teams"。**

    ![选择"Teams管理员"。](../images/MS-Teams-Admin.png)
  
3. 在Teams **中，** 选择 **"Skype** >  
  ![ 门户"选择 SfB 旧版门户。](../images/SFBlegacy-size65.png)

4. 在 **Skype for Business 管理中心**，选择“**组织**” > “**外部通信**”。
5. 要设置与特定企业或另一个域中的用户之间的通信，在下拉框中选择“**打开(仅针对被允许的域)**”。

    或者，你希望能够与世界各地采用公开的 Skype for Business 策略的所有其他人通信，请选择" **打开(被阻止的域除外)**"。这是默认设置。

6. 在 **"阻止或允许的域**"下，选择并添加 **+** 要允许的域的名称。

7. 请确保另一组织的管理员在管理中心 中执行Skype for Business **步骤**。 例如，在其" **允许的域**"列表中，其管理员需要输入贵企业的域。

8. 如果你使用的是 Windows 防火墙，Skype for Business 将自动打开所需端口。

    If your organization is using a different firewall solution to restrict computers on your network from connecting to the Internet, ensure your client computers are able to access the following [Office 365 URLs and IP address ranges](/microsoftteams/office-365-urls-ip-address-ranges). 这可能需要将 FQNS 添加到防火墙或代理基础结构配置中的出站允许列表 **\* ：.api.skype.com、.users.storage.live.com** \* ****和 graph.skype.com。** 有关如何在防火墙中打开这些端口的说明，请查看它提供的文档。

    有关需要打开的所有端口的列表，请参阅Office 365 URL[和 IP 地址范围](/microsoftteams/office-365-urls-ip-address-ranges)。

9. 确保组织的管理员也遵循了这些步骤。

10. **测试最长需要等待 24 小时** 。 更改外部通信设置时，可能需要 24 小时才能在所有数据中心填充更改。

![Skype。](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) 你可以允许用户搜索使用免费消费者应用Skype并即时消息！ 有关详细信息，请参阅[允许用户Skype for Business添加Skype联系人](let-skype-for-business-users-add-skype-contacts.md)。
  
## <a name="test-and-troubleshoot"></a>测试和故障排除

<a name="bk_preview"> </a>

 **人们在设置企业到企业通信时遇到的最常见的问题是正确完成 [Office 365 URL 和 IP 地址范围](/microsoftteams/office-365-urls-ip-address-ranges)。**
  
要测试你的设置，你需要 Skype for Business 上不受你公司的防火墙保护的联系人。
  
1. 在更改外部通信设置后， **直到等待 24 小时后再进行测试** 。

2. 在 Skype for Business 中，搜索你的 Skype for Business 联系人，然后发送聊天请求。

    如果收到由于公司策略无法发送的消息，则需要仔细检查Office 365 URL 和[IP 地址范围](/microsoftteams/office-365-urls-ip-address-ranges)。

3. 要求你的 Skype for Business 联系人向你发送聊天请求。如果你未收到其请求，那么你的防火墙有问题（假设他们已确认其防火墙设置正确）。

4. 测试问题是否出在防火墙的另一种方式是转到不在防火墙后面的 wifi 位置，例如咖啡店。 使用Skype for Business向联系人发送聊天请求。 如果消息顺利传送，但不是在你工作的时候，那么问题出自你的防火墙。

## <a name="how-to-find-others-and-be-found-when-connecting-with-another-business"></a>在与其他企业连接时如何查找其他人以及如何被找到

<a name="bk_preview"> </a>

与其他用户启用外部通信Skype for Business，用户可以通过搜索Skype for Business用户登录名来查找联合用户。 例如，Rob@contoso.com。 然后，他们需要将此人添加到联系人列表中。
  
![若要在联合企业中查找用户，必须搜索其电子邮件地址 (这通常也是其登录名) 。](../images/20242f85-0636-463b-8df3-1e123784d7fa.png)
  
## <a name="tips-on-setting-up-communications-with-federated-businesses"></a>设置联盟企业通信的提示

<a name="bk_preview"> </a>

- 若要在 Skype for Business 2015 和 Skype for Business Online 之间配置联合，请参阅本文：配置与[Skype for Business Online 联合](../../SfbHybrid/hybrid/configure-federation-with-skype-for-business-online.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)。

- 若要在 Lync 与 Skype for Business Online 之间配置联合，请参阅本文：为 Lync Online 客户[配置联合身份验证支持](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-federation-support-for-a-lync-online-customer)。

- 当 Microsoft 365 或 Office 365 中的两个 Skype for Business 用户在单独的域上相互通信时，他们只能使用 Skype for Business 功能 (例如，视频对话或桌面共享) 在两个组织中打开。

- 如果您的Skype for Business用户被置于 In-Place 或诉讼保留中，该用户与其他 Skype for Business 或 Skype 用户之间的任何 IM 对话都将保存在其邮箱中的可恢复邮件中。  这些对话将不保存在其邮箱中的" **对话历史记录**"文件夹中。

## <a name="turn-off-external-communication-for-specific-individuals"></a>关闭特定个人的外部通信

<a name="bk_preview"> </a>

为你的整个企业启用外部通信后，你可以仅为特定的个人关闭它。
  
1. 使用管理员帐户或Microsoft 365 Office 365登录。

2. 在管理中心，**转到"用户**  >  **""活动用户"。**

3. 在用户列表中，选择用户，然后在" **其他设置**"下单击" **编辑 Skype for Business 属性**"。

    ![选择"Skype for Business"。](../images/2b0f9a7b-3fee-4f4b-968a-68c429eeb395.png)
  
4. 在管理 **Skype for Business中，选择**"**外部通信"。**

    在" **选项** "页上，将选择所有选项。 清除要禁用的通信。 下图显示了 Jakob 能够与其他可信企业中的人员通信，但是无法与其他 Skype 用户通信。

    ![选择"外部联系人"。](../images/4e546321-a065-48ed-8ac7-1e112a780eab.png)
  
5. 选择" **保存**"。

> [!NOTE]
> [!注释] 你可能必须等待长达 24 小时，更改才会生效。
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]

## <a name="related-topics"></a>相关主题

<a name="bk_preview"> </a>

[设置 Skype for Business Online](set-up-skype-for-business-online.md)
  
[允许 Skype for Business 用户添加 Skype 联系人](let-skype-for-business-users-add-skype-contacts.md)
