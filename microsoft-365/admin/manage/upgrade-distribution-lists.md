---
title: Outlook에서 배포 목록을 Office 365 그룹으로 업그레이드
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 787d7a75-e201-46f3-a242-f698162ff09f
description: Outlook에서 하나 또는 여러 개의 메일 그룹을 Office 365 그룹으로 업그레이드 하는 방법 및 PowerShell을 사용 하 여 여러 메일 그룹을 동시에 업그레이드 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 7337d450cf1e9b249b2b9dc2ab66f32f5b1577e0
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/02/2020
ms.locfileid: "42361713"
---
# <a name="upgrade-distribution-lists-to-office-365-groups-in-outlook"></a><span data-ttu-id="411f9-103">Outlook에서 배포 목록을 Office 365 그룹으로 업그레이드</span><span class="sxs-lookup"><span data-stu-id="411f9-103">Upgrade distribution lists to Office 365 Groups in Outlook</span></span>

<span data-ttu-id="411f9-104">Outlook을 사용 하 여 메일 그룹을 Office 365 그룹으로 업그레이드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="411f9-104">You can upgrade distribution lists to Office 365 Groups with Outlook.</span></span> <span data-ttu-id="411f9-105">이를 통해 조직의 메일 그룹에 Office 365 그룹의 모든 기능과 기능을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="411f9-105">This is a great way to give your organization's distribution lists all the features and functionality of Office 365 groups.</span></span> [<span data-ttu-id="411f9-106">Outlook에서 배포 목록을 그룹으로 업그레이드해야 하는 이유</span><span class="sxs-lookup"><span data-stu-id="411f9-106">Why you should upgrade your distribution lists to groups in Outlook</span></span>](https://support.office.com/article/7fb3d880-593b-4909-aafa-950dd50ce188.aspx)

<span data-ttu-id="411f9-107">Dl은 한 번에 하나씩 또는 여러 개 동시에 업그레이드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="411f9-107">You can upgrade DLs one at a time, or several at the same time.</span></span>

## <a name="upgrade-one-or-many-distribution-lists-to-office-365-groups-in-outlook"></a><span data-ttu-id="411f9-108">Outlook에서 하나 이상의 메일 그룹을 Office 365 그룹으로 업그레이드</span><span class="sxs-lookup"><span data-stu-id="411f9-108">Upgrade one or many distribution lists to Office 365 Groups in Outlook</span></span>

<span data-ttu-id="411f9-109">메일 그룹을 업그레이드 하려면 Office 365 전역 관리자 또는 Exchange 관리자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="411f9-109">You must be an Office 365 global admin or Exchange admin to upgrade a distribution list.</span></span> <span data-ttu-id="411f9-110">Office 365 그룹으로 업그레이드 하려면 메일 그룹에 사서함 소유자가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="411f9-110">To upgrade to Office 365 groups, a distribution group must have an owner with a mailbox.</span></span> 

1. <span data-ttu-id="411f9-111"><a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 관리 센터</a>로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="411f9-111">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>

2. <span data-ttu-id="411f9-112">Exchange 관리 센터에서 **받는 사람** \> **그룹**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="411f9-112">In the Exchange admin center, go to **Recipients** \> **Groups**.</span></span><br/><span data-ttu-id="411f9-113">Office 365 그룹으로 업그레이드할 수 있는 메일 **그룹 (메일 그룹이** 라고도 함)이 있음을 나타내는 알림이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="411f9-113">You'll see a notice indicating you have distribution lists (also called **distribution groups** ) that are eligible to be upgraded to Office 365 groups.</span></span><br/> <span data-ttu-id="411f9-114">![시작 단추를 선택 합니다.](../../media/8cf838b4-2644-401f-a366-08c1eea183eb.png)</span><span class="sxs-lookup"><span data-stu-id="411f9-114">![Select the Get started button](../../media/8cf838b4-2644-401f-a366-08c1eea183eb.png)</span></span>

3. <span data-ttu-id="411f9-115">**그룹** 페이지에서 하나 이상의 메일 **그룹 (메일 그룹이** 라고도 함)을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="411f9-115">Select one or more distribution lists (also called a **distribution group** ) from the **groups** page.</span></span><br/><span data-ttu-id="411f9-116">![메일 그룹 선택](../../media/2c303433-d60b-4100-a6ae-5809b03a8cdb.png)</span><span class="sxs-lookup"><span data-stu-id="411f9-116">![Select a distribution group](../../media/2c303433-d60b-4100-a6ae-5809b03a8cdb.png)</span></span>

4. <span data-ttu-id="411f9-117">업그레이드 아이콘을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="411f9-117">Select the upgrade icon.</span></span><br/>![Office 365 그룹으로 업그레이드 아이콘](../../media/1e28cb3d-bff3-4be3-8329-1902d2d54720.png)

5. <span data-ttu-id="411f9-119">정보 대화 상자에서 **예** 를 선택 하 여 업그레이드를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="411f9-119">On the information dialog, select **Yes** to confirm the upgrade.</span></span> <span data-ttu-id="411f9-120">프로세스가 즉시 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="411f9-120">The process begins immediately.</span></span> <span data-ttu-id="411f9-121">업그레이드 중인 Dl의 크기 및 수에 따라 프로세스에 몇 분 또는 몇 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="411f9-121">Depending on the size and number of DLs you're upgrading, the process can take minutes or hours.</span></span><br/><span data-ttu-id="411f9-122">메일 그룹을 업그레이드할 수 없는 경우에는 대화 상자가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="411f9-122">If the distribution list can't be upgraded, a dialog appears saying so.</span></span> <span data-ttu-id="411f9-123">[업그레이드할 수 없는 메일 그룹을 확인 하 시겠습니까?](#which-distribution-lists-cannot-be-upgraded).</span><span class="sxs-lookup"><span data-stu-id="411f9-123">See [Which distribution lists cannot be upgraded?](#which-distribution-lists-cannot-be-upgraded).</span></span>

6. <span data-ttu-id="411f9-124">여러 메일 그룹을 업그레이드 하는 경우 드롭다운 목록을 사용 하 여 업그레이드 된 메일 그룹을 필터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="411f9-124">If you're upgrading multiple distribution lists, use the drop-down list to filter which distribution lists have been upgraded.</span></span> <span data-ttu-id="411f9-125">목록이 완료 되지 않으면 잠시 기다린 후 **새로 고침** 을 선택 하 여 업그레이드 된 내용을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="411f9-125">If the list isn't complete, wait a while longer and then select **Refresh** to see what's been successfully upgraded.</span></span><br/><span data-ttu-id="411f9-126">선택한 모든 Dl에 대해 업그레이드 프로세스가 완료 되 면이를 알리는 알림이 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="411f9-126">There's no notice that tells you when the upgrade process has completed for all DLs you selected.</span></span> <span data-ttu-id="411f9-127">업그레이드 또는 업그레이드 된 **dl**에서 **사용할 수 있는** 항목을 확인 하 여이를 파악할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="411f9-127">You can figure this out by looking to see what's listed under **Available for upgrade** or **Upgraded DLs**.</span></span>

7. <span data-ttu-id="411f9-128">업그레이드할 DL을 선택 했지만 업그레이드 하는 데 사용할 수 있는 페이지에 여전히 표시 되는 경우 업그레이드에 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="411f9-128">If you selected a DL for upgrade, but it's still appears on the page as Available to upgrade, then it failed to upgrade.</span></span> <span data-ttu-id="411f9-129">[업그레이드가 작동 하지 않는 경우 수행할 작업을](#what-to-do-if-the-upgrade-doesnt-work)확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="411f9-129">See [What to do if the upgrade doesn't work](#what-to-do-if-the-upgrade-doesnt-work).</span></span>

> [!NOTE]
> <span data-ttu-id="411f9-130">그룹 다이제스트 전자 메일을 사용 하는 경우에는 사용자가 담당자로 적합 한 메일 그룹을 업그레이드할 수 있도록 하는 경우를 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="411f9-130">If you're getting the groups digest emails you may notice at the bottom that it will sometimes offer to let you upgrade any eligible distribution lists that you're the owner of.</span></span> <span data-ttu-id="411f9-131">다이제스트 전자 메일에 대 한 자세한 내용은 [Outlook에서 그룹 대화 포함를](https://support.office.com/article/a0482e24-a769-4e39-a5ba-a7c56e828b22.aspx) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="411f9-131">See [Have a group conversation in Outlook](https://support.office.com/article/a0482e24-a769-4e39-a5ba-a7c56e828b22.aspx) for more information about digest emails.</span></span>


## <a name="what-to-do-if-the-upgrade-doesnt-work"></a><span data-ttu-id="411f9-132">업그레이드가 작동 하지 않는 경우 수행할 작업</span><span class="sxs-lookup"><span data-stu-id="411f9-132">What to do if the upgrade doesn't work</span></span>

<span data-ttu-id="411f9-133">업그레이드에 실패 한 메일 그룹은 변경 되지 않은 상태로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="411f9-133">Distribution lists that fail to upgrade remain unchanged.</span></span>

<span data-ttu-id="411f9-134">하나 이상의 **적합** 한 메일 그룹을 업그레이드 하지 못하면 [지원 티켓](../contact-support-for-business-products.md)을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="411f9-134">If one or more **eligible** distribution lists fail to be upgraded, open a [Support ticket](../contact-support-for-business-products.md).</span></span> <span data-ttu-id="411f9-135">문제를 파악 하기 위해이 문제를 그룹 엔지니어링 팀으로 에스컬레이션 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="411f9-135">The issue will need to be escalated to the Groups Engineering team for them to figure out the problem.</span></span>

<span data-ttu-id="411f9-136">서비스 중단으로 인해 메일 그룹이 업그레이드 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="411f9-136">It's possible that the distribution list didn't get upgraded because of a service outage, but pretty unlikely.</span></span> <span data-ttu-id="411f9-137">원하는 경우 잠시 기다린 후에 DL을 다시 업그레이드 해 보십시오.</span><span class="sxs-lookup"><span data-stu-id="411f9-137">If you want, wait a while and then try to upgrade the DL again.</span></span>

## <a name="how-to-use-powershell-to-upgrade-several-distribution-lists-at-the-same-time"></a><span data-ttu-id="411f9-138">PowerShell을 사용 하 여 여러 메일 그룹을 동시에 업그레이드 하는 방법</span><span class="sxs-lookup"><span data-stu-id="411f9-138">How to use PowerShell to upgrade several distribution lists at the same time</span></span>

<span data-ttu-id="411f9-139">PowerShell을 사용 하 고 있는 경우에는 UI를 사용 하는 대신이 경로를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="411f9-139">If you're experienced at using PowerShell, you might want to go this route instead of using the UI.</span></span> <span data-ttu-id="411f9-140">배포 목록을 업그레이드 하는 데 도움이 되는 일련의 cmdlet이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="411f9-140">We have a set of cmdlets that will help you upgrade distribution lists.</span></span> <span data-ttu-id="411f9-141">아래를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="411f9-141">See below.</span></span>

### <a name="upgrade-a-single-dl"></a><span data-ttu-id="411f9-142">단일 DL 업그레이드</span><span class="sxs-lookup"><span data-stu-id="411f9-142">Upgrade a single DL</span></span>

<span data-ttu-id="411f9-143">단일 DL을 업그레이드 하려면 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="411f9-143">To upgrade a single DL run the following command:</span></span>

`Upgrade-DistributionGroup -DlIdentities \<Dl SMTP address\>`

<span data-ttu-id="411f9-144">예를 들어 SMTP 주소 dl1@contoso.com를 사용 하 여 Dl을 업그레이드 하려면 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="411f9-144">For example, if you want to upgrade a DLs with SMTP address dl1@contoso.com, run the following command:</span></span>

`Upgrade-DistributionGroup -DlIdentities dl1@contoso.com`

> [!NOTE]
> <span data-ttu-id="411f9-145">[Remove-unifiedgroup](https://go.microsoft.com/fwlink/?LinkID=786379) PowerShell cmdlet을 사용 하 여 단일 메일 그룹을 Office 365 group으로 업그레이드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="411f9-145">You can also upgrade a single distribution list to an Office 365 group using the [New-UnifiedGroup](https://go.microsoft.com/fwlink/?LinkID=786379) PowerShell cmdlet</span></span>

### <a name="upgrade-multiple-dls-in-a-batch"></a><span data-ttu-id="411f9-146">일괄 처리에서 여러 Dl 업그레이드</span><span class="sxs-lookup"><span data-stu-id="411f9-146">Upgrade multiple DLs in a batch</span></span>

<span data-ttu-id="411f9-147">여러 Dl을 일괄적으로 전달 하 고 함께 업그레이드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="411f9-147">You can also pass multiple DLs as a batch and upgrade them together:</span></span>

```
Upgrade-DistributionGroup -DlIdentities \<DL SMTP address1\>, \< DL SMTP address2\>,

\< DL SMTP address3\>, \< DL SMTP address 4\>
```

<span data-ttu-id="411f9-148">예를 들어 SMTP `dl1@contoso.com` 주소 `dl2@contoso.com` `dl3@contoso.com` `dl4@contoso.com` `dl5@contoso.com`와을 사용 하 여 5 개의 dl을 업그레이드 하려면 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="411f9-148">For example, if you want to upgrade five DLs with SMTP address `dl1@contoso.com` and `dl2@contoso.com`, `dl3@contoso.com`, `dl4@contoso.com` and `dl5@contoso.com`, run the following command:</span></span>

`Upgrade-DistributionGroup -DlIdentities dl1@contoso.com, dl2@contoso.com, dl3@contoso.com, dl4@contoso.com, dl5@contoso.com`

### <a name="upgrade-all-eligible-dls"></a><span data-ttu-id="411f9-149">모든 적합 한 Dl 업그레이드</span><span class="sxs-lookup"><span data-stu-id="411f9-149">Upgrade all eligible DLs</span></span>

<span data-ttu-id="411f9-150">모든 적합 한 Dl을 업그레이드 하는 방법에는 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="411f9-150">There are two ways in which you can upgrade all the eligible DLs.</span></span>

> [!NOTE]
> <span data-ttu-id="411f9-151">New-distributiongroup cmdlet은 파이프라인의 데이터를 수신 하지 않으므로 "foreach-object{}" 연산자를 사용 하 여 성공적으로 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="411f9-151">The Upgrade-DistributionGroup cmdlet doesn't receive data from the pipeline, for this reason it's required to use "foreach-object{}" operator to run successfully.</span></span>

1. <span data-ttu-id="411f9-152">테 넌 트에서 적격 Dl을 가져오고 upgrade 명령을 사용 하 여 업그레이드 합니다.</span><span class="sxs-lookup"><span data-stu-id="411f9-152">Get the eligible DLs in the tenant and upgrade them using the upgrade command:</span></span>

```
Get-EligibleDistributionGroupForMigration | Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

2. <span data-ttu-id="411f9-153">모든 Dl의 목록을 가져오고 적격 Dl만 업그레이드 합니다.</span><span class="sxs-lookup"><span data-stu-id="411f9-153">Get the list of all DLs and upgrade only the eligible DLs:</span></span>

```
Get-DistributionGroup| Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

## <a name="faq-about-upgrading-distribution-lists-to-office-365-groups-in-outlook"></a><span data-ttu-id="411f9-154">Outlook에서 메일 그룹을 Office 365 그룹으로 업그레이드 하는 방법에 대 한 FAQ</span><span class="sxs-lookup"><span data-stu-id="411f9-154">FAQ about upgrading distribution lists to Office 365 Groups in Outlook</span></span>

### <a name="which-distribution-lists-cannot-be-upgraded"></a><span data-ttu-id="411f9-155">업그레이드할 수 없는 메일 그룹은 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="411f9-155">Which distribution lists cannot be upgraded?</span></span>

<span data-ttu-id="411f9-156">클라우드로 관리 되는 단순 하 고 중첩 되지 않은 메일 목록만 업그레이드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="411f9-156">You can only upgrade cloud-managed, simple, non-nested distribution lists.</span></span> <span data-ttu-id="411f9-157">아래 표에는 업그레이드할 **수** 없는 메일 그룹이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="411f9-157">The table below lists distribution lists that **CANNOT** be upgraded.</span></span>

|<span data-ttu-id="411f9-158">**속성**</span><span class="sxs-lookup"><span data-stu-id="411f9-158">**Property**</span></span>|<span data-ttu-id="411f9-159">**해당?**</span><span class="sxs-lookup"><span data-stu-id="411f9-159">**Eligible?**</span></span>|
|:-----|:-----|
|<span data-ttu-id="411f9-160">온-프레미스 관리 되는 메일 그룹</span><span class="sxs-lookup"><span data-stu-id="411f9-160">On-premises managed distribution list.</span></span>  <br/> |<span data-ttu-id="411f9-161">아니요</span><span class="sxs-lookup"><span data-stu-id="411f9-161">No</span></span>  <br/> |
|<span data-ttu-id="411f9-162">중첩 된 메일 그룹</span><span class="sxs-lookup"><span data-stu-id="411f9-162">Nested distribution lists.</span></span> <span data-ttu-id="411f9-163">메일 그룹이 하위 그룹을 포함 하거나 다른 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="411f9-163">Distribution list either has child groups or is a member of another group.</span></span>  <br/> |<span data-ttu-id="411f9-164">아니요</span><span class="sxs-lookup"><span data-stu-id="411f9-164">No</span></span>  <br/> |
|<span data-ttu-id="411f9-165">**Usermailbox**, **sharedmailbox**, **teammailbox**, **mailuser** 를 제외한 구성원 **RecipientTypeDetails** 이 포함 된 메일 그룹</span><span class="sxs-lookup"><span data-stu-id="411f9-165">Distribution lists with member **RecipientTypeDetails** other than **UserMailbox**, **SharedMailbox**, **TeamMailbox**, **MailUser**</span></span>  <br/> |<span data-ttu-id="411f9-166">아니요</span><span class="sxs-lookup"><span data-stu-id="411f9-166">No</span></span>  <br/> |
|<span data-ttu-id="411f9-167">100 개 보다 많은 소유자가 포함 된 메일 그룹</span><span class="sxs-lookup"><span data-stu-id="411f9-167">Distribution list which has more than 100 owners</span></span>  <br/> |<span data-ttu-id="411f9-168">아니요</span><span class="sxs-lookup"><span data-stu-id="411f9-168">No</span></span>  <br/> |
|<span data-ttu-id="411f9-169">구성원만 있고 소유자가 없는 메일 그룹</span><span class="sxs-lookup"><span data-stu-id="411f9-169">Distribution list which only has members but no owner</span></span>  <br/> |<span data-ttu-id="411f9-170">아니요</span><span class="sxs-lookup"><span data-stu-id="411f9-170">No</span></span>  <br/> |
|<span data-ttu-id="411f9-171">특수 문자를 포함 하는 별칭이 있는 메일 그룹</span><span class="sxs-lookup"><span data-stu-id="411f9-171">Distribution list which has alias containing special characters</span></span>  <br/> |<span data-ttu-id="411f9-172">아니요</span><span class="sxs-lookup"><span data-stu-id="411f9-172">No</span></span>  <br/> |
|<span data-ttu-id="411f9-173">메일 그룹이 공유 사서함의 전달 주소로 구성 된 경우</span><span class="sxs-lookup"><span data-stu-id="411f9-173">If the distribution list is configured to be a forwarding address for Shared Mailbox</span></span>  <br/> |<span data-ttu-id="411f9-174">아니요</span><span class="sxs-lookup"><span data-stu-id="411f9-174">No</span></span>  <br/> |
|<span data-ttu-id="411f9-175">DL이 다른 DL의 **보낸 사람 제한** 에 포함 되어 있는 경우</span><span class="sxs-lookup"><span data-stu-id="411f9-175">If the DL is part of **Sender Restriction** in another DL.</span></span>  <br/> |<span data-ttu-id="411f9-176">아니요</span><span class="sxs-lookup"><span data-stu-id="411f9-176">No</span></span>  <br/> |
|<span data-ttu-id="411f9-177">보안 그룹</span><span class="sxs-lookup"><span data-stu-id="411f9-177">Security groups</span></span>  <br/> |<span data-ttu-id="411f9-178">아니요</span><span class="sxs-lookup"><span data-stu-id="411f9-178">No</span></span>  <br/> |
|<span data-ttu-id="411f9-179">동적 메일 그룹</span><span class="sxs-lookup"><span data-stu-id="411f9-179">Dynamic Distribution lists</span></span>  <br/> |<span data-ttu-id="411f9-180">아니요</span><span class="sxs-lookup"><span data-stu-id="411f9-180">No</span></span>  <br/> |
|<span data-ttu-id="411f9-181">**RoomLists** 로 변환 된 메일 그룹</span><span class="sxs-lookup"><span data-stu-id="411f9-181">Distribution lists which were converted to **RoomLists**</span></span>  <br/> |<span data-ttu-id="411f9-182">아니요</span><span class="sxs-lookup"><span data-stu-id="411f9-182">No</span></span>  <br/> |
|<span data-ttu-id="411f9-183">**Memberjoinrestriction** 및/또는 **MemberDepartRestriction** 가 **닫혀** 있는 메일 그룹</span><span class="sxs-lookup"><span data-stu-id="411f9-183">Distribution lists where **MemberJoinRestriction** and/or **MemberDepartRestriction** is **Closed**</span></span>  <br/> |<span data-ttu-id="411f9-184">아니요</span><span class="sxs-lookup"><span data-stu-id="411f9-184">No</span></span>  <br/> |

### <a name="how-do-i-check-which-dls-are-eligible-for-upgrade"></a><span data-ttu-id="411f9-185">업그레이드할 자격이 있는 Dl을 확인 하려면 어떻게 해야 합니까?</span><span class="sxs-lookup"><span data-stu-id="411f9-185">How do I check which DLs are eligible for upgrade?</span></span>

<span data-ttu-id="411f9-186">DL이 적합 한지 여부를 확인 하려면 다음 명령을 실행 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="411f9-186">If you want to check whether a DL is eligible or not, you can run the below command:</span></span>

`Get-DistributionGroup \<DL SMTP address\> | Get-EligibleDistributionGroupForMigration`

<span data-ttu-id="411f9-187">업그레이드할 자격이 있는 Dl을 확인 하려면 다음 명령을 실행 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="411f9-187">If you want to check which DLs are eligible for upgrade just run the following command:</span></span>

`Get-EligibleDistributionGroupForMigration`

### <a name="who-can-run-the-upgrade-scripts"></a><span data-ttu-id="411f9-188">업그레이드 스크립트를 실행할 수 있는 사람은 누구 인가요?</span><span class="sxs-lookup"><span data-stu-id="411f9-188">Who can run the upgrade scripts?</span></span>

<span data-ttu-id="411f9-189">Office 365 전역 관리자 또는 Exchange 관리 권한이 있는 사용자</span><span class="sxs-lookup"><span data-stu-id="411f9-189">People with Office 365 global admin or Exchange admin rights.</span></span>

### <a name="why-is-the-contact-card-still-showing-a-distribution-list-what-should-i-do-to-prevent-a-upgraded-distribution-list-from-showing-up-in-my-auto-suggest-list"></a><span data-ttu-id="411f9-190">연락처 카드가 여전히 메일 그룹을 표시 하는 이유는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="411f9-190">Why is the contact card still showing a distribution list?</span></span> <span data-ttu-id="411f9-191">업그레이드 된 메일 그룹이 자동 제안 목록에 표시 되지 않도록 하려면 어떻게 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="411f9-191">What should I do to prevent a upgraded distribution list from showing up in my auto suggest list?</span></span>

- <span data-ttu-id="411f9-192">Outlook: 사용자가 마이그레이션 후 Office 365 그룹 이름을 입력 하 여 Outlook에서 전자 메일을 보내려고 하면 받는 사람이 그룹 대신 메일 목록으로 확인 됩니다.</span><span class="sxs-lookup"><span data-stu-id="411f9-192">For Outlook: When someone tries to send an email in Outlook by typing the Office 365 group name after migration, the recipient will be resolved as the distribution list instead of the group.</span></span> <span data-ttu-id="411f9-193">받는 사람의 연락처 카드는 메일 그룹 대화 상대 카드로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="411f9-193">The contact card of the recipient will be the distribution lists contact card.</span></span> <span data-ttu-id="411f9-194">이는 받는 사람 캐시 또는 nick 이름 캐시가 Outlook에 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="411f9-194">This is because of the recipient cache or nick name cache in Outlook.</span></span> <span data-ttu-id="411f9-195">전자 메일을 그룹으로 전송 하지만 보낸 사람에 게 혼란을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="411f9-195">The email will be sent successfully to the group, but might cause confusion to the sender.</span></span><br/><span data-ttu-id="411f9-196">이 항목의 단계를 수행 하 여 캐시를 다시 설정 하는 [Outlook 자동 완성 목록에 대 한 정보](https://go.microsoft.com/fwlink/?LinkID=798736) 로이 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="411f9-196">You can perform the steps in this topic, [Information about the Outlook AutoComplete list](https://go.microsoft.com/fwlink/?LinkID=798736) to reset the cache, which will fix this issue.</span></span>

- <span data-ttu-id="411f9-197">웹용 Outlook의 경우: 웹용 Outlook의 경우 메일 그룹 받는 사람은 여전히 캐시에 남아 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="411f9-197">For Outlook on the web: In case of Outlook on the web, the distribution list recipient will still remain in the cache.</span></span> <span data-ttu-id="411f9-198">[자동 완성 목록에서 제안 된 이름 또는 전자 메일 주소 제거](https://support.office.com/article/9E1419D9-E88F-445B-B07F-F558B8A37C58.aspx) 의 단계를 수행 하 여 캐시를 새로 고쳐 그룹 대화 상대 카드를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="411f9-198">You can follow the steps in [Remove suggested name or email address from the Auto-Complete List](https://support.office.com/article/9E1419D9-E88F-445B-B07F-F558B8A37C58.aspx) to refresh the cache to see the group contact card.</span></span>

### <a name="do-new-group-members-get-a-welcome-email-in-their-inbox"></a><span data-ttu-id="411f9-199">새 그룹 구성원에 게 받은 편지함에 환영 전자 메일이 전송 됩니까?</span><span class="sxs-lookup"><span data-stu-id="411f9-199">Do new group members get a welcome email in their inbox?</span></span>

<span data-ttu-id="411f9-200">아니요.</span><span class="sxs-lookup"><span data-stu-id="411f9-200">No.</span></span> <span data-ttu-id="411f9-201">환영 메시지를 사용 하도록 설정 하는 설정은 기본적으로 false로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="411f9-201">The setting to enable welcome messages is set to false by default.</span></span> <span data-ttu-id="411f9-202">이 설정은 마이그레이션이 완료 된 후에 참가할 수 있는 기존 그룹과 새 그룹 구성원에 모두 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="411f9-202">This setting affects both existing and new group members who may join after the migration is complete.</span></span> <span data-ttu-id="411f9-203">나중에 그룹 소유자가 게스트 사용자를 허용 하는 경우 guest 사용자는 자신의 받은 편지함에 환영 전자 메일을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="411f9-203">If the group owner later allows guest users, guest users won't receive a welcome email in their inbox.</span></span> <span data-ttu-id="411f9-204">게스트 구성원은 그룹으로 계속 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="411f9-204">Guest members can continue working with the group.</span></span>

### <a name="what-if-one-or-some-of-the-dls-are-not-upgraded"></a><span data-ttu-id="411f9-205">Dl 중 하나 또는 일부가 업그레이드 되지 않으면 어떻게 됩니까?</span><span class="sxs-lookup"><span data-stu-id="411f9-205">What if one or some of the DLs are not upgraded?</span></span>

<span data-ttu-id="411f9-206">DL이 적격이 고 업그레이드할 수 없는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="411f9-206">There are some cases in which though DL is eligible but could not be upgraded.</span></span> <span data-ttu-id="411f9-207">DL이 업그레이드 되지 않고 DL로 유지 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="411f9-207">The DL does not get upgraded and remains as a DL.</span></span>

- <span data-ttu-id="411f9-208">관리자가 조직의 그룹에 대 한 **그룹 전자 메일 주소 정책을** 적용 하 고 기준을 충족 하지 않는 dl을 업그레이드 하려고 하면 dl이 업그레이드 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="411f9-208">Where admin has applied **Group Email Address Policy** for the groups in an organization and they try to upgrade DLs which doesn't fulfill the criteria, the DL does not get upgraded</span></span>

- <span data-ttu-id="411f9-209">**Memberjoinrestriction** 또는 **MemberDepartRestriction** 이 **닫힘으로**설정 된 dl은 업그레이드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="411f9-209">DLs with **MemberJoinRestriction** or **MemberDepartRestriction** set to **Closed**, could not be upgraded</span></span>

### <a name="what-happens-to-the-dl-if-the-upgrade-from-eac-fails"></a><span data-ttu-id="411f9-210">EAC에서 업그레이드가 실패 하는 경우 DL이 어떻게 됩니까?</span><span class="sxs-lookup"><span data-stu-id="411f9-210">What happens to the DL if the upgrade from EAC fails?</span></span>

<span data-ttu-id="411f9-211">호출이 서버로 전송 될 때에만 업그레이드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="411f9-211">The upgrade will happen only when the call is submitted to the server.</span></span> <span data-ttu-id="411f9-212">업그레이드가 실패 하는 경우에는 Dl이 그대로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="411f9-212">If the upgrade fails, your DLs will be intact.</span></span> <span data-ttu-id="411f9-213">사용 하는 것과 같은 방식으로 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="411f9-213">They will work like they used to.</span></span>


