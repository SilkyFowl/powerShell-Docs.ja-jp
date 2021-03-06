---
title: GroupBy (Format) の CustomEntry の CustomItem 要素Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: e8086c5330b6644f83316ad4ae33c33ba40d9eee
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783723"
---
# <a name="customitem-element-for-customentry-for-groupby-format"></a>GroupBy の CustomEntry の CustomItem 要素 (書式)

カスタムコントロールビューとその表示方法によって表示されるデータを定義します。 この要素は、新しいオブジェクトのグループをどのように表示するかを定義するときに使用されます。

Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (形式) GroupBy 要素の groupby (format) CustomControl 要素を groupby (形式) の CustomEntries 要素の groupby (format) Customentries 要素の CustomEntry の groupby (形式) 用に指定します。

## <a name="syntax"></a>構文

```xml
<CustomItem>
  <ExpressionBinding>...</ExpressionBinding>
  <Frame>...</Frame>
  <NewLine/>
  <Text>TextToDisplay</Text>
</CustomItem>
```

## <a name="attributes-and-elements"></a>属性および要素

次のセクションでは、要素の属性、子要素、および親要素について説明し `CustomItem` ます。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

|要素|説明|
|-------------|-----------------|
|[GroupBy の CustomItem の ExpressionBinding 要素 (書式)](./expressionbinding-element-for-customitem-for-groupby-format.md)|省略可能な要素です。<br /><br /> コントロールによって表示されるデータを定義します。|
|[GroupBy の CustomItem の Frame 要素 (書式)](./frame-element-for-customitem-for-groupby-format.md)|省略可能な要素です。<br /><br /> カスタムコントロールビューとその表示方法によって表示されるデータを定義します。|
|[GroupBy の CustomItem の NewLine 要素 (書式)](./newline-element-for-customitem-for-groupby-format.md)|省略可能な要素です。<br /><br /> コントロールの表示に空白行を追加します。|
|[GroupBy の CustomItem の Text 要素 (書式)](./text-element-for-customitem-for-groupby-format.md)|省略可能な要素です。<br /><br /> コントロールによって表示されるデータに追加のテキストを指定します。|

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[GroupBy の CustomControl の CustomEntry 要素 (書式)](./customentry-element-for-customcontrol-for-groupby-format.md)|カスタムコントロールビューの定義を提供します。|

## <a name="remarks"></a>解説

## <a name="see-also"></a>参照

[GroupBy の CustomControl の CustomEntry 要素 (書式)](./customentry-element-for-customcontrol-for-groupby-format.md)

[GroupBy の CustomItem の ExpressionBinding 要素 (書式)](./expressionbinding-element-for-customitem-for-groupby-format.md)

[GroupBy の CustomItem の Frame 要素 (書式)](./frame-element-for-customitem-for-groupby-format.md)

[GroupBy の CustomItem の NewLine 要素 (書式)](./newline-element-for-customitem-for-groupby-format.md)

[GroupBy の CustomItem の Text 要素 (書式)](./text-element-for-customitem-for-groupby-format.md)

[PowerShell 書式設定ファイルを記述する](./writing-a-powershell-formatting-file.md)
