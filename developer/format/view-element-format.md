---
title: 要素 (形式) の表示 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d837d5d4-ed2e-4d84-a306-0b5d2ad2d0bf
caps.latest.revision: 24
ms.openlocfilehash: 2361c1117757569bef0815018c75764430a9e7a8
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56856148"
---
# <a name="view-element-format"></a><span data-ttu-id="61936-102">View 要素 (書式)</span><span class="sxs-lookup"><span data-stu-id="61936-102">View Element (Format)</span></span>

<span data-ttu-id="61936-103">1 つまたは複数の .NET オブジェクトを表示するビューを定義します。</span><span class="sxs-lookup"><span data-stu-id="61936-103">Defines a view that displays one or more .NET objects.</span></span> <span data-ttu-id="61936-104">書式設定ファイルで定義できるビューの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="61936-104">There is no limit to the number of views that can be defined in a formatting file.</span></span>

<span data-ttu-id="61936-105">構成要素 (形式) ViewDefinitions 要素 (形式) 表示要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="61936-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="61936-106">構文</span><span class="sxs-lookup"><span data-stu-id="61936-106">Syntax</span></span>

```xml
<View>
  <Name>Friendly name of view.</Name>
  <ViewSelectedBy>...</ViewSelectedBy>
  <Controls>...</Controls>
  <GroupBy>...</GroupBy>
  <TableControl>...</TableControl>
  <ListControl>...</ListControl>
  <WideControl>...</WideControl>
  <CustomControl>...</CustomControl>
</View>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="61936-107">属性と要素</span><span class="sxs-lookup"><span data-stu-id="61936-107">Attributes and Elements</span></span>

<span data-ttu-id="61936-108">次のセクションでは、属性、子要素、およびの親要素について説明します、`View`要素。</span><span class="sxs-lookup"><span data-stu-id="61936-108">The following sections describe the attributes, child elements, and the parent element of the `View` element.</span></span> <span data-ttu-id="61936-109">コントロールの子要素の 1 つだけを指定する必要があり、ビューとビューを使用しているオブジェクトの名前を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="61936-109">You must specify one and only one of the control child elements, and you must specify the name of the view and the objects that use the view.</span></span> <span data-ttu-id="61936-110">カスタム コントロールを定義するには、オブジェクトをグループ化する方法、および、帯域外のかどうか、ビューには指定は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="61936-110">Defining custom controls, how to group objects, and specifying if the view is out-of-band are optional.</span></span>

### <a name="attributes"></a><span data-ttu-id="61936-111">属性</span><span class="sxs-lookup"><span data-stu-id="61936-111">Attributes</span></span>

<span data-ttu-id="61936-112">なし。</span><span class="sxs-lookup"><span data-stu-id="61936-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="61936-113">子要素</span><span class="sxs-lookup"><span data-stu-id="61936-113">Child Elements</span></span>

|<span data-ttu-id="61936-114">要素</span><span class="sxs-lookup"><span data-stu-id="61936-114">Element</span></span>|<span data-ttu-id="61936-115">説明</span><span class="sxs-lookup"><span data-stu-id="61936-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="61936-116">ビュー (形式) のコントロール要素</span><span class="sxs-lookup"><span data-stu-id="61936-116">Controls Element for View (Format)</span></span>](./controls-element-for-view-format.md)|<span data-ttu-id="61936-117">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="61936-117">Optional element.</span></span><br /><br /> <span data-ttu-id="61936-118">ビュー内からの名前で参照できるコントロールのセットを定義します。</span><span class="sxs-lookup"><span data-stu-id="61936-118">Defines a set of controls that can be referenced by their name from within the view.</span></span>|
|[<span data-ttu-id="61936-119">カスタム コントロール要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="61936-119">CustomControl Element (Format)</span></span>](./customcontrol-element-for-groupby-format.md)|<span data-ttu-id="61936-120">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="61936-120">Optional element.</span></span><br /><br /> <span data-ttu-id="61936-121">ビューのカスタム コントロールの書式を定義します。</span><span class="sxs-lookup"><span data-stu-id="61936-121">Defines a custom control format for the view.</span></span>|
|[<span data-ttu-id="61936-122">ビュー (形式) の GroupBy 要素</span><span class="sxs-lookup"><span data-stu-id="61936-122">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)|<span data-ttu-id="61936-123">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="61936-123">Optional element.</span></span><br /><br /> <span data-ttu-id="61936-124">.NET オブジェクトのメンバーをグループ化する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="61936-124">Defines how the members of the .NET objects are grouped.</span></span>|
|[<span data-ttu-id="61936-125">ListControl 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="61936-125">ListControl Element (Format)</span></span>](./listcontrol-element-format.md)|<span data-ttu-id="61936-126">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="61936-126">Optional element.</span></span><br /><br /> <span data-ttu-id="61936-127">ビューの一覧の形式を定義します。</span><span class="sxs-lookup"><span data-stu-id="61936-127">Defines a list format for the view.</span></span>|
|[<span data-ttu-id="61936-128">ビュー (形式) の name 要素</span><span class="sxs-lookup"><span data-stu-id="61936-128">Name Element for View (Format)</span></span>](./name-element-for-view-format.md)|<span data-ttu-id="61936-129">必須の要素。</span><span class="sxs-lookup"><span data-stu-id="61936-129">Required element.</span></span><br /><br /> <span data-ttu-id="61936-130">ビューを参照するための名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="61936-130">Specifies the name used to reference the view.</span></span>|
|[<span data-ttu-id="61936-131">TableControl 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="61936-131">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)|<span data-ttu-id="61936-132">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="61936-132">Optional element.</span></span><br /><br /> <span data-ttu-id="61936-133">ビューのテーブル形式を定義します。</span><span class="sxs-lookup"><span data-stu-id="61936-133">Defines a table format for the view.</span></span>|
|[<span data-ttu-id="61936-134">表示 (形式) ViewSelectedBy 要素</span><span class="sxs-lookup"><span data-stu-id="61936-134">ViewSelectedBy Element for View (Format)</span></span>](./viewselectedby-element-format.md)|<span data-ttu-id="61936-135">必須の要素。</span><span class="sxs-lookup"><span data-stu-id="61936-135">Required element.</span></span><br /><br /> <span data-ttu-id="61936-136">このビューを表示する .NET オブジェクトを定義します。</span><span class="sxs-lookup"><span data-stu-id="61936-136">Defines the .NET objects that this view displays.</span></span>|
|[<span data-ttu-id="61936-137">WideControl 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="61936-137">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)|<span data-ttu-id="61936-138">省略可能な要素です。</span><span class="sxs-lookup"><span data-stu-id="61936-138">Optional element.</span></span><br /><br /> <span data-ttu-id="61936-139">ワイド (1 つの値) を定義するビューの一覧の形式。</span><span class="sxs-lookup"><span data-stu-id="61936-139">Defines a wide (single value) list format for the view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="61936-140">親要素</span><span class="sxs-lookup"><span data-stu-id="61936-140">Parent Elements</span></span>

|<span data-ttu-id="61936-141">要素</span><span class="sxs-lookup"><span data-stu-id="61936-141">Element</span></span>|<span data-ttu-id="61936-142">説明</span><span class="sxs-lookup"><span data-stu-id="61936-142">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="61936-143">ViewDefinitions 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="61936-143">ViewDefinitions Element (Format)</span></span>](./viewdefinitions-element-format.md)|<span data-ttu-id="61936-144">オブジェクトを表示するために使用するビューを定義します。</span><span class="sxs-lookup"><span data-stu-id="61936-144">Defines the views used to display objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="61936-145">コメント</span><span class="sxs-lookup"><span data-stu-id="61936-145">Remarks</span></span>

<span data-ttu-id="61936-146">さまざまなビューとカスタム コントロールのコンポーネントに関する詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="61936-146">For more information about the components of different views and custom controls, see the following topics:</span></span>

- [<span data-ttu-id="61936-147">テーブル ビュー コンポーネント</span><span class="sxs-lookup"><span data-stu-id="61936-147">Table View Components</span></span>](./creating-a-table-view.md)

- [<span data-ttu-id="61936-148">ビュー コンポーネントの一覧</span><span class="sxs-lookup"><span data-stu-id="61936-148">List View Components</span></span>](./creating-a-list-view.md)

- [<span data-ttu-id="61936-149">表示幅が広いコンポーネント</span><span class="sxs-lookup"><span data-stu-id="61936-149">Wide View Components</span></span>](./creating-a-wide-view.md)

- [<span data-ttu-id="61936-150">カスタム コントロール</span><span class="sxs-lookup"><span data-stu-id="61936-150">Custom Controls</span></span>](./creating-custom-controls.md)

## <a name="example"></a><span data-ttu-id="61936-151">例</span><span class="sxs-lookup"><span data-stu-id="61936-151">Example</span></span>

<span data-ttu-id="61936-152">この例では、`View`のテーブル ビューを定義する要素、 [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController)オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="61936-152">This example shows a `View` element that defines a table view for the [System.Serviceprocess.Servicecontroller](/dotnet/api/System.ServiceProcess.ServiceController) object.</span></span>

```xml
<ViewDefinitions>
  <View>
    <Name>service</Name>
    <ViewSelectedBy>
      <TypeName>System.ServiceProcess.ServiceController</TypeName>
    </ViewSelectedBy>
    <TableControl>...</TableControl>
  </View>
</ViewDefinitions>

```

## <a name="see-also"></a><span data-ttu-id="61936-153">参照</span><span class="sxs-lookup"><span data-stu-id="61936-153">See Also</span></span>

[<span data-ttu-id="61936-154">ViewDefinitions 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="61936-154">ViewDefinitions Element (Format)</span></span>](./viewdefinitions-element-format.md)

[<span data-ttu-id="61936-155">ビュー (形式) の name 要素</span><span class="sxs-lookup"><span data-stu-id="61936-155">Name Element for View (Format)</span></span>](./name-element-for-view-format.md)

[<span data-ttu-id="61936-156">ViewSelectedBy 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="61936-156">ViewSelectedBy Element (Format)</span></span>](./viewselectedby-element-format.md)

[<span data-ttu-id="61936-157">ビュー (形式) のコントロール要素</span><span class="sxs-lookup"><span data-stu-id="61936-157">Controls Element for View (Format)</span></span>](./controls-element-for-view-format.md)

[<span data-ttu-id="61936-158">ビュー (形式) の GroupBy 要素</span><span class="sxs-lookup"><span data-stu-id="61936-158">GroupBy Element for View (Format)</span></span>](./groupby-element-for-view-format.md)

[<span data-ttu-id="61936-159">TableControl 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="61936-159">TableControl Element (Format)</span></span>](./tablecontrol-element-format.md)

[<span data-ttu-id="61936-160">ListControl 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="61936-160">ListControl Element (Format)</span></span>](./listcontrol-element-format.md)

[<span data-ttu-id="61936-161">WideControl 要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="61936-161">WideControl Element (Format)</span></span>](./widecontrol-element-format.md)

[<span data-ttu-id="61936-162">カスタム コントロール要素 (形式)</span><span class="sxs-lookup"><span data-stu-id="61936-162">CustomControl Element (Format)</span></span>](./customcontrol-element-for-groupby-format.md)

[<span data-ttu-id="61936-163">PowerShell のファイルを書式設定の書き込み</span><span class="sxs-lookup"><span data-stu-id="61936-163">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)