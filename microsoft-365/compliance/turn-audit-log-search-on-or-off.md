---
title: 감사 로그 검색 켜기 또는 끄기
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
description: 보안 & 준수 센터에서 감사 로그 검색 기능을 설정 하거나 해제 하 여 관리자가 감사 로그를 검색 하는 기능을 사용 하거나 사용 하지 않도록 설정 하는 방법
ms.openlocfilehash: 4571c90c4fa680acd8925e83e32ffcf07de7d626
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819138"
---
# <a name="turn-audit-log-search-on-or-off"></a><span data-ttu-id="a6d82-103">감사 로그 검색 켜기 또는 끄기</span><span class="sxs-lookup"><span data-stu-id="a6d82-103">Turn audit log search on or off</span></span>

<span data-ttu-id="a6d82-104">감사 로그 검색을 시작 하기 전에 사용자 또는 다른 관리자가 감사 로깅을 켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6d82-104">You (or another admin) must turn on audit logging before you can start searching the audit log.</span></span> <span data-ttu-id="a6d82-105">보안 & 준수 센터에서 감사 로그 검색이 설정 되 면 조직의 사용자 및 관리 활동이 감사 로그에 기록 되 고, 90 일 동안 보존 되며, 사용자에 게 할당 된 라이선스에 따라 최대 1 년까지 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6d82-105">When audit log search in the Security & Compliance Center is turned on, user and admin activity from your organization is recorded in the audit log and retained for 90 days, and up to one year depending on the license assigned to users.</span></span> <span data-ttu-id="a6d82-106">그러나 조직에서 감사 로그 데이터를 기록 하 고 유지 하지 않으려는 이유가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6d82-106">However, your organization may have reasons for not wanting to record and retain audit log data.</span></span> <span data-ttu-id="a6d82-107">이러한 경우 전역 관리자가 Microsoft 365에서 감사 기능을 해제 하도록 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6d82-107">In those cases, a global admin may decide to turn off auditing in Microsoft 365.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a6d82-108">Microsoft 365에서 감사 로그 검색을 해제 하면 Office 365 관리 활동 API 또는 Azure 센티널을 사용 하 여 조직의 감사 데이터에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a6d82-108">If you turn off audit log search in Microsoft 365, you can't use the Office 365 Management Activity API or Azure Sentinel to access auditing data for your organization.</span></span> <span data-ttu-id="a6d82-109">이 문서에서 설명 하는 단계에 따라 감사 로그 검색을 해제 하면 보안 & 준수 센터를 사용 하 여 감사 로그를 검색 하거나 Exchange Online PowerShell에서 **search-unifiedauditlog** cmdlet을 실행할 때 결과가 반환 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a6d82-109">Turning off audit log search by following the steps in this article means that no results will be returned when you search the audit log using the Security & Compliance Center or when you run the **Search-UnifiedAuditLog** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="a6d82-110">이는 또한 Office 365 관리 활동 API 또는 Azure 센티널를 통해 감사 로그를 사용할 수 없다는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6d82-110">This also means that audit logs won't be available through the Office 365 Management Activity API or Azure Sentinel.</span></span>
  
## <a name="before-you-turn-audit-log-search-on-or-off"></a><span data-ttu-id="a6d82-111">감사 로그 검색을 설정 또는 해제 하기 전에</span><span class="sxs-lookup"><span data-stu-id="a6d82-111">Before you turn audit log search on or off</span></span>

- <span data-ttu-id="a6d82-112">Microsoft 365 조직에서 감사 로그 검색을 설정 하거나 해제 하려면 Exchange Online에서 감사 로그 역할을 할당 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6d82-112">You have to be assigned the Audit Logs role in Exchange Online to turn audit log search on or off in your Microsoft 365 organization.</span></span> <span data-ttu-id="a6d82-113">기본적으로이 역할은 Exchange 관리 센터의 **사용 권한** 페이지에 있는 준수 관리 및 조직 관리 역할 그룹에 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6d82-113">By default, this role is assigned to the Compliance Management and Organization Management role groups on the **Permissions** page in the Exchange admin center.</span></span> <span data-ttu-id="a6d82-114">Microsoft 365의 전역 관리자는 Exchange Online의 조직 관리 역할 그룹의 구성원입니다.</span><span class="sxs-lookup"><span data-stu-id="a6d82-114">Global admins in Microsoft 365 are members of the Organization Management role group in Exchange Online.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="a6d82-115">감사 로그 검색을 설정 또는 해제 하려면 사용자에 게 Exchange Online의 사용 권한을 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6d82-115">Users have to be assigned permissions in Exchange Online to turn audit log search on or off.</span></span> <span data-ttu-id="a6d82-116">보안 & 준수 센터의 **사용 권한** 페이지에서 사용자에 게 감사 로그 역할을 할당 하면 감사 로그 검색을 설정 하거나 해제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a6d82-116">If you assign users the Audit Logs role on the **Permissions** page in the Security & Compliance Center, they won't be able to turn audit log search on or off.</span></span> <span data-ttu-id="a6d82-117">이는 기본 cmdlet이 Exchange Online cmdlet 이기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="a6d82-117">This is because the underlying cmdlet is an Exchange Online cmdlet.</span></span> 
    
- <span data-ttu-id="a6d82-118">감사 로그를 검색 하는 단계별 지침은 [Security & 준수 센터에서 감사 로그 검색](search-the-audit-log-in-security-and-compliance.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="a6d82-118">For step-by-step instructions on searching the audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span> <span data-ttu-id="a6d82-119">Microsoft 365 관리 활동 API에 대 한 자세한 내용은 [microsoft 365 관리 api 시작](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a6d82-119">For more information about the Microsoft 365 Management Activity API, see [Get started with Microsoft 365 Management APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span>
    
## <a name="turn-on-audit-log-search"></a><span data-ttu-id="a6d82-120">감사 로그 검색 켜기</span><span class="sxs-lookup"><span data-stu-id="a6d82-120">Turn on audit log search</span></span>

<span data-ttu-id="a6d82-121">보안 & 준수 센터 또는 PowerShell을 사용 하 여 Microsoft 365에서 감사 로그 검색을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6d82-121">You can use the Security & Compliance Center or PowerShell to turn on audit log search in Microsoft 365.</span></span> <span data-ttu-id="a6d82-122">감사 로그 검색을 설정한 후에는 여러 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6d82-122">It may take several hours after you turn on audit log search before you can return results when you search the audit log.</span></span> <span data-ttu-id="a6d82-123">감사 로그 검색을 설정 하려면 Exchange Online에서 감사 로그 역할을 할당 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6d82-123">You have to be assigned the Audit Logs role in Exchange Online to turn on audit log search.</span></span>
  
### <a name="use-the-security--compliance-center-to-turn-on-audit-log-search"></a><span data-ttu-id="a6d82-124">보안 & 준수 센터를 사용 하 여 감사 로그 검색 설정</span><span class="sxs-lookup"><span data-stu-id="a6d82-124">Use the Security & Compliance Center to turn on audit log search</span></span>

1. <span data-ttu-id="a6d82-125">[보안 & 준수 센터로 이동](https://protection.office.com) 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6d82-125">[Go to the Security & Compliance Center](https://protection.office.com) and sign in.</span></span>

2. <span data-ttu-id="a6d82-126">보안 & 준수 센터에서 **검색** \> **감사 로그 검색**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6d82-126">In the Security & Compliance Center, go to **Search** \> **Audit log search**.</span></span>

   <span data-ttu-id="a6d82-127">사용자 및 관리 활동을 기록 하기 위해 감사를 설정 해야 한다는 배너가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6d82-127">A banner is displayed saying that auditing has to be turned on to record user and admin activity.</span></span>

3. <span data-ttu-id="a6d82-128">**감사 설정을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6d82-128">Click **Turn on auditing**.</span></span>

    ![감사 사용을 클릭 합니다.](../media/39a9d35f-88d0-4bbe-a962-0be2f838e2bf.png)
  
    <span data-ttu-id="a6d82-130">이 배너는 감사 로그를 준비 중 이며 몇 시간 내에 사용자 및 관리자 활동을 검색할 수 있다고 표시 하도록 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6d82-130">The banner is updated to say the audit log is being prepared and that you can search for user and admin activity in a few hours.</span></span>

### <a name="use-powershell-to-turn-on-audit-log-search"></a><span data-ttu-id="a6d82-131">PowerShell을 사용 하 여 감사 로그 검색 설정</span><span class="sxs-lookup"><span data-stu-id="a6d82-131">Use PowerShell to turn on audit log search</span></span>

1. [<span data-ttu-id="a6d82-132">Exchange Online PowerShell에 연결</span><span class="sxs-lookup"><span data-stu-id="a6d82-132">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=396554)

2. <span data-ttu-id="a6d82-133">다음 PowerShell 명령을 실행 하 여 Office 365에서 감사 로그 검색을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6d82-133">Run the following PowerShell command to turn on audit log search in Office 365.</span></span>

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    <span data-ttu-id="a6d82-134">변경 내용이 적용 되는 데 최대 60 분이 걸릴 수 있음을 알리는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6d82-134">A message is displayed saying that it may take up to 60 minutes for the change to take effect.</span></span>
  
## <a name="turn-off-audit-log-search"></a><span data-ttu-id="a6d82-135">감사 로그 검색 해제</span><span class="sxs-lookup"><span data-stu-id="a6d82-135">Turn off audit log search</span></span>

<span data-ttu-id="a6d82-136">감사 로그 검색을 해제 하려면 Exchange Online 조직에 연결 된 원격 PowerShell을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6d82-136">You have to use remote PowerShell connected to your Exchange Online organization to turn off audit log search.</span></span> <span data-ttu-id="a6d82-137">감사 로그 검색을 설정 하는 것과 마찬가지로 감사 로그 검색을 해제 하려면 Exchange Online에서 감사 로그 역할을 할당 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6d82-137">Similar to turning on audit log search, you have to be assigned the Audit Logs role in Exchange Online to turn off audit log search.</span></span>
  
1. [<span data-ttu-id="a6d82-138">Exchange Online PowerShell에 연결</span><span class="sxs-lookup"><span data-stu-id="a6d82-138">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=396554)

2. <span data-ttu-id="a6d82-139">다음 PowerShell 명령을 실행 하 여 Office 365에서 감사 로그 검색을 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6d82-139">Run the following PowerShell command to turn off audit log search in Office 365.</span></span>

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. <span data-ttu-id="a6d82-140">잠시 후에 감사 로그 검색이 해제 되어 있는지 확인 합니다 (사용 하지 않도록 설정 됨).</span><span class="sxs-lookup"><span data-stu-id="a6d82-140">After a while, verify that audit log search is turned off (disabled).</span></span> <span data-ttu-id="a6d82-141">이 작업은 다음 두 가지 방법으로 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6d82-141">There are two ways to do this:</span></span>

    - <span data-ttu-id="a6d82-142">PowerShell에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6d82-142">In PowerShell, run the following command:</span></span>

    ```powershell
    Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
    ```

      <span data-ttu-id="a6d82-143">`False` _UnifiedAuditLogIngestionEnabled_ 속성의 값은 감사 로그 검색이 해제 됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a6d82-143">The value of  `False` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that audit log search is turned off.</span></span> 

    - <span data-ttu-id="a6d82-144">[보안 & 준수 센터](https://protection.office.com)에서 **검색** \> **감사 로그 검색**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6d82-144">In the [Security & Compliance Center](https://protection.office.com), go to **Search** \> **Audit log search**.</span></span>

      <span data-ttu-id="a6d82-145">사용자 및 관리 활동을 기록 하기 위해 감사를 설정 해야 한다는 배너가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6d82-145">A banner is displayed saying that auditing has to be turned on in order to record user and admin activity.</span></span>