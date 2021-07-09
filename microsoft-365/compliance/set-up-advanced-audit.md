---
title: 2013에서 고급 감사 Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-audit
- m365initiative-compliance
- m365solution-scenario
search.appverid:
- MOE150
- MET150
description: 이 문서에서는 사용자 계정이 손상된 경우 포렌식 조사를 수행하거나 기타 보안 관련 인시던트에 대한 조사를 수행할 수 있도록 고급 감사를 설정하는 방법을 설명합니다.
ms.openlocfilehash: 825dadee5260a263d005eb3a37f280381f9425a2
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339229"
---
# <a name="set-up-advanced-audit-in-microsoft-365"></a><span data-ttu-id="98b2f-103">2013에서 고급 감사 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="98b2f-103">Set up Advanced Audit in Microsoft 365</span></span>

<span data-ttu-id="98b2f-104">조직에 고급 감사를 지원하는 구독 및 최종 사용자 라이선스가 있는 경우 다음 단계를 수행하여 고급 감사의 추가 기능을 설정하고 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="98b2f-104">If your organization has a subscription and end user licensing that supports Advanced Audit, perform the following steps to set up and use the additional capabilities in Advanced Audit.</span></span>

![고급 감사 설정 워크플로](../media/AdvancedAuditWorkflow.png)

## <a name="step-1-set-up-advanced-audit-for-users"></a><span data-ttu-id="98b2f-106">1단계: 사용자에 대한 고급 감사 설정</span><span class="sxs-lookup"><span data-stu-id="98b2f-106">Step 1: Set up Advanced Audit for users</span></span>

<span data-ttu-id="98b2f-107">MailItemsAccessed 및 전송과 같은 중요한 이벤트를 기록하는 기능과 같은 고급 감사 기능을 사용하려면 적절한 E5 라이선스가 사용자에게 할당되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98b2f-107">Advanced Audit features such as the ability to log crucial events such as MailItemsAccessed and Send require an appropriate E5 license assigned to users.</span></span> <span data-ttu-id="98b2f-108">또한 이러한 사용자에 대해 고급 감사 앱/서비스 계획을 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98b2f-108">Additionally, the Advanced Auditing app/service plan must be enabled for those users.</span></span> <span data-ttu-id="98b2f-109">고급 감사 앱이 사용자에게 할당되었는지 확인하려면 각 사용자에 대해 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="98b2f-109">To verify that the Advanced Auditing app is assigned to users, perform the following steps for each user:</span></span>

1. <span data-ttu-id="98b2f-110">[Microsoft 365 관리 센터](https://admin.microsoft.com/Adminportal)에서 **사용자** > **활성 사용자** 로 이동하여 라이선스를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="98b2f-110">In the [Microsoft 365 admin center](https://admin.microsoft.com/Adminportal), go to **Users** > **Active users**, and select a user.</span></span>

2. <span data-ttu-id="98b2f-111">사용자 속성 플라이아웃 페이지에서 **라이선스 및 앱** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="98b2f-111">On the user properties flyout page, click **Licenses and apps**.</span></span>

3. <span data-ttu-id="98b2f-112">라이선스 **섹션에서** 사용자에게 E5 라이선스가 할당되어 있는지 또는 적절한 추가 기능 라이선스가 할당되어 있는지를 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98b2f-112">In the **Licenses** section, verify that the user is assigned an E5 license or is assigned an appropriate add-on license.</span></span> <span data-ttu-id="98b2f-113">고급 감사를 지원하는 라이선스 목록은 고급 감사 라이선스 요구 [사항을 참조하세요.](auditing-solutions-overview.md#advanced-audit-1)</span><span class="sxs-lookup"><span data-stu-id="98b2f-113">For a list of licenses that support Advanced Audit, see [Advanced Audit licensing requirements](auditing-solutions-overview.md#advanced-audit-1).</span></span>

4. <span data-ttu-id="98b2f-114">**앱** 구역을 확장하고 **Microsoft 365 고급 감사** 확인란이 선택되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="98b2f-114">Expand the **Apps** section, and verify that the **Microsoft 365 Advanced Auditing** checkbox is selected.</span></span>

5. <span data-ttu-id="98b2f-115">확인란을 선택하지 않은 경우 해당 확인란을 선택한 다음 변경 내용 **저장을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="98b2f-115">If the checkbox isn't selected, select it, and then click **Save changes.**</span></span>

   <span data-ttu-id="98b2f-116">MailItemsAccessed 및 Send에 대한 감사 레코드 로깅은 24시간 이내에 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="98b2f-116">The logging of audit records for MailItemsAccessed and Send will begin within 24 hours.</span></span> <span data-ttu-id="98b2f-117">SearchQueryInitiatedExchange 및 SearchQueryInitiatedSharePoint의 두 가지 고급 감사 중요 이벤트 로깅을 시작하기 위해 3단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98b2f-117">You have to perform Step 3 to start logging of two other Advanced Audit crucial events: SearchQueryInitiatedExchange and SearchQueryInitiatedSharePoint.</span></span>

<span data-ttu-id="98b2f-118">그룹 기반 라이선스를 사용하여 사용자 그룹에 라이선스를 할당하는 조직의 경우 그룹의 Microsoft 365 고급 감사에 대한 라이선스 할당을 해제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98b2f-118">For organizations that assign licenses to groups of users by using group-based licensing, you have to turn off the licensing assignment for Microsoft 365 Advanced Auditing for the group.</span></span> <span data-ttu-id="98b2f-119">변경 내용을 저장한 후에는 그룹에 대해 Microsoft 365 고급 감사를 해제했는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="98b2f-119">After you save your changes, verify that Microsoft 365 Advanced Auditing is turned off for the group.</span></span> <span data-ttu-id="98b2f-120">그런 다음, 그룹에 대한 라이선스 할당을 다시 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="98b2f-120">Then turn the licensing assignment for the group back on.</span></span> <span data-ttu-id="98b2f-121">그룹 기반 라이선싱에 대한 자세한 내용은 [Azure Active Directory에서 그룹 구성원으로 사용자에게 라이선스 할당](/azure/active-directory/users-groups-roles/licensing-groups-assign)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="98b2f-121">For instructions about group-based licensing, see [Assign licenses to users by group membership in Azure Active Directory](/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>

<span data-ttu-id="98b2f-122">또한 사용자 사서함 또는 공유 사서함에 기록되는 사서함 작업을 사용자 지정한 경우 Microsoft에서 릴리스한 새 중요 이벤트는 해당 사서함에 대해 자동으로 감사되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="98b2f-122">Also, if you have customized the mailbox actions that are logged on user mailboxes or shared mailboxes, any new crucial events released by Microsoft will not be automatically audited on those mailboxes.</span></span> <span data-ttu-id="98b2f-123">각 로그온 유형에 대해 감사되는 사서함 작업을 변경하는 방법에 대한 자세한 내용은 [사서함 감사 관리](enable-mailbox-auditing.md#change-or-restore-mailbox-actions-logged-by-default)의 "기본적으로 로그되는 사서함 작업 변경 또는 복원" 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="98b2f-123">For information about changing the mailbox actions that are audited for each logon type, see the "Change or restore mailbox actions logged by default" section in [Manage mailbox auditing](enable-mailbox-auditing.md#change-or-restore-mailbox-actions-logged-by-default).</span></span>

## <a name="step-2-enable-crucial-events"></a><span data-ttu-id="98b2f-124">2단계: 중요한 이벤트 사용</span><span class="sxs-lookup"><span data-stu-id="98b2f-124">Step 2: Enable crucial events</span></span>

<span data-ttu-id="98b2f-125">사용자가 Exchange Online 및 SharePoint Online에서 검색을 수행할 때 두 가지 중요한 이벤트(SearchQueryInitiatedExchange 및 SearchQueryInitiatedSharePoint)를 기록하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98b2f-125">You have to enable two crucial events (SearchQueryInitiatedExchange and SearchQueryInitiatedSharePoint) to be logged when users perform searches in Exchange Online and SharePoint Online.</span></span> <span data-ttu-id="98b2f-126">사용자에 대해 이러한 두 이벤트를 감사할 수 있도록 설정하려면 [PowerShell에서](/powershell/exchange/connect-to-exchange-online-powershell)각 사용자에 대해 Exchange Online 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="98b2f-126">To enable these two events to be audited for users, run the following command (for each user) in [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell):</span></span>

```powershell
Set-Mailbox <user> -AuditOwner @{Add="SearchQueryInitiated"}
```

<span data-ttu-id="98b2f-127">다중 위치 환경에서는 사용자의 사서함이 있는 포리스트에서 이전 **Set-Mailbox** 명령을 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98b2f-127">In a multi-geo environment, you must run the previous **Set-Mailbox** command in the forest where the user's mailbox is located.</span></span> <span data-ttu-id="98b2f-128">사용자의 사서함 위치를 식별하기 위해 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="98b2f-128">To identify the user's mailbox location, run the following command:</span></span> 

```powershell
Get-Mailbox <user identity> | FL MailboxLocations
```

<span data-ttu-id="98b2f-129">검색 쿼리 감사를 사용하도록 설정하는 명령을 이전에 사용자 사서함이 있는 포리스트와 다른 포리스트에서 실행한 경우 실행하여 사용자 사서함에서 SearchQueryInitiated 값을 제거한 다음 사용자의 사서함이 있는 포리스트의 사용자 사서함에 추가해야 `Set-Mailbox -AuditOwner @{Remove="SearchQueryInitiated"}` 합니다.</span><span class="sxs-lookup"><span data-stu-id="98b2f-129">If the command to enable the auditing of search queries was previously run in a forest that's different than the one the user's mailbox is located in, then you must remove the SearchQueryInitiated value from the user's mailbox by running `Set-Mailbox -AuditOwner @{Remove="SearchQueryInitiated"}` and then add it to the user's mailbox in the forest where the user's mailbox is located.</span></span>

## <a name="step-3-set-up-audit-retention-policies"></a><span data-ttu-id="98b2f-130">3단계: 감사 보존 정책 설정</span><span class="sxs-lookup"><span data-stu-id="98b2f-130">Step 3: Set up audit retention policies</span></span>

<span data-ttu-id="98b2f-131">Exchange, SharePoint 및 Azure AD 감사 레코드를 1년 동안 유지하는 기본 정책에 더해 조직의 보안 작업, IT 및 규정 준수 팀의 요구 사항을 충족하는 추가 감사 로그 보존 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98b2f-131">In additional to the default policy that retains Exchange, SharePoint, and Azure AD audit records for one year, you can create additional audit log retention policies to meet the requirements of your organization's security operations, IT, and compliance teams.</span></span> <span data-ttu-id="98b2f-132">자세한 내용은 [감사 로그 보존 정책 관리](audit-log-retention-policies.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="98b2f-132">For more information, see [Manage audit log retention policies](audit-log-retention-policies.md).</span></span>

## <a name="step-4-search-for-crucial-events"></a><span data-ttu-id="98b2f-133">4단계: 중요한 이벤트 검색</span><span class="sxs-lookup"><span data-stu-id="98b2f-133">Step 4: Search for crucial events</span></span>

<span data-ttu-id="98b2f-134">이제 조직에 대해 고급 감사를 설정한 후, 포렌식 조사를 수행 할 때 중요한 이벤트 및 기타 활동을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98b2f-134">Now that you have Advanced Audit set up for your organization, you can search for crucial events and other activities when conducting forensic investigations.</span></span> <span data-ttu-id="98b2f-135">1단계 및 2단계를 완료한 후 감사 로그에서 손상된 계정 및 기타 유형의 보안 또는 규정 준수 조사를 포렌식으로 조사하는 동안 중요한 이벤트 및 기타 활동을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98b2f-135">After completing Step 1 and Step 2, you can search the audit log for crucial events and other activities during forensic investigations of compromised accounts and other types of security or compliance investigations.</span></span> <span data-ttu-id="98b2f-136">MailItemsAccessed 중요 이벤트를 사용하여 손상된 사용자 계정에 대한 포렌식 조사를 수행하는 데 대한 자세한 내용은 고급 감사를 사용하여 손상된 계정 조사를 [참조하세요.](mailitemsaccessed-forensics-investigations.md)</span><span class="sxs-lookup"><span data-stu-id="98b2f-136">For more information about conducting a forensics investigation of compromised user accounts by using the MailItemsAccessed crucial event, see [Use Advanced Audit to investigate compromised accounts](mailitemsaccessed-forensics-investigations.md).</span></span>
