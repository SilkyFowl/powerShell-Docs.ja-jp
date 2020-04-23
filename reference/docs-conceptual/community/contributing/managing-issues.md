---
title: イシューを管理する方法
description: この記事では、PowerShell-Docs チームがプル要求を管理する方法について説明します。
ms.date: 03/05/2020
ms.topic: conceptual
ms.openlocfilehash: cd7aba83d42a6a2eba1ce73910fdd34096342c21
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "79060277"
---
# <a name="how-we-manage-issues"></a><span data-ttu-id="53256-103">イシューを管理する方法</span><span class="sxs-lookup"><span data-stu-id="53256-103">How we manage issues</span></span>

<span data-ttu-id="53256-104">この記事では、PowerShell-Docs リポジトリでイシューを管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="53256-104">This article documents how we manage issues in the PowerShell-Docs repo.</span></span> <span data-ttu-id="53256-105">この記事は、PowerShell-Docs チームのメンバーの作業を支援することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="53256-105">This article is designed to be a job aid for members of the PowerShell-Docs team.</span></span> <span data-ttu-id="53256-106">一般の共同作成者に対してプロセスを透明化するために、ここで公開されています。</span><span class="sxs-lookup"><span data-stu-id="53256-106">It is published here to provide process transparency for our public contributors.</span></span>

## <a name="sources-of-issues"></a><span data-ttu-id="53256-107">イシューのソース</span><span class="sxs-lookup"><span data-stu-id="53256-107">Sources of issues</span></span>

- <span data-ttu-id="53256-108">コミュニティの共同作成者</span><span class="sxs-lookup"><span data-stu-id="53256-108">Community contributors</span></span>
- <span data-ttu-id="53256-109">内部の共同作成者</span><span class="sxs-lookup"><span data-stu-id="53256-109">Internal contributors</span></span>
- <span data-ttu-id="53256-110">ソーシャル メディア チャネルからのコメントの転記</span><span class="sxs-lookup"><span data-stu-id="53256-110">Transcriptions of comments from social media channels</span></span>
- <span data-ttu-id="53256-111">ドキュメント フィードバック フォームによるフィードバック</span><span class="sxs-lookup"><span data-stu-id="53256-111">Feedback via the Docs feedback form</span></span>

## <a name="response-time-targets"></a><span data-ttu-id="53256-112">目標対応時間</span><span class="sxs-lookup"><span data-stu-id="53256-112">Response time targets</span></span>

- <span data-ttu-id="53256-113">トリアージ - 5 営業日</span><span class="sxs-lookup"><span data-stu-id="53256-113">Triaged - 5 business days</span></span>
- <span data-ttu-id="53256-114">修正または変更 - 具体的な目標なし - ベスト エフォートのみ</span><span class="sxs-lookup"><span data-stu-id="53256-114">Fix or change - no specific target - best effort only</span></span>

### <a name="labeling--milestones"></a><span data-ttu-id="53256-115">ラベル付けとマイルストーン</span><span class="sxs-lookup"><span data-stu-id="53256-115">Labeling & Milestones</span></span>

#### <a name="label-types"></a><span data-ttu-id="53256-116">ラベルの種類</span><span class="sxs-lookup"><span data-stu-id="53256-116">Label Types</span></span>

|<span data-ttu-id="53256-117">Prefix</span><span class="sxs-lookup"><span data-stu-id="53256-117">Prefix</span></span>  | <span data-ttu-id="53256-118">説明</span><span class="sxs-lookup"><span data-stu-id="53256-118">Description</span></span>                                                         |
|------- | --------------------------------------------------------------------|
|<span data-ttu-id="53256-119">領域</span><span class="sxs-lookup"><span data-stu-id="53256-119">Area</span></span>    | <span data-ttu-id="53256-120">イシューを議論する、PowerShell またはドキュメントの部分を示すために使用します。</span><span class="sxs-lookup"><span data-stu-id="53256-120">Used to indicate what part of PowerShell or the docs that the issue is discussing.</span></span><br><span data-ttu-id="53256-121">機能の所有者が機能に関するイシューを見つけるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="53256-121">Useful for feature owners to find issues for their feature.</span></span>|
|<span data-ttu-id="53256-122">Pri</span><span class="sxs-lookup"><span data-stu-id="53256-122">Pri</span></span>     | <span data-ttu-id="53256-123">イシューの優先度を示すために使用します。</span><span class="sxs-lookup"><span data-stu-id="53256-123">Used to indicate the priority of the issue.</span></span> <span data-ttu-id="53256-124">値の範囲は 0 から 4 です。</span><span class="sxs-lookup"><span data-stu-id="53256-124">Value range 0-4.</span></span>        |
|<span data-ttu-id="53256-125">問題</span><span class="sxs-lookup"><span data-stu-id="53256-125">Issue</span></span>   | <span data-ttu-id="53256-126">イシューのフィードバックの種類を分類するために使用します。</span><span class="sxs-lookup"><span data-stu-id="53256-126">Used to classify the type of feedback for issue</span></span>                     |
|<span data-ttu-id="53256-127">確認</span><span class="sxs-lookup"><span data-stu-id="53256-127">Review</span></span>  | <span data-ttu-id="53256-128">チームがさらにレビューする必要があるイシューに使用します。</span><span class="sxs-lookup"><span data-stu-id="53256-128">Used for issue that require further review by the team</span></span>              |
|<span data-ttu-id="53256-129">Status</span><span class="sxs-lookup"><span data-stu-id="53256-129">Status</span></span>  | <span data-ttu-id="53256-130">作業項目の状態を示すために使用します。</span><span class="sxs-lookup"><span data-stu-id="53256-130">Used to indicate the status of the work item</span></span>                        |
|<span data-ttu-id="53256-131">待機中</span><span class="sxs-lookup"><span data-stu-id="53256-131">Waiting</span></span> | <span data-ttu-id="53256-132">チームが何かを待機していることを示すために使用します。</span><span class="sxs-lookup"><span data-stu-id="53256-132">Used to indicate that we are waiting on something</span></span>                   |

#### <a name="milestones"></a><span data-ttu-id="53256-133">Milestones</span><span class="sxs-lookup"><span data-stu-id="53256-133">Milestones</span></span>

<span data-ttu-id="53256-134">イシューと PR は、適切なマイルストーンでタグ付けする必要があります。</span><span class="sxs-lookup"><span data-stu-id="53256-134">Issues and PRs should be tagged with the appropriate milestone.</span></span> <span data-ttu-id="53256-135">イシューが特定のバージョンを対象としていない場合、マイルストーンは使用されません。</span><span class="sxs-lookup"><span data-stu-id="53256-135">If the issue is not targeted for a specific version then no milestone is used.</span></span> <span data-ttu-id="53256-136">PowerShell コード ベースにまだマージされていない変更に関するドキュメント PR のイシューは、**Future** マイルストーンに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="53256-136">Issues for Docs PRs for changes that have yet to be merged into the PowerShell code base should be assigned to the **Future** milestone.</span></span> <span data-ttu-id="53256-137">コードの変更がマージされたら、マイルストーンを適切なバージョンに変更します。</span><span class="sxs-lookup"><span data-stu-id="53256-137">After the code change has been merged, change the milestone to the appropriate version.</span></span>

|    <span data-ttu-id="53256-138">マイルストーン</span><span class="sxs-lookup"><span data-stu-id="53256-138">Milestone</span></span>     |                    <span data-ttu-id="53256-139">説明</span><span class="sxs-lookup"><span data-stu-id="53256-139">Description</span></span>                     |
| ---------------- | -------------------------------------------------- |
| <span data-ttu-id="53256-140">6.x</span><span class="sxs-lookup"><span data-stu-id="53256-140">6.x</span></span>              | <span data-ttu-id="53256-141">PowerShell 6.0 から 6.2.x に関連する作業項目</span><span class="sxs-lookup"><span data-stu-id="53256-141">Work items related to PowerShell 6.0 through 6.2.x</span></span> |
| <span data-ttu-id="53256-142">7.0.0</span><span class="sxs-lookup"><span data-stu-id="53256-142">7.0.0</span></span>            | <span data-ttu-id="53256-143">PowerShell 7.0 に関連する作業項目</span><span class="sxs-lookup"><span data-stu-id="53256-143">Work items related to PowerShell 7.0</span></span>               |
| <span data-ttu-id="53256-144">7.1.0</span><span class="sxs-lookup"><span data-stu-id="53256-144">7.1.0</span></span>            | <span data-ttu-id="53256-145">PowerShell 7.1 に関連する作業項目</span><span class="sxs-lookup"><span data-stu-id="53256-145">Work items related to PowerShell 7.1</span></span>               |
| <span data-ttu-id="53256-146">予定</span><span class="sxs-lookup"><span data-stu-id="53256-146">Future</span></span>           | <span data-ttu-id="53256-147">将来のバージョンの PowerShell の作業項目</span><span class="sxs-lookup"><span data-stu-id="53256-147">Work items a future version of PowerShell</span></span>          |
| <span data-ttu-id="53256-148">PSReadline-vNext</span><span class="sxs-lookup"><span data-stu-id="53256-148">PSReadline-vNext</span></span> | <span data-ttu-id="53256-149">将来のバージョンの PSReadline の作業項目</span><span class="sxs-lookup"><span data-stu-id="53256-149">Work items a future version of PSReadline</span></span>          |

## <a name="triage-process"></a><span data-ttu-id="53256-150">トリアージ プロセス</span><span class="sxs-lookup"><span data-stu-id="53256-150">Triage process</span></span>

<span data-ttu-id="53256-151">PowerShell ドキュメント チームは、週に 1 回集まって、前回の会議以降に追加されたイシューについて話し合います。</span><span class="sxs-lookup"><span data-stu-id="53256-151">The PowerShell docs team meets once per week to discuss any issues added since last meeting.</span></span> <span data-ttu-id="53256-152">ラベルが割り当てられたとき、または所有者が割り当てられたときに、イシューはトリアージされたと見なされます。</span><span class="sxs-lookup"><span data-stu-id="53256-152">An issue is considered to have been triaged when labels have been assigned or an owner has been assigned.</span></span> <span data-ttu-id="53256-153">PowerShell ドキュメント チームのメンバーには、イシューを毎日レビューし、新たに報告されたイシューをトリアージすることが推奨されます。</span><span class="sxs-lookup"><span data-stu-id="53256-153">PowerShell docs team members are encouraged to review the issues daily and triage new issues as they arrive.</span></span> <span data-ttu-id="53256-154">必要に応じて、週 1 回のトリアージ会議を利用して、新しいイシューについてさらに詳しく話し合うこともできます。</span><span class="sxs-lookup"><span data-stu-id="53256-154">The weekly triage meeting can then be used to discuss the new issues in more detail, as needed.</span></span>

### <a name="misplaced-product-feedback"></a><span data-ttu-id="53256-155">間違って送られた製品フィードバック</span><span class="sxs-lookup"><span data-stu-id="53256-155">Misplaced product feedback</span></span>

- <span data-ttu-id="53256-156">その顧客に対して、製品フィードバックであることを示すコメントを入力し、適切なフィードバック チャネルへのリンクを提供します。</span><span class="sxs-lookup"><span data-stu-id="53256-156">Enter a comment for the customer indicating it is product feedback and provide a link to the appropriate feedback channel.</span></span>
- <span data-ttu-id="53256-157">省略可能:イシューを適切な製品フィードバックの場所にコピーし、コピーした項目へのリンクを追加して、イシューを閉じます。</span><span class="sxs-lookup"><span data-stu-id="53256-157">Optional: Copy the issue to the appropriate product feedback location, add a link to the copied item, and close the issue.</span></span> <span data-ttu-id="53256-158">イシューを UserVoice にコピーしないでください。</span><span class="sxs-lookup"><span data-stu-id="53256-158">DO NOT copy issues to UserVoice.</span></span>

  | <span data-ttu-id="53256-159">ドキュメント セット</span><span class="sxs-lookup"><span data-stu-id="53256-159">DocSet</span></span>    | <span data-ttu-id="53256-160">製品フィードバックの URL</span><span class="sxs-lookup"><span data-stu-id="53256-160">Product Feedback URL</span></span>                                         |
  | --------- | ------------------------------------------------------------ |
  | <span data-ttu-id="53256-161">developer</span><span class="sxs-lookup"><span data-stu-id="53256-161">developer</span></span> | https://github.com/PowerShell/PowerShell/issues/new/choose   |
  | <span data-ttu-id="53256-162">dsc</span><span class="sxs-lookup"><span data-stu-id="53256-162">dsc</span></span>       | https://windowsserver.uservoice.com/forums/301869-powershell |
  | <span data-ttu-id="53256-163">ギャラリー</span><span class="sxs-lookup"><span data-stu-id="53256-163">gallery</span></span>   | https://github.com/powershell/powershellgallery/issues/new   |
  | <span data-ttu-id="53256-164">jea</span><span class="sxs-lookup"><span data-stu-id="53256-164">jea</span></span>       | https://github.com/powershell/jea/issues/new                 |
  | <span data-ttu-id="53256-165">reference</span><span class="sxs-lookup"><span data-stu-id="53256-165">reference</span></span> | https://github.com/PowerShell/PowerShell/issues/new/choose   |
  | <span data-ttu-id="53256-166">wmf</span><span class="sxs-lookup"><span data-stu-id="53256-166">wmf</span></span>       | https://windowsserver.uservoice.com/forums/301869-powershell |

### <a name="support-requests"></a><span data-ttu-id="53256-167">サポート要求</span><span class="sxs-lookup"><span data-stu-id="53256-167">Support requests</span></span>

- <span data-ttu-id="53256-168">サポートに関する質問が単純な場合は、質問に丁寧に答えてイシューを閉じます。</span><span class="sxs-lookup"><span data-stu-id="53256-168">If the support question is simple, answer it politely and close the issue.</span></span>
- <span data-ttu-id="53256-169">質問が複雑な場合や、送信者からさらに多くの質問が返ってきた場合は、フォーラムおよびサポート チャネルにリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="53256-169">If the question is more complicated, or the submitter replies with more questions, redirect them to forums and support channels.</span></span> <span data-ttu-id="53256-170">フォーラムにリダイレクトする際の推奨されるテキストは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="53256-170">Suggested text for redirecting to forums:</span></span>

    > <span data-ttu-id="53256-171">これは、この種の質問に適したフォーラムではありません。</span><span class="sxs-lookup"><span data-stu-id="53256-171">This is not the right forum for these kinds of questions.</span></span> <span data-ttu-id="53256-172">コミュニティ サポート フォーラムで質問を投稿してください。</span><span class="sxs-lookup"><span data-stu-id="53256-172">Try posting your question in a community support forum.</span></span> <span data-ttu-id="53256-173">コミュニティ フォーラムの一覧については、 https://docs.microsoft.com/powershell/scripting/community/community-support をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="53256-173">For a list of community forums see: https://docs.microsoft.com/powershell/scripting/community/community-support</span></span>

### <a name="code-of-conduct-violations"></a><span data-ttu-id="53256-174">行動規範違反</span><span class="sxs-lookup"><span data-stu-id="53256-174">Code of conduct violations</span></span>

- <span data-ttu-id="53256-175">必要に応じて、イシューを編集し、不快感を与えるコンテンツを削除します。</span><span class="sxs-lookup"><span data-stu-id="53256-175">Edit the issue to remove any offensive content, if necessary.</span></span>
- <span data-ttu-id="53256-176">そのイシューがスパムであることを示すコメントを入力し、イシューを閉じ、それ以上コメントできないようにロックします。</span><span class="sxs-lookup"><span data-stu-id="53256-176">Enter a comment indicating the issue is spam, close the issue, and then lock it to prevent further comments.</span></span>
- <span data-ttu-id="53256-177">これが発生するたびに、毎週のトリアージで話し合って、さらなる措置 (GitHub または Microsoft 法務部への報告) の必要性を判断する必要があります。</span><span class="sxs-lookup"><span data-stu-id="53256-177">Each occurrence of this should be discussed in the weekly triage to determine the need for further action (report to GitHub or Microsoft Legal).</span></span>