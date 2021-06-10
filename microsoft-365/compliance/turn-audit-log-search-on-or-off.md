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
description: Microsoft 365 준수 센터에서 감사 로그 검색 기능을 켜거나 끄고 관리자가 감사 로그를 검색할 수 있도록 설정하거나 사용하지 않도록 설정하는 방법
ms.openlocfilehash: 457f453b001f71a095bc60932c8e0cebf46aa7b1
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706667"
---
# <a name="turn-auditing-on-or-off"></a><span data-ttu-id="1ff06-103">감사 켜기 또는 끄기</span><span class="sxs-lookup"><span data-stu-id="1ff06-103">Turn auditing on or off</span></span>

<span data-ttu-id="1ff06-104">Microsoft 365 및 Office 365 엔터프라이즈 조직에서는 기본적으로 감사 로그 검색이 켜져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ff06-104">Audit logging is turned on by default for Microsoft 365 and Office 365 enterprise organizations.</span></span> <span data-ttu-id="1ff06-105">여기에는 E3/G3 또는 E5/G5 구독이 있는 조직이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ff06-105">This includes organizations with E3/G3 or E5/G5 subscriptions.</span></span> <span data-ttu-id="1ff06-106">준수 센터의 감사가 켜져 있는 경우 조직의 사용자 및 관리자 활동이 감사 로그에 기록되고 90일 동안, 사용자에게 할당된 라이선스에 따라 최대 1년 동안 보존됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ff06-106">When auditing in the compliance center is turned on, user and admin activity from your organization is recorded in the audit log and retained for 90 days, and up to one year depending on the license assigned to users.</span></span> <span data-ttu-id="1ff06-107">그러나 조직에 감사 로그 데이터를 기록하고 보존하지 않을 이유가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ff06-107">However, your organization may have reasons for not wanting to record and retain audit log data.</span></span> <span data-ttu-id="1ff06-108">이러한 경우 전역 관리자는 전역 관리자의 감사를 해제할 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1ff06-108">In those cases, a global admin may decide to turn off auditing in Microsoft 365.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1ff06-109">조직에서 감사를 Microsoft 365 경우 Office 365 관리 활동 API 또는 Azure Sentinel을 사용하여 조직의 감사 데이터에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1ff06-109">If you turn off auditing in Microsoft 365, you can't use the Office 365 Management Activity API or Azure Sentinel to access auditing data for your organization.</span></span> <span data-ttu-id="1ff06-110">이 문서의 단계를 수행하여 감사를 끄면 보안 & 준수 센터를 사용하여 감사 로그를 검색하거나 PowerShell에서 **Search-UnifiedAuditLog** cmdlet을 실행할 때 결과가 Exchange Online 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1ff06-110">Turning off auditing by following the steps in this article means that no results will be returned when you search the audit log using the Security & Compliance Center or when you run the **Search-UnifiedAuditLog** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="1ff06-111">이는 또한 관리 활동 API 또는 Azure Sentinel을 통해 감사 Office 365 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1ff06-111">This also means that audit logs won't be available through the Office 365 Management Activity API or Azure Sentinel.</span></span>
  
## <a name="before-you-turn-auditing-on-or-off"></a><span data-ttu-id="1ff06-112">감사를 켜거나 끄기 전에</span><span class="sxs-lookup"><span data-stu-id="1ff06-112">Before you turn auditing on or off</span></span>

- <span data-ttu-id="1ff06-113">조직에서 감사를 설정하거나 해제하려면 Exchange Online 감사 로그 역할이 Microsoft 365 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ff06-113">You have to be assigned the Audit Logs role in Exchange Online to turn auditing on or off in your Microsoft 365 organization.</span></span> <span data-ttu-id="1ff06-114">기본적으로 이 역할은 Exchange 관리 센터의 사용 권한  페이지에서 준수 관리 및 조직 관리 역할 그룹에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ff06-114">By default, this role is assigned to the Compliance Management and Organization Management role groups on the **Permissions** page in the Exchange admin center.</span></span> <span data-ttu-id="1ff06-115">조직의 전역 Microsoft 365 조직 관리 역할 그룹의 구성원입니다Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="1ff06-115">Global admins in Microsoft 365 are members of the Organization Management role group in Exchange Online.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="1ff06-116">감사를 설정하거나 해제하려면 사용자에게 Exchange Online 권한을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ff06-116">Users have to be assigned permissions in Exchange Online to turn auditing on or off.</span></span> <span data-ttu-id="1ff06-117">보안 및 준수 센터의 사용  권한 페이지에서 사용자에게 감사 로그 역할을 & 감사를 설정하거나 해제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1ff06-117">If you assign users the Audit Logs role on the **Permissions** page in the Security & Compliance Center, they won't be able to turn auditing on or off.</span></span> <span data-ttu-id="1ff06-118">이는 PowerShell cmdlet의 Exchange Online cmdlet이기 때문에입니다.</span><span class="sxs-lookup"><span data-stu-id="1ff06-118">This is because the underlying cmdlet is an Exchange Online PowerShell cmdlet.</span></span> 

- <span data-ttu-id="1ff06-119">감사 로그 검색에 대한 단계별 지침은 보안 및 준수 센터에서 감사 [로그 & 참조하세요.](search-the-audit-log-in-security-and-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="1ff06-119">For step-by-step instructions on searching the audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span> <span data-ttu-id="1ff06-120">관리 활동 API의 Microsoft 365 자세한 내용은 Microsoft 365 관리 API [시작을 참조하세요.](/office/office-365-management-api/get-started-with-office-365-management-apis)</span><span class="sxs-lookup"><span data-stu-id="1ff06-120">For more information about the Microsoft 365 Management Activity API, see [Get started with Microsoft 365 Management APIs](/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span>

- <span data-ttu-id="1ff06-121">감사가 켜져 있는지 확인하기 위해 PowerShell에서 다음 명령을 Exchange Online 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ff06-121">To verify that auditing is turned on, you can run the following command in Exchange Online PowerShell:</span></span>

    ```powershell
    Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
    ```

    <span data-ttu-id="1ff06-122">`True` _UnifiedAuditLogIngestionEnabled_ 속성의 값은 감사가 켜져 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1ff06-122">The value of  `True` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that auditing is turned on.</span></span> 

## <a name="turn-on-auditing"></a><span data-ttu-id="1ff06-123">감사 켜기</span><span class="sxs-lookup"><span data-stu-id="1ff06-123">Turn on auditing</span></span>

<span data-ttu-id="1ff06-124">조직에 대한 감사가 설정되어 있지 않은 경우 규정 준수 센터에서 또는 PowerShell을 사용하여 Exchange Online 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ff06-124">If auditing is not turned on for your organization, you can turn it on in the compliance center or by using Exchange Online PowerShell.</span></span> <span data-ttu-id="1ff06-125">감사 로그를 검색할 때 결과를 반환하려면 감사를 설정한 후 몇 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ff06-125">It may take several hours after you turn on auditing before you can return results when you search the audit log.</span></span>
  
### <a name="use-the-compliance-center-to-turn-on-auditing"></a><span data-ttu-id="1ff06-126">준수 센터를 사용하여 감사 켜기</span><span class="sxs-lookup"><span data-stu-id="1ff06-126">Use the compliance center to turn on auditing</span></span>

1. <span data-ttu-id="1ff06-127"><https://compliance.microsoft.com>으로 이동하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="1ff06-127">Go to <https://compliance.microsoft.com> and sign in.</span></span>

2. <span data-ttu-id="1ff06-128">규정 준수 센터의 왼쪽 탐색 Microsoft 365 모두 표시를 **클릭한** 다음 감사를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="1ff06-128">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **Audit**.</span></span>

   <span data-ttu-id="1ff06-129">조직에 대한 감사가 설정되어 있지 않은 경우 사용자 및 관리자 활동 기록을 시작하라는 배너가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ff06-129">If auditing is not turned on for your organization, a banner is displayed prompting you start recording user and admin activity.</span></span>

   ![감사 페이지의 배너](../media/AuditingBanner.png)

3. <span data-ttu-id="1ff06-131">사용자 **및 관리자 활동 기록 시작 배너를** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1ff06-131">Click the **Start recording user and admin activity** banner.</span></span>

   <span data-ttu-id="1ff06-132">변경을 적용하는 데 최대 60분이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ff06-132">It may take up to 60 minutes for the change to take effect.</span></span>

### <a name="use-powershell-to-turn-on-auditing"></a><span data-ttu-id="1ff06-133">PowerShell을 사용하여 감사 켜기</span><span class="sxs-lookup"><span data-stu-id="1ff06-133">Use PowerShell to turn on auditing</span></span>

1. [<span data-ttu-id="1ff06-134">Exchange Online PowerShell에 연결</span><span class="sxs-lookup"><span data-stu-id="1ff06-134">Connect to Exchange Online PowerShell</span></span>](/powershell/exchange/connect-to-exchange-online-powershell)

2. <span data-ttu-id="1ff06-135">다음 PowerShell 명령을 실행하여 감사 기능을 Office 365.</span><span class="sxs-lookup"><span data-stu-id="1ff06-135">Run the following PowerShell command to turn on auditing in Office 365.</span></span>

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    <span data-ttu-id="1ff06-136">변경이 적용되는 데 최대 60분이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ff06-136">A message is displayed saying that it may take up to 60 minutes for the change to take effect.</span></span>
  
## <a name="turn-off-auditing"></a><span data-ttu-id="1ff06-137">감사 끄기</span><span class="sxs-lookup"><span data-stu-id="1ff06-137">Turn off auditing</span></span>

<span data-ttu-id="1ff06-138">감사를 Exchange Online PowerShell을 사용하여 감사를 해제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ff06-138">You have to use Exchange Online PowerShell to turn off auditing.</span></span>
  
1. [<span data-ttu-id="1ff06-139">Exchange Online PowerShell에 연결</span><span class="sxs-lookup"><span data-stu-id="1ff06-139">Connect to Exchange Online PowerShell</span></span>](/powershell/exchange/connect-to-exchange-online-powershell)

2. <span data-ttu-id="1ff06-140">다음 PowerShell 명령을 실행하여 감사를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="1ff06-140">Run the following PowerShell command to turn off auditing.</span></span>

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. <span data-ttu-id="1ff06-141">잠시 후 감사가 꺼져 있는지(사용 안 하게) 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ff06-141">After a while, verify that auditing is turned off (disabled).</span></span> <span data-ttu-id="1ff06-142">이 작업을 수행하는 방법은 다음 두 가지입니다.</span><span class="sxs-lookup"><span data-stu-id="1ff06-142">There are two ways to do this:</span></span>

    - <span data-ttu-id="1ff06-143">PowerShell Exchange Online 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1ff06-143">In Exchange Online PowerShell, run the following command:</span></span>

      ```powershell
      Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
      ```

      <span data-ttu-id="1ff06-144">`False` _UnifiedAuditLogIngestionEnabled_ 속성의 값은 감사가 해제되어 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1ff06-144">The value of  `False` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that auditing is turned off.</span></span>

    - <span data-ttu-id="1ff06-145">규정 준수 **센터의** 감사 Microsoft 365 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="1ff06-145">Go to the **Audit** page in the Microsoft 365 compliance center.</span></span>

      <span data-ttu-id="1ff06-146">조직에 대한 감사가 설정되어 있지 않은 경우 사용자 및 관리자 활동 기록을 시작하라는 배너가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ff06-146">If auditing is not turned on for your organization, a banner is displayed prompting you start recording user and admin activity.</span></span>
