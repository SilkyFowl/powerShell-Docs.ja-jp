---
title: WideControl (Format) の EntrySelectedBy の SelectionCondition の ScriptBlock 要素Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: c8f2223d4a1217786a930eb82390c24b81d2f72e
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787616"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format"></a><span data-ttu-id="cdf4e-102">WideControl の EntrySelectedBy の SelectionCondition の ScriptBlock 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="cdf4e-102">ScriptBlock Element for SelectionCondition for EntrySelectedBy for WideControl (Format)</span></span>

<span data-ttu-id="cdf4e-103">条件をトリガーするスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="cdf4e-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="cdf4e-104">このスクリプトがに評価されると、 `true` 条件が満たされ、ワイドエントリの定義が使用されます。</span><span class="sxs-lookup"><span data-stu-id="cdf4e-104">When this script is evaluated to `true`, the condition is met, and the wide entry definition is used.</span></span>

<span data-ttu-id="cdf4e-105">Configuration 要素 (Format) ViewDefinitions 要素 (書式) ビュー要素 (format) WideControl Element (format) WideEntries Element (format) WideEntry Element (format) Element (format) Element (format) EntrySelectedBy for WideEntry (format) の SelectionCondition 要素を WideEntry (format) の selectioncondition 要素に指定します。 EntrySelectedBy for WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="cdf4e-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) SelectionCondition Element for EntrySelectedBy for WideEntry (Format) ScriptBlock Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="cdf4e-106">構文</span><span class="sxs-lookup"><span data-stu-id="cdf4e-106">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="cdf4e-107">属性および要素</span><span class="sxs-lookup"><span data-stu-id="cdf4e-107">Attributes and Elements</span></span>

<span data-ttu-id="cdf4e-108">次のセクションでは、要素の属性、子要素、および親要素について説明し `ScriptBlock` ます。</span><span class="sxs-lookup"><span data-stu-id="cdf4e-108">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="cdf4e-109">属性</span><span class="sxs-lookup"><span data-stu-id="cdf4e-109">Attributes</span></span>

<span data-ttu-id="cdf4e-110">なし。</span><span class="sxs-lookup"><span data-stu-id="cdf4e-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="cdf4e-111">子要素</span><span class="sxs-lookup"><span data-stu-id="cdf4e-111">Child Elements</span></span>

<span data-ttu-id="cdf4e-112">なし。</span><span class="sxs-lookup"><span data-stu-id="cdf4e-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="cdf4e-113">親要素</span><span class="sxs-lookup"><span data-stu-id="cdf4e-113">Parent Elements</span></span>

|<span data-ttu-id="cdf4e-114">要素</span><span class="sxs-lookup"><span data-stu-id="cdf4e-114">Element</span></span>|<span data-ttu-id="cdf4e-115">説明</span><span class="sxs-lookup"><span data-stu-id="cdf4e-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="cdf4e-116">WideEntry (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="cdf4e-116">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="cdf4e-117">この定義を使用するために必要な条件を定義します。</span><span class="sxs-lookup"><span data-stu-id="cdf4e-117">Defines the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="cdf4e-118">テキスト値</span><span class="sxs-lookup"><span data-stu-id="cdf4e-118">Text Value</span></span>

<span data-ttu-id="cdf4e-119">評価されるスクリプトを指定します。</span><span class="sxs-lookup"><span data-stu-id="cdf4e-119">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="cdf4e-120">解説</span><span class="sxs-lookup"><span data-stu-id="cdf4e-120">Remarks</span></span>

<span data-ttu-id="cdf4e-121">選択条件では、評価するスクリプトまたはプロパティ名を少なくとも1つ指定する必要がありますが、両方を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="cdf4e-121">The selection condition must specify at least one script or property name to evaluate, but cannot specify both.</span></span> <span data-ttu-id="cdf4e-122">選択条件の使用方法の詳細については、「[データを表示するときの条件の定義](./defining-conditions-for-displaying-data.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cdf4e-122">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="cdf4e-123">ワイドビューのその他のコンポーネントの詳細については、「 [Wide ビュー](./creating-a-wide-view.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cdf4e-123">For more information about other components of a wide view, see [Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="cdf4e-124">参照</span><span class="sxs-lookup"><span data-stu-id="cdf4e-124">See Also</span></span>

[<span data-ttu-id="cdf4e-125">ワイド ビューを作成する</span><span class="sxs-lookup"><span data-stu-id="cdf4e-125">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="cdf4e-126">データを表示するときの条件の定義</span><span class="sxs-lookup"><span data-stu-id="cdf4e-126">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="cdf4e-127">WideEntry の EntrySelectedBy の SelectionCondition の PropertyName 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="cdf4e-127">PropertyName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

[<span data-ttu-id="cdf4e-128">WideEntry (Format) の EntrySelectedBy の SelectionCondition 要素</span><span class="sxs-lookup"><span data-stu-id="cdf4e-128">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="cdf4e-129">PowerShell 書式設定ファイルを記述する</span><span class="sxs-lookup"><span data-stu-id="cdf4e-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
