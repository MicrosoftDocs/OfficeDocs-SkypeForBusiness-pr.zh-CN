---
title: 为 Skype for Business Server 2015 创建初始拓扑设计
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 安装 Skype for Business Server 计划工具后，即可开始规划工具并开始设计策划的 Skype for Business Server 2015 基础结构。
ms.openlocfilehash: 8c19551d2273b992b5148646e28d726f5aea5900
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816491"
---
# <a name="create-the-initial-topology-design-for-skype-for-business-server-2015"></a>为 Skype for Business Server 2015 创建初始拓扑设计

安装 Skype for Business Server 计划工具后，即可开始规划工具并开始设计策划的 Skype for Business Server 2015 基础结构。

> [!NOTE]
>  规划工具是一个向导驱动的工具，带有详细指南，可在设计网站和拓扑时通知决策过程。 本主题不是详尽指南，只是为了帮助你开始在设计会话中使用计划工具。

### <a name="to-get-started-using-the-planning-tool-and-create-the-initial-design"></a>开始使用规划工具并创建初始设计

1. 启动 Skype for Business Server 2015 规划工具：单击 "**开始**"，单击 "**所有程序**"，单击 " **Skype for business Server 2015**"，然后单击 "**规划工具**"。

2. 开始规划工具后，将显示 "**欢迎使用 Skype for business 的规划工具" 服务器 2015**页面。 选择以下选项之一，开始你的设计：

   - **选项1：入门**单击 "**开始**" 提供一系列特定的面试问题，其中包含相关选择来定义条件。 完成初始的“**开始**”访谈部分后，继续进入“**设计站点**”来定义站点体系结构。 要完成该选项，请继续执行步骤 3。

   - **选项2：设计网站**单击 "欢迎" 页面上的 "**设计网站**" 将绕过 "**入门**" 部分中介绍的 "面试" 问题。 此选项会将本应通过响应“**开始**”部分中的访谈式问题而收集到的信息设置为默认值。 经验丰富的设计师可以通过单击“**设计站点**”跳过初始访谈，并根据需要更改“**中央站点**”开始页上的默认值。 要完成该选项，请跳过步骤 3-5，从步骤 6 开始。

   - **选项3：显示已保存的拓扑**如果已通过以前使用计划工具完成并保存了拓扑，则可以跳过这些步骤，并通过打开并显示拓扑开始。 你也可更改和更新拓扑，重新保存，然后将其导出到 Microsoft Excel 或 Microsoft Visio。 要完成该选项，请跳过步骤 3-12，从步骤 13 开始。

3. 单击 "**入门**" 开始设计 Skype For business Server 2015 拓扑。

4. 通过选择适合你的设计的条件回答每部分的问题，然后单击“**下一步**”继续进入下一个向导页。单击“**上一步**”可更改之前的页面。

    > [!TIP]
    > 每个页面中都有对选择条件的说明以及基于首选做法和容量规划给出的建议。 如果需要其他详细信息，请单击 "**了解详细**信息" 以阅读 Microsoft 网站上的 Skype For business Server 2015 规划文档中的详细信息。 您必须具有互联网连接才能访问 Microsoft 网站。

5. 为设计选择适当的选项。 定义初始条件后，会出现一个页面，确认“功能概述”已完成。

6. 单击 "**设计网站**" 以定义您的中心网站。

    > [!NOTE]
    > 每个 Skype for Business Server 2015 拓扑至少将有一个中心网站。 你的设计可能有单个中心网站、一个包含多个分支网站的中心网站、多个中心网站，或者包含与每个中心网站相关联的分支网站的多个中心网站。

7. 在 "**网站名称**" 中，键入将标识此中心网站的名称。

8. 在 "**网站托管用户**" 中，键入将托管在此中心网站中的本地并发用户的预期数量。

9. 在 "**云托管用户**" 中，键入将托管在此中心网站中的联机并行用户的预期数量。

10. 根据需要修改“联机协作”、“用户”、“语音”、“其他部署选项”或“服务器应用程序”的相关选项。

    > [!IMPORTANT]
    > 在设计的这个阶段，只能选择或清除适用于你的部署的选项。 但是，你可以在规划工具的后期阶段配置更多选项。 还有一些选项不可用且无法清除。 此外，可能必须先清除一个选项后才能清除另一个。 例如，如果清除“语音”下的“**企业语音**”选项，那么“服务器应用程序”下的“**响应组**”、“**公告**”和“**呼叫寄存**”选项（均属于企业语音的功能）也将一并清除。

11. 定义站点名称和用户数量后，单击“**下一步**”。

12. 以下页面要求提供有关 SIP 域、会议设置、语音设置和基础结构、Exchange UM、外部用户访问、持久聊天设置、客户端设置、collocation 选项和分支网站的信息。 根据需要回答这些问题。

13. 最后一个问题将询问你是否要创建另一个中心网站。 如果选择 **"是**"，则计划工具将返回到 "中央网站" 页面。 如果选择“**否**”，请单击“**下一步**”，然后单击“**绘制**”，此时将显示高级“全局拓扑”视图。

14. 要查看现有拓扑，请单击“**显示**”。

15. 单击代表之前保存的拓扑的 .xml 文件，然后单击“**打开**”。

16. 规划工具将显示 "全局拓扑结构" 页面。 现在，你可以使用规划工具中提供的工具开始编辑、更新或更改拓扑。

## <a name="see-also"></a>另请参阅

[Editing the Design](https://technet.microsoft.com/library/08f639ba-0e5f-4ae7-9191-c3d96c25b169.aspx)
