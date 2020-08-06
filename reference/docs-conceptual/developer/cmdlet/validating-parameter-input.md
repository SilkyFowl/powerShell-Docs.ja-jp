---
title: パラメーターの入力を検証しています |Microsoft Docs
ms.date: 09/13/2016
helpviewer_keywords:
- parameters, validation rules
- validation, examples
- validation
ms.openlocfilehash: e12c715cfa24edfff958b12be1f3517b2f545256
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783995"
---
# <a name="validating-parameter-input"></a><span data-ttu-id="792ab-102">パラメーター入力を検証する</span><span class="sxs-lookup"><span data-stu-id="792ab-102">Validating Parameter Input</span></span>

<span data-ttu-id="792ab-103">PowerShell では、コマンドレットパラメーターに渡す引数をいくつかの方法で検証できます。</span><span class="sxs-lookup"><span data-stu-id="792ab-103">PowerShell can validate the arguments passed to cmdlet parameters in several ways.</span></span>
<span data-ttu-id="792ab-104">PowerShell では、引数の長さ、範囲、および文字のパターンを検証できます。</span><span class="sxs-lookup"><span data-stu-id="792ab-104">PowerShell can validate the length, the range, and the pattern of the characters of the argument.</span></span>
<span data-ttu-id="792ab-105">使用可能な引数の数 (カウント) を検証できます。</span><span class="sxs-lookup"><span data-stu-id="792ab-105">It can validate the number of arguments available (the count).</span></span>
<span data-ttu-id="792ab-106">これらの検証規則は、コマンドレットクラスのパブリックプロパティでパラメーター属性を使用して宣言された検証属性によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="792ab-106">These validation rules are defined by validation attributes that are declared with the Parameter attribute on public properties of the cmdlet class.</span></span>

<span data-ttu-id="792ab-107">パラメーター引数を検証するために、PowerShell ランタイムは検証属性によって提供される情報を使用して、コマンドレットの実行前にパラメーターの値を確認します。</span><span class="sxs-lookup"><span data-stu-id="792ab-107">To validate a parameter argument, the PowerShell runtime uses the information provided by the validation attributes to confirm the value of the parameter before the cmdlet is run.</span></span>
<span data-ttu-id="792ab-108">パラメーターの入力が有効でない場合、ユーザーはエラーメッセージを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="792ab-108">If the parameter input is not valid, the user receives an error message.</span></span>
<span data-ttu-id="792ab-109">各検証パラメーターでは、PowerShell によって適用される検証規則を定義します。</span><span class="sxs-lookup"><span data-stu-id="792ab-109">Each validation parameter defines a validation rule that is enforced by PowerShell.</span></span>

<span data-ttu-id="792ab-110">PowerShell では、次の属性に基づいて検証規則が適用されます。</span><span class="sxs-lookup"><span data-stu-id="792ab-110">PowerShell enforces the validation rules based on the following attributes.</span></span>

### <a name="validatecount"></a><span data-ttu-id="792ab-111">ValidateCount</span><span class="sxs-lookup"><span data-stu-id="792ab-111">ValidateCount</span></span>

<span data-ttu-id="792ab-112">パラメーターが受け入れることができる引数の最小数と最大数を指定します。</span><span class="sxs-lookup"><span data-stu-id="792ab-112">Specifies the minimum and maximum number of arguments that a parameter can accept.</span></span>
<span data-ttu-id="792ab-113">詳細については、「 [Validatecount 属性の宣言](./validatecount-attribute-declaration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="792ab-113">For more information, see [ValidateCount Attribute Declaration](./validatecount-attribute-declaration.md).</span></span>

### <a name="validatelength"></a><span data-ttu-id="792ab-114">ValidateLength</span><span class="sxs-lookup"><span data-stu-id="792ab-114">ValidateLength</span></span>

<span data-ttu-id="792ab-115">パラメーター引数の文字数の最小値と最大値を指定します。</span><span class="sxs-lookup"><span data-stu-id="792ab-115">Specifies the minimum and maximum number of characters in the parameter argument.</span></span>
<span data-ttu-id="792ab-116">詳細については、「 [ValidateLength Attribute 宣言](./validatelength-attribute-declaration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="792ab-116">For more information, see [ValidateLength Attribute Declaration](./validatelength-attribute-declaration.md).</span></span>

### <a name="validatepattern"></a><span data-ttu-id="792ab-117">ValidatePattern</span><span class="sxs-lookup"><span data-stu-id="792ab-117">ValidatePattern</span></span>

<span data-ttu-id="792ab-118">パラメーター引数を検証する正規表現を指定します。</span><span class="sxs-lookup"><span data-stu-id="792ab-118">Specifies a regular expression that validates the parameter argument.</span></span>
<span data-ttu-id="792ab-119">詳細については、「 [Validatepattern 属性の宣言](./validatepattern-attribute-declaration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="792ab-119">For more information, see [ValidatePattern Attribute Declaration](./validatepattern-attribute-declaration.md).</span></span>

### <a name="validaterange"></a><span data-ttu-id="792ab-120">ValidateRange</span><span class="sxs-lookup"><span data-stu-id="792ab-120">ValidateRange</span></span>

<span data-ttu-id="792ab-121">パラメーター引数の最小値と最大値を指定します。</span><span class="sxs-lookup"><span data-stu-id="792ab-121">Specifies the minimum and maximum values of the parameter argument.</span></span>
<span data-ttu-id="792ab-122">詳細については、「 [ValidateRange Attribute 宣言](./validaterange-attribute-declaration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="792ab-122">For more information, see [ValidateRange Attribute Declaration](./validaterange-attribute-declaration.md).</span></span>

### <a name="validateset"></a><span data-ttu-id="792ab-123">ValidateSet</span><span class="sxs-lookup"><span data-stu-id="792ab-123">ValidateSet</span></span>

<span data-ttu-id="792ab-124">パラメーター引数の有効な値を指定します。</span><span class="sxs-lookup"><span data-stu-id="792ab-124">Specifies the valid values for the parameter argument.</span></span>
<span data-ttu-id="792ab-125">詳細については、「 [Validateset 属性の宣言](./validateset-attribute-declaration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="792ab-125">For more information, see [ValidateSet Attribute Declaration](./validateset-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="792ab-126">参照</span><span class="sxs-lookup"><span data-stu-id="792ab-126">See Also</span></span>

[<span data-ttu-id="792ab-127">パラメーター入力を検証する方法</span><span class="sxs-lookup"><span data-stu-id="792ab-127">How to Validate Parameter Input</span></span>](./how-to-validate-parameter-input.md)

[<span data-ttu-id="792ab-128">Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)</span><span class="sxs-lookup"><span data-stu-id="792ab-128">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
