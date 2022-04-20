---
author: LanaChin
ms.author: v-lanachin
ms.date: 03/31/2022
ms.topic: include
audience: admin
ms.service: msteams
ms.openlocfilehash: ab375a876eb62e5f41e5dd7cda3743d4010b95ff
ms.sourcegitcommit: bf0071417188b33fc23e2a420187da5024d4bd40
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2022
ms.locfileid: "64593634"
---
在开始之前，请确保具有以下先决条件：

- Blue Yonder WFM 版本 2020.3、2021.1 或 2021.2。

    > [!NOTE]
    > 如果有 Blue Yonder WFM 2020.3 或 2021.1，请应用 2020.3.0.4 或 2021.1.0.3 修补程序。 此修补程序修复了用户在 Shifts 中收到持久性错误消息的问题。 它还修复了阻止用户在 Shifts 中更新其可用性的问题。

- Blue Yonder WFM 服务帐户名称、密码和服务 URL：

    - 联合身份验证 URL
    - Cookie 身份验证 URL
    - 员工自助服务 URL
    - 零售 Web API URL
    - 站点管理器 API URL
    - 管理 API URL

    如果没有此信息，请联系 Blue Yonder 支持人员。 该帐户由 Blue Yonder 企业管理员在根企业级别创建。 它必须具有 API 访问权限、客户端管理员和 Store Manager 访问权限。 创建连接需要帐户和密码。
- 在 Blue Yonder WFM 环境中启用联合 SSO 身份验证。 请联系 Blue Yonder 支持部门，确保已启用联合 SSO。 他们需要以下信息：

    - federatedSSOValidationService： `https://wfmconnector.teams.microsoft.com/api/v1/fedauth/{tenantId}/6A51B888-FF44-4FEA-82E1-839401E9CD74/authorize` {tenantId} 是 tenantId 的位置
     - proxyHeader：X-MS-AuthToken

- Teams中至少设置了一个团队。
- 将Microsoft 365系统帐户作为团队所有者添加到要映射的所有团队。</br> [在Microsoft 365中创建此帐户](/microsoft-365/admin/add-users/add-users)，并为其分配Microsoft 365许可证。 然后，将帐户作为团队所有者添加到要映射的所有团队。 在同步来自 Blue Yonder WFM 的 Shifts 更改时，Shifts 连接器使用此帐户。

    建议专门为此创建帐户，而不要使用用户帐户。