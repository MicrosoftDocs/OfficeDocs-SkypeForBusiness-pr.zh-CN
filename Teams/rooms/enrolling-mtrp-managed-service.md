---
title: 在 Teams 会议室 托管服务中Microsoft Teams 会议室 高级版设备
author: v-smandalika
ms.author: v-smandalika
manager: serdars
ms.reviewer: ''
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 了解如何在托管服务Microsoft Teams 会议室注册Microsoft Teams 会议室 高级版帐户。
f1keywords: ''
ms.openlocfilehash: 6ac3a9752fcb285c663e05939ae31b2e60a8a1e6
ms.sourcegitcommit: 3ebf9c5d27263b7e92163f1a61844a5367a4744f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2021
ms.locfileid: "58449017"
---
# <a name="enroll-a-device-in-the-microsoft-teams-rooms-premium-managed-service"></a>在托管服务中Microsoft Teams 会议室 高级版设备

若要在Microsoft Teams 会议室服务中注册Teams 会议室 高级版设备，需要向托管服务管理员再分配一个用户，然后使用该用户完成注册步骤。

## <a name="assign-users-to-the-managed-service-administrator-role"></a>将用户分配到托管服务管理员角色

完成以下步骤，将用户分配到托管服务管理员角色：

1. 使用与[Teams 会议室 高级版](https://portal.rooms.microsoft.com/)相同的管理员权限登录到 Microsoft 365 管理中心。
2. 导航到  >  **设置设置**  >  **角色"，** 然后选择"**托管服务管理员"。**
3. 在 **"托管服务管理员"** 下，选择"**分配"** 选项卡，然后选择"**添加"。**
4. 按照向导命名分配并选择应添加到该分配的用户。 该作业将应用于所有会议室和会议室组。
5. 在作业向导的末尾，选择"添加 **分配"。**

分配有托管服务管理员角色的用户负责对托管服务门户进行日常管理和Teams 会议室 高级版监视。

将用户分配到托管服务管理员角色后，请继续"注册设备"部分，Teams 会议室设备添加到托管服务门户。 [](#enroll-a-teams-rooms-device)

## <a name="enroll-a-teams-rooms-device"></a>注册Teams 会议室设备

完成以下步骤，在托管服务中Teams 会议室 高级版设备：

1. 使用Teams 会议室 高级版"托管[](https://portal.rooms.microsoft.com/)服务管理员"角色的用户登录到门户。
2. 在？  图标以启动帮助菜单。 帮助菜单包括安装 [指南，](https://portal.rooms.microsoft.com/docs/MMR%20Monitoring%20Software%20Installation%20Guide%20Feb%202021.pdf) 其中包含详细的注册说明：

    1. 查看 **安装指南中的** "先决条件"部分。 确认"通信所需的 URL"列表中列出的 **URL** 已添加到防火墙的流量允许列表。
    2. 按照启用 **TPM** 设置部分中的说明在设备上启用 (TPM) 模块功能。
    3. 按照添加 **代理设置部分中** 的说明将设备配置为使用代理网关（如果有）。
    4. 按照"流程 **"部分中** 的说明在设备上安装监视代理软件并配置自注册密钥。

3. 在设备上配置监视代理和唯一 XML 密钥后，导航到"聊天室名称>">"状态"，然后选择"注册 **"。**

    > [!NOTE]
    > 托管Teams 会议室将保持 **载入状态，** 直到托管服务管理员使用门户注册设备。

## <a name="link-to-installation-guide"></a>安装指南链接

" **帮助** "菜单提供指向安装 [指南的链接](https://portal.rooms.microsoft.com/docs/MMR%20Monitoring%20Software%20Installation%20Guide%20Feb%202021.pdf) ，该链接反过来提供以下信息：

- 有关需要允许列出才能向托管服务发送房间遥测数据的 URL 的说明。
- 有关在托管服务Microsoft Teams 会议室 高级版设备时应用监视代理和唯一 XML 密钥的说明。
- 故障排除说明。
