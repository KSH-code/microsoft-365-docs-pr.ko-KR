---
title: 레코드 관리
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: Microsoft 365의 레코드 관리를 사용하여 보존 일정을 파일 플랜에 적용하여 보존, 레코드 선언, 처리를 관리할 수 있습니다.
ms.openlocfilehash: 48705ac6d0c271ca2646de7c058a340ee3f736ae
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818958"
---
# <a name="records-management-in-microsoft-365"></a><span data-ttu-id="7ef4a-103">Microsoft 365의 레코드 관리</span><span class="sxs-lookup"><span data-stu-id="7ef4a-103">Records management in Microsoft 365</span></span>

><span data-ttu-id="7ef4a-104">*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](https://aka.ms/ComplianceSD)*</span><span class="sxs-lookup"><span data-stu-id="7ef4a-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="7ef4a-105">모든 유형의 조직에는 레코드 관리 솔루션이 있어야 회사 데이터에서 규정, 법률 및 비즈니스에 중요한 레코드를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ef4a-105">Organizations of all types require a records-management solution to manage regulatory, legal, and business-critical records across their corporate data.</span></span> <span data-ttu-id="7ef4a-106">Microsoft 365의 레코드 관리는 조직이 법적인 의무를 관리하는 데 도움이 되고, 규정 준수를 입증하는 기능을 제공하며, 비즈니스 목적에 대해 더 이상 보존할 필요가 없거나, 더 이상 가치가 없거나, 사용하지 않는 항목을 정기적으로 처리하여 효율성을 높입니다.</span><span class="sxs-lookup"><span data-stu-id="7ef4a-106">Records management in Microsoft 365 helps an organization manage their legal obligations, provides the ability to demonstrate compliance with regulations, and increases efficiency with regular disposition of items that are no longer required to be retained, no longer of value, or no longer required for business purposes.</span></span>

<span data-ttu-id="7ef4a-107">Microsoft 365의 레코드 관리는 다음과 같은 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7ef4a-107">Records management in Microsoft 365 provides the following capabilities:</span></span>

- <span data-ttu-id="7ef4a-108">**콘텐츠를 레코드로 레이블**</span><span class="sxs-lookup"><span data-stu-id="7ef4a-108">**Label content as a record**.</span></span> <span data-ttu-id="7ef4a-109">콘텐츠를 [레코드](records.md)로 표시하여 최종 사용자가 적용하거나 중요한 정보, 키워드 또는 콘텐츠 유형을 식별하여 [자동으로 적용](labels.md#applying-a-retention-label-automatically-based-on-conditions)할 수 있는 보존 레이블을 작성하고 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="7ef4a-109">Create and publish retention labels that mark content as a [record](records.md) that can then be applied by end users or [auto-applied](labels.md#applying-a-retention-label-automatically-based-on-conditions) by identifying sensitive information, keywords, or content types.</span></span>

- <span data-ttu-id="7ef4a-110">**파일 계획을 사용하여 보존 요구 사항을 마이그레이션하고 관리합니다**.</span><span class="sxs-lookup"><span data-stu-id="7ef4a-110">**Migrate and manage your retention requirements with file plan**.</span></span> <span data-ttu-id="7ef4a-111">[파일 계획](file-plan-manager.md)을 사용하여 기존 보존 계획을 Microsoft 365으로 가져오거나 개선된 관리 기능을 위해 새 계획을 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ef4a-111">By using a [file plan](file-plan-manager.md), you can bring in an existing retention plan to Microsoft 365, or build a new one for enhanced management capabilities.</span></span>

- <span data-ttu-id="7ef4a-112">**레코드 레이블 내에 보존 및 삭제 정책을 설정합니다**.</span><span class="sxs-lookup"><span data-stu-id="7ef4a-112">**Establish retention and deletion policies within the record label**.</span></span> <span data-ttu-id="7ef4a-113">마지막으로 수정 또는 생성된 날짜를 비롯하여 다양한 요소를 기반으로 [보존](create-retention-policies.md#retaining-content-for-a-specific-period-of-time) 및 [처리](create-retention-policies.md#deleting-content-thats-older-than-a-specific-age) 기간을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7ef4a-113">Define [retention](create-retention-policies.md#retaining-content-for-a-specific-period-of-time) and [disposition](create-retention-policies.md#deleting-content-thats-older-than-a-specific-age) periods based on various factors that include the date last modified or created.</span></span>

- <span data-ttu-id="7ef4a-114">[이벤트 기반 보존](event-driven-retention.md)을 통해 **이벤트 기반 보존을 트리거**합니다.</span><span class="sxs-lookup"><span data-stu-id="7ef4a-114">**Trigger event-based retention** with [event-based retention](event-driven-retention.md).</span></span>

- <span data-ttu-id="7ef4a-115">[처리 검토](disposition.md#disposition-reviews) 및 [레코드 삭제](disposition.md#disposition-of-records) 검사를 통해 **처리를 검토하고 확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="7ef4a-115">**Review and validate disposition** with [disposition reviews](disposition.md#disposition-reviews) and proof of [records deletion](disposition.md#disposition-of-records).</span></span>

- <span data-ttu-id="7ef4a-116">[내보내기 옵션](disposition.md#filter-and-export-the-views)으로 **모든 처리된 항목에 대한 정보를 내보냅니다**.</span><span class="sxs-lookup"><span data-stu-id="7ef4a-116">**Export information about all disposed items** with the [export option](disposition.md#filter-and-export-the-views).</span></span>

- <span data-ttu-id="7ef4a-117">조직 레코드 관리자 기능의 **특정 권한을 설정**하여 [올바른 액세스 권한을 보유](../security/office-365-security/permissions-in-the-security-and-compliance-center.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7ef4a-117">**Set specific permissions** for records manager functions in your organization to [have the right access](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="7ef4a-118">Microsoft 365의 레코드 관리 솔루션을 사용하여 조직의 보존 일정을 파일 플랜에 반영하여 콘텐츠의 전체 수명 주기를 지원하는 보존, 레코드 선언, 처리를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ef4a-118">With the records-management solution in Microsoft 365, you can incorporate your organization’s retention schedules into the file plan to manage retention, records declaration, and disposition to support the full lifecycle of your content.</span></span>

## <a name="next-steps"></a><span data-ttu-id="7ef4a-119">다음 단계</span><span class="sxs-lookup"><span data-stu-id="7ef4a-119">Next steps</span></span>

<span data-ttu-id="7ef4a-120">Microsoft 365에서 레코드 관리를 시작할 준비가 되었으면 [레코드에 대해 알아보기](records.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7ef4a-120">If you are ready to get started with records management in Microsoft 365, see [Learn about records](records.md).</span></span>
