---
title: CustomControl for ビュー (Format) に対する CustomItem の式のバインド要素 |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 1885a2820c0cb250aa6fda80544f58d06136cfeb
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87773795"
---
# <a name="expressionbinding-element-for-customitem-for-customcontrol-for-view-format"></a>View の CustomControl の CustomItem の ExpressionBinding 要素 (書式)

コントロールによって表示されるデータを定義します。 この要素は、カスタムコントロールビューを定義するときに使用されます。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (形式) の CustomControl 要素を表示するための CustomControl for view (format) CustomEntries 要素に対して、CustomControl for view (format) customentries 要素の CustomEntries for for view (format) の Customentries 要素を指定します。

## <a name="syntax"></a>構文

```xml
<ExpressionBinding>
  <CustomControl>...</CustomControl>
  <CustomControlName>NameofCommonCustomControl</CustomControlName>
  <EnumerateCollection/>
  <ItemSelectionCondition>...</ItemSelectionCondition>
  <PropertyName>Nameof.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate></ScriptBlock>
</ExpressionBinding>
```

## <a name="attributes-and-elements"></a>属性および要素

次のセクションでは、要素の属性、子要素、および親要素について説明し `ExpressionBinding` ます。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|`CustomControl Element`|省略可能な要素です。<br /><br /> このコントロールによって使用されるコントロールを定義します。|
|[View の CustomControl の ExpressionBinding の CustomControlName 要素 (書式)](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)|省略可能な要素です。<br /><br /> コモンコントロールまたはビューコントロールの名前を指定します。|
|[View の CustomControl の ExpressionBinding の EnumerateCollection 要素 (書式)](./enumeratecollection-element-for-expressionbinding-for-customcontrol-for-view-format.md)|省略可能な要素です。<br /><br /> コレクションの要素が表示されることを指定します。|
|[CustomControl for View (Format) の式のバインドの ItemSelectionCondition 要素](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)|省略可能な要素です。<br /><br /> このコントロールを使用するために必要な条件を定義します。|
|[View の CustomControl の ExpressionBinding の PropertyName 要素 (書式)](./propertyname-element-for-expressionbinding-for-customcontrol-for-view-format.md)|省略可能な要素です。<br /><br /> コントロールによって表示される値を持つ .NET プロパティを指定します。|
|[CustomCustomControl for View (Format) の式のバインドの ScriptBlock 要素](./scriptblock-element-for-expressionbinding-for-customcontrol-for-view-format.md)|省略可能な要素です。<br /><br /> コントロールによって値が表示されるスクリプトを指定します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[View の CustomControl の CustomEntry の CustomItem 要素 (書式)](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)|カスタムコントロールビューとその表示方法によって表示されるデータを定義します。|

## <a name="remarks"></a>解説

## <a name="see-also"></a>参照

[View の CustomControl の ExpressionBinding の CustomControlName 要素 (書式)](./customcontrolname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[View の CustomControl の ExpressionBinding の EnumerateCollection 要素 (書式)](./enumeratecollection-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[CustomControl for View (Format) の式のバインドの ItemSelectionCondition 要素](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)

[View の CustomControl の ExpressionBinding の PropertyName 要素 (書式)](./propertyname-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[View の CustomControl の ExpressionBinding の ScriptBlock 要素 (書式)](./scriptblock-element-for-expressionbinding-for-customcontrol-for-view-format.md)

[View の CustomControl の CustomEntry の CustomItem 要素 (書式)](./customitem-element-for-customentry-for-customcontrol-for-view-format.md)

[PowerShell 書式設定ファイルを記述する](./writing-a-powershell-formatting-file.md)
