---
title: Office 365 감사 로그 검색 켜기 또는 끄기
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
description: 보안 & 준수 센터에서 감사 로그 검색 기능을 설정할 수 있습니다. 생각이 변경 되 면 언제 든 지 설정을 해제할 수 있습니다. 감사 로그 검색이 해제 되 면 관리자가 조직의 사용자 및 관리자 활동에 대 한 Office 365 감사 로그를 검색할 수 없습니다.
ms.openlocfilehash: 83ef355c4acd5e0af4fd7ffbf13157307bcac930
ms.sourcegitcommit: 53d848ebd4799b285d0f67c49b0aa24c88bd0e23
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2019
ms.locfileid: "37334248"
---
# <a name="turn-office-365-audit-log-search-on-or-off"></a><span data-ttu-id="52ef8-105">Office 365 감사 로그 검색 켜기 또는 끄기</span><span class="sxs-lookup"><span data-stu-id="52ef8-105">Turn Office 365 audit log search on or off</span></span>

<span data-ttu-id="52ef8-106">사용자 (또는 다른 관리자)가 감사 로깅을 켜야 Office 365 감사 로그 검색을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52ef8-106">You (or another admin) must turn on audit logging before you can start searching the Office 365 audit log.</span></span> <span data-ttu-id="52ef8-107">보안 & 준수 센터에서 감사 로그 검색이 설정 된 경우 조직의 사용자 및 관리 활동이 감사 로그에 기록 되 고 90 일 동안 보존 됩니다.</span><span class="sxs-lookup"><span data-stu-id="52ef8-107">When audit log search in the Security & Compliance Center is turned on, user and admin activity from your organization is recorded in the audit log and retained for 90 days.</span></span> <span data-ttu-id="52ef8-108">하지만 조직에서 감사 로그 데이터를 기록 및 보존 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52ef8-108">However, your organization may not want to record and retain audit log data.</span></span> <span data-ttu-id="52ef8-109">또는 타사의 SIEM (보안 정보 및 이벤트 관리) 응용 프로그램을 사용 하 여 감사 데이터에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52ef8-109">Or you may be using a third-party security information and event management (SIEM) application to access your auditing data.</span></span> <span data-ttu-id="52ef8-110">이러한 경우 전역 관리자가 Office 365에서 감사 로그 검색을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52ef8-110">In those cases, a global admin can turn off audit log search in Office 365.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="52ef8-111">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="52ef8-111">Before you begin</span></span>

- <span data-ttu-id="52ef8-112">Office 365 조직에서 감사 로그 검색을 설정 하거나 해제 하려면 Exchange Online에서 감사 로그 역할을 할당 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52ef8-112">You have to be assigned the Audit Logs role in Exchange Online to turn audit log search on or off in your Office 365 organization.</span></span> <span data-ttu-id="52ef8-113">기본적으로이 역할은 Exchange 관리 센터의 **사용 권한** 페이지에 있는 준수 관리 및 조직 관리 역할 그룹에 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="52ef8-113">By default, this role is assigned to the Compliance Management and Organization Management role groups on the **Permissions** page in the Exchange admin center.</span></span> <span data-ttu-id="52ef8-114">Office 365의 전역 관리자는 Exchange Online의 조직 관리 역할 그룹의 구성원입니다.</span><span class="sxs-lookup"><span data-stu-id="52ef8-114">Global admins in Office 365 are members of the Organization Management role group in Exchange Online.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="52ef8-115">감사 로그 검색을 설정 또는 해제 하려면 사용자에 게 Exchange Online의 사용 권한을 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52ef8-115">Users have to be assigned permissions in Exchange Online to turn audit log search on or off.</span></span> <span data-ttu-id="52ef8-116">보안 & 준수 센터의 **사용 권한** 페이지에서 사용자에 게 감사 로그 역할을 할당 하면 감사 로그 검색을 설정 하거나 해제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="52ef8-116">If you assign users the Audit Logs role on the **Permissions** page in the Security & Compliance Center, they won't be able to turn audit log search on or off.</span></span> <span data-ttu-id="52ef8-117">이는 기본 cmdlet이 Exchange Online cmdlet 이기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="52ef8-117">This is because the underlying cmdlet is an Exchange Online cmdlet.</span></span> 
  
- <span data-ttu-id="52ef8-118">Office 365에서 감사 로그 검색을 해제 하면 Office 365 관리 작업 API를 사용 하 여 조직의 감사 데이터에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="52ef8-118">If you turn off audit log search in Office 365, you can't use the Office 365 Management Activity API to access auditing data for your organization.</span></span> <span data-ttu-id="52ef8-119">이 문서에서 설명 하는 단계에 따라 감사 로그 검색을 해제 하면 보안 & 준수 센터를 사용 하 여 감사 로그를 검색 하거나 Exchange Online PowerShell에서 **search-unifiedauditlog** cmdlet을 실행할 때 결과가 반환 되지 않습니다. .</span><span class="sxs-lookup"><span data-stu-id="52ef8-119">Turning off audit log search by following the steps in this article means that no results will be returned when you search the audit log using the Security & Compliance Center or when you run the **Search-UnifiedAuditLog** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="52ef8-120">이는 또한 Office 365 관리 활동 API를 통해 감사 로그를 사용할 수 없다는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="52ef8-120">This also means that your audit logs won't be available through the Office 365 Management Activity API.</span></span>  
    
- <span data-ttu-id="52ef8-121">Office 365 감사 로그를 검색 하는 방법에 대 한 단계별 지침은 [Security & 준수 센터에서 감사 로그 검색](search-the-audit-log-in-security-and-compliance.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="52ef8-121">For step-by-step instructions on searching the Office 365 audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span>
    
## <a name="turn-on-audit-log-search"></a><span data-ttu-id="52ef8-122">감사 로그 검색 켜기</span><span class="sxs-lookup"><span data-stu-id="52ef8-122">Turn on audit log search</span></span>

<span data-ttu-id="52ef8-123">보안 & 준수 센터 또는 PowerShell을 사용 하 여 Office 365에서 감사 로그 검색을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52ef8-123">You can use the Security & Compliance Center or PowerShell to turn on audit log search in Office 365.</span></span> <span data-ttu-id="52ef8-124">감사 로그 검색을 설정한 후에는 여러 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52ef8-124">It may take several hours after you turn on audit log search before you can return results when you search the audit log.</span></span> <span data-ttu-id="52ef8-125">감사 로그 검색을 설정 하려면 Exchange Online에서 감사 로그 역할을 할당 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52ef8-125">You have to be assigned the Audit Logs role in Exchange Online to turn on audit log search.</span></span>
  
### <a name="use-the-security--compliance-center-to-turn-on-audit-log-search"></a><span data-ttu-id="52ef8-126">보안 & 준수 센터를 사용 하 여 감사 로그 검색 설정</span><span class="sxs-lookup"><span data-stu-id="52ef8-126">Use the Security & Compliance Center to turn on audit log search</span></span>

1. <span data-ttu-id="52ef8-127">보안 & 준수 센터에서 **검색** \> **감사 로그 검색**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="52ef8-127">In the Security & Compliance Center, go to **Search** \> **Audit log search**.</span></span>
    
   <span data-ttu-id="52ef8-128">사용자 및 관리 활동을 기록 하기 위해 감사를 설정 해야 한다는 배너가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="52ef8-128">A banner is displayed saying that auditing has to be turned on to record user and admin activity.</span></span>

2. <span data-ttu-id="52ef8-129">**감사 설정을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="52ef8-129">Click **Turn on auditing**.</span></span>
    
    ![감사 사용을 클릭 합니다.](media/39a9d35f-88d0-4bbe-a962-0be2f838e2bf.png)
  
    <span data-ttu-id="52ef8-131">이 배너는 감사 로그를 준비 중 이며 몇 시간 내에 사용자 및 관리자 활동을 검색할 수 있다고 표시 하도록 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="52ef8-131">The banner is updated to say the audit log is being prepared and that you can search for user and admin activity in a few hours.</span></span>
    
### <a name="use-powershell-to-turn-on-audit-log-search"></a><span data-ttu-id="52ef8-132">PowerShell을 사용 하 여 감사 로그 검색 설정</span><span class="sxs-lookup"><span data-stu-id="52ef8-132">Use PowerShell to turn on audit log search</span></span>

1. [<span data-ttu-id="52ef8-133">Exchange Online PowerShell에 연결</span><span class="sxs-lookup"><span data-stu-id="52ef8-133">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=396554)
    
2. <span data-ttu-id="52ef8-134">다음 PowerShell 명령을 실행 하 여 Office 365에서 감사 로그 검색을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="52ef8-134">Run the following PowerShell command to turn on audit log search in Office 365.</span></span>
    
    ```
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    <span data-ttu-id="52ef8-135">변경 내용이 적용 되는 데 최대 60 분이 걸릴 수 있음을 알리는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="52ef8-135">A message is displayed saying that it may take up to 60 minutes for the change to take effect.</span></span>
  
## <a name="turn-off-audit-log-search"></a><span data-ttu-id="52ef8-136">감사 로그 검색 해제</span><span class="sxs-lookup"><span data-stu-id="52ef8-136">Turn off audit log search</span></span>

<span data-ttu-id="52ef8-137">감사 로그 검색을 해제 하려면 Exchange Online 조직에 연결 된 원격 PowerShell을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52ef8-137">You have to use remote PowerShell connected to your Exchange Online organization to turn off audit log search.</span></span> <span data-ttu-id="52ef8-138">감사 로그 검색을 설정 하는 것과 마찬가지로 감사 로그 검색을 해제 하려면 Exchange Online에서 감사 로그 역할을 할당 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52ef8-138">Similar to turning on audit log search, you have to be assigned the Audit Logs role in Exchange Online to turn off audit log search.</span></span>
  
1. [<span data-ttu-id="52ef8-139">Exchange Online PowerShell에 연결</span><span class="sxs-lookup"><span data-stu-id="52ef8-139">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=396554)
    
2. <span data-ttu-id="52ef8-140">다음 PowerShell 명령을 실행 하 여 Office 365에서 감사 로그 검색을 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="52ef8-140">Run the following PowerShell command to turn off audit log search in Office 365.</span></span>
    
    ```
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. <span data-ttu-id="52ef8-141">잠시 후에 감사 로그 검색이 해제 되어 있는지 확인 합니다 (사용 하지 않도록 설정 됨).</span><span class="sxs-lookup"><span data-stu-id="52ef8-141">After a while, verify that audit log search is turned off (disabled).</span></span> <span data-ttu-id="52ef8-142">이 작업은 다음 두 가지 방법으로 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52ef8-142">There are two ways to do this:</span></span>
    
    - <span data-ttu-id="52ef8-143">PowerShell에서 다음 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="52ef8-143">In PowerShell, run the following command:</span></span>

            ```
            Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
            ```

           The value of  `False` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that audit log search is turned off. 
    
    - <span data-ttu-id="52ef8-144">보안 & 준수 센터에서 **검색** \> **감사 로그 검색**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="52ef8-144">In the Security & Compliance Center, go to **Search** \> **Audit log search**.</span></span>
    
           A banner is displayed saying that auditing has to be turned on in order to record user and admin activity.
