---
title: View (Format) の CustomControl の ItemSelectionCondition の ScriptBlock 要素Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 31873e886af04f8eedaf859af1d6bc1d5bcfdbf7
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87772877"
---
# <a name="scriptblock-element-for-itemselectioncondition-for-customcontrol-for-view-format"></a>View の CustomControl の ItemSelectionCondition の ScriptBlock 要素 (書式)

条件をトリガーするスクリプトを指定します。 このスクリプトがに評価されると、 `true` 条件が満たされ、コントロールが使用されます。 この要素は、カスタムコントロールビューを定義するときに使用されます。

Configuration 要素 (Format) ViewDefinitions 要素 (形式) ビュー要素 (Format) CustomControl 要素 (形式) CustomControl for view (format) の CustomEntries for ビュー (形式) の CustomEntries を指定します。 Mentry for view (format) 式のバインド要素の CustomControl for view (format) ItemSelectionCondition 要素の CustomControl for view (format) ScriptBlock 要素の CustomControl for ビューの ItemSelectionCondition のバインド要素

## <a name="syntax"></a>構文

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a>属性および要素

次のセクションでは、要素の属性、子要素、および親要素について説明し `ScriptBlock` ます。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[CustomControl for View (Format) の式のバインドの ItemSelectionCondition 要素](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)|このコントロールを使用するために必要な条件を定義します。|

## <a name="text-value"></a>テキスト値

評価されるスクリプトを指定します。

## <a name="remarks"></a>解説

この要素が使用されている場合、選択条件を定義するときに[PropertyName](./propertyname-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)要素を指定することはできません。

## <a name="see-also"></a>参照

[View の CustomControl の ItemSelectionCondition の PropertyName 要素 (書式)](./propertyname-element-for-itemselectioncondition-for-customcontrol-for-view-format.md)

[CustomControl for View (Format) の式のバインドの ItemSelectionCondition 要素](./itemselectioncondition-element-for-expressionbinding-for-customcontrol-format.md)

[PowerShell 書式設定ファイルを記述する](./writing-a-powershell-formatting-file.md)
