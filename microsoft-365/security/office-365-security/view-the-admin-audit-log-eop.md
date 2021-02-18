---
title: 독립 실행형 EOP에서 관리자 감사 로그 보기
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 003d7a74-3e16-4453-ae0c-9dbae51f66d1
description: 관리자는 독립 실행형 EOP(Exchange Online Protection)에서 관리자 감사 로그를 보고 검색하는 방법을 배울 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ab6bf0a2739a88a075b636b990539b24006f3e63
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286480"
---
# <a name="view-the-admin-audit-log-in-standalone-eop"></a><span data-ttu-id="f0b1e-103">독립 실행형 EOP에서 관리자 감사 로그 보기</span><span class="sxs-lookup"><span data-stu-id="f0b1e-103">View the admin audit log in standalone EOP</span></span>

<span data-ttu-id="f0b1e-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="f0b1e-104">**Applies to**</span></span>
- [<span data-ttu-id="f0b1e-105">Exchange Online Protection 독립 실행형</span><span class="sxs-lookup"><span data-stu-id="f0b1e-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="f0b1e-106">Exchange Online 사서함이 없는 독립 실행형 EOP(Exchange Online Protection) 조직에서는 EAC(Exchange 관리 센터) 또는 독립 실행형 EOP PowerShell을 사용하여 관리자 감사 로그의 항목을 검색하고 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0b1e-106">In standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you can use the Exchange admin center (EAC) or standalone EOP PowerShell to search for and view entries in the admin audit log.</span></span>

<span data-ttu-id="f0b1e-107">관리자 감사 로그는 독립 실행형 EOP PowerShell cmdlet을 기반으로 관리 권한이 할당된 관리자 및 사용자가 수행한 특정 작업을 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="f0b1e-107">The admin audit log records specific actions, based on standalone EOP PowerShell cmdlets, done by admins and users who have been assigned administrative privileges.</span></span> <span data-ttu-id="f0b1e-108">관리자 감사 로그의 항목은 실행된 cmdlet, 사용된 매개 변수, cmdlet을 실행한 사용자 및 영향을 받은 개체에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f0b1e-108">Entries in the admin audit log provide you with information about what cmdlet was run, which parameters were used, who ran the cmdlet, and what objects were affected.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="f0b1e-109">관리자 감사 로깅은 기본적으로 사용하도록 설정되어 있으며 사용하지 않도록 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f0b1e-109">Admin auditing logging is enabled by default, and you can't disable it.</span></span>
>
> - <span data-ttu-id="f0b1e-110">관리자 감사 로그는 **Get,** **Search** 또는 Test 동사로 시작하는 cmdlet에 따라 작업을 기록하지 **않습니다.**</span><span class="sxs-lookup"><span data-stu-id="f0b1e-110">The admin audit log doesn't record actions based on cmdlets that begins with the verbs **Get**, **Search**, or **Test**.</span></span>
>
> - <span data-ttu-id="f0b1e-111">감사 로그 항목은 90일 동안 보관됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0b1e-111">Audit log entries are kept for 90 days.</span></span> <span data-ttu-id="f0b1e-112">항목이 90일보다 오래된 경우 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0b1e-112">When an entry is older than 90 days, it's deleted</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f0b1e-113">시작하기 전에 알아야 할 사항은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="f0b1e-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f0b1e-114">Exchange 관리 센터를 열하려면 독립 실행형 [EOP에서 Exchange 관리 센터를 참조하세요.](exchange-admin-center-in-exchange-online-protection-eop.md)</span><span class="sxs-lookup"><span data-stu-id="f0b1e-114">To open the Exchange admin center, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="f0b1e-115">독립 실행형 EOP PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f0b1e-115">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="f0b1e-116">이 문서의 절차를 수행하려면 먼저 Exchange Online Protection에서 사용 권한을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0b1e-116">You need to be assigned permissions in Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="f0b1e-117">특히 조직 관리, 준수 관리 및 보안 관리자 역할 그룹에 기본적으로 할당되는 감사 로그 또는 보기 전용 감사 로그 역할이 필요합니다.   </span><span class="sxs-lookup"><span data-stu-id="f0b1e-117">Specifically, you need the **Audit Logs** or **View-Only Audit Logs** role, which are assigned to the **Organization Management**, **Compliance Management**, and **Security Administrator** role groups by default.</span></span> <span data-ttu-id="f0b1e-118">자세한 내용은 독립 실행형 [EOP의](feature-permissions-in-eop.md) 사용 권한을 참조하고 EAC를 사용하여 역할 그룹의 구성원 목록을 [수정합니다.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)</span><span class="sxs-lookup"><span data-stu-id="f0b1e-118">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="f0b1e-119">이 문서의 절차에 적용할 수 있는 바로 가기 키에 대한 자세한 내용은 [Exchange Online의 Exchange](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)관리 센터에 대한 바로 가기 키를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f0b1e-119">For information about keyboard shortcuts that may apply to the procedures in this article, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

> [!TIP]
> <span data-ttu-id="f0b1e-120">문제가 있나요?</span><span class="sxs-lookup"><span data-stu-id="f0b1e-120">Having problems?</span></span> <span data-ttu-id="f0b1e-121">[Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) 포럼에서 도움을 요청하세요.</span><span class="sxs-lookup"><span data-stu-id="f0b1e-121">Ask for help in the [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) forum.</span></span>

## <a name="use-the-eac-to-view-the-admin-audit-log"></a><span data-ttu-id="f0b1e-122">EAC를 사용하여 관리자 감사 로그 보기</span><span class="sxs-lookup"><span data-stu-id="f0b1e-122">Use the EAC to view the admin audit log</span></span>

1. <span data-ttu-id="f0b1e-123">EAC에서 준수 관리  감사로 이동한 다음 관리자 감사 로그 보고서 \>  **실행을 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="f0b1e-123">In the EAC, go to **Compliance management** \> **Auditing**, and then choose **Run the admin audit log report**.</span></span>

2. <span data-ttu-id="f0b1e-124">관리자  역할 그룹 변경 내용 검색 페이지가 열리면  시작 날짜와 종료 날짜(기본 범위는 지난 2주)를 선택한 다음 검색을 **선택합니다.** </span><span class="sxs-lookup"><span data-stu-id="f0b1e-124">In the **Search for changes to administrator role groups** page that opens, choose a **Start date** and **End date** (the default range is the past two weeks), and then choose **Search**.</span></span> <span data-ttu-id="f0b1e-125">지정된 기간 동안 적용된 모든 구성 변경 내용이 표시되고 다음 정보를 사용하여 정렬할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0b1e-125">All configuration changes made during the specified time period are displayed, and can be sorted, using the following information:</span></span>

   - <span data-ttu-id="f0b1e-126">**날짜:** 구성이 변경된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="f0b1e-126">**Date**: The date and time that the configuration change was made.</span></span> <span data-ttu-id="f0b1e-127">날짜와 시간은 UTC(협정 세계시) 형식으로 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0b1e-127">The date and time are stored in Coordinated Universal Time (UTC) format.</span></span>

   - <span data-ttu-id="f0b1e-128">**cmdlet:** 구성을 변경하는 데 사용된 cmdlet의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f0b1e-128">**Cmdlet**: The name of the cmdlet that was used to make the configuration change.</span></span>

   - <span data-ttu-id="f0b1e-129">**사용자:** 구성을 변경한 사용자의 사용자 계정 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f0b1e-129">**User**: The name of the user account of the user who made the configuration change.</span></span>

     <span data-ttu-id="f0b1e-p107">여러 페이지에 항목이 5,000개까지 표시됩니다. 결과의 범위를 좁혀야 하는 경우 날짜 범위를 더 좁게 지정하세요. 개별 검색 결과를 선택하면 세부 정보 창에 다음 추가 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0b1e-p107">Up to 5000 entries will be displayed on multiple pages. Specify a smaller date range if you need to narrow your results. If you select an individual search result, the following additional information is displayed in the details pane:</span></span>

   - <span data-ttu-id="f0b1e-133">**수정된 개체:** cmdlet에 의해 수정된 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="f0b1e-133">**Object modified**: The object that was modified by the cmdlet.</span></span>

   - <span data-ttu-id="f0b1e-134">**매개 변수(매개 변수:값)**: 사용된 cmdlet 매개 변수 및 매개 변수로 지정된 모든 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f0b1e-134">**Parameters (Parameter:Value)**: The cmdlet parameters that were used, and any value specified with the parameter.</span></span>

3. <span data-ttu-id="f0b1e-135">특정 감사 로그 항목을 인쇄하려면 세부 정보 창의 **인쇄** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f0b1e-135">If you want to print a specific audit log entry, choose the **Print** button in the details pane.</span></span>

## <a name="use-standalone-eop-powershell-to-view-the-admin-audit-log"></a><span data-ttu-id="f0b1e-136">독립 실행형 EOP PowerShell을 사용하여 관리자 감사 로그 보기</span><span class="sxs-lookup"><span data-stu-id="f0b1e-136">Use standalone EOP PowerShell to view the admin audit log</span></span>

<span data-ttu-id="f0b1e-137">독립 실행형 EOP PowerShell을 사용하여 지정한 기준을 충족하는 감사 로그 항목을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0b1e-137">You can use standalone EOP PowerShell to search for audit log entries that meet the criteria you specify.</span></span> <span data-ttu-id="f0b1e-138">다음 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f0b1e-138">Use the following syntax:</span></span>

```PowerShell
Search-AdminAuditLog [-Cmdlets <Cmdlet1,Cmdlet2,...CmdletN>] [-Parameters <Parameter1,Parameter2,...ParameterN>] [-StartDate <UTCDateTime>] [-EndDate <UTCDateTime>] [-UserIds <"User1","User2",..."UserN">] [-ObjectIds <"Object1","Object2",..."ObjectN">] [-IsSuccess <$true | $false>]
```

<span data-ttu-id="f0b1e-139">**참고:**</span><span class="sxs-lookup"><span data-stu-id="f0b1e-139">**Notes**:</span></span>

- <span data-ttu-id="f0b1e-140">_Parameters_ 매개 변수는 _Cmdlets_ 매개 변수와 함께만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0b1e-140">You can only use the _Parameters_ parameter together with the _Cmdlets_ parameter.</span></span>

- <span data-ttu-id="f0b1e-141">_ObjectIds_ 매개 변수는 cmdlet에서 수정한 개체에 따라 결과를 필터합니다.</span><span class="sxs-lookup"><span data-stu-id="f0b1e-141">The _ObjectIds_ parameter filters the results by the object that was modified by the cmdlet.</span></span> <span data-ttu-id="f0b1e-142">유효한 값은 개체가 감사 로그에 어떻게 나타내는지 여부에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0b1e-142">A valid value depends on how the object is represented in the audit log.</span></span> <span data-ttu-id="f0b1e-143">예시:</span><span class="sxs-lookup"><span data-stu-id="f0b1e-143">For example:</span></span>

  - <span data-ttu-id="f0b1e-144">이름</span><span class="sxs-lookup"><span data-stu-id="f0b1e-144">Name</span></span>
  - <span data-ttu-id="f0b1e-145">정식 고유 이름(예: contoso.com/Users/Akia 알-주하이리)</span><span class="sxs-lookup"><span data-stu-id="f0b1e-145">Canonical distinguished name (for example, contoso.com/Users/Akia Al-Zuhairi)</span></span>

  <span data-ttu-id="f0b1e-146">이 cmdlet에서 다른 필터링 매개 변수를 사용하여 결과 범위를 좁히고 관심 있는 개체 유형을 식별해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0b1e-146">You'll likely need to use other filtering parameters on this cmdlet to narrow down the results and identify the types of objects that you're interested in.</span></span>

- <span data-ttu-id="f0b1e-147">_UserIds_ 매개 변수는 변경한 사용자(cmdlet을 런 사용자)를 통해 결과를 필터로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f0b1e-147">The _UserIds_ parameter filters the results by the user who made the change (who ran the cmdlet).</span></span>

- <span data-ttu-id="f0b1e-148">_StartDate_ 및 _EndDate_ 매개 변수의 경우 표준 시간대 없이 날짜/시간 값을 지정하는 경우 값은 UTC(협정 세계시)입니다.</span><span class="sxs-lookup"><span data-stu-id="f0b1e-148">For the _StartDate_ and _EndDate_ parameters, if you specify a date/time value without a time zone, the value is in Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="f0b1e-149">이 매개 변수에 대한 날짜/시간값을 지정하려면 다음 옵션 중 하나를 사용하십시오.</span><span class="sxs-lookup"><span data-stu-id="f0b1e-149">To specify a date/time value for this parameter, use either of the following options:</span></span>

  - <span data-ttu-id="f0b1e-150">UTC로 날짜/시간 값 지정. 예: "2016-05-06 14:30:00z"</span><span class="sxs-lookup"><span data-stu-id="f0b1e-150">Specify the date/time value in UTC: For example, "2016-05-06 14:30:00z".</span></span>

  - <span data-ttu-id="f0b1e-151">날짜/시간 값을 현지 표준 시간대의 날짜/시간을 UTC로 변환하는 수식으로 지정합니다. 예를 들면 다음과 `(Get-Date "5/6/2016 9:30 AM").ToUniversalTime()` 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f0b1e-151">Specify the date/time value as a formula that converts the date/time in your local time zone to UTC: For example, `(Get-Date "5/6/2016 9:30 AM").ToUniversalTime()`.</span></span> <span data-ttu-id="f0b1e-152">자세한 내용은 [Get-Date](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-date)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f0b1e-152">For more information, see [Get-Date](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-date).</span></span>

- <span data-ttu-id="f0b1e-153">이 cmdlet은 기본적으로 최대 1,000개 로그 항목을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f0b1e-153">The cmdlet returns a maximum of 1,000 log entries by default.</span></span> <span data-ttu-id="f0b1e-154">_ResultSize_ 매개 변수를 사용하여 최대 250,000개 로그 항목을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f0b1e-154">Use the _ResultSize_ parameter to specify up to 250,000 log entries.</span></span> <span data-ttu-id="f0b1e-155">또는 값을 사용하여 모든 `Unlimited` 항목을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f0b1e-155">Or, use the value `Unlimited` to return all entries.</span></span>

<span data-ttu-id="f0b1e-156">이 예에서는 다음 기준을 사용하여 모든 감사 로그 항목을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="f0b1e-156">This example performs a search for all audit log entries with the following criteria:</span></span>

- <span data-ttu-id="f0b1e-157">**시작 날짜:** 2019년 8월 4일</span><span class="sxs-lookup"><span data-stu-id="f0b1e-157">**Start date**: August 4, 2019</span></span>
- <span data-ttu-id="f0b1e-158">**종료 날짜:** 2019년 10월 3일</span><span class="sxs-lookup"><span data-stu-id="f0b1e-158">**End date**: October 3, 2019</span></span>
- <span data-ttu-id="f0b1e-159">**cmdlet**: Update-RoleGroupMember</span><span class="sxs-lookup"><span data-stu-id="f0b1e-159">**Cmdlets**: Update-RoleGroupMember</span></span>

```PowerShell
Search-AdminAuditLog -Cmdlets Update-RoleGroupMember -StartDate (Get-Date "08/04/2019").ToUniversalTime() -EndDate (Get-Date "10/03/2019").ToUniversalTime()
```

<span data-ttu-id="f0b1e-160">구문과 매개 변수에 대한 자세한 내용은 [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f0b1e-160">For detailed syntax and parameter information, see [Search-AdminAuditLog](https://docs.microsoft.com/powershell/module/exchange/search-adminauditlog).</span></span>

### <a name="view-details-of-audit-log-entries"></a><span data-ttu-id="f0b1e-161">감사 로그 항목의 상세 정보 보기</span><span class="sxs-lookup"><span data-stu-id="f0b1e-161">View details of audit log entries</span></span>

<span data-ttu-id="f0b1e-162">**Search-AdminAuditLog** cmdlet은 이 문서 부분의 감사 로그 콘텐츠 [섹션에](#audit-log-contents) 설명된 필드를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f0b1e-162">The **Search-AdminAuditLog** cmdlet returns the fields described in the [Audit log contents](#audit-log-contents) section later in this article.</span></span> <span data-ttu-id="f0b1e-163">cmdlet에서 반환되는 필드 중 **CmdletParameters** 및 **ModifiedProperties의** 두 필드에는 기본적으로 반환되지 않는 추가 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0b1e-163">Of the fields returned by the cmdlet, two fields, **CmdletParameters** and **ModifiedProperties**, contain additional information that isn't returned by default.</span></span>

<span data-ttu-id="f0b1e-164">**CmdletParameters** 및 **ModifiedProperties** 필드의 콘텐츠를 보려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="f0b1e-164">To view the contents of the **CmdletParameters** and **ModifiedProperties** fields, use the following steps.</span></span>

1. <span data-ttu-id="f0b1e-165">검색할 기준을 정하고 **Search-AdminAuditLog** cmdlet을 실행한 후 다음 명령을 사용하여 변수에 결과를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="f0b1e-165">Decide the criteria you want to search for, run the **Search-AdminAuditLog** cmdlet, and store the results in a variable using the following command.</span></span>

    ```PowerShell
    $Results = Search-AdminAuditLog <search criteria>
    ```

2. <span data-ttu-id="f0b1e-166">각 감사 로그 항목은 변수에 배열 요소로 `$Results` 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0b1e-166">Each audit log entry is stored as an array element in the variable `$Results`.</span></span> <span data-ttu-id="f0b1e-167">배열 요소 인덱스를 지정하여 배열 요소를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0b1e-167">You can select an array element by specifying its array element index.</span></span> <span data-ttu-id="f0b1e-168">배열 요소 인덱스는 첫 번째 배열 요소에 대해 0에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="f0b1e-168">Array element indexes start at zero (0) for the first array element.</span></span> <span data-ttu-id="f0b1e-169">예를 들어, 인덱스가 4인 5번째 배열 요소를 검색하려면 다음 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f0b1e-169">For example, to retrieve the 5th array element, which has an index of 4, use the following command.</span></span>

    ```PowerShell
    $Results[4]
    ```

3. <span data-ttu-id="f0b1e-p115">이전 명령이 배열 요소 4에 저장된 로그 항목을 반환합니다. 이 로그 항목의 **CmdletParameters** 및 **ModifiedProperties** 필드의 콘텐츠를 보려면 다음 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f0b1e-p115">The previous command returns the log entry stored in array element 4. To see the contents of the **CmdletParameters** and **ModifiedProperties** fields for this log entry, use the following commands.</span></span>

    ```PowerShell
    $Results[4].CmdletParameters
    $Results[4].ModifiedProperties
    ```

4. <span data-ttu-id="f0b1e-172">다른 로그 항목의 **CmdletParameters** 또는 **ModifiedParameters** 필드의 콘텐츠를 보려면 배열 요소 인덱스를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="f0b1e-172">To view the contents of the **CmdletParameters** or **ModifiedParameters** fields in another log entry, change the array element index.</span></span>

## <a name="audit-log-contents"></a><span data-ttu-id="f0b1e-173">감사 로그 콘텐츠</span><span class="sxs-lookup"><span data-stu-id="f0b1e-173">Audit log contents</span></span>

<span data-ttu-id="f0b1e-174">각 감사 로그 항목에는 다음 표에 설명된 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0b1e-174">Each audit log entry contains the information described in the following table.</span></span> <span data-ttu-id="f0b1e-175">감사 로그에는 하나 이상의 감사 로그 항목이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0b1e-175">The audit log contains one or more audit log entries.</span></span>

****

|<span data-ttu-id="f0b1e-176">필드</span><span class="sxs-lookup"><span data-stu-id="f0b1e-176">Field</span></span>|<span data-ttu-id="f0b1e-177">설명</span><span class="sxs-lookup"><span data-stu-id="f0b1e-177">Description</span></span>|
|---|---|
|`RunspaceId`|<span data-ttu-id="f0b1e-178">이 필드는 EOP에서 내부적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0b1e-178">This field is used internally by EOP.</span></span>|
|`ObjectModified`|<span data-ttu-id="f0b1e-179">이 필드에는 필드에 지정된 cmdlet에 의해 수정된 개체가 `CmdletName` 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0b1e-179">This field contains the object that was modified by the cmdlet specified in the `CmdletName` field.</span></span>|
|`CmdletName`|<span data-ttu-id="f0b1e-180">이 필드에는 필드의 사용자가 실행한 cmdlet의 이름이 `Caller` 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0b1e-180">This field contains the name of the cmdlet that was run by the user in the `Caller` field.</span></span>|
|`CmdletParameters`|<span data-ttu-id="f0b1e-181">이 필드에는 필드의 cmdlet이 실행될 때 지정된 매개 `CmdletName` 변수가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0b1e-181">This field contains the parameters that were specified when the cmdlet in the `CmdletName` field was run.</span></span> <span data-ttu-id="f0b1e-182">또한 이 매개 변수로 지정된 값(있는 경우)은 이 필드에 저장되지만 기본 출력에서 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f0b1e-182">Also stored in this field, but not visible in the default output, is the value specified with the parameter, if any.</span></span>|
|`ModifiedProperties`|<span data-ttu-id="f0b1e-183">이 필드에는 필드의 개체에서 수정된 속성이 `ObjectModified` 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0b1e-183">This field contains the properties that were modified on the object in the `ObjectModified` field.</span></span> <span data-ttu-id="f0b1e-184">또한 저장된 속성의 이전 값 및 새 값은 이 필드에 저장되지만 기본 출력에서 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f0b1e-184">Also stored in this field, but not visible in the default output, are the old value of the property and the new value that was stored.</span></span>|
|`Caller`|<span data-ttu-id="f0b1e-185">이 필드에는 필드에서 cmdlet을런 사용자의 사용자 계정이 `CmdletName` 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0b1e-185">This field contains the user account of the user who ran the cmdlet in the `CmdletName` field.</span></span>|
|`ExternalAccess`|<span data-ttu-id="f0b1e-186">이 필드는 EOP에서 내부적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0b1e-186">This field is used internally by EOP.</span></span>|
|`Succeeded`|<span data-ttu-id="f0b1e-187">이 필드는 필드의 cmdlet이 성공적으로 `CmdletName` 성공한지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f0b1e-187">This field specifies whether the cmdlet in the `CmdletName` field ran successfully.</span></span> <span data-ttu-id="f0b1e-188">값은 다음 중 하나 또는 `True` `False` .</span><span class="sxs-lookup"><span data-stu-id="f0b1e-188">The value is either `True` or `False`.</span></span>|
|`Error`|<span data-ttu-id="f0b1e-189">이 필드에는 필드의 cmdlet이 성공적으로 완료되지 못한 경우 생성되는 오류 `CmdletName` 메시지가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0b1e-189">This field contains the error message generated if the cmdlet in the `CmdletName` field failed to complete successfully.</span></span>|
|`RunDate`|<span data-ttu-id="f0b1e-190">이 필드에는 필드의 cmdlet이 실행된 날짜와 시간이 `CmdletName` 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0b1e-190">This field contains the date and time when the cmdlet in the `CmdletName` field was run.</span></span> <span data-ttu-id="f0b1e-191">날짜와 시간은 UTC(협정 세계시) 형식으로 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0b1e-191">The date and time are stored in Coordinated Universal Time (UTC) format.</span></span>|
|`OriginatingServer`|<span data-ttu-id="f0b1e-192">이 필드는 필드에 지정된 cmdlet이 실행된 서버를 `CmdletName` 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f0b1e-192">This field indicates the server on which the cmdlet specified in the `CmdletName` field was run.</span></span>|
|`ClientIP`|<span data-ttu-id="f0b1e-193">이 필드는 EOP에서 내부적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0b1e-193">This field is used internally by EOP.</span></span>|
|`SessionId`|<span data-ttu-id="f0b1e-194">이 필드는 EOP에서 내부적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0b1e-194">This field is used internally by EOP.</span></span>|
|`AppId`|<span data-ttu-id="f0b1e-195">이 필드는 EOP에서 내부적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0b1e-195">This field is used internally by EOP.</span></span>|
|`ClientAppId`|<span data-ttu-id="f0b1e-196">이 필드는 EOP에서 내부적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0b1e-196">This field is used internally by EOP.</span></span>|
|`Identity`|<span data-ttu-id="f0b1e-197">이 필드는 EOP에서 내부적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0b1e-197">This field is used internally by EOP.</span></span>|
|`IsValid`|<span data-ttu-id="f0b1e-198">이 필드는 EOP에서 내부적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0b1e-198">This field is used internally by EOP.</span></span>|
|`ObjectState`|<span data-ttu-id="f0b1e-199">이 필드는 EOP에서 내부적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0b1e-199">This field is used internally by EOP.</span></span>|
|
