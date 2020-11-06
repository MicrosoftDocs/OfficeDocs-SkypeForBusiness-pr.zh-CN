---
title: 管理团队管理中心中的表扬应用
author: cichur
ms.author: v-cichur
manager: serdars
audience: admin
ms.topic: article
ms.service: msteams
localization_priority: Normal
description: 了解 Microsoft 团队管理中心中的表扬应用中的管理员设置
ms.openlocfilehash: 4e96355a3b05af2c9df484a2451014fbbaf0e926
ms.sourcegitcommit: 4b01e4091d22d925d22a2e921963843175a4180b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/06/2020
ms.locfileid: "48929523"
---
# <a name="manage-the-praise-app-in-the-microsoft-teams-admin-center"></a>在 Microsoft 团队管理中心中管理表扬应用

> [!NOTE]
> 管理员必须拥有团队许可证才能访问此功能。 如果您尝试在没有团队许可证的情况下访问此功能，您将收到一条错误消息。

Microsoft 团队中的表扬应用可帮助用户向组织或课堂成员显示感激。 通过选择要选择的锁屏提醒集和创建您自己的徽章的选项，表扬旨在帮助您认识到团队用户在团队用户执行的工作范围内，从教师到一线工作人员的工作量。 若要了解详细信息，请参阅 [向用户发送表扬](https://support.microsoft.com/office/send-praise-to-people-50f26b47-565f-40fe-8642-5ca2a5ed261e)。

管理员可以从 Microsoft 团队管理中心控制哪些徽章对其组织可用。 在左侧导航中，转到 " **团队应用" > "管理应用** "。 在应用列表中，单击 " **表扬** "，然后选择 " **设置** "。  在此处，您可以选择启用默认的和内置的锁屏提醒集，并创建自定义徽章。

![表扬应用的 "设置" 选项卡的屏幕截图](media/manage-praise-app-settings.png)

> [!NOTE]
> 表扬应用功能不适用于美国政府云。

## <a name="use-built-in-badge-sets"></a>使用内置的锁屏提醒集

内置集是 Microsoft 为表扬应用设计的锁屏提醒的集合。 管理员无法编辑这些集。 默认徽章集已启用并在表扬应用中可用。 若要更改默认集或任何锁屏提醒集的可用性，请将相应的开关切换为 "打开" 或 "关闭"。 

<a name="default-badges"></br></a>

### <a name="default-badges"></a>默认锁屏提醒

默认的锁屏提醒集旨在帮助团队用户识别其对等用户在其工作上进行操作。

![默认徽章集的预览](media/default-set-praise.png)

<a name="sel-edu-badges"></br></a>

### <a name="social-and-emotional-learning-badges-for-education"></a>用于教育的社交和激动人心的学习徽章

教师可以通过标记来识别单个学生的社交和激动人心的学习 (SEL) 成就和行为，其中演示了这些概念。

![用于教育的社交和激动人心学习徽章的预览](media/sel-edu-set-praise.png)

<a name="create-your-own-badges"></br></a>

## <a name="create-your-own-badges"></a>创建自己的徽章

选择 " **创建自定义徽章** "。 在此处，您可以在侧面板中设计自定义徽章。 您最多可以创建25个自定义徽章。 

![创建自定义锁屏提醒窗格的屏幕截图](media/manage-praise-app-create-custom-badge.png)

1. 输入徽章名称。 这是用户发送表扬时将在锁屏提醒上显示的名称。

2. 设置锁屏提醒颜色。 若要设置锁屏提醒的文本和背景色，需要输入十六进制) 值的十六进制 (的颜色。

   > [!TIP]
   > 如果您不熟悉十六进制值，本文将 [介绍](#hex-colors-intro) 如何使用它们。

3. 上载锁屏提醒图像。 接受的文件类型为。PNG. 图像文件必须小于 40 KB，最大尺寸为 216 X 216 像素。
![带有标签的背景、文本和图像字段的锁屏提醒](media/praise-app-badge-fields.png)

4. 本地化徽章名称：在 " **本地化徽章名称** " 下，选择 " **添加** "。 从下拉列表中选择所需的区域设置。 然后在指定语言中输入徽章名称。

5. 从特定区域设置中排除徽章：在 " **从这些区域设置中排除徽章** " 下，选择 " **添加** "。 从下拉列表中选择要排除的区域设置。

6. 选择 " **应用** "。 您的新锁屏提醒现在将显示在 "自定义锁屏提醒" 表中。

> [!NOTE]
> 如果跳过第4步和第5步，则标记将为所有区域设置的默认语言。
>
> 更改完锁屏提醒选择后，请确保选择 " **提交** "。 在你的组织可使用这些更改之前，可能需要长达几个小时。

<a name="hex-colors-intro"></br></a>

## <a name="specify-colors-with-hex-values"></a>指定具有十六进制值的颜色

十六进制颜色值是六个十六进制数字的字符串，表示红色 (RR 的浓度) ，绿色 (GG) ，以及蓝色 (BB) ，在00到 FF 的比例上以特定颜色表示。 将所有三种颜色的值放在一起时，将得到一个十六进制值： #RRGGBB

例如，红色的十六进制值是 #FF0000 的，因为在最大可能值（即，"FF" 和 "绿色" 和 "蓝色"）下设置 "红色"，每个值最小可能值00。

若要浏览不同颜色及其十六进制值，请查看 [必应颜色选取器](https://www.bing.com/search?q=color+picker)。

下面是开始使用的示例颜色的列表：

|颜色  |十六进制值|
|-------|---------|
|![十六进制颜色 #FF6666](media/hexColor1.png)|  #FF6666   |
|![十六进制颜色 #7FFFD4](media/hexColor2.png)|  #7FFFD4   |
|![十六进制颜色 #FF75F0](media/hexColor3.png)|  #FF75F0   |
|![十六进制颜色 #00BFFF](media/hexColor4.png)|  #00BFFF   |
|![十六进制颜色 #800080](media/hexColor5.png)|  #800080   |
|![十六进制颜色 #000000](media/hexColor6.png)|  #000000   |

<a name="best-practices"></br></a>

## <a name="best-practices-for-creating-custom-badges"></a>创建自定义徽章的最佳做法

**一次提交您的所有徽章。** 由于处理新徽章需要花费一些时间，因此最好先将所有自定义徽章添加到表格中，然后再提交。

**选择颜色时，请牢记辅助功能。** 某些颜色比其他颜色更好。  创建文本和背景颜色之间的对比度，使徽章名称易于阅读。 例如，如果您选择了深色背景色，请选择一种浅色文本颜色。

**选择图像时，请记住徽章尺寸。** 为了获得最佳质量，建议上载 216 x 216 像素 (的图像文件，这是最大尺寸) 。 避免拉伸或扭曲图像以适合这些尺寸。

**如果您的锁屏提醒图像不是矩形，请使图像透明。** 在将图像文件上载到表扬之前，需要执行此操作。

![左侧：带有非透明图像的锁屏提醒，右侧：带有透明图像的锁屏提醒](media/praise-app-best-practices.png)

## <a name="badge-set-assets"></a>徽章集资源

无法修改内置的锁屏提醒集，因此当启用内置集时，该集中的所有徽章都将添加到表扬应用。 如果想要从内置的组中添加特定徽章并退出其他人，请重新创建要用作自定义徽章的徽章。 你可以下载锁屏提醒图像，并从下表中的内置集查找锁屏提醒的文本和背景颜色。

### <a name="default-badges-assets"></a>默认锁屏提醒资源

</br>

|徽章名称     |图像文件  |文本颜色 | 背景色 |
|---------------|------------|---------- |--------|
|Achiever       |[Achiever PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/achiever-badge.png)|#D36E70    |#E3F4FC|
|主要        |[非常棒的 PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/awesome-badge.png)</a>|#8283B2    |#D1EFF2|
|教练          |[教练 PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/coach-badge.png)</a>|#6AA55A    |#DBF1D6|
|勇气        |[勇气 PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/courage-badge.png)</a>|#DC5041    |#FCF6C8|
|极       |[创作 PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/creative-badge.png) |#CF9D50    |#FCF6C8|
|非      |[非独占 PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/inclusive-badge.png)</a>|#3C77BB    |#E2F4FC|
|种类心     |[类型心形 PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/kind-heart-badge.png)</a>|#D36D6E    |#F4DEDE|
|能力     |[领先的 PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/leadership-badge.png)|#419098    |#D2EAEC|
|Optimism       |[Optimism PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/optimism-badge.png)</a>|#D8338C    |#F4DDDE|
|问题规划求解 |[问题求解 PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/problem-solver-badge.png)|#B8916E    |#CBDADF|
|工作组玩家    |[工作组播放器 PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/team-player-badge.png)|#8B8DC0    |#F4EEC0|
|谢谢      |[谢谢您的 PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/default-set/thank-you-badge.png)|#469CA4    |#BACCB6|

</br>

### <a name="social-and-emotional-learning-badges-for-education-assets"></a>教育资产的社交和激动人心的学习徽章

</br>

|徽章名称        |图像文件  |文本颜色 | 背景色 |
|------------------|------------|---------- |--------|
|通信     |[通信 PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/communication-badge.png)|#FFFFFF    |#173B65|
|关键思维 |[重要思维 PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/critical-thinking-badge.png)|#FFFFFF    |#084D26|
|好奇心         |[好奇心 PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/curiosity-badge.png)|#FFFFFF    |#008078|
|理解           |[理解 PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/empathy-badge.png)|#FFFFFF    |#650B35|
|目标追求      |[目标追求 PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/goal-pursuit-badge.png)|#FFFFFF    |#006F95|
|动机        |[激励 PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/motivation-badge.png)|#FFFFFF    |#C52127|
|持久化       |[持久性 PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/persistence-badge.png)|#FFFFFF    |#167D3E|
|互相           |[尊重 PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/respect-badge.png)|#FFFFFF    |#8251A0|
|起    |[责任 PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/responsibility-badge.png)|#FFFFFF    |#B05DA3|
|自我意识    |[自我感知 PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/self-awareness-badge.png)|#FFFFFF    |#1680E5|
|自我管理   |[自我管理 PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/self-management-badge.png)|#FFFFFF    |#4C144D|
|Thoughtfulness    |[Thoughtfulness PNG](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/raw/live/Teams/downloads/praise-app/sel-edu-set/thoughtfulness-badge.png)|#FFFFFF    |#EE4086|
