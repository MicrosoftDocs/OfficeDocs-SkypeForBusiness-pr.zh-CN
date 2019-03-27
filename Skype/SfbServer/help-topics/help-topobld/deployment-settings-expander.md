---
title: 部署设置扩展器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/25/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.DeploymentSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7220ec1f-38cb-4297-870e-591a832cd2f2
description: 可以使用以下部分编辑现有部署的属性：
ms.openlocfilehash: d9a42dffe3782a84b90b8cecbbc2af2835871732
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30878089"
---
# <a name="deployment-settings-expander"></a>部署设置扩展器

可以使用以下部分编辑现有部署的属性：

- SIP 域

- 简单 URL

- 中央管理服务器

## <a name="sip-domain"></a>SIP 域

要编辑“**默认 SIP 域**”，请输入新的域名。

要添加“**支持的其他 SIP 域**”，请键入需要添加的域名。单击“**添加**”以接受其作为新的会话初始协议 (SIP) 域名。

要更新现有的其他 SIP 域名，请选择相应的域名并在文本框中进行更改。单击“**更新**”接受更改。

要删除已定义的其他 SIP 域名，请选择相应的域名，然后单击“**删除**”。

在“编辑属性”页上完成所有更改后，单击“**确定**”保存更改。 单击“**取消**”将放弃更改。

## <a name="simple-urls"></a>简单 URL

要修改或定义简单 URL，请确定要编辑或更改三种简单 URL 中的哪一种。可以从电话访问 URL、会议 URL 和管理访问 URL 中进行选择。

要修改电话访问 URL 或会议 URL，请选择需要更改的 URL。单击“**编辑 URL**”。然后编辑该 URL，并单击“**确定**”保存该 URL。单击“**取消**”将放弃所有更改。

要添加新 URL，请单击“**添加**”。在“**添加简单 URL**”对话框中，指定 URL，并单击“**确定**”保存该 URL。如果需要将新的 URL 设置为活动 URL，请选择“**将此设为选定域的活动 URL**”。单击“**取消**”将放弃所有更改。

要将其他 URL 设为活动 URL（URL 旁边有绿色复选标记），请选择相应的 URL，然后单击“**变为活动状态**”。

> [!NOTE]
> 每个 SIP 域只能有一个活动 URL。

如果需要删除 URL，请选择相应的 URL，并单击“**删除**”。

> [!CAUTION]
> 仔细阅读简单 URL 设置对话框页面上的信息。删除会议 URL 后，将无法再访问用户安排的现有会议。请考虑在将新的会议 URL 设为活动状态后保留之前的 URL。在确保用户不再使用旧的会议 URL 后，可以安全地删除该 URL。

要编辑或更改管理访问 URL，请编辑该条目。

在“编辑属性”页上完成所有更改后，单击“**确定**”保存更改。单击“**取消**”将放弃更改。

## <a name="central-management-server"></a>中央管理服务器

可以将中央管理服务器从一个定义的前端池更改为另一个定义的前端池。要更改中央管理服务器的位置，请从“**要安装中央管理服务器的前端服务器位置**”下的下拉列表中选择前端池。前端服务器可以是 Enterprise Edition 前端池或 Standard Edition 前端服务器。

> [!IMPORTANT]
> 为基础结构定义、发布并部署中央管理存储后，则必须通过外部进程将中央管理存储重新定位至其他前端，然后才能更改中央管理存储的位置。

有关移动中央管理存储的详细信息，请参阅 Windows PowerShell cmdlet 参考中的 [Move-CsManagementServer](https://docs.microsoft.com/powershell/module/skype/move-csmanagementserver?view=skype-ps)。

## <a name="see-also"></a>另请参阅

有关定义和配置这些设置的详细信息，请参阅[Defining and Configuring the Topology](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx)。


