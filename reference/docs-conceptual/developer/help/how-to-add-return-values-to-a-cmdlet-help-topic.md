---
title: コマンドレットのヘルプ トピックに戻り値を追加する方法
ms.date: 09/12/2016
ms.openlocfilehash: c164556cd06b332d04857987360c98f740a150b5
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/22/2020
ms.locfileid: "86893358"
---
# <a name="how-to-add-return-values-to-a-cmdlet-help-topic"></a>コマンドレットのヘルプ トピックに戻り値を追加する方法

このセクションでは、出力セクションを PowerShell コマンドレットのヘルプトピックに追加する方法について説明します。 **OUTPUTS**セクションには、コマンドレットが返す、またはパイプラインを渡すオブジェクトの .net クラスが一覧表示されます。

**OUTPUTS**セクションに追加できるクラスの数に制限はありません。 コマンドレットの戻り値の型はノードで囲み `<command:returnValues>` 、各クラスは要素で囲まれてい `<command:returnValue>` ます。

コマンドレットで出力が生成されない場合は、出力がないことを示すためにこのセクションを使用します。 たとえば、クラス名の代わりに、 **「None** 」と記述し、簡単な説明を入力します。 コマンドレットによって出力が条件付きで生成される場合は、このノードを使用して条件を説明し、条件付き出力を記述します。

スキーマには、各要素に2つの要素が含まれてい `<maml:description>` `<command:returnValue>` ます。
ただし、この `Get-Help` コマンドレットは要素の内容のみを表示し `<command:returnValue>/<maml:description>` ます。

PowerShell 3.0 以降では、 `Get-Help` コマンドレットによって要素の内容が表示され `<maml:uri>` ます。
この要素を使用すると、.NET クラスを説明するトピックにユーザーを誘導できます。

次の XML は、ノードを示して `<maml:returnValues>` います。

```xml
<command:returnValues>
  <command:returnValue>
    <dev:type>
      <maml:name> Class Name </maml:name>
      <maml:uri>  URI of a topic that describes the class </maml:uri>
      <maml:description/>
    </dev:type>
    <maml:description>
       <maml:para> Brief description <maml:para>

</maml:description>
  </command: returnValue>
</command: returnValues>
```

次の XML は、ノードを使用して出力の種類をドキュメント化する例を示して `<maml:returnValues>` います。

```xml
<command:returnValues>
  <command:returnValue>
    <dev:type>
      <maml:name> System.DateTime </maml:name>
      <maml:uri>  https://msdn.microsoft.com/library/system.datetime.aspx </maml:uri>
      <maml:description/>
    </dev:type>
    <maml:description>
      <maml:para> Get-Date returns a DateTime object. <maml:para>
    </maml:description>
  </command: returnValue>
</command: returnValues>
```
