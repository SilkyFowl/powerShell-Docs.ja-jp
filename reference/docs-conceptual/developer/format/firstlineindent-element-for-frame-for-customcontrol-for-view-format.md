---
title: CustomControl for View (Format) のフレームの FirstLineIndent 要素Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 0d51be5b5fc04bc0ea8442ca96767b1d9d8473a4
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785814"
---
# <a name="firstlineindent-element-for-frame-for-customcontrol-for-view-format"></a>View の CustomControl の Frame の FirstLineIndent 要素 (書式)

データの最初の行を右にシフトする文字数を指定します。 この要素は、カスタムコントロールビューを定義するときに使用されます。

Configuration 要素 (Format) ViewDefinitions 要素 (形式) ビュー要素 (Format) CustomControl 要素 (形式) の customentries for CustomControl for view (format) Customentries 要素の CustomEntries for CustomControl for View (format) の Customentries 要素を使用して、for View (Format) FirstLineIndent 要素を設定します。

## <a name="syntax"></a>構文

```xml
<FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
```

## <a name="attributes-and-elements"></a>属性および要素

次のセクションでは、要素の属性、子要素、および親要素について説明し `FirstLineIndent` ます。

### <a name="attributes"></a>属性

なし。

### <a name="child-elements"></a>子要素

なし。

### <a name="parent-elements"></a>親要素

|要素|説明|
|-------------|-----------------|
|[View の CustomControl の CustomItem の Frame 要素 (書式)](./frame-element-for-customitem-for-customcontrol-for-view-format.md)|データを左右に移動するなど、データの表示方法を定義します。|

## <a name="text-value"></a>テキスト値

データの最初の行をシフトする文字数を指定します。

## <a name="remarks"></a>解説

この要素が指定されている場合、 [Firstlinehanging](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md)要素を指定することはできません。

## <a name="see-also"></a>参照

[View の CustomControl の Frame の FirstLineHanging 要素 (書式)](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md)

[View の CustomControl の CustomItem の Frame 要素 (書式)](./frame-element-for-customitem-for-customcontrol-for-view-format.md)

[PowerShell 書式設定ファイルを記述する](./writing-a-powershell-formatting-file.md)
