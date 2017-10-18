---
description: 
manager: carmonm
ms.topic: article
author: jpjofre
ms.prod: powershell
keywords: "PowerShell, コマンドレット"
ms.date: 2016-12-12
title: test pswaauthorizationrule
ms.technology: powershell
ms.openlocfilehash: 900547301c815ba6fe3a9507f975503fec864e4e
ms.sourcegitcommit: d6ab9ab5909ed59cce4ce30e29457e0e75c7ac12
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2017
---
# <a name="test-pswaauthorizationrule"></a><span data-ttu-id="f480c-103">Test-PswaAuthorizationRule</span><span class="sxs-lookup"><span data-stu-id="f480c-103">Test-PswaAuthorizationRule</span></span>

## <a name="synopsis"></a><span data-ttu-id="f480c-104">概要</span><span class="sxs-lookup"><span data-stu-id="f480c-104">SYNOPSIS</span></span>

<span data-ttu-id="f480c-105">指定されたユーザー、コンピューター、またはエンドポイントに規則が存在するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="f480c-105">Verifies whether a rule exists for a specified user, computer, or endpoint.</span></span>

## <a name="syntax"></a><span data-ttu-id="f480c-106">構文</span><span class="sxs-lookup"><span data-stu-id="f480c-106">SYNTAX</span></span>

### <a name="computername"></a><span data-ttu-id="f480c-107">ComputerName</span><span class="sxs-lookup"><span data-stu-id="f480c-107">ComputerName</span></span>
```
Test-PswaAuthorizationRule [-UserName] <String> [-ComputerName] <String> [[-ConfigurationName] <String> ] [-Credential <PSCredential> ] [-Rule <PswaAuthorizationRule[]> ] [ <CommonParameters>]
```

### <a name="connectionuri"></a><span data-ttu-id="f480c-108">ConnectionUri</span><span class="sxs-lookup"><span data-stu-id="f480c-108">ConnectionUri</span></span>
```
Test-PswaAuthorizationRule [-UserName] <String> [-ConnectionUri] <Uri> [[-ConfigurationName] <String> ] [-Credential <PSCredential> ] [-Rule <PswaAuthorizationRule[]> ] [ <CommonParameters>]
```

## <a name="description"></a><span data-ttu-id="f480c-109">説明</span><span class="sxs-lookup"><span data-stu-id="f480c-109">DESCRIPTION</span></span>

<span data-ttu-id="f480c-110">**Test-PswaAuthorizationRule** コマンドレットは、指定されたユーザー、コンピューター、またはエンドポイントに規則が存在するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="f480c-110">The **Test-PswaAuthorizationRule** cmdlet verifies whether a rule exists for a specified user, computer, or endpoint.</span></span>
<span data-ttu-id="f480c-111">また、特定のユーザー、コンピューター、エンドポイント アクセス要求が承認されていることを確認する承認規則のテストにもこのコマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f480c-111">This cmdlet can also be used to test authorization rules, to validate that a particular user, computer or endpoint access request is authorized.</span></span>
<span data-ttu-id="f480c-112">このコマンドレットは、既定で承認ファイルのすべての規則を評価します。</span><span class="sxs-lookup"><span data-stu-id="f480c-112">By default, this cmdlet evaluates all rules in the authorization file.</span></span>
<span data-ttu-id="f480c-113">ただし、テスト対象として一部の規則を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="f480c-113">However, you can specify a subset of rules to test.</span></span>

<span data-ttu-id="f480c-114">このコマンドレットは、認証エラーを解決するときに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f480c-114">You can use this cmdlet to help troubleshoot authentication failures.</span></span>

<span data-ttu-id="f480c-115">このコマンドレットのパラメーターは、Windows PowerShell® Web Access のサインオン ページ上のフィールドに対応しています。</span><span class="sxs-lookup"><span data-stu-id="f480c-115">The parameters for this cmdlet correspond to fields on the Windows PowerShell® Web Access sign-on page.</span></span>

## <a name="parameters"></a><span data-ttu-id="f480c-116">パラメータ</span><span class="sxs-lookup"><span data-stu-id="f480c-116">PARAMETERS</span></span>

### <a name="-computername-ltstringgt"></a><span data-ttu-id="f480c-117">-ComputerName &lt;String&gt;</span><span class="sxs-lookup"><span data-stu-id="f480c-117">-ComputerName &lt;String&gt;</span></span>

<span data-ttu-id="f480c-118">テストするコンピューターの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="f480c-118">Specifies the name of the computer to test.</span></span>

|||  
|-|-|
| <span data-ttu-id="f480c-119">エイリアス</span><span class="sxs-lookup"><span data-stu-id="f480c-119">Aliases</span></span>                              | <span data-ttu-id="f480c-120">なし</span><span class="sxs-lookup"><span data-stu-id="f480c-120">none</span></span>                                 |
| <span data-ttu-id="f480c-121">必須?</span><span class="sxs-lookup"><span data-stu-id="f480c-121">Required?</span></span>                            | <span data-ttu-id="f480c-122">true</span><span class="sxs-lookup"><span data-stu-id="f480c-122">true</span></span>                                 |
| <span data-ttu-id="f480c-123">位置は?</span><span class="sxs-lookup"><span data-stu-id="f480c-123">Position?</span></span>                            | <span data-ttu-id="f480c-124">2</span><span class="sxs-lookup"><span data-stu-id="f480c-124">2</span></span>                                    |
| <span data-ttu-id="f480c-125">既定値</span><span class="sxs-lookup"><span data-stu-id="f480c-125">Default Value</span></span>                        | <span data-ttu-id="f480c-126">なし</span><span class="sxs-lookup"><span data-stu-id="f480c-126">none</span></span>                                 |
| <span data-ttu-id="f480c-127">パイプライン入力を許可する</span><span class="sxs-lookup"><span data-stu-id="f480c-127">Accept Pipeline Input?</span></span>               | <span data-ttu-id="f480c-128">false</span><span class="sxs-lookup"><span data-stu-id="f480c-128">false</span></span>                                |
| <span data-ttu-id="f480c-129">ワイルドカード文字を許可する</span><span class="sxs-lookup"><span data-stu-id="f480c-129">Accept Wildcard Characters?</span></span>          | <span data-ttu-id="f480c-130">false</span><span class="sxs-lookup"><span data-stu-id="f480c-130">false</span></span>                                |

### <a name="-configurationname-ltstringgt"></a><span data-ttu-id="f480c-131">-ConfigurationName &lt;String&gt;</span><span class="sxs-lookup"><span data-stu-id="f480c-131">-ConfigurationName &lt;String&gt;</span></span>

<span data-ttu-id="f480c-132">テストする Windows PowerShell セッション構成 (エンドポイント、実行空間とも呼ばれます) の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="f480c-132">Specifies the name of the Windows PowerShell session configuration, also known as endpoint or runspace, to test.</span></span>

|||  
|-|-|
| <span data-ttu-id="f480c-133">エイリアス</span><span class="sxs-lookup"><span data-stu-id="f480c-133">Aliases</span></span>                              | <span data-ttu-id="f480c-134">なし</span><span class="sxs-lookup"><span data-stu-id="f480c-134">none</span></span>                                 |
| <span data-ttu-id="f480c-135">必須?</span><span class="sxs-lookup"><span data-stu-id="f480c-135">Required?</span></span>                            | <span data-ttu-id="f480c-136">false</span><span class="sxs-lookup"><span data-stu-id="f480c-136">false</span></span>                                |
| <span data-ttu-id="f480c-137">位置は?</span><span class="sxs-lookup"><span data-stu-id="f480c-137">Position?</span></span>                            | <span data-ttu-id="f480c-138">3</span><span class="sxs-lookup"><span data-stu-id="f480c-138">3</span></span>                                    |
| <span data-ttu-id="f480c-139">既定値</span><span class="sxs-lookup"><span data-stu-id="f480c-139">Default Value</span></span>                        | <span data-ttu-id="f480c-140">なし</span><span class="sxs-lookup"><span data-stu-id="f480c-140">none</span></span>                                 |
| <span data-ttu-id="f480c-141">パイプライン入力を許可する</span><span class="sxs-lookup"><span data-stu-id="f480c-141">Accept Pipeline Input?</span></span>               | <span data-ttu-id="f480c-142">false</span><span class="sxs-lookup"><span data-stu-id="f480c-142">false</span></span>                                |
| <span data-ttu-id="f480c-143">ワイルドカード文字を許可する</span><span class="sxs-lookup"><span data-stu-id="f480c-143">Accept Wildcard Characters?</span></span>          | <span data-ttu-id="f480c-144">false</span><span class="sxs-lookup"><span data-stu-id="f480c-144">false</span></span>                                |

### <a name="-connectionuri-lturigt"></a><span data-ttu-id="f480c-145">-ConnectionUri &lt;Uri&gt;</span><span class="sxs-lookup"><span data-stu-id="f480c-145">-ConnectionUri &lt;Uri&gt;</span></span>

<span data-ttu-id="f480c-146">テストする接続 URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="f480c-146">Specifies the connection URI to test.</span></span>

|||  
|-|-|
| <span data-ttu-id="f480c-147">エイリアス</span><span class="sxs-lookup"><span data-stu-id="f480c-147">Aliases</span></span>                              | <span data-ttu-id="f480c-148">なし</span><span class="sxs-lookup"><span data-stu-id="f480c-148">none</span></span>                                 |
| <span data-ttu-id="f480c-149">必須?</span><span class="sxs-lookup"><span data-stu-id="f480c-149">Required?</span></span>                            | <span data-ttu-id="f480c-150">true</span><span class="sxs-lookup"><span data-stu-id="f480c-150">true</span></span>                                 |
| <span data-ttu-id="f480c-151">位置は?</span><span class="sxs-lookup"><span data-stu-id="f480c-151">Position?</span></span>                            | <span data-ttu-id="f480c-152">2</span><span class="sxs-lookup"><span data-stu-id="f480c-152">2</span></span>                                    |
| <span data-ttu-id="f480c-153">既定値</span><span class="sxs-lookup"><span data-stu-id="f480c-153">Default Value</span></span>                        | <span data-ttu-id="f480c-154">なし</span><span class="sxs-lookup"><span data-stu-id="f480c-154">none</span></span>                                 |
| <span data-ttu-id="f480c-155">パイプライン入力を許可する</span><span class="sxs-lookup"><span data-stu-id="f480c-155">Accept Pipeline Input?</span></span>               | <span data-ttu-id="f480c-156">false</span><span class="sxs-lookup"><span data-stu-id="f480c-156">false</span></span>                                |
| <span data-ttu-id="f480c-157">ワイルドカード文字を許可する</span><span class="sxs-lookup"><span data-stu-id="f480c-157">Accept Wildcard Characters?</span></span>          | <span data-ttu-id="f480c-158">false</span><span class="sxs-lookup"><span data-stu-id="f480c-158">false</span></span>                                |

### <a name="-credential-ltpscredentialgt"></a><span data-ttu-id="f480c-159">-Credential &lt;PSCredential&gt;</span><span class="sxs-lookup"><span data-stu-id="f480c-159">-Credential &lt;PSCredential&gt;</span></span>

<span data-ttu-id="f480c-160">Windows PowerShell Web Access 承認規則のテストに使用するユーザー アカウントの **PSCredential** オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="f480c-160">Specifies a **PSCredential** object for a user account that you want to use to test Windows PowerShell Web Access authorization rules.</span></span> <span data-ttu-id="f480c-161">このパラメーターを追加しない場合、現在ログオンしているユーザー アカウントがコマンドレットにより使用されます。</span><span class="sxs-lookup"><span data-stu-id="f480c-161">If you do not add this parameter, the cmdlet uses the currently logged-on user account.</span></span> <span data-ttu-id="f480c-162">承認規則をリモートからテストするために必要な **PSCredential** オブジェクトを取得するには、[Get-Credential](http://go.microsoft.com/fwlink/?LinkID=293936) コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="f480c-162">To get a **PSCredential** object, which is required to test authorization rules remotely, run the [Get-Credential](http://go.microsoft.com/fwlink/?LinkID=293936) cmdlet.</span></span>

|||  
|-|-|
| <span data-ttu-id="f480c-163">エイリアス</span><span class="sxs-lookup"><span data-stu-id="f480c-163">Aliases</span></span>                              | <span data-ttu-id="f480c-164">なし</span><span class="sxs-lookup"><span data-stu-id="f480c-164">none</span></span>                                 |
| <span data-ttu-id="f480c-165">必須?</span><span class="sxs-lookup"><span data-stu-id="f480c-165">Required?</span></span>                            | <span data-ttu-id="f480c-166">false</span><span class="sxs-lookup"><span data-stu-id="f480c-166">false</span></span>                                |
| <span data-ttu-id="f480c-167">位置は?</span><span class="sxs-lookup"><span data-stu-id="f480c-167">Position?</span></span>                            | <span data-ttu-id="f480c-168">名前付き</span><span class="sxs-lookup"><span data-stu-id="f480c-168">named</span></span>                                |
| <span data-ttu-id="f480c-169">既定値</span><span class="sxs-lookup"><span data-stu-id="f480c-169">Default Value</span></span>                        | <span data-ttu-id="f480c-170">なし</span><span class="sxs-lookup"><span data-stu-id="f480c-170">none</span></span>                                 |
| <span data-ttu-id="f480c-171">パイプライン入力を許可する</span><span class="sxs-lookup"><span data-stu-id="f480c-171">Accept Pipeline Input?</span></span>               | <span data-ttu-id="f480c-172">false</span><span class="sxs-lookup"><span data-stu-id="f480c-172">false</span></span>                                |
| <span data-ttu-id="f480c-173">ワイルドカード文字を許可する</span><span class="sxs-lookup"><span data-stu-id="f480c-173">Accept Wildcard Characters?</span></span>          | <span data-ttu-id="f480c-174">false</span><span class="sxs-lookup"><span data-stu-id="f480c-174">false</span></span>                                |

### <a name="-rule-ltpswaauthorizationrulegt"></a><span data-ttu-id="f480c-175">-Rule &lt;PswaAuthorizationRule\[\]&gt;</span><span class="sxs-lookup"><span data-stu-id="f480c-175">-Rule &lt;PswaAuthorizationRule\[\]&gt;</span></span>

<span data-ttu-id="f480c-176">テストする規則のサブセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="f480c-176">Specifies a subset of rules to test.</span></span> <span data-ttu-id="f480c-177">このパラメーターを指定しない場合、すべての承認規則に対してテストが実行されます。</span><span class="sxs-lookup"><span data-stu-id="f480c-177">If this parameter is not specified, then this cmdlet tests against all authorization rules.</span></span>

|||  
|-|-|
| <span data-ttu-id="f480c-178">エイリアス</span><span class="sxs-lookup"><span data-stu-id="f480c-178">Aliases</span></span>                              | <span data-ttu-id="f480c-179">なし</span><span class="sxs-lookup"><span data-stu-id="f480c-179">none</span></span>                                 |
| <span data-ttu-id="f480c-180">必須?</span><span class="sxs-lookup"><span data-stu-id="f480c-180">Required?</span></span>                            | <span data-ttu-id="f480c-181">false</span><span class="sxs-lookup"><span data-stu-id="f480c-181">false</span></span>                                |
| <span data-ttu-id="f480c-182">位置は?</span><span class="sxs-lookup"><span data-stu-id="f480c-182">Position?</span></span>                            | <span data-ttu-id="f480c-183">名前付き</span><span class="sxs-lookup"><span data-stu-id="f480c-183">named</span></span>                                |
| <span data-ttu-id="f480c-184">既定値</span><span class="sxs-lookup"><span data-stu-id="f480c-184">Default Value</span></span>                        | <span data-ttu-id="f480c-185">なし</span><span class="sxs-lookup"><span data-stu-id="f480c-185">none</span></span>                                 |
| <span data-ttu-id="f480c-186">パイプライン入力を許可する</span><span class="sxs-lookup"><span data-stu-id="f480c-186">Accept Pipeline Input?</span></span>               | <span data-ttu-id="f480c-187">True (ByValue)</span><span class="sxs-lookup"><span data-stu-id="f480c-187">True (ByValue)</span></span>                       |
| <span data-ttu-id="f480c-188">ワイルドカード文字を許可する</span><span class="sxs-lookup"><span data-stu-id="f480c-188">Accept Wildcard Characters?</span></span>          | <span data-ttu-id="f480c-189">false</span><span class="sxs-lookup"><span data-stu-id="f480c-189">false</span></span>                                |

### <a name="-username-ltstringgt"></a><span data-ttu-id="f480c-190">-UserName &lt;String&gt;</span><span class="sxs-lookup"><span data-stu-id="f480c-190">-UserName &lt;String&gt;</span></span>

<span data-ttu-id="f480c-191">テストするユーザーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="f480c-191">Specifies the name of the user to test.</span></span>

|||  
|-|-|
| <span data-ttu-id="f480c-192">エイリアス</span><span class="sxs-lookup"><span data-stu-id="f480c-192">Aliases</span></span>                              | <span data-ttu-id="f480c-193">なし</span><span class="sxs-lookup"><span data-stu-id="f480c-193">none</span></span>                                 |
| <span data-ttu-id="f480c-194">必須?</span><span class="sxs-lookup"><span data-stu-id="f480c-194">Required?</span></span>                            | <span data-ttu-id="f480c-195">true</span><span class="sxs-lookup"><span data-stu-id="f480c-195">true</span></span>                                 |
| <span data-ttu-id="f480c-196">位置は?</span><span class="sxs-lookup"><span data-stu-id="f480c-196">Position?</span></span>                            | <span data-ttu-id="f480c-197">1 で保護されたプロセスとして起動されました</span><span class="sxs-lookup"><span data-stu-id="f480c-197">1</span></span>                                    |
| <span data-ttu-id="f480c-198">既定値</span><span class="sxs-lookup"><span data-stu-id="f480c-198">Default Value</span></span>                        | <span data-ttu-id="f480c-199">なし</span><span class="sxs-lookup"><span data-stu-id="f480c-199">none</span></span>                                 |
| <span data-ttu-id="f480c-200">パイプライン入力を許可する</span><span class="sxs-lookup"><span data-stu-id="f480c-200">Accept Pipeline Input?</span></span>               | <span data-ttu-id="f480c-201">false</span><span class="sxs-lookup"><span data-stu-id="f480c-201">false</span></span>                                |
| <span data-ttu-id="f480c-202">ワイルドカード文字を許可する</span><span class="sxs-lookup"><span data-stu-id="f480c-202">Accept Wildcard Characters?</span></span>          | <span data-ttu-id="f480c-203">false</span><span class="sxs-lookup"><span data-stu-id="f480c-203">false</span></span>                                |

### <a name="ltcommonparametersgt"></a><span data-ttu-id="f480c-204">&lt;CommonParameters&gt;</span><span class="sxs-lookup"><span data-stu-id="f480c-204">&lt;CommonParameters&gt;</span></span>

<span data-ttu-id="f480c-205">このコマンドレットは、-Verbose、-Debug、-ErrorAction、-ErrorVariable、-OutBuffer、および -OutVariable という共通パラメーターをサポートします。</span><span class="sxs-lookup"><span data-stu-id="f480c-205">This cmdlet supports the common parameters: -Verbose, -Debug, -ErrorAction, -ErrorVariable, -OutBuffer, and -OutVariable.</span></span>
<span data-ttu-id="f480c-206">詳細については、「[about_CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f480c-206">For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216).</span></span>

## <a name="inputs"></a><span data-ttu-id="f480c-207">入力</span><span class="sxs-lookup"><span data-stu-id="f480c-207">INPUTS</span></span>

### <a name="microsoftmanagementpowershellwebaccesspswaauthorizationrule"></a><span data-ttu-id="f480c-208">Microsoft.Management.PowerShellWebAccess.PswaAuthorizationRule\[\]</span><span class="sxs-lookup"><span data-stu-id="f480c-208">Microsoft.Management.PowerShellWebAccess.PswaAuthorizationRule\[\]</span></span>

<span data-ttu-id="f480c-209">このコマンドレットは、入力として PswaAuthorizationRule オブジェクトの配列を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="f480c-209">This cmdlet accepts an array of PswaAuthorizationRule objects as input.</span></span>

## <a name="outputs"></a><span data-ttu-id="f480c-210">出力</span><span class="sxs-lookup"><span data-stu-id="f480c-210">OUTPUTS</span></span>

### <a name="microsoftmanagementpowershellwebaccesspswaauthorizationrule"></a><span data-ttu-id="f480c-211">Microsoft.Management.PowerShellWebAccess.PswaAuthorizationRule\[\]</span><span class="sxs-lookup"><span data-stu-id="f480c-211">Microsoft.Management.PowerShellWebAccess.PswaAuthorizationRule\[\]</span></span>

<span data-ttu-id="f480c-212">このコマンドレットは、出力として PswaAuthorizationRule オブジェクトの配列を生成します。</span><span class="sxs-lookup"><span data-stu-id="f480c-212">This cmdlet produces an array of PswaAuthorizationRule objects as output.</span></span>

## <a name="examples"></a><span data-ttu-id="f480c-213">例</span><span class="sxs-lookup"><span data-stu-id="f480c-213">EXAMPLES</span></span>

### <a name="example-1"></a><span data-ttu-id="f480c-214">例 1</span><span class="sxs-lookup"><span data-stu-id="f480c-214">EXAMPLE 1</span></span>

<span data-ttu-id="f480c-215">この例では、ユーザー *contoso\\mhanson* に対して、コンピューター *srv2* への接続と、*test* という Windows PowerShell セッション構成の使用を許可するために、すべての承認規則をテストします。</span><span class="sxs-lookup"><span data-stu-id="f480c-215">This example tests all authorization rules in order to display all the rules that allow the user *contoso\\mhanson* to connect to the computer *srv2* and use a Windows PowerShell session configuration named *test*.</span></span>

```
Test-PswaAuthorizationRule -ComputerName srv2.contoso.com -UserName contoso\mhanson -ConfigurationName test
```

### <a name="example-2"></a><span data-ttu-id="f480c-216">例 2</span><span class="sxs-lookup"><span data-stu-id="f480c-216">EXAMPLE 2</span></span>

<span data-ttu-id="f480c-217">この例では、ユーザー *contoso\\mhanson* に適用される承認規則を確認するために、すべての承認規則をテストします。</span><span class="sxs-lookup"><span data-stu-id="f480c-217">This example tests all authorization rules to check which authorization rules apply to the user *contoso\\mhanson*.</span></span>

```
Test-PswaAuthorizationRule -UserName contoso\mhanson -ComputerName *
```

## <a name="related-topics"></a><span data-ttu-id="f480c-218">関連トピック</span><span class="sxs-lookup"><span data-stu-id="f480c-218">Related topics</span></span>

- [<span data-ttu-id="f480c-219">Add-PswaAuthorizationRule</span><span class="sxs-lookup"><span data-stu-id="f480c-219">Add-PswaAuthorizationRule</span></span>](add-pswaauthorizationrule.md)
- [<span data-ttu-id="f480c-220">Get-PswaAuthorizationRule</span><span class="sxs-lookup"><span data-stu-id="f480c-220">Get-PswaAuthorizationRule</span></span>](get-pswaauthorizationrule.md)
- [<span data-ttu-id="f480c-221">Install-PswaWebApplication</span><span class="sxs-lookup"><span data-stu-id="f480c-221">Install-PswaWebApplication</span></span>](install-pswawebapplication.md)
- [<span data-ttu-id="f480c-222">Remove-PswaAuthorizationRule</span><span class="sxs-lookup"><span data-stu-id="f480c-222">Remove-PswaAuthorizationRule</span></span>](remove-pswaauthorizationrule.md)