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
ms.openlocfilehash: 08b028bbd28c06684245321e09f8ef3252098956
ms.sourcegitcommit: a53af7a228bb1f58cb8128a69a19da49f9e28700
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/23/2020
ms.locfileid: "45372491"
---
# <a name="records-management-in-microsoft-365"></a><span data-ttu-id="3f860-103">Microsoft 365의 레코드 관리</span><span class="sxs-lookup"><span data-stu-id="3f860-103">Records management in Microsoft 365</span></span>

><span data-ttu-id="3f860-104">*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](https://aka.ms/ComplianceSD)*</span><span class="sxs-lookup"><span data-stu-id="3f860-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="3f860-105">모든 유형의 조직에는 레코드 관리 솔루션이 있어야 회사 데이터에서 규정, 법률 및 비즈니스에 중요한 레코드를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f860-105">Organizations of all types require a records-management solution to manage regulatory, legal, and business-critical records across their corporate data.</span></span> <span data-ttu-id="3f860-106">Microsoft 365의 레코드 관리는 조직이 법적인 의무를 관리하는 데 도움이 되고, 규정 준수를 입증하는 기능을 제공하며, 비즈니스 목적에 대해 더 이상 보존할 필요가 없거나, 더 이상 가치가 없거나, 사용하지 않는 항목을 정기적으로 처리하여 효율성을 높입니다.</span><span class="sxs-lookup"><span data-stu-id="3f860-106">Records management in Microsoft 365 helps an organization manage their legal obligations, provides the ability to demonstrate compliance with regulations, and increases efficiency with regular disposition of items that are no longer required to be retained, no longer of value, or no longer required for business purposes.</span></span>

<span data-ttu-id="3f860-107">Microsoft 365의 레코드 관리는 다음과 같은 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3f860-107">Records management in Microsoft 365 provides the following capabilities:</span></span>

- <span data-ttu-id="3f860-108">**콘텐츠를 레코드로 레이블**</span><span class="sxs-lookup"><span data-stu-id="3f860-108">**Label content as a record**.</span></span> <span data-ttu-id="3f860-109">콘텐츠를 [레코드](records.md)로 표시하여 사용자가 적용하거나 중요한 정보, 키워드 또는 콘텐츠 유형을 식별하여 [자동으로 적용](apply-retention-labels-automatically.md)하기 위해 보존 레이블을 작성하고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="3f860-109">Create and configure retention labels to mark content as a [record](records.md) that can then be applied by users or [auto-applied](apply-retention-labels-automatically.md) by identifying sensitive information, keywords, or content types.</span></span>

- <span data-ttu-id="3f860-110">**파일 계획을 사용하여 보존 요구 사항을 마이그레이션하고 관리합니다**.</span><span class="sxs-lookup"><span data-stu-id="3f860-110">**Migrate and manage your retention requirements with file plan**.</span></span> <span data-ttu-id="3f860-111">[파일 계획](file-plan-manager.md)을 사용하여 기존 보존 계획을 Microsoft 365으로 가져오거나 개선된 관리 기능을 위해 새 계획을 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f860-111">By using a [file plan](file-plan-manager.md), you can bring in an existing retention plan to Microsoft 365, or build a new one for enhanced management capabilities.</span></span>

- <span data-ttu-id="3f860-112">**보존 레이블을 사용하여 보존 및 삭제 설정을 구성**합니다.</span><span class="sxs-lookup"><span data-stu-id="3f860-112">**Configure retention and deletion settings with the retention label**.</span></span> <span data-ttu-id="3f860-113">마지막으로 수정 또는 생성된 날짜를 비롯한 다양한 요소를 기반으로 보존 기간 및 작업을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="3f860-113">Define retention periods and actions based on various factors that include the date last modified or created.</span></span>

- <span data-ttu-id="3f860-114">[이벤트 기반 보존\*\*을 사용하여 \*\*이벤트가 발생하는 경우 다른 보존 기간을 시작](event-driven-retention.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3f860-114">**Start different retention periods when an event occurs** with [event-based retention](event-driven-retention.md).</span></span>

- <span data-ttu-id="3f860-115">[처리 검토](disposition.md#disposition-reviews) 및 [레코드 삭제](disposition.md#disposition-of-records) 검사를 통해 **처리를 검토하고 확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="3f860-115">**Review and validate disposition** with [disposition reviews](disposition.md#disposition-reviews) and proof of [records deletion](disposition.md#disposition-of-records).</span></span>

- <span data-ttu-id="3f860-116">[내보내기 옵션](disposition.md#filter-and-export-the-views)으로 **모든 처리된 항목에 대한 정보를 내보냅니다**.</span><span class="sxs-lookup"><span data-stu-id="3f860-116">**Export information about all disposed items** with the [export option](disposition.md#filter-and-export-the-views).</span></span>

- <span data-ttu-id="3f860-117">조직 레코드 관리자 기능의 **특정 권한을 설정**하여 [올바른 액세스 권한을 보유](../security/office-365-security/permissions-in-the-security-and-compliance-center.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3f860-117">**Set specific permissions** for records manager functions in your organization to [have the right access](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="3f860-118">Microsoft 365의 레코드 관리 솔루션을 사용하면 조직의 보존 일정 및 요구 사항을 파일 계획에 통합하여 보존, 레코드 선언 및 처리를 관리하여 컨텐츠의 전체 라이프사이클을 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f860-118">With the records-management solution in Microsoft 365, you can incorporate your organization's retention schedules and requirements into a file plan that manages retention, records declaration, and disposition to support the full lifecycle of your content.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3f860-119">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="3f860-119">Additional resources</span></span>

<span data-ttu-id="3f860-120">레코드 관리에 대한 [웨비나 녹음](https://aka.ms/MIPC/Video-RecordsManagementWebinar) 및 [FAQ를 포함한 데크](https://aka.ms/MIPC/Blog-RecordsManagementWebinar)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3f860-120">See the [webinar recording](https://aka.ms/MIPC/Video-RecordsManagementWebinar) and [deck with FAQs](https://aka.ms/MIPC/Blog-RecordsManagementWebinar) for records management.</span></span>

## <a name="next-steps"></a><span data-ttu-id="3f860-121">다음 단계</span><span class="sxs-lookup"><span data-stu-id="3f860-121">Next steps</span></span>

<span data-ttu-id="3f860-122">Microsoft 365에서 레코드 관리를 시작할 준비가 되었으면 [레코드에 대해 알아보기](records.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3f860-122">If you are ready to get started with records management in Microsoft 365, see [Learn about records](records.md).</span></span>
