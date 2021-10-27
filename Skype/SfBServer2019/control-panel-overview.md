---
title: 控制面板 - 概述
ms.reviewer: ''
ms.author: v-smandalika
author: v-smandalika
manager: dansimp
ms.date: 10/13/2021
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
description: 本文概述了新的控制面板。
ms.openlocfilehash: 8a4f8e073b424969951a69c620dd5f65a582fd75
ms.sourcegitcommit: b57e19e20900ff02f3196c811bf1dd1acd149c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/26/2021
ms.locfileid: "60579752"
---
# <a name="control-panel"></a>控制面板

当前控制面板是旧版控制面板的新版本，与旧版本一起存在。 新的控制面板是 2019 年 7 月累积更新中的一部分。 它有助于管理组织环境中服务器、用户、客户端和设备的配置。

旧版控制面板可能无法使用，因为 Silverlight 技术在 2021 年 10 月 12 日已进入"停止支持"阶段。 有关详细信息，请参阅 [Silverlight 停止提供支持](https://support.microsoft.com/windows/silverlight-end-of-support-0a3be3c7-bead-e203-2dfd-74f0a64f1788)。

> [!NOTE]
> 有关旧版控制面板的信息，请参阅控制面板 [，然后](../SfbServer/management-tools/install-and-open-administrative-tools.md)导航到"控制面板"Skype for Business Server"**部分**。

## <a name="access-control-panel"></a>访问控制面板

若要在浏览器中启动新的控制面板，请输入 https:// &lt; 池 FQDN &gt; /macp 或配置的简单 URL。

新的控制面板包括满足组织大部分需求的常用菜单项。 旧版控制面板中的一些菜单项在新的控制面板中不可用。 但是，用户可以选择通过 PowerShell cmdlet 使用这些菜单项中的功能。 有关详细信息，请参阅下表。

> [!NOTE]
> 随后将分阶段提供其他菜单项的文档。

## <a name="client"></a>Client

|子菜单  |cmdlet 的信息源  |
|---------|---------|
|客户端版本策略         |    [客户端版本策略](use-powershell-client-menu.md#client-version-policy)     |
|客户端版本配置      |  [客户端版本配置](use-powershell-client-menu.md#client-version-configuration)       |
|设备更新    | [设备更新](use-powershell-client-menu.md#device-update)        |
|测试设备     | [测试设备](use-powershell-client-menu.md#test-device)        |
|设备日志配置         |    [设备日志配置](use-powershell-client-menu.md#device-log-configuration)     |
|设备配置         |    [设备配置](use-powershell-client-menu.md#device-configuration)     |
|移动策略         |    [移动策略](use-powershell-client-menu.md#mobility-policy)     |
|推送通知配置         |    [推送通知配置](use-powershell-client-menu.md#push-notification-configuration)     |