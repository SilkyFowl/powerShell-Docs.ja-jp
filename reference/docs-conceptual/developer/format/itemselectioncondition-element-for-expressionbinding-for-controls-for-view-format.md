---
title: ビューのコントロールの式のバインドの ItemSelectionCondition 要素 (Format) |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: e8e3ea64fd947fbb2b98c410ac08533f386c9505
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87781207"
---
# <a name="itemselectioncondition-element-for-expressionbinding-for-controls-for-view-format"></a><span data-ttu-id="156f2-102">View の Controls の ExpressionBinding の ItemSelectionCondition 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="156f2-102">ItemSelectionCondition Element for ExpressionBinding for Controls for View (Format)</span></span>

<span data-ttu-id="156f2-103">このコントロールを使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="156f2-103">Defines the condition that must exist for this control to be used.</span></span> <span data-ttu-id="156f2-104">この要素は、ビューで使用できるコントロールを定義するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="156f2-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="156f2-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (書式) コントロール要素 (書式) のコントロールの要素 (形式) コントロール要素を表示するためのコントロールの CustomControl 要素 (形式) CustomControl for ビュー (形式) の CustomEntries 要素ビュー (format) のコントロール用の CustomEntries のコントロールのビュー (形式) の式のバインド要素を表示するためのコントロール用の Customentries のバインド要素 (format) ビューのコントロールの式のバインドのバインド要素 (format)</span><span class="sxs-lookup"><span data-stu-id="156f2-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) CustomItem Element for CustomEntry for Controls for View (Format) ExpressionBinding Element for CustomItem for Controls for View (Format) ItemSelectionCondition Element of ExpressionBinding for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="156f2-106">構文</span><span class="sxs-lookup"><span data-stu-id="156f2-106">Syntax</span></span>

```xml
<ItemSelectionCondition>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</ItemSelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="156f2-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="156f2-107">Attributes and Elements</span></span>

<span data-ttu-id="156f2-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `ItemSelectionCondition` ます。</span><span class="sxs-lookup"><span data-stu-id="156f2-108">The following sections describe attributes, child elements, and the parent element of the `ItemSelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="156f2-109">属性</span><span class="sxs-lookup"><span data-stu-id="156f2-109">Attributes</span></span>

<span data-ttu-id="156f2-110">なし。</span><span class="sxs-lookup"><span data-stu-id="156f2-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="156f2-111">子要素</span><span class="sxs-lookup"><span data-stu-id="156f2-111">Child Elements</span></span>

|<span data-ttu-id="156f2-112">要素</span><span class="sxs-lookup"><span data-stu-id="156f2-112">Element</span></span>|<span data-ttu-id="156f2-113">説明</span><span class="sxs-lookup"><span data-stu-id="156f2-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="156f2-114">View の Controls の ItemSelectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="156f2-114">PropertyName Element for ItemSelectionCondition for Controls for View (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md)|<span data-ttu-id="156f2-115">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="156f2-115">Optional element.</span></span><br /><br /> <span data-ttu-id="156f2-116">条件をトリガーする .NET プロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="156f2-116">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="156f2-117">View の Controls の ItemSelectionCondition の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="156f2-117">ScriptBlock Element for ItemSelectionCondition for Controls for View (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-controls-for-view-format.md)|<span data-ttu-id="156f2-118">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="156f2-118">Optional element.</span></span><br /><br /> <span data-ttu-id="156f2-119">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="156f2-119">Specifies the script that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="156f2-120">親要素</span><span class="sxs-lookup"><span data-stu-id="156f2-120">Parent Elements</span></span>

|<span data-ttu-id="156f2-121">要素</span><span class="sxs-lookup"><span data-stu-id="156f2-121">Element</span></span>|<span data-ttu-id="156f2-122">説明</span><span class="sxs-lookup"><span data-stu-id="156f2-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="156f2-123">View の Controls の CustomItem の ExpressionBinding 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="156f2-123">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)|<span data-ttu-id="156f2-124">コントロールによって表示されるデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="156f2-124">Defines the data that is displayed by the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="156f2-125">解説</span><span class="sxs-lookup"><span data-stu-id="156f2-125">Remarks</span></span>

<span data-ttu-id="156f2-126">この条件には、1つのプロパティ名またはスクリプトを指定できますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="156f2-126">You can specify one property name or a script for this condition but cannot specify both.</span></span>

## <a name="see-also"></a><span data-ttu-id="156f2-127">参照</span><span class="sxs-lookup"><span data-stu-id="156f2-127">See Also</span></span>

[<span data-ttu-id="156f2-128">View の Controls の ItemSelectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="156f2-128">PropertyName Element for ItemSelectionCondition for Controls for View (Format)</span></span>](./propertyname-element-for-itemselectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="156f2-129">View の Controls の ItemSelectionCondition の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="156f2-129">ScriptBlock Element for ItemSelectionCondition for Controls for View (Format)</span></span>](./scriptblock-element-for-itemselectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="156f2-130">View の Controls の CustomItem の ExpressionBinding 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="156f2-130">ExpressionBinding Element for CustomItem for Controls for View (Format)</span></span>](./expressionbinding-element-for-customitem-for-controls-for-view-format.md)

[<span data-ttu-id="156f2-131">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="156f2-131">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
