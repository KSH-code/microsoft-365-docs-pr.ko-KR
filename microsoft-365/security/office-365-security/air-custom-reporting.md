---
title: 자동화된 조사 및 응답이 있는 사용자 지정 보고 솔루션
keywords: SIEM, API, AIR, autoIR, ATP, 자동화된 조사, 통합, 사용자 지정 보고서
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 자동화된 조사 및 대응을 사용자 지정 또는 타사 보고 솔루션과 통합하는 방법을 알아보십시오.
ms.date: 01/29/2021
ms.custom:
- air
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3d8363ada4de60d37cb0d247d8b1af74df4226d1
ms.sourcegitcommit: d739f48b991793c08522a3d5323beba27f0111b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/08/2021
ms.locfileid: "50142978"
---
# <a name="custom-or-third-party-reporting-solutions-for-microsoft-defender-for-office-365"></a><span data-ttu-id="816b1-104">Office 365용 Microsoft Defender에 대한 사용자 지정 또는 타사 보고 솔루션</span><span class="sxs-lookup"><span data-stu-id="816b1-104">Custom or third-party reporting solutions for Microsoft Defender for Office 365</span></span>

<span data-ttu-id="816b1-105">[Office 365용 Microsoft Defender를](office-365-atp.md)사용하면 자동화된 조사에 대한 자세한 [정보를 얻을 수 있습니다.](air-view-investigation-results.md)</span><span class="sxs-lookup"><span data-stu-id="816b1-105">With [Microsoft Defender for Office 365](office-365-atp.md), you get [detailed information about automated investigations](air-view-investigation-results.md).</span></span> <span data-ttu-id="816b1-106">그러나 일부 조직에서는 사용자 지정 또는 타사 보고 솔루션도 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="816b1-106">However, some organizations also use a custom or third-party reporting solution.</span></span> <span data-ttu-id="816b1-107">조직에서 자동화된 조사에 [](office-365-air.md) 대한 정보를 이러한 솔루션과 통합하려는 경우 Office 365 관리 활동 API를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="816b1-107">If your organization wants to integrate information about [automated investigations](office-365-air.md) with such a solution, you can use the Office 365 Management Activity API.</span></span>

<span data-ttu-id="816b1-108">통합을 구성하기 위한 리소스</span><span class="sxs-lookup"><span data-stu-id="816b1-108">Resources to configure integration</span></span>

|<span data-ttu-id="816b1-109">리소스</span><span class="sxs-lookup"><span data-stu-id="816b1-109">Resource</span></span>|<span data-ttu-id="816b1-110">설명</span><span class="sxs-lookup"><span data-stu-id="816b1-110">Description</span></span>|
|:---|:---|
|[<span data-ttu-id="816b1-111">Office 365 관리 API 개요</span><span class="sxs-lookup"><span data-stu-id="816b1-111">Office 365 Management APIs overview</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)|<span data-ttu-id="816b1-112">Office 365 관리 활동 API는 Microsoft 365 및 Azure Active Directory 활동 로그의 다양한 사용자, 관리자, 시스템 및 정책 작업 및 이벤트에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="816b1-112">The Office 365 Management Activity API provides information about various user, admin, system, and policy actions and events from Microsoft 365 and Azure Active Directory activity logs.</span></span>|
|[<span data-ttu-id="816b1-113">Office 365 관리 API 시작</span><span class="sxs-lookup"><span data-stu-id="816b1-113">Get started with Office 365 Management APIs</span></span>](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)|<span data-ttu-id="816b1-114">Office 365 관리 API는 Azure AD를 사용하여 응용 프로그램에서 Microsoft 365 데이터에 액세스할 수 있는 인증 서비스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="816b1-114">The Office 365 Management API uses Azure AD to provide authentication services for your application to access Microsoft 365 data.</span></span> <span data-ttu-id="816b1-115">이 문서의 단계에 따라 이 단계를 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="816b1-115">Follow the steps in this article to set this up.</span></span>|
|[<span data-ttu-id="816b1-116">Office 365 관리 작업 API 참고자료</span><span class="sxs-lookup"><span data-stu-id="816b1-116">Office 365 Management Activity API reference</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)|<span data-ttu-id="816b1-117">Office 365 관리 활동 API를 사용하여 Microsoft 365 및 Azure AD 활동 로그에서 사용자, 관리자, 시스템 및 정책 작업 및 이벤트에 대한 정보를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="816b1-117">You can use the Office 365 Management Activity API to retrieve information about user, admin, system, and policy actions and events from Microsoft 365 and Azure AD activity logs.</span></span> <span data-ttu-id="816b1-118">이 문서의 작동 방식에 대해 자세히 알아보고자 합니다.</span><span class="sxs-lookup"><span data-stu-id="816b1-118">Read this article to learn more about how this works.</span></span>|
|[<span data-ttu-id="816b1-119">Office 365 관리 작업 API 스키마</span><span class="sxs-lookup"><span data-stu-id="816b1-119">Office 365 Management Activity API schema</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)|<span data-ttu-id="816b1-120">Office 365용 [Common schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) 및 [Defender for Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) 및 위협 조사 및 응답 계획에 대한 개요를 확인하여 Office 365 관리 활동 API를 통해 사용할 수 있는 특정 종류의 데이터에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="816b1-120">Get an overview of the [Common schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) and the [Defender for Office 365 and threat investigation and response schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) to learn about specific kinds of data available through the Office 365 Management Activity API.</span></span>|
|

## <a name="see-also"></a><span data-ttu-id="816b1-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="816b1-121">See also</span></span>

- [<span data-ttu-id="816b1-122">Office 365용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="816b1-122">Microsoft Defender for Office 365</span></span>](office-365-atp.md)
- [<span data-ttu-id="816b1-123">Microsoft 365 Defender의 자동화된 조사 및 대응</span><span class="sxs-lookup"><span data-stu-id="816b1-123">Automated investigation and response in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
