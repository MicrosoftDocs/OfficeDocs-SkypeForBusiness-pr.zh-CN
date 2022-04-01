---
author: LanaChin
ms.author: v-lanachin
ms.date: 03/31/2022
ms.topic: include
audience: admin
ms.service: msteams
ms.openlocfilehash: ab375a876eb62e5f41e5dd7cda3743d4010b95ff
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/31/2022
ms.locfileid: "64593634"
---
在开始使用之前，请确保满足以下先决条件：

- Blue Yonder WFM 版本 2020.3、2021.1 或 2021.2。

    > [!NOTE]
    > 如果有 Blue Yonder WFM 2020.3 或 2021.1，请应用 2020.3.0.4 或 2021.1.0.3 修补程序。 此修补程序修复了用户在 Shifts 中收到持久错误消息的问题。 它还修复了阻止用户在 Shifts 中更新其可用性的问题。

- Blue Yonder WFM 服务帐户名称和密码和服务 URL：

    - 联合身份验证 URL
    - Cookie 身份验证 URL
    - 员工自助服务 URL
    - 零售 Web API URL
    - 站点管理器 API URL
    - 管理 API URL

    如果没有此信息，请联系 Blue Yonder 支持人员。 该帐户由 Blue Yonder 企业管理员在根企业级别创建。 它必须具有 API 访问权限、客户端管理员和应用商店管理器访问权限。 创建连接需要帐户和密码。
- 在 Blue Yonder WFM 环境中启用联合 SSO 身份验证。 请联系 Blue Yonder 支持部门，确保已启用联合 SSO。 他们需要以下信息：

    - federatedSSOValidationService： `https://wfmconnector.teams.microsoft.com/api/v1/fedauth/{tenantId}/6A51B888-FF44-4FEA-82E1-839401E9CD74/authorize` 其中 {tenantId} 是 tenantId
     - proxyHeader：X-MS-AuthToken

- 在团队中至少设置了一Teams。
- 你以Microsoft 365所有者的团队成员帐户添加到了要映射的所有团队。</br> [在帐户中创建此Microsoft 365](/microsoft-365/admin/add-users/add-users)，并为其分配Microsoft 365许可证。 然后，将帐户作为团队所有者添加到要映射的所有团队。 从 Blue Yonder WFM 同步 Shifts 更改时，Shifts 连接器使用此帐户。

    我们建议专门为此目的创建一个帐户，而不要使用你的用户帐户。