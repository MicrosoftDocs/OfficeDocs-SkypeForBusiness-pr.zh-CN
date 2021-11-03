---
title: 在 Microsoft Teams 中管理外部访问（联合身份验证）
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
ms.reviewer: vinbel
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.externalaccess.overview
- seo-marvel-mar2020
description: Teams 或 IT 管理员可以为其他域 (联合身份验证) 配置外部访问权限，以便这些域中的用户可以查找、呼叫、聊天以及设置与用户的会议。
appliesto:
- Microsoft Teams
ms.localizationpriority: high
ms.openlocfilehash: ee2492038ac05f54d1846703851846bef95893eb
ms.sourcegitcommit: 197debacdcd1f7902f6e16940ef9bec8b07641af
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2021
ms.locfileid: "60634921"
---
# <a name="manage-external-access-in-microsoft-teams"></a>在 Microsoft Teams 中管理外部访问

外部访问让组织外的 Teams 用户能够在 Teams 中进行查找、通话、聊天和设置与你之间的会议。 还可使用外部访问与仍在使用 Skype for Business（联机和本地）和 Skype（预览版）的其他组织人员进行通信。

如果希望其他组织中的人员有权访问你的团队和频道，请改用来宾访问。 有关外部访问和来宾访问之间的差异的详细信息，请参阅[比较外部访问和来宾访问](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access)。 

在以下情况下使用外部访问：
  
- 你在外部域中有需要协作的用户。例如，Rob@contoso.com 和 Ann@northwindtraders.com 与 contoso.com 和 northwindtraders.com 域中的其他一些人协作处理某个项目。

- 你希望自己组织内的人员使用 Teams 联系组织外特定企业中的人员。

- 你希望世界各地使用 Teams 的所有其他人都能够通过使用你的电子邮件地址找到并联系你。 

## <a name="plan-for-external-access"></a>规划外部访问

默认情况下，Teams 中的外部访问处于启用状态，这意味着你的组织可以与所有外部域进行通信。 如果添加阻止的域，将允许所有其他域；如果添加允许的域，将阻止所有其他域。 此规则的例外是允许匿名参与者参加会议。 在 Teams 管理中心 (**用户** > **外部访问**) 设置外部访问有三种情形:

> [!NOTE]
> 主持会议或与来自其他组织的人员聊天时，Teams 用户可以添加应用。 当他们加入由其他组织主持的会议或聊天时，也可以使用由这些组织的人共享的应用。 将应用主持用户组织的数据策略，以及该用户组织共享的任何第三方应用的数据共享实践。

> [!NOTE]
> 如果关闭组织中的外部访问，外部用户仍可通过匿名加入加入会议。 若要了解详细信息，请参阅[管理 Teams 中的会议策略](meeting-settings-in-teams.md)。

- **允许所有外部域**: 这是 Teams 中的默认设置，可让你组织中的用户查找你组织外部任何域中的人员，并与这些人员进行通话、聊天和安排会议。

    在这种情形中，你的用户能够与符合以下条件的所有外部域进行通信: 正在运行 Teams 或 Skype for Business、或者允许所有外部域、或者已将你的域添加到他们允许列表中。

- **仅允许特定外部域**: 通过将域添加到 **“允许”** 列表中，将外部访问限制为仅允许的域。 设置允许的域列表后，将阻止所有其他域。 若要允许特定域，请单击“**添加域**”，添加域名，单击“**要在此域上执行的操作**”，然后选择“**已允许**”。

- **阻止特定域** - 通过将域添加到“**阻止**”列表中，可与 *除阻止的域之外* 的所有外部域进行通信。 若要阻止特定域，请单击“**添加域**”，添加域名，单击“**要在此域上执行的操作**”，然后选择“**已阻止**”。 设置阻止的域列表后，将允许所有其他域。

- **阻止所有外部域**: 阻止组织中的人在任何域中查找、呼叫、聊天和与组织外部的人安排会议。

> [!NOTE]
> 允许或阻止的域仅适用于会议（当匿名访问会议"关闭"时）。

## <a name="allow-or-block-domains"></a>允许或阻止域

  **使用 Microsoft Teams 管理中心**

允许特定域

1. 在 Teams 管理中心，转到 **“用户”** > **“外部访问”**。

2. 在 **选择用户有权访问的域** 下，选择 **仅允许特定外部域**。

3. 选择 **允许域**。

4. 在 **域** 框中，键入想要允许的域，然后单击 **完成**。

5. 如果要允许其他域，请单击 **添加域**。

6. 单击“**保存**”。

阻止特定域

1. 在 Teams 管理中心，转到 **“用户”** > **“外部访问”**。

2. 在 **选择用户有权访问的域** 下，选择 **仅阻止特定外部域**。

3. 选择 **阻止域**。

4. 在 **域** 框中，键入想要允许的域，然后单击 **完成**。

5. 如果要阻止其他域，请单击 **添加域**。

6. 单击“**保存**”。

请确保其他 Teams 组织的管理员完成这些相同的步骤。例如，如果他们要限制可与其用户通信的组织，其管理员需要在 **“允许的域”** 列表中输入你企业的域。

## <a name="communicate-with-skype-users-preview"></a>与 Skype 用户进行通信 (预览阶段)

请按照以下步骤，让你组织中的 Teams 用户与 Skype 用户聊天和通话。 然后，Teams 用户可以搜索和启动与 Skype 用户之间的一次性文本对话或音频/视频通话，以及反向操作。

  **使用 Microsoft Teams 管理中心**

1. 在左侧导航栏中，转到 **用户** > **外部域**。

2. 启动 **允许组织中的用户与 Skype 用户通信** 设置。

若要深入了解 Teams 用户和 Skype 用户之间的通信方式（包括适用的限制），请参阅 [Teams 和 Skype 的互操作性](teams-skype-interop.md)。

## <a name="block-unsolicited-contact-with-external-unmanaged-teams-users"></a>阻止与外部非托管 Teams 用户的未经请求的联系

请按照以下步骤操作，以防止组织中的 Teams 用户与帐户不受组织管理的外部 Teams 用户进行未经请求的联系。

  **使用 Microsoft Teams 管理中心**

1. 在左侧导航栏中，转到 **用户** > **外部域**。

2. 执行下列步骤之一：

    - 如果要阻止组织中的 Teams 用户与帐户不由组织管理的外部 Teams 用户进行通信，请禁用“**我的组织中的用户可以与帐户不受组织管理的 Teams 用户通信**”设置，并清除“**具有非组织管理 Teams 账户的外部用户可以联系我的组织中的用户**”复选框。

    - 要允许组织中的 Teams 用户与帐户不由组织管理的外部 Teams 用户进行通信，如果你的 Teams 用户已发起联系，请启用“**我的组织中的用户可以与帐户不受组织管理的 Teams 用户通信**”设置，并清除“**具有非组织管理 Teams 账户的外部用户可以联系我的组织中的用户**”复选框。

    - 要允许组织中的 Teams 用户与帐户不由组织管理的外部 Teams 用户进行通信，并且收到与该外部 Teams 用户通信的请求，请启用“**我的组织中的用户可以与帐户不受组织管理的 Teams 用户通信**”设置，并选中“**具有非组织管理 Teams 账户的外部用户可以联系我的组织中的用户**”复选框。

## <a name="test-access"></a>测试访问

若要测试你的设置，你需要一名不在你防火墙后方的 Teams 用户。
  
1. 在你和你组织的管理员更改了“**外部访问**”设置后，应该可以继续进行操作。

2. 在 Teams 应用中，通过电子邮件地址搜索该用户，并发送聊天请求。

3. 要求你的 Teams 联系人向你发送聊天请求。如果未收到其请求，则问题在于你的防火墙设置（假设他们已确认其防火墙设置正确）。

4. 另一个测试问题是否出自你的防火墙的方法是在不受你的防火墙保护的 WiFi 位置（例如咖啡店）使用 Teams 向你的联系人发送聊天请求。如果消息在 WiFi 位置顺利传送，但不是在你工作的时候，则问题出自你的防火墙。

> [!NOTE]
> 如果你和另一名用户都启用了外部访问并允许了彼此的域，应该可以正常工作。 如果不正常，另一名用户应确保其配置未阻止你的域。

## <a name="common-external-access-scenarios"></a>常见外部访问情形

以下部分介绍了如何为常见外部访问方案启用联合身份验证，以及 TeamsUpgradePolicy 如何确定传入聊天和呼叫的传递。

### <a name="enable-federation"></a>启用联盟：

若要使组织中的用户能与另一个组织中用户进行通信，两个组织必须启用联合身份验证。 为给定组织启用联合身份验证的步骤取决于组织是否完全联机、混合或完全在本地。

| 如果你的组织是 | 启用联合身份验证，如下所示 |
|:---------|:-----------------------|
|在线，无需内部部署Skype for Business。 这包括具有 TeamsOnly 用户和/或 Skype for Business Online 用户的组织。| 如果使用 Teams 管理中心： <br>- 请确保在外部访问中允许想要通信的域。<br><br>如果使用 PowerShell：<br>- 确保为联合身份验证启用租户： `Get-CsTenantFederationConfiguration` 必须显示 `AllowFederatedUsers=true`。 <br>- 确保用户具有 `CsExternalAccessPolicy` 有效 `EnableFederationAccess=true`。<br>- 如果不使用打开的联盟，请确保目标域列于`AllowedDomains``CsTenantFederationConfiguration`。 |
|纯本地 | 在本地工具中： <br>- 确保 `CsAccessEdgeConfiguration`已启用。<br>- 确保通过策略 `ExternalAccessPolicy` 用户联盟（通过全局策略、网站策略或用户分配的策略）。 <br> - 如果不使用打开的联盟，请确保目标域列于 `AllowedDomains`。 |
|与一些联机用户（在 Skype for Business 或 Teams 中）和一些本地用户混合。 | 为联机组织本地组织执行上述步骤。 |

### <a name="delivery-of-incoming-chats-and-calls"></a>送达传入聊天和呼叫 

联合组织的传入聊天和呼叫将位于用户的 Teams 或 Skype for Business 客户端，具体取决于 TeamsUpgradePolicy 中收件人的模式。

| 如果要 | 执行以下操作： |
|:---------|:-----------------------|
| 确保传入的联合聊天和呼叫会到达用户的 Teams 客户端： | 将用户配置为 TeamsOnly。
| 确保传入的联合聊天和呼叫会到达用户的 Skype for Business 客户端 | 将用户配置为除 TeamsOnly 外的任何模式。 |


### <a name="enable-federation-between-users-in-your-organization-and-consumer-users-of-skype"></a>在组织用户与 Skype 消费者用户之间启用联合身份验证

若要在组织用户与 Skype 消费者用户之间启用联合身份验证：

| 如果你的组织是 | 启用消费者联合身份验证，如下所示 |
|:---------|:-----------------------|
| 纯在线，本地没有 Skype for Business。  这包括具有 TeamsOnly 用户和/或 Skype for Business Online 用户的组织。 | 如果使用 Teams 管理中心： <br>- 请确保 **允许组织中的用户与 Skype 用户通信** 在外部访问中启用。<br><br>如果使用 PowerShell： <br>-确保为联合身份验证启用租户： `Get-CsTenantFederationConfiguration` 必须显示 `AllowPublicUsers=true`。 <br> - 确保用户具有 `CsExternalAccessPolicy` 有效 `EnablePublicCloudAccess=true`。 |
| 纯本地 | 在本地工具中： <br> - 确保启用 Skype 作为联盟合作伙伴。 <br> - 通过 `EnablePublicCloudAccess=true` 确保 `ExternalAccessPolicy` 服务（通过全局策略、网站策略或用户分配的策略）。|
| 与一些联机用户（在 Skype for Business 或 Teams 中）和一些本地用户混合。| 为联机组织本地组织执行上述步骤。


> [!IMPORTANT]
> 你无需添加任何 **Skype 域** 作为允许的域，就可以使 Teams 或 Skype for Business Online 用户与你组织内部或外部的 Skype 用户进行通信。已允许所有 **Skype 域**。

## <a name="federation-diagnostic-tool"></a>联合诊断工具

如果你是管理员，则可以使用以下诊断工具来验证 Teams 用户是否可以与联合 Teams 用户进行通信:

1. 选择下面 **运行测试**，这将在 Microsoft 365 管理中心中弹出诊断结果。 

   > [!div class="nextstepaction"]
   > [运行测试: Teams 联盟](https://aka.ms/TeamsFederationDiag)

2. 在“运行”诊断窗格中，输入 **会话初始协议 (SIP) 地址** 和 **联合租户的域名**，然后选择 **运行测试**。

3. 测试将返回最佳后续步骤，以解决阻止与联合用户通信的任何租户或策略配置的问题。


## <a name="related-topics"></a>相关主题

- [外部（联合身份验证）用户的本机聊天体验](native-chat-for-external-users.md)
