---
title: 감사 켜기 또는 끄기
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
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: e893b19a-660c-41f2-9074-d3631c95a014
ms.custom: seo-marvel-apr2020
description: 관리자의 감사 로그 검색 기능을 설정하거나 해제하여 Microsoft 365 규정 준수 센터 감사 로그를 검색할 수 있는 기능을 활성화 또는 비활성화하는 방법
ms.openlocfilehash: dd39b883036ce6060aef71c6a927c03f391d827f
ms.sourcegitcommit: 5db5047c24b56f3af90c2bc5c830a7a13eeeccad
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2021
ms.locfileid: "53341499"
---
# <a name="turn-auditing-on-or-off"></a><span data-ttu-id="ef359-103">감사 켜기 또는 끄기</span><span class="sxs-lookup"><span data-stu-id="ef359-103">Turn auditing on or off</span></span>

<span data-ttu-id="ef359-104">Microsoft 365 및 Office 365 엔터프라이즈 조직에서는 기본적으로 감사 로그 검색이 켜져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef359-104">Audit logging is turned on by default for Microsoft 365 and Office 365 enterprise organizations.</span></span> <span data-ttu-id="ef359-105">조직에서 감사를 Microsoft 365 규정 준수 센터 조직의 사용자 및 관리자 활동이 감사 로그에 기록되고 90일 동안 보존되고 사용자에게 할당된 라이선스에 따라 최대 1년 동안 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef359-105">When auditing in the Microsoft 365 compliance center is turned on, user and admin activity from your organization is recorded in the audit log and retained for 90 days, and up to one year depending on the license assigned to users.</span></span> <span data-ttu-id="ef359-106">그러나 조직에 감사 로그 데이터를 기록하고 보존하지 않을 이유가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef359-106">However, your organization may have reasons for not wanting to record and retain audit log data.</span></span> <span data-ttu-id="ef359-107">이러한 경우 전역 관리자는 전역 관리자의 감사를 해제할 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ef359-107">In those cases, a global admin may decide to turn off auditing in Microsoft 365.</span></span>

<span data-ttu-id="ef359-108">조직에서 새 Microsoft 365 Office 365 조직의 감사 상태를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef359-108">When setting up a new Microsoft 365 or Office 365 organization, you can verify the auditing status for your organization.</span></span> <span data-ttu-id="ef359-109">자세한 내용은 이 문서의 [조직에](#verify-the-auditing-status-for-your-organization) 대한 감사 상태 확인 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ef359-109">For instructions, see the [Verify the auditing status for your organization](#verify-the-auditing-status-for-your-organization) section in this article.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ef359-110">조직에서 감사를 Microsoft 365 경우 Office 365 관리 활동 API 또는 Azure Sentinel을 사용하여 조직의 감사 데이터에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ef359-110">If you turn off auditing in Microsoft 365, you can't use the Office 365 Management Activity API or Azure Sentinel to access auditing data for your organization.</span></span> <span data-ttu-id="ef359-111">이 문서의 단계를 수행하여 감사를 끄면 감사 로그를 사용하여 감사 로그를 검색하거나 Microsoft 365 규정 준수 센터 PowerShell에서 **Search-UnifiedAuditLog** cmdlet을 실행할 때 결과가 Exchange Online 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ef359-111">Turning off auditing by following the steps in this article means that no results will be returned when you search the audit log using the Microsoft 365 compliance center or when you run the **Search-UnifiedAuditLog** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="ef359-112">이는 또한 관리 활동 API 또는 Azure Sentinel을 통해 감사 Office 365 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ef359-112">This also means that audit logs won't be available through the Office 365 Management Activity API or Azure Sentinel.</span></span>
  
## <a name="before-you-turn-auditing-on-or-off"></a><span data-ttu-id="ef359-113">감사를 켜거나 끄기 전에</span><span class="sxs-lookup"><span data-stu-id="ef359-113">Before you turn auditing on or off</span></span>

- <span data-ttu-id="ef359-114">조직에서 감사를 설정하거나 해제하려면 Exchange Online 감사 로그 역할이 Microsoft 365 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef359-114">You have to be assigned the Audit Logs role in Exchange Online to turn auditing on or off in your Microsoft 365 organization.</span></span> <span data-ttu-id="ef359-115">기본적으로 이 역할은 Exchange 관리 센터의 사용 권한  페이지에서 준수 관리 및 조직 관리 역할 그룹에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef359-115">By default, this role is assigned to the Compliance Management and Organization Management role groups on the **Permissions** page in the Exchange admin center.</span></span> <span data-ttu-id="ef359-116">조직의 전역 Microsoft 365 조직 관리 역할 그룹의 구성원입니다Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ef359-116">Global admins in Microsoft 365 are members of the Organization Management role group in Exchange Online.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ef359-117">감사를 설정하거나 해제하려면 사용자에게 Exchange Online 권한을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef359-117">Users have to be assigned permissions in Exchange Online to turn auditing on or off.</span></span> <span data-ttu-id="ef359-118">권한 페이지의 권한 페이지에서 사용자에게 감사  로그 역할을 Microsoft 365 규정 준수 센터 감사를 설정하거나 해제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ef359-118">If you assign users the Audit Logs role on the **Permissions** page in the Microsoft 365 compliance center, they won't be able to turn auditing on or off.</span></span> <span data-ttu-id="ef359-119">이는 PowerShell cmdlet의 Exchange Online cmdlet이기 때문에입니다.</span><span class="sxs-lookup"><span data-stu-id="ef359-119">This is because the underlying cmdlet is an Exchange Online PowerShell cmdlet.</span></span>

- <span data-ttu-id="ef359-120">감사 로그 검색에 대한 단계별 지침은 감사 로그 [검색을 참조하세요.](search-the-audit-log-in-security-and-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="ef359-120">For step-by-step instructions on searching the audit log, see [Search the audit log](search-the-audit-log-in-security-and-compliance.md).</span></span> <span data-ttu-id="ef359-121">관리 활동 API의 Microsoft 365 자세한 내용은 Microsoft 365 관리 API [시작을 참조하세요.](/office/office-365-management-api/get-started-with-office-365-management-apis)</span><span class="sxs-lookup"><span data-stu-id="ef359-121">For more information about the Microsoft 365 Management Activity API, see [Get started with Microsoft 365 Management APIs](/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span>

## <a name="verify-the-auditing-status-for-your-organization"></a><span data-ttu-id="ef359-122">조직의 감사 상태 확인</span><span class="sxs-lookup"><span data-stu-id="ef359-122">Verify the auditing status for your organization</span></span>

<span data-ttu-id="ef359-123">조직에 대한 감사가 설정되어 있는지 확인하기 위해 [PowerShell에서](/powershell/exchange/connect-to-exchange-online-powershell)다음 명령을 Exchange Online 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef359-123">To verify that auditing is turned on for your organization, you can run the following command in [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell):</span></span>

```powershell
Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
```

<span data-ttu-id="ef359-124">`True` _UnifiedAuditLogIngestionEnabled_ 속성의 값은 감사가 켜져 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ef359-124">A value of `True` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that auditing is turned on.</span></span> <span data-ttu-id="ef359-125">값은 `False` 감사가 켜져 있지 않다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ef359-125">A value of `False` indicates that auditing is not turned on.</span></span>

## <a name="turn-on-auditing"></a><span data-ttu-id="ef359-126">감사 켜기</span><span class="sxs-lookup"><span data-stu-id="ef359-126">Turn on auditing</span></span>

<span data-ttu-id="ef359-127">조직에 대한 감사가 설정되어 있지 않은 경우 조직에서 또는 PowerShell을 사용하여 Microsoft 365 규정 준수 센터 수 Exchange Online 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef359-127">If auditing is not turned on for your organization, you can turn it on in the Microsoft 365 compliance center or by using Exchange Online PowerShell.</span></span> <span data-ttu-id="ef359-128">감사 로그를 검색할 때 결과를 반환하려면 감사를 설정한 후 몇 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef359-128">It may take several hours after you turn on auditing before you can return results when you search the audit log.</span></span>
  
### <a name="use-the-compliance-center-to-turn-on-auditing"></a><span data-ttu-id="ef359-129">준수 센터를 사용하여 감사 켜기</span><span class="sxs-lookup"><span data-stu-id="ef359-129">Use the compliance center to turn on auditing</span></span>

1. <span data-ttu-id="ef359-130"><https://compliance.microsoft.com>으로 이동하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="ef359-130">Go to <https://compliance.microsoft.com> and sign in.</span></span>

2. <span data-ttu-id="ef359-131">창의 왼쪽 탐색 창에서 Microsoft 365 규정 준수 센터 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="ef359-131">In the left navigation pane of the Microsoft 365 compliance center, click **Audit**.</span></span>

   <span data-ttu-id="ef359-132">조직에 대한 감사가 설정되어 있지 않은 경우 사용자 및 관리자 활동 기록을 시작하라는 배너가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef359-132">If auditing is not turned on for your organization, a banner is displayed prompting you start recording user and admin activity.</span></span>

   ![감사 페이지의 배너](../media/AuditingBanner.png)

3. <span data-ttu-id="ef359-134">사용자 **및 관리자 활동 기록 시작 배너를** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ef359-134">Click the **Start recording user and admin activity** banner.</span></span>

   <span data-ttu-id="ef359-135">변경을 적용하는 데 최대 60분이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef359-135">It may take up to 60 minutes for the change to take effect.</span></span>

### <a name="use-powershell-to-turn-on-auditing"></a><span data-ttu-id="ef359-136">PowerShell을 사용하여 감사 켜기</span><span class="sxs-lookup"><span data-stu-id="ef359-136">Use PowerShell to turn on auditing</span></span>

1. <span data-ttu-id="ef359-137">[Exchange Online PowerShell에 연결합니다](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="ef359-137">[Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="ef359-138">다음 PowerShell 명령을 실행하여 감사를 켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef359-138">Run the following PowerShell command to turn on auditing.</span></span>

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    <span data-ttu-id="ef359-139">변경이 적용되는 데 최대 60분이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef359-139">A message is displayed saying that it may take up to 60 minutes for the change to take effect.</span></span>
  
## <a name="turn-off-auditing"></a><span data-ttu-id="ef359-140">감사 끄기</span><span class="sxs-lookup"><span data-stu-id="ef359-140">Turn off auditing</span></span>

<span data-ttu-id="ef359-141">감사를 Exchange Online PowerShell을 사용하여 감사를 해제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef359-141">You have to use Exchange Online PowerShell to turn off auditing.</span></span>
  
1. <span data-ttu-id="ef359-142">[Exchange Online PowerShell에 연결합니다](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="ef359-142">[Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="ef359-143">다음 PowerShell 명령을 실행하여 감사를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="ef359-143">Run the following PowerShell command to turn off auditing.</span></span>

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. <span data-ttu-id="ef359-144">잠시 후 감사가 꺼져 있는지(사용 안 하게) 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef359-144">After a while, verify that auditing is turned off (disabled).</span></span> <span data-ttu-id="ef359-145">이 작업을 수행하는 방법은 다음 두 가지입니다.</span><span class="sxs-lookup"><span data-stu-id="ef359-145">There are two ways to do this:</span></span>

    - <span data-ttu-id="ef359-146">PowerShell Exchange Online 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ef359-146">In Exchange Online PowerShell, run the following command:</span></span>

      ```powershell
      Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
      ```

      <span data-ttu-id="ef359-147">`False` _UnifiedAuditLogIngestionEnabled_ 속성의 값은 감사가 해제되어 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ef359-147">The value of  `False` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that auditing is turned off.</span></span>

    - <span data-ttu-id="ef359-148">에서 **감사** 페이지로 Microsoft 365 규정 준수 센터.</span><span class="sxs-lookup"><span data-stu-id="ef359-148">Go to the **Audit** page in the Microsoft 365 compliance center.</span></span>

      <span data-ttu-id="ef359-149">조직에 대한 감사가 설정되어 있지 않은 경우 사용자 및 관리자 활동 기록을 시작하라는 배너가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef359-149">If auditing is not turned on for your organization, a banner is displayed prompting you start recording user and admin activity.</span></span>
