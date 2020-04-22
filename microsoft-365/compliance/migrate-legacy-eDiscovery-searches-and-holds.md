---
title: 레거시 eDiscovery 검색 및 보류를 Microsoft 365 준수 센터로 마이그레이션
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
ROBOTS: NOINDEX, NOFOLLOW
description: ''
ms.openlocfilehash: bb2bccc6689a3739bcb1f3736771cf81b7c467bd
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637940"
---
# <a name="migrate-legacy-ediscovery-searches-and-holds-to-the-microsoft-365-compliance-center"></a><span data-ttu-id="26d55-102">레거시 eDiscovery 검색 및 보류를 Microsoft 365 준수 센터로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="26d55-102">Migrate legacy eDiscovery searches and holds to the Microsoft 365 compliance center</span></span>

<span data-ttu-id="26d55-103">Microsoft 365 준수 센터에서는 더 높은 안정성, 성능 향상, 관련 콘텐츠를 구성 하는 경우를 비롯 하 여 eDiscovery 워크플로에 적합 한 다양 한 기능을 제공 하 고, 검토 집합에서 콘텐츠 및 분석을 검토 하 여 근접 중복 그룹, 전자 메일 스레딩, 테마 분석 및 예측 코딩 등의 검토를 위한 데이터를 cull 수 있도록 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="26d55-103">The Microsoft 365 compliance center provides an improved experience for eDiscovery usage, including: higher reliability, better performance and many features tailored to eDiscovery workflows including cases to organize your content by matter, review sets to review content and analytics to help cull data for review such as near-duplicate grouping, email threading, themes analysis, and predictive coding.</span></span>

<span data-ttu-id="26d55-104">이 문서에서는 고객이 새로운 기능과 향상 된 기능을 활용할 수 있도록 하기 위해 Exchange 관리 센터에서 Microsoft 365 준수 센터로 원본 위치 eDiscovery 검색 및 보존을 마이그레이션하는 방법에 대 한 기본 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="26d55-104">To help customers take advantage of the new and improved functionality, this article provides basic guidance on how to migrate In-Place eDiscovery searches and holds from the Exchange admin center to the Microsoft 365 compliance center.</span></span>

> [!NOTE]
> <span data-ttu-id="26d55-105">다양 한 시나리오가 있으므로이 문서에서는 Microsoft 365 준수 센터의 핵심 eDiscovery 사례에 대 한 전환 검색 및 보존에 대 한 일반적인 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="26d55-105">Because there are many different scenarios, this article provides general guidance to transition searches and holds to a core eDiscovery case in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="26d55-106">EDiscovery 사례를 사용 하는 것은 항상 필요한 것은 아니지만 조직의 eDiscovery 사례에 액세스할 수 있는 사람을 제어 하기 위해 사용 권한을 할당할 수 있도록 하 여 추가 보안 계층을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="26d55-106">Using eDiscovery cases aren't always required, but they add an extra layer of security by letting you assign permissions to control who has access to the eDiscovery cases in your organization.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="26d55-107">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="26d55-107">Before you begin</span></span>

- <span data-ttu-id="26d55-108">이 문서에서 설명 하는 PowerShell 명령을 실행 하려면 보안 & 준수 센터에서 eDiscovery 관리자 역할 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26d55-108">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center to run the PowerShell commands described in this article.</span></span> <span data-ttu-id="26d55-109">또한 Exchange 관리 센터에서 Discovery Management 역할 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26d55-109">You also have to be a member of the Discovery Management role group in the Exchange admin center.</span></span>

- <span data-ttu-id="26d55-110">이 문서에서는 eDiscovery 보존을 만드는 방법에 대 한 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="26d55-110">This article provides guidance on how to create an eDiscovery hold.</span></span> <span data-ttu-id="26d55-111">비동기 프로세스를 통해 사서함에 보존 정책이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="26d55-111">The hold policy will be applied to mailboxes through an asynchronous process.</span></span> <span data-ttu-id="26d55-112">EDiscovery 보류를 만들 때 New-caseholdpolicy 및 New-caseholdrule를 모두 만들어야 하며 그렇지 않으면 보류가 만들어지지 않으며 콘텐츠 위치가 보류 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="26d55-112">When creating an eDiscovery hold, you must create both a CaseHoldPolicy and CaseHoldRule, otherwise the hold will not be created and content locations will not be placed on hold.</span></span>

## <a name="step-1-connect-to-exchange-online-powershell-and-security--compliance-center-powershell"></a><span data-ttu-id="26d55-113">1 단계: Exchange Online PowerShell 및 보안 & 준수 센터 PowerShell에 연결</span><span class="sxs-lookup"><span data-stu-id="26d55-113">Step 1: Connect to Exchange Online PowerShell and Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="26d55-114">첫 번째 단계는 Exchange Online PowerShell 및 Security & 준수 센터 PowerShell에 연결 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="26d55-114">The first step is to connect to Exchange Online PowerShell and Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="26d55-115">다음 스크립트를 복사 하 여 PowerShell 창에 붙여 넣은 다음 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26d55-115">You can copy the following script, paste it into a PowerShell window and then run it.</span></span> <span data-ttu-id="26d55-116">연결 하려는 조직의 자격 증명을 입력 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="26d55-116">You'll be prompted for credentials for the organization that you want to connect to.</span></span> 

```powershell
$UserCredential = Get-Credential
$sccSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection
Import-PSSession $sccSession -DisableNameChecking
$exoSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
Import-PSSession $exoSession -AllowClobber -DisableNameChecking
```

<span data-ttu-id="26d55-117">이 PowerShell 세션에서는 다음 단계에서 명령을 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26d55-117">You need to run the commands in the following steps in this PowerShell session.</span></span>

## <a name="step-2-get-a-list-of-in-place-ediscovery-searches-by-using-get-mailboxsearch"></a><span data-ttu-id="26d55-118">2 단계: New-mailboxsearch을 사용 하 여 원본 위치 eDiscovery 검색 목록 가져오기</span><span class="sxs-lookup"><span data-stu-id="26d55-118">Step 2: Get a list of In-Place eDiscovery searches by using Get-MailboxSearch</span></span>

<span data-ttu-id="26d55-119">인증을 받은 후 **new-mailboxsearch** cmdlet을 실행 하 여 원본 위치 eDiscovery 검색 목록을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26d55-119">After you've authenticated, you can get a list of In-Place eDiscovery searches by running the **Get-MailboxSearch** cmdlet.</span></span> <span data-ttu-id="26d55-120">다음 명령을 복사 하 여 PowerShell에 붙여 넣은 다음 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="26d55-120">Copy and paste the following command into PowerShell and then run it.</span></span> <span data-ttu-id="26d55-121">검색 목록과 이름이 함께 나열 되 고 원본 위치 유지 상태가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="26d55-121">A list of searches will be listed with their names and the status of any In-Place Holds.</span></span>

```powershell
Get-MailboxSearch
```

<span data-ttu-id="26d55-122">Cmdlet 출력은 다음과 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="26d55-122">The cmdlet output will be similar to the following:</span></span>

![PowerShell 예제 New-mailboxsearch](../media/MigrateLegacyeDiscovery1.png)

## <a name="step-3-get-information-about-the-in-place-ediscovery-searches-and-in-place-holds-you-want-to-migrate"></a><span data-ttu-id="26d55-124">3 단계: 마이그레이션할 원본 위치 eDiscovery 검색 및 현재 위치 유지에 대 한 정보 가져오기</span><span class="sxs-lookup"><span data-stu-id="26d55-124">Step 3: Get information about the In-Place eDiscovery searches and In-Place Holds you want to migrate</span></span>

<span data-ttu-id="26d55-125">이번에는 **new-mailboxsearch** cmdlet을 사용 하지만 이번에는 검색의 속성을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="26d55-125">Again you will use the **Get-MailboxSearch** cmdlet, but this time to get the properties of the search.</span></span> <span data-ttu-id="26d55-126">이러한 속성을 변수에 저장 하 여 나중에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26d55-126">You can store these properties in a variable for use later.</span></span> <span data-ttu-id="26d55-127">다음은 **new-mailboxsearch** cmdlet의 결과를 변수에 저장 한 후 검색 속성을 표시 하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="26d55-127">The following example stores the results of the **Get-MailboxSearch** cmdlet in a variable and then displays the properties of the search.</span></span>

```powershell
$search = Get-MailboxSearch -Identity "Search 1"
```

```powershell
$search | FL
```

<span data-ttu-id="26d55-128">이러한 두 명령 출력은 다음과 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="26d55-128">The output of these two commands will be similar to the following:</span></span>

![개별 검색에 대해 New-mailboxsearch를 사용 하는 경우의 PowerShell 출력 예제](../media/MigrateLegacyeDiscovery2.png)

> [!NOTE]
> <span data-ttu-id="26d55-130">이 예의 원본 위치 유지 기간은 무제한입니다 (*ItemHoldPeriod: 제한 없음*).</span><span class="sxs-lookup"><span data-stu-id="26d55-130">The duration of the In-Place Hold in this example is indefinite (*ItemHoldPeriod: Unlimited*).</span></span> <span data-ttu-id="26d55-131">이는 eDiscovery 및 법적 조사 시나리오에서 일반적으로 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="26d55-131">This is typical for eDiscovery and legal investigation scenarios.</span></span> <span data-ttu-id="26d55-132">보류 기간이 무기한 값과 다른 경우 보존 시나리오에서 콘텐츠를 보존 하기 위해 보류가 사용 되 고 있기 때문일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26d55-132">If the hold duration has is different value than indefinite, the reason is likely because the hold is being used to retain content in a retention scenario.</span></span> <span data-ttu-id="26d55-133">보존 시나리오의 경우 Security & 준수 센터 PowerShell에서 eDiscovery cmdlet을 사용 하는 대신 [new-retentioncompliancepolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-retentioncompliancepolicy) 및 [new-retentioncompliancerule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-retentioncompliancerule) 을 사용 하 여 콘텐츠를 보존 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="26d55-133">Instead of using the eDiscovery cmdlets in Security & Compliance Center PowerShell for retention scenarios, we recommend that you use [New-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-retentioncompliancepolicy) and [New-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-retentioncompliancerule) to retain content.</span></span> <span data-ttu-id="26d55-134">이러한 cmdlet을 사용 하는 경우에는 **new-caseholdpolicy** 및 **new-caseholdrule**를 사용 하는 것과 유사 하지만 보존 기간 및 보존 기간이 만료 된 후에 콘텐츠를 삭제 하는 것과 같은 유지 작업을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26d55-134">The result of using these cmdlets will be similar to using **New-CaseHoldPolicy** and **New-CaseHoldRule**, but you'll able to specify a retention period and a retention action, such as deleting content after the retention period expires.</span></span> <span data-ttu-id="26d55-135">또한 보존 cmdlet을 사용 하는 경우에는 보존 보류와 eDiscovery 사례를 연결할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="26d55-135">Also, using the retention cmdlets don't require you to associate the retention holds with an eDiscovery case.</span></span>

## <a name="step-4-create-a-case-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="26d55-136">4 단계: Microsoft 365 준수 센터에서 사례 만들기</span><span class="sxs-lookup"><span data-stu-id="26d55-136">Step 4: Create a case in the Microsoft 365 Compliance center</span></span>

<span data-ttu-id="26d55-137">EDiscovery 보류를 만들려면 보류를 연결 하는 eDiscovery 사례를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26d55-137">To create an eDiscovery hold, you have to create an eDiscovery case to associate the hold with.</span></span> <span data-ttu-id="26d55-138">다음 예제에서는 선택한 이름을 사용 하 여 eDiscovery 사례를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="26d55-138">The following example creates an eDiscovery case using a name of your choice.</span></span> <span data-ttu-id="26d55-139">나중에 사용할 수 있도록 새 사례의 속성을 변수에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="26d55-139">We will store the properties of the new case in a variable for use later.</span></span> <span data-ttu-id="26d55-140">사례를 만든 후에 `$case | FL` 명령을 실행 하 여 이러한 속성을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26d55-140">You can view those properties by running the `$case | FL` command after you create the case.</span></span>

```powershell
$case = New-ComplianceCase -Name "[Case name of your choice]"
```
![Remove-compliancecase 명령을 실행 하는 예제](../media/MigrateLegacyeDiscovery3.png)

## <a name="step-5-create-the-ediscovery-hold"></a><span data-ttu-id="26d55-142">5 단계: eDiscovery 보류 만들기</span><span class="sxs-lookup"><span data-stu-id="26d55-142">Step 5: Create the eDiscovery hold</span></span>

<span data-ttu-id="26d55-143">사례를 만든 후에는 보류를 만들어 이전 단계에서 만든 사례와 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26d55-143">After the case is created, you can create the hold and associate it with the case that you created in the previous step.</span></span> <span data-ttu-id="26d55-144">케이스 보류 정책과 케이스 보류 규칙을 모두 만들어야 한다는 점에 유의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26d55-144">It's important to remember that you must create both a case hold policy and a case hold rule.</span></span> <span data-ttu-id="26d55-145">사례 보류 정책을 만든 후에 서비스 케이스 보류 규칙을 만들지 않으면 eDiscovery 보류가 만들어지지 않고 콘텐츠가 보류 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="26d55-145">If the case hold rule isn't created after you created case hold policy, the eDiscovery hold will not be created and any content won't be placed on hold.</span></span>

<span data-ttu-id="26d55-146">다음 명령을 실행 하 여 마이그레이션할 eDiscovery 보존을 다시 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="26d55-146">Run the following commands to re-create the eDiscovery hold that you want to migrate.</span></span> <span data-ttu-id="26d55-147">다음 예제에서는 마이그레이션하려는 3 단계의 원본 위치 유지에 대 한 속성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="26d55-147">These examples use the properties from In-Place Hold from Step 3 that you want to migrate.</span></span> <span data-ttu-id="26d55-148">첫 번째 명령은 새 케이스 보류 정책을 만들고 속성을 변수에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="26d55-148">The first command creates a new case hold policy and saves the properties to a variable.</span></span> <span data-ttu-id="26d55-149">두 번째 명령은 해당 케이스 보류 규칙을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="26d55-149">The second command creates the corresponding case hold rule.</span></span>

```powershell
$policy = New-CaseHoldPolicy -Name $search.Name -Case $case.Identity -ExchangeLocation $search.SourceMailboxes
```

```powershell
New-CaseHoldRule -Name $search.Name -Policy $policy.Identity
```

![NewCaseHoldPolicy 및 NewCaseHoldRule cmdlet 사용 예제](../media/MigrateLegacyeDiscovery4.png)

## <a name="step-6-verify-the-ediscovery-hold"></a><span data-ttu-id="26d55-151">6 단계: eDiscovery 보류 확인</span><span class="sxs-lookup"><span data-stu-id="26d55-151">Step 6: Verify the eDiscovery hold</span></span>

<span data-ttu-id="26d55-152">보류를 만드는 데 문제가 없는지 확인 하려면 배포 상태가 성공 인지 확인 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="26d55-152">To make sure there were no issues in creating the hold, it's good to check that the hold distribution status is successful.</span></span> <span data-ttu-id="26d55-153">배포는 이전 단계의 *ExchangeLocation* 매개 변수에 지정 된 모든 콘텐츠 위치에 보류가 적용 되었음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="26d55-153">Distribution means that the hold has been applied to all the content locations specified in the *ExchangeLocation* parameter in the previous step.</span></span> <span data-ttu-id="26d55-154">이 작업을 수행 하려면 **new-caseholdpolicy** cmdlet을 실행 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="26d55-154">To do this, you can run the **Get-CaseHoldPolicy** cmdlet.</span></span> <span data-ttu-id="26d55-155">이전 단계에서 만든 *$policy* 변수에 저장 된 속성은 변수에 자동으로 업데이트 되지 않으므로 cmdlet을 다시 실행 하 여 배포가 정상적으로 작동 하는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26d55-155">Because the properties saved to the *$policy* variable that you created in the previous step aren't automatically updated in the variable, you need to rerun the cmdlet to verify that distribution is successful.</span></span> <span data-ttu-id="26d55-156">케이스 보류 정책을 성공적으로 배포 하려면 5 분에서 24 시간까지 소요 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26d55-156">It can take between 5 minutes and 24 hours for case hold policies to be successfully distributed.</span></span>

<span data-ttu-id="26d55-157">다음 명령을 실행 하 여 eDiscovery 보류가 성공적으로 배포 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="26d55-157">Run the following command to verify that the eDiscovery hold has been successfully distributed.</span></span>

```powershell
Get-CaseHoldPolicy -Identity $policy.Identity | Select name, DistributionStatus
```

<span data-ttu-id="26d55-158">*DistributionStatus* 속성의 **성공** 값은 해당 보류가 콘텐츠 위치에 성공적으로 설정 되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="26d55-158">The value of **Success** for the *DistributionStatus* property indicates the hold was successfully placed on the content locations.</span></span> <span data-ttu-id="26d55-159">배포가 아직 완료 되지 않은 경우 **보류** 중 값이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="26d55-159">If the distribution is not yet complete, a value of **Pending** is displayed.</span></span>

![PowerShell Get-New-caseholdpolicy 예제](../media/MigrateLegacyeDiscovery5.png)

## <a name="step-7-create-the-search"></a><span data-ttu-id="26d55-161">7 단계: 검색 만들기</span><span class="sxs-lookup"><span data-stu-id="26d55-161">Step 7: Create the search</span></span>

<span data-ttu-id="26d55-162">마지막 단계는 3 단계에서 식별 한 검색을 다시 만들고 사례와 연결 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="26d55-162">The last step is to re-create the search that you identified in Step 3 and associate it with the case.</span></span> <span data-ttu-id="26d55-163">검색을 만든 후에는 **ComplianceSearch** cmdlet을 사용 하거나 나중에 실행 해 서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26d55-163">After you create the search, you can run it by using the **Start-ComplianceSearch** cmdlet or run at a later time.</span></span>

```powershell
New-ComplianceSearch -Name $search.Name -ExchangeLocation $search.SourceMailboxes -ContentMatchQuery $search.SearchQuery -Case $case.name
```

![PowerShell 새 ComplianceSearch 예제](../media/MigrateLegacyeDiscovery6.png)

## <a name="step-8-verify-the-case-hold-and-search-in-the-microsoft-365-compliance-center"></a><span data-ttu-id="26d55-165">8 단계: Microsoft 365 준수 센터의 사례, 보류 및 검색 확인</span><span class="sxs-lookup"><span data-stu-id="26d55-165">Step 8: Verify the case, hold, and search in the Microsoft 365 compliance center</span></span>

<span data-ttu-id="26d55-166">모든 기능이 제대로 설정 되었는지 확인 하려면 Microsoft 365 준수 센터로 [https://compliance.microsoft.com](https://compliance.microsoft.com)이동 하 여 **eDiscovery > Core**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="26d55-166">To make sure that everything is set up correctly, go to the Microsoft 365 compliance center at [https://compliance.microsoft.com](https://compliance.microsoft.com), and click **eDiscovery > Core**.</span></span>

![Microsoft 365 준수 센터 eDiscovery](../media/MigrateLegacyeDiscovery7.png)

<span data-ttu-id="26d55-168">3 단계에서 만든 사례가 **핵심 eDiscovery** 페이지에 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="26d55-168">The case that you created in Step 3 is listed on the **Core eDiscovery** page.</span></span> <span data-ttu-id="26d55-169">사례를 연 다음 4 단계에서 **만든 보류가 보류 탭에** 표시 되는지 확인 합니다. 보류를 클릭 하 여 보존을 적용 한 사서함 수와 배포 상태를 비롯 하 여 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26d55-169">Open the case and then notice the hold that you created in Step 4 in listed on the **Holds** tab. You can click the hold to see details, including the number of mailboxes the hold is applied to and the distribution status.</span></span>

![Microsoft 365 준수 센터의 eDiscovery 보류](../media/MigrateLegacyeDiscovery8.png)

<span data-ttu-id="26d55-171">7 단계에서 만든 검색이 eDiscovery 사례의 **검색** 탭에 나열 된 대로 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26d55-171">The search that you created in Step 7 is listed on the listed on the **Searches** tab of the eDiscovery case.</span></span>

![Microsoft 365 준수 센터의 eDiscovery 사례 검색](../media/MigrateLegacyeDiscovery9.png)

<span data-ttu-id="26d55-173">원본 위치 eDiscovery 검색을 마이그레이션하는 경우 eDiscovery 사례와 연결 하지 않으면 Microsoft 365 준수 센터의 콘텐츠 검색 페이지에 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="26d55-173">If you migrate an In-Place eDiscovery search but don't associate it with an eDiscovery case, it will be listed on the Content search page in the Microsoft 365 compliance center.</span></span>

## <a name="more-information"></a><span data-ttu-id="26d55-174">추가 정보</span><span class="sxs-lookup"><span data-stu-id="26d55-174">More information</span></span>

- <span data-ttu-id="26d55-175">Exchange 관리 센터의 원본 위치 eDiscovery & 보류에 대 한 자세한 내용은 다음 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="26d55-175">For more information about In-Place eDiscovery & Holds in the Exchange admin center, see:</span></span>
  
  - [<span data-ttu-id="26d55-176">원본 위치 eDiscovery</span><span class="sxs-lookup"><span data-stu-id="26d55-176">In-Place eDiscovery</span></span>](https://docs.microsoft.com/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery)

  - [<span data-ttu-id="26d55-177">원본 위치 유지 및 소송 보존</span><span class="sxs-lookup"><span data-stu-id="26d55-177">In-Place Hold and Litigation Hold</span></span>](https://docs.microsoft.com/exchange/security-and-compliance/in-place-and-litigation-holds)

- <span data-ttu-id="26d55-178">문서에 사용 된 PowerShell cmdlet에 대 한 자세한 내용은 다음 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="26d55-178">For more information about the PowerShell cmdlets used in the article, see:</span></span>

  - [<span data-ttu-id="26d55-179">New-mailboxsearch</span><span class="sxs-lookup"><span data-stu-id="26d55-179">Get-MailboxSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-mailboxsearch)
  
  - [<span data-ttu-id="26d55-180">Remove-compliancecase</span><span class="sxs-lookup"><span data-stu-id="26d55-180">New-ComplianceCase</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/new-compliancecase)

  - [<span data-ttu-id="26d55-181">New-caseholdpolicy</span><span class="sxs-lookup"><span data-stu-id="26d55-181">New-CaseHoldPolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/new-caseholdpolicy)
  
  - [<span data-ttu-id="26d55-182">New-caseholdrule</span><span class="sxs-lookup"><span data-stu-id="26d55-182">New-CaseHoldRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/new-caseholdrule)

  - [<span data-ttu-id="26d55-183">New-caseholdpolicy</span><span class="sxs-lookup"><span data-stu-id="26d55-183">Get-CaseHoldPolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-caseholdpolicy)
  
  - [<span data-ttu-id="26d55-184">New-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="26d55-184">New-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-compliancesearch)

  - [<span data-ttu-id="26d55-185">Start-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="26d55-185">Start-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/start-compliancesearch)

- <span data-ttu-id="26d55-186">Microsoft 365 준수 센터에 대 한 자세한 내용은 [microsoft 365 준수 센터 개요](microsoft-365-compliance-center.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="26d55-186">For more information about the Microsoft 365 compliance center, see [Overview of the Microsoft 365 compliance center](microsoft-365-compliance-center.md).</span></span>
