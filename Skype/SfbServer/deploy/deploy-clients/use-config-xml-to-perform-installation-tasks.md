---
title: 使用 Config.xml 执行安装任务 Skype 中的商业客户端
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0813184a-ab40-417c-b3a3-c2090766b831
description: 摘要：如何使用 Config.xml 文件指定附加安装说明。
ms.openlocfilehash: ea869fe2b49d5c1a5b4e04c3bc75cfd52b66555e
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "21003506"
---
# <a name="use-configxml-to-perform-installation-tasks-in-skype-for-business-clients"></a>使用 Config.xml 执行安装任务 Skype 中的商业客户端
 
**摘要：** 如何使用 Config.xml 文件指定附加安装说明。
  
尽管 Office 自定义工具 (OCT) 是用于自定义安装的主要工具，但管理员可以使用 Config.xml 文件指定在 OCT 中不可用的其他安装说明。下列自定义只能通过 Config.xml 文件来进行：
  
- 指定网络安装点的路径。
    
- 选择要安装的产品。
    
- 配置日志记录和安装程序自定义文件及软件更新的位置。
    
- 指定安装选项，如用户名。
    
- 无需安装 Office，将本地安装源 (LIS) 复制到用户的计算机上。
    
- 在安装中添加语言或从安装中删除语言。
    
我们建议使用 Config.xml 文件配置 Skype 的业务无提示安装。 
  
默认情况下，存储在核心产品文件夹中的 Config.xml 文件 (例如，\_产品_。WW) 指示安装程序来安装该产品。 例如，以下文件夹中的 Config.xml 文件安装 for Business 的 Skype:
  
- \\server\share\Skype15\Skype.WW \Config.xml
    
下表中列出的最常用的 Skype 业务安装的 Config.xml 元素。
  
**Config.xml 元素**

|**元素**|**说明**|
|:-----|:-----|
|配置  <br/> |顶级元素（必需）。包含 Product 属性，例如：Product=Lync（这适用于 Skype for Business 客户端）  <br/> |
|OptionState  <br/> | 指定在安装期间如何处理特定产品功能。 使用以下属性来防止安装 Business Connectivity Services，其中包括 Outlook 会干扰的共享的组件： <br/>  Id ="LOBiMain" <br/>  State="Absent" <br/>  Children="Force" <br/> |
|Display  <br/> | 安装程序向用户显示的 UI 级别。典型属性包括： <br/>  CompletionNotice ="Yes" | "No"(default) <br/>  AcceptEula ="Yes" | "No"(default) <br/> |
|日志记录  <br/> | 安装程序执行的日志记录类型的选项。典型属性包括： <br/>  类型 ="Off" | "Standard"(default) | "Verbose" <br/>  模板 =" _filename_.txt"（日志文件的名称）  <br/> |
|设置  <br/> | 指定 Windows Installer 属性的值。典型属性包括：<br/>  Setting Id =" _name_"（Windows Installer 属性的名称）  <br/>  值 ="_值_"（要分配给属性的值）  <br/> |
|DistributionPoint  <br/> | 从该位置运行安装的网络安装点的完全限定路径。包括 Location 属性：<br/>  位置 ="_路径_"  <br/> |
   
下面的示例演示业务客户端 Skype 的典型无提示安装的 Config.xml 文件。 
  
```
<Configuration Product="Lync"> 
  <OptionState Id="LOBiMain" State="Absent" Children="Force" /> 
  <Display Level="None" CompletionNotice="No" AcceptEula="Yes" /> 
  <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
  <Setting Id="SETUP_REBOOT" Value="Never" /> 
  <DistributionPoint Location="\\server\share\Skype15" /> 
</Configuration>
```

有关使用 Config.xml 文件执行 Office 安装和维护任务的详细的信息，请在[https://go.microsoft.com/fwlink/p/?linkid=267514](https://go.microsoft.com/fwlink/p/?linkid=267514)。
  
## <a name="to-customize-the-configxml-file"></a>自定义 Config.xml 文件

1. 使用文本编辑器工具（例如记事本）打开 Config.xml 文件。
    
2. 找到包含您要更改元素的行。
    
3. 使用您需要的静默选项修改元素项。 请确保您删除注释分隔符，"\<！-"和"-\>"。 例如，使用以下语法：
    
  <pre>
  < DistributionPoint Location="\\server\share\Skype15" />
  </pre>

4. 保存 Config.xml 文件。
    

