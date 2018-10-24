---
title: Windows PowerShell Cmdlet、参数和参数值
TOCTitle: Windows PowerShell Cmdlet、参数和参数值
ms:assetid: 04615700-099f-4ac5-a801-ddeffccb9e4f
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn362765(v=OCS.15)
ms:contentKeyID: 56271115
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Windows PowerShell Cmdlet、参数和参数值

 

_**上一次修改主题：** 2015-06-22_

如果您熟悉在 Windows 的所有版本中找到的命令窗口（或者您熟悉 MS-DOS），那么当提及了解如何使用 Windows PowerShell 时，您有先行一步的优势。在命令窗口中键入命令，然后按 Enter。作为响应，计算机将运行命令或可执行文件。例如，要运行有关当前目录中的所有文件和文件夹的信息，您可以在命令提示符处键入此命令，然后按 Enter：

    dir

之后，您将获得有关当前目录中的所有文件和文件夹的信息：

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

当您仅键入命令或可执行文件的名称时，将返回结果的一个示例。然而，从命令窗口中运行的许多命令也接受*参数*。参数是指传递到命令的许多信息片段，可修改命令的行为。例如，您只希望查看当前目录中的文件和文件夹的名称，而不查看其他信息（例如，文件和文件夹的大小或者文件或文件夹的创建日期和时间）。在这种情况下，当运行 dir 命令时，您应追加 **/b** 参数：

    dir /b

当包括 **/b** 参数时，**dir** 命令仅报告在当前目录中找到的文件夹和文件的名称：

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

在上述命令中，**/b** 参数是将返回的数据限制为文件和文件夹名称所需的唯一信息。命令行命令通常这样使用：只有当需要更改命令的行为时才需要参数。（也就是说，包括 **/b** 参数可隐藏其他信息，排除 **/b** 参数可显示额外信息。）然而，在其他情况下，您必须指定*参数值*。参数值是传递给参数本身的附加信息。例如，**/o** 参数使您能够指定希望 dir 命令如何对返回的数据进行排序。除了其他选项之外，您可以使用参数值 **e** 按文件扩展名进行排序，或者使用参数值 **s** 按文件大小进行排序。例如，此命令按文件扩展名对返回的数据进行排序。请注意参数值 **e** 如何紧跟在 **/o** 参数后面：

    dir /oe

使用我们的示例文件夹，返回的数据如下所示，文件按扩展名的字母顺序进行排序：

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

或者，为帮助您更准确地了解所述内容：

setup. **doc**  
RHDSetup. **exe**  
pldok. **log**

尽管 Windows PowerShell 使用不同的术语，然而使用 Windows PowerShell 的基本方法与命令窗口相同：键入命令，根据需要包括参数和参数值，然后按 Enter 以执行这些命令。然而如前所述，Windows PowerShell 使用的术语与命令外壳不同。在 Windows PowerShell 中，您执行的命令称为 *cmdlet*。而传递到 cmdlet 的实际参数称为*形式参数*，传递到形式参数的值称为*形式参数值*。

前面的定义在某种程度上经过简化。Cmdlet 本质上是微型应用程序，只能从 Windows PowerShell 环境中运行。但是，您也可以从 Windows PowerShell 中运行其他命令和应用程序，包括可以从命令窗口运行的大多数命令和应用程序。例如，如果希望从 Windows PowerShell 中启动记事本，您只需键入以下内容，然后按 Enter：

    notepad.exe

但是，当提及管理 Skype for Business Online 时，大多数管理员依赖 Windows PowerShell cmdlet 执行管理任务。有时，可以使用少数其他类型的命令或应用程序管理 Skype for Business Online。而有时，可以不带任何附加参数使用 Skype for Business Online cmdlet（如前所述，实际参数在 Windows PowerShell 中称为形式参数）。例如，以下命令不带任何附加参数调用 [Get-CsOnlineUser](get-csonlineuser.md) cmdlet。该命令本身会返回有关您的所有 Skype for Business Online 用户的信息：

    Get-CsOnlineUser

但是，大多数 Skype for Business Online cmdlet 也接受参数（和参数值）。请考虑以下命令：

    Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"

此命令由三个部分组成：

  - cmdlet **Get-CsOnlineUser**。

  - Identity 参数。请注意，在 Windows PowerShell 中，参数始终以短划线 (-) 作为前缀。这意味着对于此相同 cmdlet，UnassignedUser 参数将使用此语法指明：
    
        -UnassignedUser
    
    知道此信息非常有用，不仅是因为参数必须以短划线作为前缀，而且也因为这不同于命令窗口，在命令窗口中，参数必须以正斜线 (/) 作为前缀：
    
    ``` 
    /b
    ```

  - 参数值 **kenmyer@litwareinc.com**。

该命令有时会返回有关特定用户的信息：标识为 kenmyer@litwareinc.com 的用户。

## 另请参阅

#### 概念

[Windows PowerShell 和 Lync Online 简介](an-introduction-to-windows-powershell-and-skype-for-business-online.md)

