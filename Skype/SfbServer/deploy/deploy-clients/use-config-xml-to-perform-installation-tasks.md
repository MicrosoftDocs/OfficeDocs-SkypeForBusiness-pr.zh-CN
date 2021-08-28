---
title: 使用Config.xml在客户端中执行Skype for Business任务
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 0813184a-ab40-417c-b3a3-c2090766b831
description: 摘要：如何使用 Config.xml文件指定其他安装说明。
ms.openlocfilehash: f79dcc1d31fdd862ca8705552d7894dcdd90fcd7
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58620488"
---
# <a name="use-configxml-to-perform-installation-tasks-in-skype-for-business-clients"></a>使用Config.xml在客户端中执行Skype for Business任务

**摘要：** 如何使用 Config.xml 文件指定其他安装说明。

尽管 Office 自定义工具 (OCT) 是用于自定义安装的主要工具，但管理员可以使用 Config.xml 文件指定在 OCT 中不可用的其他安装说明。下列自定义只能通过 Config.xml 文件来进行：

- 指定网络安装点的路径。

- 选择要安装的产品。

- 配置日志记录和安装程序自定义文件及软件更新的位置。

- 指定安装选项，如用户名。

- 无需安装 Office，将本地安装源 (LIS) 复制到用户的计算机上。

- 在安装中添加或删除语言。

建议您使用 Config.xml 文件配置无Skype for Business安装。 

默认情况下，Config.xml核心产品文件夹中存储的 (文件，例如 \ _product_。WW) 指示安装程序安装该产品。 例如，以下Config.xml中的文件将安装Skype for Business：

- \\server\share\Skype15\Skype。WW \Config.xml

下表Config.xml最常用于Skype for Business安装的元素。

**Config.xml 元素**


| **元素**              | **说明**                                                                                                                                                                                                                                                                                         |
|:-------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 配置  <br/>     | 顶级元素（必需）。 包含 Product 属性，例如：Product=Lync (这适用于Skype for Business客户端)   <br/>                                                                                                                                                          |
| OptionState  <br/>       | 指定在安装期间如何处理特定产品功能。 使用以下属性阻止安装 业务连接 Services，其中包括干扰 Outlook： <br/>  Id="LOBiMain" <br/>  State="Absent" <br/>  Children="Force" <br/> |
| 显示  <br/>           | 安装程序向用户显示的 UI 级别。典型属性包括： <br/>  CompletionNotice="Yes"                                                                                                                                                                                |
| 日志记录  <br/>           | 安装程序执行的日志记录类型的选项。典型属性包括： <br/>  Type ="Off"                                                                                                                                                                                       |
| 设置  <br/>           | 指定 Windows Installer 属性的值。典型属性包括：<br/>  Setting Id=" *name*" (Windows Installer 属性)   <br/>  Value=" *value*" (要分配给属性属性的值)   <br/>                                                             |
| DistributionPoint  <br/> | 从该位置运行安装的网络安装点的完全限定路径。包括 Location 属性：<br/>  Location=" *path*"  <br/>                                                                                                                                     |

下面的示例演示一个Config.xml客户端的典型无提示安装Skype for Business文件。 

```xml
<Configuration Product="Lync"> 
  <OptionState Id="LOBiMain" State="Absent" Children="Force" /> 
  <Display Level="None" CompletionNotice="No" AcceptEula="Yes" /> 
  <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
  <Setting Id="SETUP_REBOOT" Value="Never" /> 
  <DistributionPoint Location="\\server\share\Skype15" /> 
</Configuration>
```

有关使用 Config.xml 文件执行Office和维护任务的详细信息，请参阅 [https://go.microsoft.com/fwlink/p/?linkid=267514](/previous-versions/office/office-2013-resource-kit/cc179195(v=office.15)) 。

## <a name="to-customize-the-configxml-file"></a>自定义 Config.xml 文件

1. 使用文本编辑器工具（例如记事本）打开 Config.xml 文件。

2. 找到包含您要更改元素的行。

3. 使用您需要的静默选项修改元素项。 请确保删除注释分隔符" \<!--" and "--\> "。 例如，使用以下语法：

   <pre>
   < DistributionPoint Location="\\server\share\Skype15" />
   </pre>

4. 保存 Config.xml 文件。