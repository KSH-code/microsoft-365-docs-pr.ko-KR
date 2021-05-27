---
title: Microsoft 365의 Microsoft 정보 거버넌스
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
recommendations: false
description: Microsoft 정보 거버넌스 기능을 구현하여 규정 준수 또는 규제 요구 사항에 대한 데이터를 관리합니다.
ms.openlocfilehash: a62b1a20aa07c8b5d147fd24e3867c4d4c50174e
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683538"
---
# <a name="microsoft-information-governance-in-microsoft-365"></a><span data-ttu-id="f3658-103">Microsoft 365의 Microsoft 정보 거버넌스</span><span class="sxs-lookup"><span data-stu-id="f3658-103">Microsoft Information Governance in Microsoft 365</span></span>

><span data-ttu-id="f3658-104">*[보안 및 규정 준수에 대한 Microsoft 365 라이선싱 지침](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span><span class="sxs-lookup"><span data-stu-id="f3658-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

<span data-ttu-id="f3658-105">Microsoft 정보 거버넌스(MIG) 기능을 사용하여 규정 준수 또는 규제 요구 사항에 대한 데이터를 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="f3658-105">Use Microsoft Information Governance (sometimes abbreviated to MIG) capabilities to govern your data for compliance or regulatory requirements.</span></span>

![데이터 관리 - 정보 거버넌스 및 레코드 관리](../media/information-governance-records-management.png)

<span data-ttu-id="f3658-107">데이터 보호에 대해 찾고 있으신가요?</span><span class="sxs-lookup"><span data-stu-id="f3658-107">Looking to protect your data?</span></span> <span data-ttu-id="f3658-108">[Microsoft 365의 Microsoft 정보 보호](information-protection.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f3658-108">See [Microsoft Information Protection in Microsoft 365](information-protection.md).</span></span>

<span data-ttu-id="f3658-p102">Microsoft는 사용자가 데이터 개인 정보 보호 규정을 준수할 수 있도록 안전한 액세스, 위협 방지, 정보 보호, 데이터 거버넌스를 비롯한 Microsoft 365 전반에서 기능을 계획하고 구현하기 위한 종단 간 프로세스를 안내하는 워크플로를 설계했습니다. 자세한 내용은 [Microsoft 365로 데이터 개인 정보 보호 규정에 대한 정보 보호 배포(](../solutions/information-protection-deploy.md)(aka.ms/m365dataprivacy)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f3658-p102">To help you comply with data privacy regulations, we’ve designed a workflow to guide you through an end-to-end process to plan and implement capabilities across Microsoft 365, including secure access, threat protection, information protection, and data governance. For more information, see [Deploy information protection for data privacy regulations with Microsoft 365](../solutions/information-protection-deploy.md) (aka.ms/m365dataprivacy).</span></span> 

## <a name="information-governance"></a><span data-ttu-id="f3658-111">정보 거버넌스</span><span class="sxs-lookup"><span data-stu-id="f3658-111">Information governance</span></span>

<span data-ttu-id="f3658-112">필요한 사항은 보존하고 필요하지 않은 사항을 삭제하려면 다음과 같이 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="f3658-112">To keep what you need and delete what you don't:</span></span>
 
|<span data-ttu-id="f3658-113">기능</span><span class="sxs-lookup"><span data-stu-id="f3658-113">Capability</span></span>|<span data-ttu-id="f3658-114">어떤 문제를 해결하나요?</span><span class="sxs-lookup"><span data-stu-id="f3658-114">What problems does it solve?</span></span>|<span data-ttu-id="f3658-115">시작</span><span class="sxs-lookup"><span data-stu-id="f3658-115">Get started</span></span>|
|:------|:------------|:--------------------|:-----------------------------|
|[<span data-ttu-id="f3658-116">보존 정책 및 보존 레이블</span><span class="sxs-lookup"><span data-stu-id="f3658-116">Retention policies and retention labels</span></span>](retention.md)| <span data-ttu-id="f3658-117">정책 관리와 전자 메일, 문서, 인스턴트 메시지 등의 삭제 워크플로를 사용하여 콘텐츠 보존 또는 삭제</span><span class="sxs-lookup"><span data-stu-id="f3658-117">Retain or delete content with policy management and a deletion workflow for email, documents, instant messages, and more</span></span> <br /><br /><span data-ttu-id="f3658-118">시나리오 예시: [보존 레이블을 콘텐츠에 자동으로 적용](apply-retention-labels-automatically.md)</span><span class="sxs-lookup"><span data-stu-id="f3658-118">Example scenario: [Apply a retention label to content automatically](apply-retention-labels-automatically.md)</span></span> | [<span data-ttu-id="f3658-119">보존 정책 및 보존 레이블 시작하기</span><span class="sxs-lookup"><span data-stu-id="f3658-119">Get started with retention policies and retention labels</span></span>](get-started-with-retention.md)|
|[<span data-ttu-id="f3658-120">서비스 가져오기</span><span class="sxs-lookup"><span data-stu-id="f3658-120">Import service</span></span>](importing-pst-files-to-office-365.md)| <span data-ttu-id="f3658-121">Exchange Online 사서함으로 PST 파일을 대량으로 가져오고 규정 준수 또는 규제 요구 사항에 대한 전자 메일 메시지를 보존하고 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3658-121">Bulk-import PST files to Exchange Online mailboxes to retain and search email messages for compliance or regulatory requirements</span></span> | [<span data-ttu-id="f3658-122">네트워크 업로드를 사용하여 조직의 PST 파일을 Microsoft 365로 가져오기</span><span class="sxs-lookup"><span data-stu-id="f3658-122">Use network upload to import your organization's PST files to Microsoft 365</span></span>](use-network-upload-to-import-pst-files.md)|
|[<span data-ttu-id="f3658-123">타사 데이터 보관</span><span class="sxs-lookup"><span data-stu-id="f3658-123">Archive third-party data</span></span>](archiving-third-party-data.md)| <span data-ttu-id="f3658-124">소셜 미디어 플랫폼, 인스턴트 메시징 플랫폼 및 문서 공동 작업 플랫폼에서 타사 데이터에 준수 솔루션 가져오기, 보관 및 적용하기</span><span class="sxs-lookup"><span data-stu-id="f3658-124">Import, archive, and apply compliance solutions to third-party data from social media platforms, instant messaging platforms, and document collaboration platforms</span></span>| [<span data-ttu-id="f3658-125">타사 커넥터</span><span class="sxs-lookup"><span data-stu-id="f3658-125">Third-party connectors</span></span>](archiving-third-party-data.md#third-party-data-connectors)|
|[<span data-ttu-id="f3658-126">비활성 사서함</span><span class="sxs-lookup"><span data-stu-id="f3658-126">Inactive mailboxes</span></span>](inactive-mailboxes-in-office-365.md)| <span data-ttu-id="f3658-127">직원이 조직을 떠난 후 사서함 콘텐츠 보존</span><span class="sxs-lookup"><span data-stu-id="f3658-127">Retain mailbox content after employees leave the organization</span></span> | [<span data-ttu-id="f3658-128">비활성 사서함 생성 및 관리</span><span class="sxs-lookup"><span data-stu-id="f3658-128">Create and manage inactive mailboxes</span></span>](create-and-manage-inactive-mailboxes.md)|

## <a name="records-management"></a><span data-ttu-id="f3658-129">레코드 관리</span><span class="sxs-lookup"><span data-stu-id="f3658-129">Records management</span></span>

<span data-ttu-id="f3658-130">법적, 비즈니스 또는 규제 의무 사항에 대해 가치가 높은 콘텐츠를 관리하려면 다음과 같이 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="f3658-130">To manage high-value content for legal, business, or regulatory obligations:</span></span>

|<span data-ttu-id="f3658-131">기능</span><span class="sxs-lookup"><span data-stu-id="f3658-131">Capability</span></span>|<span data-ttu-id="f3658-132">어떤 문제를 해결하나요?</span><span class="sxs-lookup"><span data-stu-id="f3658-132">What problems does it solve?</span></span>|<span data-ttu-id="f3658-133">시작</span><span class="sxs-lookup"><span data-stu-id="f3658-133">Get started</span></span>|
|:------|:------------|---------------------|:----------------------------|
|[<span data-ttu-id="f3658-134">레코드 관리</span><span class="sxs-lookup"><span data-stu-id="f3658-134">Records management</span></span>](records-management.md)| <span data-ttu-id="f3658-135">레코드 선언, 보존 및 처리를 사용하여 콘텐츠의 전체 수명을 지원하는 파일 계획에서 보존 일정 및 요구 사항을 통합하는 전자 메일 및 문서에 대한 단일 솔루션</span><span class="sxs-lookup"><span data-stu-id="f3658-135">A single solution for email and documents that incorporates retention schedules and requirements into a file plan that supports the full lifecycle of your content with records declaration, retention, and disposition</span></span> <br /><br /><span data-ttu-id="f3658-136">시나리오 예시: [레코드의 처리](disposition.md#disposition-of-records)</span><span class="sxs-lookup"><span data-stu-id="f3658-136">Example scenario: [Disposition of records](disposition.md#disposition-of-records)</span></span>|[<span data-ttu-id="f3658-137">레코드 관리 시작</span><span class="sxs-lookup"><span data-stu-id="f3658-137">Get started with records management</span></span>](get-started-with-records-management.md) |

## <a name="licensing-requirements"></a><span data-ttu-id="f3658-138">라이선스 요구사항</span><span class="sxs-lookup"><span data-stu-id="f3658-138">Licensing requirements</span></span>

<span data-ttu-id="f3658-139">Microsoft 정보 거버넌스에 대한 라이선스 요구 사항은 이 페이지에 나열된 각 기능에 대한 라이선스 요구 사항을 설정하는 것이 아니라 사용하는 시나리오 및 기능에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="f3658-139">License requirements for Microsoft Information Governance depend on the scenarios and features you use, rather than set licensing requirements for each capability listed on this page.</span></span> <span data-ttu-id="f3658-140">라이선스 요구 사항 및 옵션을 이해하려면 Microsoft 365 라이선싱 설명서의 [정보 거버넌스](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance) 및 [레코드 관리](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#records-management) 섹션을 참조하고 관련 PDF 또는 Excel을 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="f3658-140">To understand your licensing requirements and options, see the [Information Governance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance) and [Records Management](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#records-management) sections from the Microsoft 365 licensing documentation, and download the related PDF or Excel.</span></span>