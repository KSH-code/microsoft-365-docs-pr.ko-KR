---
title: Outlook에서 메일 그룹을 Microsoft 365 그룹으로 업그레이드
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 787d7a75-e201-46f3-a242-f698162ff09f
description: 하나 또는 여러 메일 그룹을 Outlook의 Microsoft 365 그룹으로 업그레이드하는 방법과 PowerShell을 사용하여 여러 메일 그룹을 동시에 업그레이드하는 방법을 배워야 합니다.
ms.openlocfilehash: ab7c2ff68b1f16915d65fff0d7292e3b3ad72d02
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579245"
---
# <a name="upgrade-distribution-lists-to-microsoft-365-groups-in-outlook"></a><span data-ttu-id="84cf6-103">Outlook에서 메일 그룹을 Microsoft 365 그룹으로 업그레이드</span><span class="sxs-lookup"><span data-stu-id="84cf6-103">Upgrade distribution lists to Microsoft 365 Groups in Outlook</span></span>

<span data-ttu-id="84cf6-104">Outlook을 사용하여 메일 그룹을 Microsoft 365 그룹으로 업그레이드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84cf6-104">You can upgrade distribution lists to Microsoft 365 Groups with Outlook.</span></span> <span data-ttu-id="84cf6-105">이는 조직의 메일 그룹에 Microsoft 365 그룹의 모든 기능을 제공하는 좋은 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="84cf6-105">This is a great way to give your organization's distribution lists all the features and functionality of Microsoft 365 Groups.</span></span> [<span data-ttu-id="84cf6-106">Outlook에서 배포 목록을 그룹으로 업그레이드해야 하는 이유</span><span class="sxs-lookup"><span data-stu-id="84cf6-106">Why you should upgrade your distribution lists to groups in Outlook</span></span>](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188)

<span data-ttu-id="84cf6-107">DLS를 한 번씩 업그레이드하거나 동시에 여러 DLS를 업그레이드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84cf6-107">You can upgrade DLs one at a time, or several at the same time.</span></span>

## <a name="upgrade-one-or-many-distribution-lists-to-microsoft-365-groups-in-outlook"></a><span data-ttu-id="84cf6-108">Outlook에서 메일 그룹 하나 또는 여러 개를 Microsoft 365 그룹으로 업그레이드</span><span class="sxs-lookup"><span data-stu-id="84cf6-108">Upgrade one or many distribution lists to Microsoft 365 Groups in Outlook</span></span>

<span data-ttu-id="84cf6-109">메일 그룹 업그레이드를 위해 전역 관리자 또는 Exchange 관리자 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84cf6-109">You must be a global admin or Exchange admin to upgrade a distribution list.</span></span> <span data-ttu-id="84cf6-110">Microsoft 365 그룹으로 업그레이드하려면 메일 그룹에 사서함이 있는 소유자가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84cf6-110">To upgrade to Microsoft 365 Groups, a distribution group must have an owner with a mailbox.</span></span>

1. <span data-ttu-id="84cf6-111"><a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 관리 센터</a>로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="84cf6-111">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>

2. <span data-ttu-id="84cf6-112">Exchange 관리 센터에서 받는 사람 **그룹 으로** \> **이동 합니다.**</span><span class="sxs-lookup"><span data-stu-id="84cf6-112">In the Exchange admin center, go to **Recipients** \> **Groups**.</span></span><br/><span data-ttu-id="84cf6-113">Microsoft 365 그룹으로 업그레이드할 수 있는  메일 그룹(메일 그룹이라고도 하는 메일 그룹)이 있는 경우를 나타내는 알림이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="84cf6-113">You'll see a notice indicating you have distribution lists (also called **distribution groups** ) that are eligible to be upgraded to Microsoft 365 Groups.</span></span><br/> <span data-ttu-id="84cf6-114">![시작 단추 선택](../../media/8cf838b4-2644-401f-a366-08c1eea183eb.png)</span><span class="sxs-lookup"><span data-stu-id="84cf6-114">![Select the Get started button](../../media/8cf838b4-2644-401f-a366-08c1eea183eb.png)</span></span>

3. <span data-ttu-id="84cf6-115">그룹 페이지에서 하나 이상의 메일 그룹(메일 그룹이라고도  합니다.)을 선택합니다. </span><span class="sxs-lookup"><span data-stu-id="84cf6-115">Select one or more distribution lists (also called a **distribution group** ) from the **groups** page.</span></span><br/><span data-ttu-id="84cf6-116">![메일 그룹 선택](../../media/2c303433-d60b-4100-a6ae-5809b03a8cdb.png)</span><span class="sxs-lookup"><span data-stu-id="84cf6-116">![Select a distribution group](../../media/2c303433-d60b-4100-a6ae-5809b03a8cdb.png)</span></span>

4. <span data-ttu-id="84cf6-117">업그레이드 아이콘을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="84cf6-117">Select the upgrade icon.</span></span><br/>![Microsoft 365 그룹으로 업그레이드 아이콘](../../media/1e28cb3d-bff3-4be3-8329-1902d2d54720.png)

5. <span data-ttu-id="84cf6-119">정보 대화 상자에서 **예를** 선택하여 업그레이드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="84cf6-119">On the information dialog, select **Yes** to confirm the upgrade.</span></span> <span data-ttu-id="84cf6-120">프로세스가 즉시 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="84cf6-120">The process begins immediately.</span></span> <span data-ttu-id="84cf6-121">업그레이드하는 DLS의 크기와 수에 따라 프로세스에 몇 분 또는 몇 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84cf6-121">Depending on the size and number of DLs you're upgrading, the process can take minutes or hours.</span></span><br/><span data-ttu-id="84cf6-122">메일 목록을 업그레이드할 수 없는 경우 해당 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="84cf6-122">If the distribution list can't be upgraded, a dialog appears saying so.</span></span> <span data-ttu-id="84cf6-123">업그레이드할 수 없는 메일 [목록을 참조하세요.](#which-distribution-lists-cant-be-upgraded)</span><span class="sxs-lookup"><span data-stu-id="84cf6-123">See [Which distribution lists cannot be upgraded?](#which-distribution-lists-cant-be-upgraded).</span></span>

6. <span data-ttu-id="84cf6-124">여러 메일 목록을 업그레이드하는 경우 드롭다운 목록을 사용하여 업그레이드된 메일 목록을 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="84cf6-124">If you're upgrading multiple distribution lists, use the drop-down list to filter which distribution lists have been upgraded.</span></span> <span data-ttu-id="84cf6-125">목록이 완료되지 않은 경우 잠시 기다렸다가  새로 고침을 선택하여 성공적으로 업그레이드된 항목도 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84cf6-125">If the list isn't complete, wait a while longer and then select **Refresh** to see what's been successfully upgraded.</span></span><br/><span data-ttu-id="84cf6-126">선택한 모든 DLS에 대해 업그레이드 프로세스가 완료된 경우 알림이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="84cf6-126">There's no notice that tells you when the upgrade process has completed for all DLs you selected.</span></span> <span data-ttu-id="84cf6-127">업그레이드 가능 또는 업그레이드된 DLS 아래에  나열된 것을 보고 이를 알아 **볼 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="84cf6-127">You can figure this out by looking to see what's listed under **Available for upgrade** or **Upgraded DLs**.</span></span>

7. <span data-ttu-id="84cf6-128">업그레이드할 DL을 선택했지만 해당 DL이 페이지에 업그레이드할 수 있는 것으로 나타나면 업그레이드하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="84cf6-128">If you selected a DL for upgrade, but it's still appears on the page as Available to upgrade, then it failed to upgrade.</span></span> <span data-ttu-id="84cf6-129">업그레이드가 작동하지 않는 경우 할 일 [을 참조합니다.](#what-to-do-if-the-upgrade-doesnt-work)</span><span class="sxs-lookup"><span data-stu-id="84cf6-129">See [What to do if the upgrade doesn't work](#what-to-do-if-the-upgrade-doesnt-work).</span></span>

> [!NOTE]
> <span data-ttu-id="84cf6-130">그룹 다이제스트 전자 메일을 받고 있는 경우 소유자인 적합한 메일 그룹을 업그레이드할 수 있는 메일 그룹이 제공될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84cf6-130">If you're getting the groups digest emails you may notice at the bottom that it will sometimes offer to let you upgrade any eligible distribution lists that you're the owner of.</span></span> <span data-ttu-id="84cf6-131">다이제스트 전자 메일에 대한 자세한 [내용은 Outlook에서](https://support.microsoft.com/office/a0482e24-a769-4e39-a5ba-a7c56e828b22) 그룹 대화하기를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="84cf6-131">See [Have a group conversation in Outlook](https://support.microsoft.com/office/a0482e24-a769-4e39-a5ba-a7c56e828b22) for more information about digest emails.</span></span>

## <a name="what-to-do-if-the-upgrade-doesnt-work"></a><span data-ttu-id="84cf6-132">업그레이드가 작동하지 않는 경우의 작업</span><span class="sxs-lookup"><span data-stu-id="84cf6-132">What to do if the upgrade doesn't work</span></span>

<span data-ttu-id="84cf6-133">업그레이드하지 못하는 메일 목록은 변경되지 않은 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="84cf6-133">Distribution lists that fail to upgrade remain unchanged.</span></span>

<span data-ttu-id="84cf6-134">하나 이상의  적합한 메일 목록을 업그레이드하지 못하면 지원 [티켓을 열 수 있습니다.](../contact-support-for-business-products.md)</span><span class="sxs-lookup"><span data-stu-id="84cf6-134">If one or more **eligible** distribution lists fail to be upgraded, open a [Support ticket](../contact-support-for-business-products.md).</span></span> <span data-ttu-id="84cf6-135">이 문제를 해결하려면 그룹 엔지니어링 팀으로 에스컬레이터해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84cf6-135">The issue will need to be escalated to the Groups Engineering team for them to figure out the problem.</span></span>

<span data-ttu-id="84cf6-136">서비스 정전으로 메일 목록이 업그레이드되지 않았을 수 있지만 거의 업그레이드되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="84cf6-136">It's possible that the distribution list didn't get upgraded because of a service outage, but pretty unlikely.</span></span> <span data-ttu-id="84cf6-137">원하는 경우 잠시 기다렸다가 DL을 다시 업그레이드합니다.</span><span class="sxs-lookup"><span data-stu-id="84cf6-137">If you want, wait a while and then try to upgrade the DL again.</span></span>

## <a name="how-to-use-powershell-to-upgrade-several-distribution-lists-at-the-same-time"></a><span data-ttu-id="84cf6-138">PowerShell을 사용하여 여러 메일 목록을 동시에 업그레이드하는 방법</span><span class="sxs-lookup"><span data-stu-id="84cf6-138">How to use PowerShell to upgrade several distribution lists at the same time</span></span>

<span data-ttu-id="84cf6-139">PowerShell 사용 경험이 있는 경우 UI를 사용하는 대신 이 경로를 이동해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84cf6-139">If you're experienced at using PowerShell, you might want to go this route instead of using the UI.</span></span> <span data-ttu-id="84cf6-140">메일 목록을 업그레이드하는 데 도움이 되는 cmdlet 집합이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84cf6-140">We have a set of cmdlets that will help you upgrade distribution lists.</span></span> <span data-ttu-id="84cf6-141">아래를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="84cf6-141">See below.</span></span>

### <a name="upgrade-a-single-dl"></a><span data-ttu-id="84cf6-142">단일 DL 업그레이드</span><span class="sxs-lookup"><span data-stu-id="84cf6-142">Upgrade a single DL</span></span>

<span data-ttu-id="84cf6-143">단일 DL을 업그레이드하려면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="84cf6-143">To upgrade a single DL run the following command:</span></span>

```PowerShell
Upgrade-DistributionGroup -DlIdentities \<Dl SMTP address\>`
```

<span data-ttu-id="84cf6-144">예를 들어 SMTP 주소가 있는 DLS를 업그레이드하려면 dl1@contoso.com 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="84cf6-144">For example, if you want to upgrade a DLs with SMTP address dl1@contoso.com, run the following command:</span></span>

```PowerShell
Upgrade-DistributionGroup -DlIdentities dl1@contoso.com`
```

> [!NOTE]
> <span data-ttu-id="84cf6-145">[New-UnifiedGroup](/powershell/module/exchange/new-unifiedgroup) PowerShell cmdlet을 사용하여 단일 메일 그룹을 Microsoft 365 그룹으로 업그레이드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84cf6-145">You can also upgrade a single distribution list to a Microsoft 365 group using the [New-UnifiedGroup](/powershell/module/exchange/new-unifiedgroup) PowerShell cmdlet</span></span>

### <a name="upgrade-multiple-dls-in-a-batch"></a><span data-ttu-id="84cf6-146">일괄 처리로 여러 DLS 업그레이드</span><span class="sxs-lookup"><span data-stu-id="84cf6-146">Upgrade multiple DLs in a batch</span></span>

<span data-ttu-id="84cf6-147">여러 DLS를 일괄 처리로 전달하고 함께 업그레이드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84cf6-147">You can also pass multiple DLs as a batch and upgrade them together:</span></span>

```PowerShell
Upgrade-DistributionGroup -DlIdentities \<DL SMTP address1\>, \< DL SMTP address2\>,
\< DL SMTP address3\>, \< DL SMTP address 4\>
```

<span data-ttu-id="84cf6-148">예를 들어, SMTP 주소 및 , 및 를 사용하여 5개의 DLS를 업그레이드하려면 `dl1@contoso.com` `dl2@contoso.com` 다음 명령을 `dl3@contoso.com` `dl4@contoso.com` `dl5@contoso.com` 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="84cf6-148">For example, if you want to upgrade five DLs with SMTP address `dl1@contoso.com` and `dl2@contoso.com`, `dl3@contoso.com`, `dl4@contoso.com` and `dl5@contoso.com`, run the following command:</span></span>

`Upgrade-DistributionGroup -DlIdentities dl1@contoso.com, dl2@contoso.com, dl3@contoso.com, dl4@contoso.com, dl5@contoso.com`

### <a name="upgrade-all-eligible-dls"></a><span data-ttu-id="84cf6-149">모든 적합한 DLS 업그레이드</span><span class="sxs-lookup"><span data-stu-id="84cf6-149">Upgrade all eligible DLs</span></span>

<span data-ttu-id="84cf6-150">두 가지 방법으로 모든 적합한 DLS를 업그레이드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84cf6-150">There are two ways in which you can upgrade all the eligible DLs.</span></span>

> [!NOTE]
> <span data-ttu-id="84cf6-151">이러한 Upgrade-DistributionGroup cmdlet은 파이프라인에서 데이터를 받지 못합니다. 따라서 성공적으로 실행하려면 "foreach-object" 연산자를 {} 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84cf6-151">The Upgrade-DistributionGroup cmdlet doesn't receive data from the pipeline, for this reason it's required to use "foreach-object{}" operator to run successfully.</span></span>

1. <span data-ttu-id="84cf6-152">테넌트에서 적합한 DLS를 구하고 업그레이드 명령을 사용하여 업그레이드합니다.</span><span class="sxs-lookup"><span data-stu-id="84cf6-152">Get the eligible DLs in the tenant and upgrade them using the upgrade command:</span></span>

```PowerShell
Get-EligibleDistributionGroupForMigration | Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

2. <span data-ttu-id="84cf6-153">모든 DLS 목록을 표시하고 적합한 DLS만 업그레이드합니다.</span><span class="sxs-lookup"><span data-stu-id="84cf6-153">Get the list of all DLs and upgrade only the eligible DLs:</span></span>

```PowerShell
Get-DistributionGroup| Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

## <a name="faq-about-upgrading-distribution-lists-to-microsoft-365-groups-in-outlook"></a><span data-ttu-id="84cf6-154">Outlook에서 메일 그룹을 Microsoft 365 그룹으로 업그레이드하는 데 대한 FAQ</span><span class="sxs-lookup"><span data-stu-id="84cf6-154">FAQ about upgrading distribution lists to Microsoft 365 Groups in Outlook</span></span>

### <a name="which-distribution-lists-cant-be-upgraded"></a><span data-ttu-id="84cf6-155">어떤 메일 목록을 업그레이드할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="84cf6-155">Which distribution lists can't be upgraded?</span></span>

<span data-ttu-id="84cf6-156">클라우드에서 관리되는 단순하고 중첩되지 않은 메일 그룹만 업그레이드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84cf6-156">You can only upgrade cloud-managed, simple, non-nested distribution lists.</span></span> <span data-ttu-id="84cf6-157">아래 표에는 업그레이드할 수 없는 메일 **목록이** 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="84cf6-157">The table below lists distribution lists that **CANNOT** be upgraded.</span></span>

|<span data-ttu-id="84cf6-158">**속성**</span><span class="sxs-lookup"><span data-stu-id="84cf6-158">**Property**</span></span>|<span data-ttu-id="84cf6-159">**적합한가요?**</span><span class="sxs-lookup"><span data-stu-id="84cf6-159">**Eligible?**</span></span>|
|:-----|:-----|
|<span data-ttu-id="84cf6-160">On-premises managed distribution list.</span><span class="sxs-lookup"><span data-stu-id="84cf6-160">On-premises managed distribution list.</span></span>  <br/> |<span data-ttu-id="84cf6-161">아니요</span><span class="sxs-lookup"><span data-stu-id="84cf6-161">No</span></span>  <br/> |
|<span data-ttu-id="84cf6-162">중첩된 메일 그룹.</span><span class="sxs-lookup"><span data-stu-id="84cf6-162">Nested distribution lists.</span></span> <span data-ttu-id="84cf6-163">메일 그룹은 하위 그룹을 들이거나 다른 그룹의 구성원입니다.</span><span class="sxs-lookup"><span data-stu-id="84cf6-163">Distribution list either has child groups or is a member of another group.</span></span>  <br/> |<span data-ttu-id="84cf6-164">아니요</span><span class="sxs-lookup"><span data-stu-id="84cf6-164">No</span></span>  <br/> |
|<span data-ttu-id="84cf6-165">**UserMailbox, SharedMailbox,** **TeamMailbox,** **MailUser** 외의 구성원이 **RecipientTypeDetails인** 메일 목록</span><span class="sxs-lookup"><span data-stu-id="84cf6-165">Distribution lists with member **RecipientTypeDetails** other than **UserMailbox**, **SharedMailbox**, **TeamMailbox**, **MailUser**</span></span>  <br/> |<span data-ttu-id="84cf6-166">아니요</span><span class="sxs-lookup"><span data-stu-id="84cf6-166">No</span></span>  <br/> |
|<span data-ttu-id="84cf6-167">소유자가 100명 이상인 메일 목록</span><span class="sxs-lookup"><span data-stu-id="84cf6-167">Distribution list which has more than 100 owners</span></span>  <br/> |<span data-ttu-id="84cf6-168">아니요</span><span class="sxs-lookup"><span data-stu-id="84cf6-168">No</span></span>  <br/> |
|<span data-ttu-id="84cf6-169">구성원만 있지만 소유자가 없는 메일 목록</span><span class="sxs-lookup"><span data-stu-id="84cf6-169">Distribution list which only has members but no owner</span></span>  <br/> |<span data-ttu-id="84cf6-170">아니요</span><span class="sxs-lookup"><span data-stu-id="84cf6-170">No</span></span>  <br/> |
|<span data-ttu-id="84cf6-171">특수 문자를 포함하는 별칭이 있는 메일 목록</span><span class="sxs-lookup"><span data-stu-id="84cf6-171">Distribution list which has alias containing special characters</span></span>  <br/> |<span data-ttu-id="84cf6-172">아니요</span><span class="sxs-lookup"><span data-stu-id="84cf6-172">No</span></span>  <br/> |
|<span data-ttu-id="84cf6-173">메일 목록이 공유 사서함의 전달 주소로 구성되어 있는 경우</span><span class="sxs-lookup"><span data-stu-id="84cf6-173">If the distribution list is configured to be a forwarding address for Shared Mailbox</span></span>  <br/> |<span data-ttu-id="84cf6-174">아니요</span><span class="sxs-lookup"><span data-stu-id="84cf6-174">No</span></span>  <br/> |
|<span data-ttu-id="84cf6-175">DL이 다른 DL에서 **보낸** 사람 제한의 일부인 경우</span><span class="sxs-lookup"><span data-stu-id="84cf6-175">If the DL is part of **Sender Restriction** in another DL.</span></span>  <br/> |<span data-ttu-id="84cf6-176">아니요</span><span class="sxs-lookup"><span data-stu-id="84cf6-176">No</span></span>  <br/> |
|<span data-ttu-id="84cf6-177">보안 그룹</span><span class="sxs-lookup"><span data-stu-id="84cf6-177">Security groups</span></span>  <br/> |<span data-ttu-id="84cf6-178">아니요</span><span class="sxs-lookup"><span data-stu-id="84cf6-178">No</span></span>  <br/> |
|<span data-ttu-id="84cf6-179">동적 메일 그룹</span><span class="sxs-lookup"><span data-stu-id="84cf6-179">Dynamic Distribution lists</span></span>  <br/> |<span data-ttu-id="84cf6-180">아니요</span><span class="sxs-lookup"><span data-stu-id="84cf6-180">No</span></span>  <br/> |
|<span data-ttu-id="84cf6-181">**RoomLists로** 변환된 메일 목록</span><span class="sxs-lookup"><span data-stu-id="84cf6-181">Distribution lists which were converted to **RoomLists**</span></span>  <br/> |<span data-ttu-id="84cf6-182">아니요</span><span class="sxs-lookup"><span data-stu-id="84cf6-182">No</span></span>  <br/> |
|<span data-ttu-id="84cf6-183">**MemberJoinRestriction** 및/또는 **MemberDepartRestriction이 닫힌** 메일 **목록**</span><span class="sxs-lookup"><span data-stu-id="84cf6-183">Distribution lists where **MemberJoinRestriction** and/or **MemberDepartRestriction** is **Closed**</span></span>  <br/> |<span data-ttu-id="84cf6-184">아니요</span><span class="sxs-lookup"><span data-stu-id="84cf6-184">No</span></span>  <br/> |

### <a name="check-which-dls-are-eligible-for-upgrade"></a><span data-ttu-id="84cf6-185">업그레이드할 수 있는 DLS 확인</span><span class="sxs-lookup"><span data-stu-id="84cf6-185">Check which DLs are eligible for upgrade</span></span>

<span data-ttu-id="84cf6-186">DL이 적합한지 여부를 확인하려는 경우 다음 명령을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84cf6-186">If you want to check whether a DL is eligible or not, you can run the below command:</span></span>

`Get-DistributionGroup \<DL SMTP address\> | Get-EligibleDistributionGroupForMigration`

<span data-ttu-id="84cf6-187">업그레이드에 적합한 DLS를 확인하려면 다음 명령을 실행하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="84cf6-187">If you want to check which DLs are eligible for upgrade just run the following command:</span></span>

`Get-EligibleDistributionGroupForMigration`

### <a name="who-can-run-the-upgrade-scripts"></a><span data-ttu-id="84cf6-188">업그레이드 스크립트를 실행할 수 있는 사람</span><span class="sxs-lookup"><span data-stu-id="84cf6-188">Who can run the upgrade scripts?</span></span>

<span data-ttu-id="84cf6-189">전역 관리자 또는 Exchange 관리자 권한이 있는 사용자</span><span class="sxs-lookup"><span data-stu-id="84cf6-189">People with global admin or Exchange admin rights.</span></span>

### <a name="why-is-the-contact-card-still-showing-a-distribution-list-what-should-i-do-to-prevent-a-upgraded-distribution-list-from-showing-up-in-my-auto-suggest-list"></a><span data-ttu-id="84cf6-190">연락처 카드에 메일 목록이 계속 표시된 이유는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="84cf6-190">Why is the contact card still showing a distribution list?</span></span> <span data-ttu-id="84cf6-191">업그레이드된 메일 목록이 자동 제안 목록에 표시되지 않도록 방지하려면 어떻게 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="84cf6-191">What should I do to prevent a upgraded distribution list from showing up in my auto suggest list?</span></span>

- <span data-ttu-id="84cf6-192">Outlook의 경우: 마이그레이션 후 Microsoft 365 그룹 이름을 입력하여 Outlook에서 전자 메일을 보내면 받는 사람이 그룹이 아닌 메일 그룹으로 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="84cf6-192">For Outlook: When someone tries to send an email in Outlook by typing the Microsoft 365 group name after migration, the recipient will be resolved as the distribution list instead of the group.</span></span> <span data-ttu-id="84cf6-193">받는 사람의 연락처 카드는 메일 목록 연락처 카드가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="84cf6-193">The contact card of the recipient will be the distribution lists contact card.</span></span> <span data-ttu-id="84cf6-194">이는 Outlook의 받는 사람 캐시 또는 별칭 이름 캐시 때문에입니다.</span><span class="sxs-lookup"><span data-stu-id="84cf6-194">This is because of the recipient cache or nick name cache in Outlook.</span></span> <span data-ttu-id="84cf6-195">전자 메일이 그룹에 전송되지만 보낸 사람이 혼동을 일으킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84cf6-195">The email will be sent successfully to the group, but might cause confusion to the sender.</span></span><br/><span data-ttu-id="84cf6-196">Outlook 자동 완료 목록에 대한 [](/outlook/troubleshoot/contacts/information-about-the-outlook-autocomplete-list) 정보 항목의 단계를 수행하여 캐시를 다시 설정하면 이 문제가 해결됩니다.</span><span class="sxs-lookup"><span data-stu-id="84cf6-196">You can perform the steps in this topic, [Information about the Outlook AutoComplete list](/outlook/troubleshoot/contacts/information-about-the-outlook-autocomplete-list) to reset the cache, which will fix this issue.</span></span>

- <span data-ttu-id="84cf6-197">웹용 Outlook: 웹용 Outlook의 경우 메일 목록 받는 사람은 여전히 캐시에 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84cf6-197">For Outlook on the web: In case of Outlook on the web, the distribution list recipient will still remain in the cache.</span></span> <span data-ttu-id="84cf6-198">자동 완성 목록에서 [](https://support.microsoft.com/office/9E1419D9-E88F-445B-B07F-F558B8A37C58) 제안된 이름 또는 전자 메일 주소 제거의 단계에 따라 캐시를 새로 고쳐 그룹 연락처 카드를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84cf6-198">You can follow the steps in [Remove suggested name or email address from the Auto-Complete List](https://support.microsoft.com/office/9E1419D9-E88F-445B-B07F-F558B8A37C58) to refresh the cache to see the group contact card.</span></span>

### <a name="do-new-group-members-get-a-welcome-email-in-their-inbox"></a><span data-ttu-id="84cf6-199">새 그룹 구성원이 받은 편지함에서 환영 전자 메일을 받을 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="84cf6-199">Do new group members get a welcome email in their inbox?</span></span>

<span data-ttu-id="84cf6-200">아니요.</span><span class="sxs-lookup"><span data-stu-id="84cf6-200">No.</span></span> <span data-ttu-id="84cf6-201">시작 메시지를 사용하도록 설정하는 설정은 기본적으로 false로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="84cf6-201">The setting to enable welcome messages is set to false by default.</span></span> <span data-ttu-id="84cf6-202">이 설정은 마이그레이션이 완료된 후 참가할 수 있는 기존 그룹 구성원과 새 그룹 구성원 모두에 영향을 미치게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="84cf6-202">This setting affects both existing and new group members who may join after the migration is complete.</span></span> <span data-ttu-id="84cf6-203">나중에 그룹 소유자가 게스트 사용자를 허용하는 경우 게스트 사용자는 받은 편지함에서 환영 전자 메일을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="84cf6-203">If the group owner later allows guest users, guest users won't receive a welcome email in their inbox.</span></span> <span data-ttu-id="84cf6-204">게스트 구성원은 그룹 작업을 계속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84cf6-204">Guest members can continue working with the group.</span></span>

### <a name="what-if-one-or-some-of-the-dls-are-not-upgraded"></a><span data-ttu-id="84cf6-205">DLS 중 하나 또는 일부가 업그레이드되지 않는 경우 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="84cf6-205">What if one or some of the DLs are not upgraded?</span></span>

<span data-ttu-id="84cf6-206">DL을 사용할 수 있지만 업그레이드할 수 없는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84cf6-206">There are some cases in which though DL is eligible but could not be upgraded.</span></span> <span data-ttu-id="84cf6-207">DL은 업그레이드되지 않고 DL로 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84cf6-207">The DL does not get upgraded and remains as a DL.</span></span>

- <span data-ttu-id="84cf6-208">관리자가 조직의  그룹에 대해 그룹 전자 메일 주소 정책을 적용한 경우 조건을 충족하지 않는 DL을 업그레이드하려고 시도하면 DL이 업그레이드되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="84cf6-208">Where admin has applied **Group Email Address Policy** for the groups in an organization and they try to upgrade DLs which doesn't fulfill the criteria, the DL does not get upgraded</span></span>

- <span data-ttu-id="84cf6-209">**MemberJoinRestriction** 또는 **MemberDepartRestriction이** **Closed로** 설정된 DLS를 업그레이드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="84cf6-209">DLs with **MemberJoinRestriction** or **MemberDepartRestriction** set to **Closed**, could not be upgraded</span></span>

### <a name="what-happens-to-the-dl-if-the-upgrade-from-eac-fails"></a><span data-ttu-id="84cf6-210">EAC에서 업그레이드가 실패하면 DL은 어떻게 하나요?</span><span class="sxs-lookup"><span data-stu-id="84cf6-210">What happens to the DL if the upgrade from EAC fails?</span></span>

<span data-ttu-id="84cf6-211">업그레이드는 통화가 서버에 제출될 때만 진행됩니다.</span><span class="sxs-lookup"><span data-stu-id="84cf6-211">The upgrade will happen only when the call is submitted to the server.</span></span> <span data-ttu-id="84cf6-212">업그레이드가 실패하면 DLS가 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="84cf6-212">If the upgrade fails, your DLs will be intact.</span></span> <span data-ttu-id="84cf6-213">이 두 개는 사용 중일 때처럼 작동됩니다.</span><span class="sxs-lookup"><span data-stu-id="84cf6-213">They will work like they used to.</span></span>