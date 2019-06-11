---
title: Skype for Business Online 中的 Windows PowerShell cmdlet、参数和参数值
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Windows PowerShell cmdlets, parameters, and parameter values
ms:assetid: 04615700-099f-4ac5-a801-ddeffccb9e4f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362765(v=OCS.15)
ms:contentKeyID: 56558799
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce954eff790bae6974f144360637d6061318d3d3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838060"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="windows-powershell-cmdlets-parameters-and-parameter-values-in-skype-for-business-online"></a>Skype for Business Online 中的 Windows PowerShell cmdlet、参数和参数值

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-07-05_

如果你熟悉在所有 Windows 版本 (或你熟悉 MS-DOS) 中找到的命令窗口, 则在学习如何使用 Windows PowerShell 时, 你将开始使用一个头部。 在 "命令" 窗口中, 键入命令并按 ENTER。 在响应中, 计算机运行一个命令或一个可执行文件。 例如, 若要返回有关当前目录中的所有文件和文件夹的信息, 请在命令提示符处键入此命令, 然后按 ENTER:

    dir

然后, 你将返回有关当前目录中的所有文件和文件夹的信息:

``` 
    Directory: C:\

03/21/2013  03:39 PM    <DIR>          Deploy
03/21/2013  02:55 PM    <DIR>          Intel
07/26/2012  12:33 AM    <DIR>          PerfLogs
04/10/2013  10:29 AM    <DIR>          Program Files
04/08/2013  10:28 AM    <DIR>          Program Files (x86)
03/22/2013  08:44 AM    <DIR>          Users
04/11/2013  03:00 PM    <DIR>              Windows
03/13/2013  02:53 PM                 117   pldok.log
03/21/2013  03:35 PM                 769   RHDSetup.exe
03/21/2013  03:37 PM            207   setup.doc
              3 File(s)        1,093 bytes
              7 Dir(s)21,386,002,432 bytes free
```

当您只键入命令的名称或可执行文件时, 这就是结果的一个示例。 但是, 从命令窗口中运行的许多命令也都接受*参数*。 参数是传递给命令的附加信息部分, 用于修改命令的行为。 例如, 如果你只想查看当前目录中的文件和文件夹的名称, 而不是其他信息, 如文件或文件夹的大小, 或者文件夹或文件夹的创建日期和时间。 在这种情况下, 当运行 dir 命令时, 将附加 **/b**参数:

    dir /b

如果包含 **/b**参数, **dir**命令仅返回在当前目录中找到的文件夹和文件的名称:

    Deploy
    Intel
    PerfLogs
    Program Files
    Program Files (x86)
    Users
    Windows
    pldok.log
    RHDSetup.exe
    setup.doc

在前面的命令中, **/b**参数是将返回的数据限制为文件和文件夹名称所需的唯一信息。 使用命令行命令时, 通常会出现这种情况: 只需更改命令的行为即可使用参数。 (也就是说, 你包含 **/b**参数以隐藏其他信息, 或者排除 **/b**参数以显示额外信息。)但是, 在其他情况下, 必须指定*参数值*。 参数值是传递给参数本身的其他信息。 例如, **/o**参数使你可以指定你希望 dir 命令对返回的数据进行排序的方式。 在其他选项中, 你可以使用参数值**e**按文件扩展名或参数值**s**进行排序, 以按文件大小排序。 例如, 此命令按文件扩展名对返回的数据进行排序。 注意 **/o**参数后紧跟的参数值**e**的包含方式:

    dir /oe

使用我们的示例文件夹, 返回的数据将如下所示, 文件扩展名按字母顺序排序:

``` 
    Directory: C:\

03/21/2013  03:39 PM    <DIR>          Deploy
03/21/2013  02:55 PM    <DIR>          Intel
07/26/2012  12:33 AM    <DIR>          PerfLogs
04/10/2013  10:29 AM    <DIR>          Program Files
04/08/2013  10:28 AM    <DIR>          Program Files (x86)
03/22/2013  08:44 AM    <DIR>          Users
04/11/2013  03:00 PM    <DIR>              Windows
03/21/2013  03:37 PM            207   setup.doc
03/21/2013  03:35 PM                 769   RHDSetup.exe
03/13/2013  02:53 PM                 117   pldok.log
              3 File(s)        1,093 bytes
              7 Dir(s)21,386,002,432 bytes free
```

或者, 帮助准确确定我们所谈论的内容:

设定. **首**  
RHDSetup. **执行**  
pldok. **先**

虽然 Windows PowerShell 使用不同术语, 但使用 Windows PowerShell 的基本方法与使用命令窗口相同: 你可以键入命令, 根据需要包含参数和参数值, 然后按 ENTER 执行这些命令。 但是, 如所述, Windows PowerShell 使用的术语不同于命令外壳使用的术语。 在 Windows PowerShell 中, 你执行的命令称为*cmdlet*。 反过来, 传递给 cmdlet 的参数称为*参数*, 传递给参数的值称为*参数值*。

前面的定义将稍加简化。 Cmdlet 实质上是一个迷你应用程序, 只能从 Windows PowerShell 环境内运行。 但是, 你也可以从 Windows PowerShell 内部运行其他命令和应用程序, 包括可以从命令窗口运行的大多数命令和应用程序。 例如, 如果要从 Windows PowerShell 内部启动记事本, 只需键入以下内容, 然后按 ENTER:

    notepad.exe

但是, 当需要管理 Skype for Business Online 时, 大多数管理员将依靠 Windows PowerShell cmdlet 来执行管理任务。 在时, 有很少的其他类型的命令或应用程序可用于管理 Skype for Business Online。 有时, 可以使用 Skype for Business Online cmdlet, 无需任何其他参数 (如有说明, 参数称为 Windows PowerShell 中的参数)。 例如, 以下命令调用[CsOnlineUser](https://technet.microsoft.com/en-us/library/JJ994026(v=OCS.15)) cmdlet, 不带任何其他参数。 该命令将返回有关您的所有 Skype for Business Online 用户的信息:

    Get-CsOnlineUser

但是, 大多数 Skype for Business Online cmdlet 也接受参数 (和参数值)。 请考虑以下命令:

    Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"

此命令包括三个部分:

  - Cmdlet **CsOnlineUser**。

  - 标识参数。 请注意, 在 Windows PowerShell 中, 参数始终以短划线 (-) 开头。 这意味着, 对于此同一 cmdlet, 将使用以下语法指示 UnassignedUser 参数:
    
        -UnassignedUser
    
    这一点非常有用, 不仅是因为参数必须以短划线开头, 而且也是因为它不同于命令窗口, 其中参数是使用正斜杠 (/) 开头的:
    
    ``` 
    /b
    ```

  - 参数值**kenmyer@litwareinc.com**。

该命令 (顺便说一下) 将返回有关特定用户的信息: kenmyer@litwareinc.com 标识的用户。

<div>

## <a name="see-also"></a>另请参阅


[Windows PowerShell 和 Skype for Business Online 简介](https://technet.microsoft.com/en-us/library/Dn362785(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

