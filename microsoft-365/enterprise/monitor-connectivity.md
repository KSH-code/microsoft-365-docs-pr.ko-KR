---
title: Microsoft 365 연결 모니터링
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 8/4/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 53cdb60c-a6b2-4848-b3ff-e7b75dc3fd1f
description: 이 문서에서는 연결 연결을 모니터링하고 유지 관리하는 데 사용할 수 있는 도구와 기술을 Microsoft 365 있습니다.
ms.openlocfilehash: 8fa0820cf9b7778001be5184041e5c96930a29dd
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924202"
---
# <a name="monitor-microsoft-365-connectivity"></a><span data-ttu-id="defbe-103">Microsoft 365 연결 모니터링</span><span class="sxs-lookup"><span data-stu-id="defbe-103">Monitor Microsoft 365 connectivity</span></span>

<span data-ttu-id="defbe-104">배포한 Microsoft 365 아래 도구와 기술을 사용하여 Microsoft 365 연결을 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="defbe-104">Once you've deployed Microsoft 365, you can maintain Microsoft 365 connectivity using some of the tools and techniques below.</span></span> <span data-ttu-id="defbe-105">공식적인 서비스 상태 및 [](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity) 연속성 지침과 느린 네트워크에서 Microsoft 365 모범 [사례를 이해해야 합니다.](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166)</span><span class="sxs-lookup"><span data-stu-id="defbe-105">You'll want to understand the official [Service Health and Continuity](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity) guidelines as well as our [Best practices for using Microsoft 365 on a slow network](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166).</span></span> <span data-ttu-id="defbe-106">또한 비즈니스용 Microsoft 365 앱의 책갈피를 잡고 비즈니스용 Microsoft 365 - 관리자 도움말을 책갈피로 [설정해야 합니다.](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791) [](https://blogs.office.com/2015/03/13/administer-on-the-go-with-the-updated-office-365-admin-app/)</span><span class="sxs-lookup"><span data-stu-id="defbe-106">You'll also want to grab the [Microsoft 365 admin app](https://blogs.office.com/2015/03/13/administer-on-the-go-with-the-updated-office-365-admin-app/) and bookmark our [Microsoft 365 for business - Admin Help](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791).</span></span>
  
## <a name="monitoring-microsoft-365-connectivity"></a><span data-ttu-id="defbe-107">연결 Microsoft 365 모니터링</span><span class="sxs-lookup"><span data-stu-id="defbe-107">Monitoring Microsoft 365 Connectivity</span></span>

|<span data-ttu-id="defbe-108">모니터링 유형</span><span class="sxs-lookup"><span data-stu-id="defbe-108">Type of monitoring</span></span> |<span data-ttu-id="defbe-109">설명</span><span class="sxs-lookup"><span data-stu-id="defbe-109">Description</span></span> |
|:-----|:-----|
|<span data-ttu-id="defbe-110">**새 끝점에 대한 Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="defbe-110">**Getting notified of new Microsoft 365 endpoints**</span></span> <br/> |<span data-ttu-id="defbe-111">If you're [Managing Microsoft 365 endpoints](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a), you'll want to receive notifications when we publish new endpoints, you can subscribe to our RSS feed using your favorite RSS reader.</span><span class="sxs-lookup"><span data-stu-id="defbe-111">If you're [Managing Microsoft 365 endpoints](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a), you'll want to receive notifications when we publish new endpoints, you can subscribe to our RSS feed using your favorite RSS reader.</span></span> <span data-ttu-id="defbe-112">다음은 를 통해 [구독하는 Outlook](https://go.microsoft.com/fwlink/p/?LinkId=532416) RSS 피드 업데이트를 전자 메일로 [보낼 수 있는 방법입니다.](https://go.microsoft.com/fwlink/p/?LinkId=532417)</span><span class="sxs-lookup"><span data-stu-id="defbe-112">Here is how to [subscribe via Outlook](https://go.microsoft.com/fwlink/p/?LinkId=532416) or you can [have the RSS feed updates emailed to you](https://go.microsoft.com/fwlink/p/?LinkId=532417).</span></span>  <br/> |
|<span data-ttu-id="defbe-113">**이 System Center 사용하여 모니터링 Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="defbe-113">**Use System Center to Monitor Microsoft 365**</span></span> <br/> |<span data-ttu-id="defbe-114">Microsoft System Center 사용하는 경우 지금 System Center 관리 팩을 다운로드하여 Office 365 수 Microsoft 365 있습니다. [](https://www.microsoft.com/download/details.aspx?id=43708)</span><span class="sxs-lookup"><span data-stu-id="defbe-114">If you're using Microsoft System Center, you can download the [System Center Management Pack for Office 365](https://www.microsoft.com/download/details.aspx?id=43708) to begin monitoring Microsoft 365 today.</span></span> <span data-ttu-id="defbe-115">자세한 지침은 관리 팩 작업 가이드를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="defbe-115">For more detailed guidance, please see the management pack operations guide.</span></span> <br/> |
|<span data-ttu-id="defbe-116">**Azure ExpressRoute** 의 상태 모니터링</span><span class="sxs-lookup"><span data-stu-id="defbe-116">**Monitoring the health of Azure ExpressRoute**</span></span> <br/> |<span data-ttu-id="defbe-117">Microsoft 365 Azure ExpressRoute를 사용하여 Microsoft 365 연결하는 경우 azure 리소스 상태의 문제 해결 시간 단축뿐만 아니라 Microsoft 365 서비스 상태 대시보드를 모두 [](https://azure.microsoft.com/blog/reduce-troubleshooting-time-with-azure-resource-health/) 사용하고 있는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="defbe-117">If you are connecting to Microsoft 365 using Azure ExpressRoute for Microsoft 365, you'll want to ensure that you're using both the Microsoft 365 Service Health Dashboard as well as the Azure [Reducing troubleshooting time with Azure Resource health](https://azure.microsoft.com/blog/reduce-troubleshooting-time-with-azure-resource-health/)</span></span> <br/> |
|<span data-ttu-id="defbe-118">**AD FS와 Azure Active Directory Connect Health 사용**</span><span class="sxs-lookup"><span data-stu-id="defbe-118">**Using Azure AD Connect Health with AD FS**</span></span> <br/> |<span data-ttu-id="defbe-119">단일 응용 Sign-On AD FS를 사용하는 Microsoft 365 Azure AD 커넥트 Health를 사용하여 AD FS 인프라를 [모니터링할 수 있습니다.](/azure/active-directory/hybrid/how-to-connect-health-adfs)</span><span class="sxs-lookup"><span data-stu-id="defbe-119">If you're using AD FS for Single Sign-On with Microsoft 365, you'll want to begin [using Azure AD Connect Health to monitor your AD FS infrastructure](/azure/active-directory/hybrid/how-to-connect-health-adfs).</span></span>  <br/> |
|<span data-ttu-id="defbe-120">**프로그래밍식 모니터링 Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="defbe-120">**Programmatically monitor Microsoft 365**</span></span> <br/> |<span data-ttu-id="defbe-121">Microsoft 365 [관리 API에 대한 지침을 참조하세요.](/office/office-365-management-api/office-365-management-apis-overview)</span><span class="sxs-lookup"><span data-stu-id="defbe-121">Refer to our guidance on the [Microsoft 365 Management API](/office/office-365-management-api/office-365-management-apis-overview).</span></span>  <br/> |

<span data-ttu-id="defbe-122">다음의 간단한 링크를 사용할 수 있습니다. [https://aka.ms/monitorconnectivity365]()</span><span class="sxs-lookup"><span data-stu-id="defbe-122">Here's a short link you can use to come back: [https://aka.ms/monitorconnectivity365]()</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="defbe-123">관련 항목</span><span class="sxs-lookup"><span data-stu-id="defbe-123">Related topics</span></span>

[<span data-ttu-id="defbe-124">서비스 Microsoft 365 Enterprise 응용 프로그램 구성</span><span class="sxs-lookup"><span data-stu-id="defbe-124">Configure Microsoft 365 Enterprise services and applications</span></span>](configure-services-and-applications.md)
  
[<span data-ttu-id="defbe-125">조직에서 조직에 대한 Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="defbe-125">Get your organization ready for Microsoft 365 Enterprise</span></span>](get-your-organization-ready-for-office-365.md)
  
[<span data-ttu-id="defbe-126">Microsoft 365의 네트워크 계획 및 성능 조정</span><span class="sxs-lookup"><span data-stu-id="defbe-126">Network planning and performance tuning for Microsoft 365</span></span>](network-planning-and-performance.md)
  
[<span data-ttu-id="defbe-127">Microsoft 365 환경과의 통합</span><span class="sxs-lookup"><span data-stu-id="defbe-127">Microsoft 365 integration with on-premises environments</span></span>](microsoft-365-integration.md)
  
[<span data-ttu-id="defbe-128">끝점 Microsoft 365 관리</span><span class="sxs-lookup"><span data-stu-id="defbe-128">Managing Microsoft 365 endpoints</span></span>](managing-office-365-endpoints.md)
