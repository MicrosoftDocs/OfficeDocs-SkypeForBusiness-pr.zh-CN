---
title: 允许用户联系外部 Skype for Business 用户
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: b414873a-0059-4cd5-aea1-e5d0857dbc94
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1_keywords:
- For O365M_ShareLync
- ms.lync.lac.OrgExternalAccess
- ms.lync.lac.skypefederation
- O365E_HRCLYNC _ SipFederationSrvRecordVerified_FL312122
- O365E_ShareLync
- O365M_ShareLync
- O365P_ExternalCommDesc
- O365P_ShareLync
ms.custom:
- Setup
- LIL_Placement
description: 'See how to configure Skype for Business to let users talk to users in another organization, or let outside contacts to them. '
ms.openlocfilehash: d8cac3838550530666c2e7550c616a0b77cfd820
ms.sourcegitcommit: a5b8b0a1e5ae5eb718e296ca6df6687368ee9174
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2018
ms.locfileid: "19500680"
---
# <a name="allow-users-to-contact-external-skype-for-business-users"></a>允许用户联系外部 Skype for Business 用户

> [!NOTE]
> 为业务联盟的 Skype 不可用到由 21Vianet 和 Office 365 德国组织的 Office 365。 
  
在下列情况下，请按照本文的步骤进行操作：
  
- 你的用户在企业内的不同域中。例如，Rob@ContosoEast.com 和 Ann@ContosoWest.com。
    
- 希望你组织的人员使用 Skype for Business 联系你组织外特定企业中的人员。
    
-您希望任何其他人在世界上使用 for Business 的 Skype 能够找到并与您联系，使用您的电子邮件地址。 如果你和他们都使用默认的 Skype for Business 设置，此功能会自动运行。 如果他们更改了默认设置，他们需要确认其配置没有阻止你的域。
    
## <a name="enable-business-to-business-communications-for-your-users"></a>为你的用户启用企业到企业通信
<a name="bk_preview"> </a>

在这两个组织为此，您必须在 Office 365 中具有[管理员权限](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)。

![sfb-徽标-30x30.png](../images/sfb-logo-30x30.png) **使用业务管理中心的 Skype**
  
1. 使用 Office 365 管理员帐户登录。 
    
2. In the Office 365 admin center, go to **Admin Centers** > **Skype for Business**.
    
    ![Choose the Skype for Business admin center.](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. 在 **Skype for Business 管理中心**，选择“**组织**” > “**外部通信**”。
    
4. 若要设置通信与特定的企业或用户在另一个域中，在下拉列表框中，选择**在仅允许域**。
    
    或者，你希望能够与世界各地采用公开的 Skype for Business 策略的所有其他人通信，请选择" **打开(被阻止的域除外)**"。这是默认设置。
    
5. 在**已阻止或允许的域**，下，选择**+**，添加您希望允许的域的名称。
    
6. 确保其他组织中的管理员执行其**业务管理中心的 Skype**这些相同步骤。 例如，在其" **允许的域**"列表中，其管理员需要输入贵企业的域。
    
7. 如果你使用的是 Windows 防火墙，Skype for Business 将自动打开所需端口。
    
    If your organization is using a different firewall solution to restrict computers on your network from connecting to the Internet, ensure your client computers are able to access the following [Office 365 URLs and IP address ranges](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges). 这可能需要添加到出站的 Fqdn 允许在防火墙或代理的列表基础结构配置： ** \*。 api.skype.com**， \* **。 users.storage.live.com**，和**graph.skype.com**。 有关如何在防火墙中打开这些端口上的说明，检查与其附带的文档。
    
    您需要打开的所有端口的列表，请参阅[Office 365 Url 和 IP 地址范围](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges)。

8. 请确保组织中的管理员还具有执行这些步骤。
    
9. **测试最长需要等待 24 小时** 。如果你更改了外部通信设置，最长需要等待 24 小时才能让更改传播到所有数据中心。
    
![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) 现在，你可以允许你的用户搜索使用 Skype 这一免费应用的任何人并与其进行即时消息通信！ 若要了解详细信息，请参阅[适用于业务用户允许 Skype 添加 Skype 联系人](let-skype-for-business-users-add-skype-contacts.md)。
  
## <a name="test-and-troubleshoot"></a>测试和故障排除
<a name="bk_preview"> </a>

 **人们在设置企业到企业通信时遇到的最常见的问题是正确完成[Office 365 URL 和 IP 地址范围](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges)。**
  
要测试你的设置，你需要 Skype for Business 上不受你公司的防火墙保护的联系人。
  
1. 在更改外部通信设置后， **直到等待 24 小时后再进行测试** 。
    
2. 在 Skype for Business 中，搜索你的 Skype for Business 联系人，然后发送聊天请求。
    
    如果您收到一条消息，无法将其发送由于公司策略，您需要仔细检查您的[Office 365 Url 和 IP 地址范围](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges)。
    
3. 要求你的 Skype for Business 联系人向你发送聊天请求。如果你未收到其请求，那么你的防火墙有问题（假设他们已确认其防火墙设置正确）。
    
4. 另一个测试问题是否出自你的防火墙的方法是在不受你的防火墙保护的 WiFi 位置（例如咖啡店）使用 Skype for Business 向你的 Skype 联系人发送聊天请求。如果消息顺利传送，但不是在你工作的时候，那么问题出自你的防火墙。
    
## <a name="how-to-find-others-and-be-found-when-connecting-with-another-business"></a>在与其他企业连接时如何查找其他人以及如何被找到
<a name="bk_preview"> </a>

您的用户启用与其他 Skype 业务用户的外部通信后，可以通过搜索其登录名为企业用户查找联盟的 Skype： 例如，Rob@contoso.com。 然后他们将需要将此人添加到他们的联系人列表。
  
![若要联合的商业中查找用户，您必须搜索其电子邮件地址 （这通常也是其登录名）。](../images/20242f85-0636-463b-8df3-1e123784d7fa.png)
  
## <a name="tips-on-setting-up-communications-with-federated-businesses"></a>设置联盟企业通信的提示
<a name="bk_preview"> </a>

- 要配置 Skype for Business 2015 与 Skype for Business Online 之间的联盟，请参阅 TechNet 文章：[配置与 Skype for Business Online 联盟](https://technet.microsoft.com/en-us/library/jj205126.aspx)。
    
- 要配置 Lync 与 Skype for Business Online 之间的联盟，请参阅 TechNet 文章：[为 Lync Online 客户配置联盟支持](https://technet.microsoft.com/en-us/library/hh202193.aspx)。
    
- 当 Office 365 中的两个 Skype for Business 用户在单独的域上相互通信时，他们只能使用在两个组织中都启用的 Skype for Business 功能（例如，视频对话或桌面共享）。
    
- 如果您的组织中的业务用户 Skype 置于就地或诉讼保留，该用户和其他 Skype 业务或 Skype 用户之间的 IM 对话将保存其邮箱中的**可恢复的项目**中。 这些对话将不保存在其邮箱中的" **对话历史记录**"文件夹中。
    
## <a name="turn-off-external-communication-for-specific-individuals"></a>关闭特定个人的外部通信
<a name="bk_preview"> </a>

为你的整个企业启用外部通信后，你可以仅为特定的个人关闭它。
  
1. 使用 Office 365 管理员帐户登录。
    
2. 在 Office 365 管理中心，转到**用户** > **活动用户**。
    
3. 在用户列表中，选择用户，然后在" **其他设置**"下单击" **编辑 Skype for Business 属性**"。
    
    ![Choose Skype for Business](../images/2b0f9a7b-3fee-4f4b-968a-68c429eeb395.png)
  
4. 在**Skype 业务管理中心的**中，选择**外部通信**。
    
    在**选项**页中，将为选择所有选项。 清除要禁用通信。 下图显示了 Jakob 能够与其他可信企业中的人员通信，但是无法与其他 Skype 用户通信。
    
    ![Choose External contacts](../images/4e546321-a065-48ed-8ac7-1e112a780eab.png)
  
5. 选择" **保存**"。
    
> [!NOTE]
> [!注释] 你可能必须等待长达 24 小时，更改才会生效。 
  


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
   
## <a name="related-topics"></a>相关主题
<a name="bk_preview"> </a>

[设置 Skype for Business Online](set-up-skype-for-business-online.md)
  
[允许 Skype for Business 用户添加 Skype 联系人](let-skype-for-business-users-add-skype-contacts.md)
  
  
 
