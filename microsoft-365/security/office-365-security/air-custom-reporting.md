---
title: Office 365의 자동화 된 조사 및 응답과 함께 사용자 지정 보고 솔루션 사용
keywords: AIR, autoIR, ATP, 자동화, 조사, 대응, 재구성, 위협, 고급, 위협, 보호
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: 사용자 지정 또는 타사 보고 솔루션을 사용 하 여 Office 365 자동화 조사 및 응답을 통합 하는 방법을 알아봅니다.
ms.openlocfilehash: 3df69c9118b3170924a99a1787761b1bb07aadfa
ms.sourcegitcommit: 2f117a6fd27a097ca25afa933dd088b69d483974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/20/2020
ms.locfileid: "42175952"
---
# <a name="use-the-office-365-management-activity-api-for-custom-or-third-party-reporting-solutions"></a><span data-ttu-id="086af-104">사용자 지정 또는 타사 보고 솔루션에 Office 365 관리 활동 API 사용</span><span class="sxs-lookup"><span data-stu-id="086af-104">Use the Office 365 Management Activity API for custom or third-party reporting solutions</span></span>

<span data-ttu-id="086af-105">[Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)을 사용 하 여 [자동화 된 조사에 대 한 자세한 정보](air-view-investigation-results.md)를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="086af-105">With [Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp), you get [detailed information about automated investigations](air-view-investigation-results.md).</span></span> <span data-ttu-id="086af-106">그러나 일부 조직에서는 사용자 지정 또는 타사 보고 솔루션을 사용 하기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="086af-106">However, some organizations also use a custom or third-party reporting solution.</span></span> <span data-ttu-id="086af-107">조직에서 이러한 솔루션을 통해 자동화 된 조사에 대 한 정보를 통합 하려는 경우에는 Office 365 관리 활동 API를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="086af-107">If your organization wants to integrate information about automated investigations with such a solution, you can use the Office 365 Management Activity API.</span></span>

<span data-ttu-id="086af-108">다음 리소스를 사용 하 여이를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="086af-108">Use the following resources to set this up:</span></span>

|<span data-ttu-id="086af-109">리소스</span><span class="sxs-lookup"><span data-stu-id="086af-109">Resource</span></span>  |<span data-ttu-id="086af-110">설명</span><span class="sxs-lookup"><span data-stu-id="086af-110">Description</span></span>  |
|---------|---------|
|[<span data-ttu-id="086af-111">Office 365 관리 Api 개요</span><span class="sxs-lookup"><span data-stu-id="086af-111">Office 365 Management APIs overview</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)     |<span data-ttu-id="086af-112">Office 365 관리 활동 API는 Office 365 및 Azure Active Directory 활동 로그에서 다양 한 사용자, 관리자, 시스템 및 정책 작업과 이벤트에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="086af-112">The Office 365 Management Activity API provides information about various user, admin, system, and policy actions and events from Office 365 and Azure Active Directory activity logs.</span></span>         |
|[<span data-ttu-id="086af-113">Office 365 관리 Api 시작 하기</span><span class="sxs-lookup"><span data-stu-id="086af-113">Get started with Office 365 Management APIs</span></span>](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)     |<span data-ttu-id="086af-114">Office 365 관리 API는 Azure AD를 사용 하 여 응용 프로그램에서 Office 365 데이터에 액세스 하는 데 필요한 인증 서비스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="086af-114">The Office 365 Management API uses Azure AD to provide authentication services for your application to access Office 365 data.</span></span> <span data-ttu-id="086af-115">이 문서에서 설명 하는 단계에 따라 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="086af-115">Follow the steps in this article to set this up.</span></span>          |
|[<span data-ttu-id="086af-116">Office 365 관리 활동 API 참조</span><span class="sxs-lookup"><span data-stu-id="086af-116">Office 365 Management Activity API reference</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)     |<span data-ttu-id="086af-117">Office 365 관리 활동 API를 사용 하 여 Office 365 및 Azure AD 활동 로그에서 사용자, 관리자, 시스템 및 정책 작업과 이벤트에 대 한 정보를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="086af-117">You can use the Office 365 Management Activity API to retrieve information about user, admin, system, and policy actions and events from Office 365 and Azure AD activity logs.</span></span> <span data-ttu-id="086af-118">이 문서를 읽으면 작동 방식에 대해 자세히 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="086af-118">Read this article to learn more about how this works.</span></span>        |
|[<span data-ttu-id="086af-119">Office 365 관리 활동 API 스키마</span><span class="sxs-lookup"><span data-stu-id="086af-119">Office 365 Management Activity API schema</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)     |<span data-ttu-id="086af-120">Office 365 관리 활동 API를 통해 사용할 수 있는 특정 종류의 데이터에 대 한 자세한 내용은 [일반 스키마](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) 및 [Office 365 ATP 및 위협 조사 및 응답 스키마](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) 개요를 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="086af-120">Get an overview of the [Common schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) and the [Office 365 ATP and threat investigation and response schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) to learn about specific kinds of data available through the Office 365 Management Activity API.</span></span>         |

## <a name="related-articles"></a><span data-ttu-id="086af-121">관련 문서</span><span class="sxs-lookup"><span data-stu-id="086af-121">Related articles</span></span>

- [<span data-ttu-id="086af-122">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="086af-122">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)

- [<span data-ttu-id="086af-123">Microsoft Threat Protection의 자동화 된 조사 및 응답에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="086af-123">Learn about automated investigation and response in Microsoft Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)