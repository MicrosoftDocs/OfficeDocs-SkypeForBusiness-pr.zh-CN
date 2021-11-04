---
title: 为 Skype for Business Server 2015 创建初始拓扑设计
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: f3131153-de14-41be-b1e6-7d4bb0191af1
description: 安装完 Skype for Business Server 规划工具后，即可启动规划工具并开始设计建议的 Skype for Business Server 2015 基础结构。
ms.openlocfilehash: 0b1b477dffb6547629844268b8ade6ed5620ecbf
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60750141"
---
# <a name="create-the-initial-topology-design-for-skype-for-business-server-2015"></a>为 Skype for Business Server 2015 创建初始拓扑设计

安装完 Skype for Business Server 规划工具后，即可启动规划工具并开始设计建议的 Skype for Business Server 2015 基础结构。

> [!NOTE]
>  规划工具是一个向导驱动的工具，具有详细的指南，可告知您设计站点和拓扑时的决策流程。 本主题并不作为详尽指南，而只是为了帮助您开始在设计会话中使用规划工具。

### <a name="to-get-started-using-the-planning-tool-and-create-the-initial-design"></a>开始使用规划工具并创建初始设计

1. 启动 Skype for Business Server 2015 规划工具：单击"开始"，单击"所有程序"，单击 **"Skype for Business Server 2015"，** 然后单击"**规划工具"。**

2. 规划工具启动后，将显示"欢迎使用 **Skype for Business Server 2015 规划** 工具"页。 选择以下选项之一开始设计：

   - **选项 1：入门** 单击 **入门** 可提供一系列特定的访谈问题以及相关选择来定义条件。 完成初始的访谈入门，继续进入设计 **网站** 以定义网站体系结构。 若要完成此选项，请继续执行步骤 3。

   - **选项 2：设计网站** 单击 **"欢迎**"页上的"设计站点"将绕过"欢迎"**部分** 入门问题。 此选项将本该通过回复 入门 **中的访谈** 问题而收集的信息设置为默认值。 通过单击 **"设计站点**"，有经验的设计人员可以绕过初始访谈并根据需要更改中央站点起始页上 **的** 默认值。 若要完成此选项，请跳过步骤 3-5，从步骤 6 开始。

   - **选项 3：显示保存的拓扑** 如果已使用规划工具完成并保存了拓扑，可以跳过这些步骤中的大多数步骤，首先打开并显示拓扑。 还可以对拓扑进行更改和更新、重新保存，然后将它导出到 Microsoft Excel 或 Microsoft Visio。 若要完成此选项，请跳过步骤 3-12，从步骤 13 开始。

3. 单击 **入门** 开始设计 Skype for Business Server 2015 拓扑。

4. 通过为设计选择相应的条件回答每部分的问题，然后单击 **“下一步”** 继续进入下一个向导页。 单击 **"上** 一步"对之前的页面进行更改。

    > [!TIP]
    > 每个页面中都有对选择条件的说明以及基于首选做法和容量规划给出的建议。 如果需要其他详细信息，请单击"**了解详细信息**"阅读 Microsoft 网站上 Skype for Business Server 2015 规划文档中的详细信息。 您必须具有 Internet 连接来访问 Microsoft 网站。

5. 为设计选择适当的选项。定义初始条件后，会出现一个页面，确认“功能概述”已完成。

6. 单击 **"设计网站** "以定义中央站点。

    > [!NOTE]
    > 每个 Skype for Business Server 2015 拓扑将至少有一个中央站点。 您的设计可能只有一个中央站点、一个中央站点（具有多个分支站点、多个中央站点）或多个具有与每个中央站点关联的分支站点的中央站点。

7. 在 **"网站** 名称"中，键入将标识此中央站点的名称。

8. 在 **"网站用户"** 中，键入将位于此中央站点的预期本地并发用户数。

9. 在 **"云托管用户**"中，键入将托管在此中央站点的预期联机并发用户数。

10. 根据需要修改联机协作、用户、语音、其他部署选项或服务器应用程序的选择。

    > [!IMPORTANT]
    > 在设计的这一阶段，只能选择或清除部署选项。 但是，您可以在规划工具的稍后阶段配置更多选项。 还有一些选项不可用且无法清除。 此外，可能必须先清除一个选项后才能清除另一个。 例如，如果清除"语音"下的"企业语音"选项，则"服务器应用程序"下的"响应组"、"通知"和"呼叫 (所有这些选项都是企业语音) 的功能。  

11. 定义站点名称和用户数量后，单击 **“下一步”**。

12. 以下页面请求有关 SIP 域、会议设置、语音设置和基础结构、Exchange UM、外部用户访问、持久聊天设置、客户端设置、并置选项和分支站点的信息。 根据需要回答这些问题。

13. 最后一个问题询问您是否要创建另一个中央站点。 如果选择" **是"，** 则规划工具将返回到"中央站点"页。 如果选择"否 **"，** 请单击"**下** 一步"，然后单击"绘制"以显示高级全局拓扑视图。 

14. 若要查看现有拓扑，请单击"显示 **"。**

15. 单击代表之前保存的拓扑的 .xml 文件，然后单击 **“打开”**。

16. 规划工具显示"全局拓扑"页。 现在，可以使用规划工具中提供的工具开始编辑、更新或更改拓扑。

## <a name="see-also"></a>另请参阅

[编辑设计](/previous-versions/office/lync-server-2013/lync-server-2013-editing-the-design)