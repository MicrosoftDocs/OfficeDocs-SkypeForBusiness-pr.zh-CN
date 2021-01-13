---
title: 为 Skype for Business Server 2015 创建初始拓扑设计
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f3131153-de14-41be-b1e6-7d4bb0191af1
description: 安装完 Skype for Business Server 规划工具后，即可开始规划工具并开始设计建议的 Skype for Business Server 2015 基础结构。
ms.openlocfilehash: 7de930de8d7e194f14145c1a976fbe6b96cf234a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834962"
---
# <a name="create-the-initial-topology-design-for-skype-for-business-server-2015"></a>为 Skype for Business Server 2015 创建初始拓扑设计

安装完 Skype for Business Server 规划工具后，即可开始规划工具并开始设计建议的 Skype for Business Server 2015 基础结构。

> [!NOTE]
>  规划工具是向导驱动的工具，具有详细的指南，可告知您设计站点和拓扑时的决策流程。 本主题不作为详尽指南，而只是帮助您开始在设计会话中使用规划工具。

### <a name="to-get-started-using-the-planning-tool-and-create-the-initial-design"></a>开始使用规划工具并创建初始设计

1. 启动 Skype for Business Server 2015规划工具：单击"开始"，单击"所有程序"，再单击 **"Skype for Business Server 2015"，** 然后单击"**规划工具"。**

2. 规划工具启动后，将显示" **欢迎使用 Skype for Business Server 2015 规划工具** "页。 选择以下选项之一开始设计：

   - **选项 1：入门** 单击 **"入门** "可提供一系列特定的访谈问题以及相关选择来定义条件。 完成初始的"入门"访谈部分后，继续进入"设计 **网站**"以定义网站体系结构。 若要完成此选项，请继续执行步骤 3。

   - **选项 2：设计网站** 单击 **"** 欢迎"页上的设计网站将绕过"入门"部分中介绍的 **访谈** 式问题。 使用此选项，通过响应"入门"部分中的访谈问题来收集的信息将设置为默认值。 通过单击 **"** 设计网站"，有经验的设计人员可以绕过初始访谈，并根据需要在中央 **站点** 起始页上更改默认值。 若要完成此选项，请跳过步骤 3-5，然后从步骤 6 开始。

   - **选项 3：显示保存的拓扑** 如果之前使用规划工具已完成并保存了拓扑，可以跳过其中大多数步骤，然后打开并显示拓扑。 还可以对拓扑进行更改和更新，重新保存拓扑，然后将它导出到 Microsoft Excel 或 Microsoft Visio。 若要完成此选项，请跳过步骤 3-12，然后从步骤 13 开始。

3. 单击 **"入门** "开始设计 Skype for Business Server 2015 拓扑。

4. 通过为设计选择相应的条件回答每部分的问题，然后单击 **“下一步”** 继续进入下一个向导页。 单击 **"** 上一步"对上一页进行更改。

    > [!TIP]
    > 每个页面中都有对选择条件的说明以及基于首选做法和容量规划给出的建议。 如果需要其他详细信息，请单击" **了解详细信息** "以从 Microsoft 网站的 Skype for Business Server 2015 规划文档中阅读详细信息。 您必须具有 Internet 连接，以访问 Microsoft 网站。

5. 为设计选择适当的选项。 定义初始条件后，会出现一个页面，确认“功能概述”已完成。

6. 单击 **"设计网站** "以定义中央网站。

    > [!NOTE]
    > 每个 Skype for Business Server 2015 拓扑将至少有一个中央站点。 您的设计可能具有一个中央站点、一个具有多个分支站点的中央站点、一些中央站点或多个中央站点，这些中央站点具有与每个中央站点关联的分支站点。

7. 在 **"网站** 名称"中，键入将标识此中央站点的名称。

8. 在 **"网站主** 用户"中，键入将位于此中央站点中的本地并发用户的预期数量。

9. 在 **云托管用户中**，键入将托管在此中央站点中的预期联机并发用户数。

10. 根据需要修改联机协作、用户、语音、其他部署选项或服务器应用程序的选择。

    > [!IMPORTANT]
    > 在设计的此时，只能为部署选择或清除选项。 但是，您可以在规划工具的稍后阶段配置更多选项。 还有一些选项不可用且无法清除。 此外，可能必须先清除一个选项后才能清除另一个。 例如，如果清除语音下的 **企业语音** 选项，则"服务器应用程序" (下的响应组、通知和呼叫企业语音) 也将清除。 

11. 定义站点名称和用户数量后，单击 **“下一步”**。

12. 以下页面请求有关 SIP 域、会议设置、语音设置和基础结构、Exchange UM、外部用户访问、持久聊天设置、客户端设置、并置选项和分支站点的信息。 根据需要回答这些问题。

13. 最后一个问题询问您是否要创建另一个中央站点。 如果选择" **是**"，则规划工具将返回到"中央站点"页。 如果选择"**否**"，请单击 **"** 下一步"，然后单击"绘制"以显示高级全局拓扑视图。 

14. 若要查看现有拓扑，请单击"显示 **"。**

15. 单击代表之前保存的拓扑的 .xml 文件，然后单击 **“打开”**。

16. 规划工具显示"全局拓扑"页。 现在，可以使用规划工具中提供的工具开始编辑、更新或更改拓扑。

## <a name="see-also"></a>另请参阅

[编辑设计](https://technet.microsoft.com/library/08f639ba-0e5f-4ae7-9191-c3d96c25b169.aspx)
