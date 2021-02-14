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
description: 이 문서에서는 Microsoft 365 연결을 모니터링하고 유지 관리하는 데 사용할 수 있는 도구 및 기술에 대해 알아보고 있습니다.
ms.openlocfilehash: 7e62bcaae24f9e42fd0514c34c3d7dee764bc271
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46692306"
---
# <a name="monitor-microsoft-365-connectivity"></a><span data-ttu-id="75d8c-103">Microsoft 365 연결 모니터링</span><span class="sxs-lookup"><span data-stu-id="75d8c-103">Monitor Microsoft 365 connectivity</span></span>

<span data-ttu-id="75d8c-104">Microsoft 365를 배포한 후 아래 도구 및 기술을 사용하여 Microsoft 365 연결을 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d8c-104">Once you've deployed Microsoft 365, you can maintain Microsoft 365 connectivity using some of the tools and techniques below.</span></span> <span data-ttu-id="75d8c-105">공식 서비스 상태 및 [](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity) 연속성 지침과 저속 네트워크에서 [Microsoft 365를](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166)사용하는 모범 사례를 이해하고자 합니다.</span><span class="sxs-lookup"><span data-stu-id="75d8c-105">You'll want to understand the official [Service Health and Continuity](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity) guidelines as well as our [Best practices for using Microsoft 365 on a slow network](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166).</span></span> <span data-ttu-id="75d8c-106">또한 [Microsoft 365](https://blogs.office.com/2015/03/13/administer-on-the-go-with-the-updated-office-365-admin-app/) 관리자 앱을 잡고 비즈니스용 Microsoft 365 - 관리자 도움말을 책갈피로 [설정하고 싶을 것입니다.](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791)</span><span class="sxs-lookup"><span data-stu-id="75d8c-106">You'll also want to grab the [Microsoft 365 admin app](https://blogs.office.com/2015/03/13/administer-on-the-go-with-the-updated-office-365-admin-app/) and bookmark our [Microsoft 365 for business - Admin Help](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791).</span></span>
  
## <a name="monitoring-microsoft-365-connectivity"></a><span data-ttu-id="75d8c-107">Microsoft 365 연결 모니터링</span><span class="sxs-lookup"><span data-stu-id="75d8c-107">Monitoring Microsoft 365 Connectivity</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="75d8c-108">**새 Microsoft 365 끝점에 대한 알림을 받고**</span><span class="sxs-lookup"><span data-stu-id="75d8c-108">**Getting notified of new Microsoft 365 endpoints**</span></span> <br/> |<span data-ttu-id="75d8c-109">If you're [Managing Microsoft 365 endpoints,](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)you'll want to receive notifications when we publish new endpoints, you can subscribe to our RSS feed using your favorite RSS reader.</span><span class="sxs-lookup"><span data-stu-id="75d8c-109">If you're [Managing Microsoft 365 endpoints](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a), you'll want to receive notifications when we publish new endpoints, you can subscribe to our RSS feed using your favorite RSS reader.</span></span> <span data-ttu-id="75d8c-110">다음은 [Outlook을 통해 구독하는 방법](https://go.microsoft.com/fwlink/p/?LinkId=532416) 또는 RSS 피드 업데이트를 전자 메일로 [전송하는 방법입니다.](https://go.microsoft.com/fwlink/p/?LinkId=532417)</span><span class="sxs-lookup"><span data-stu-id="75d8c-110">Here is how to [subscribe via Outlook](https://go.microsoft.com/fwlink/p/?LinkId=532416) or you can [have the RSS feed updates emailed to you](https://go.microsoft.com/fwlink/p/?LinkId=532417).</span></span>  <br/> |
|<span data-ttu-id="75d8c-111">**System Center를 사용하여 Microsoft 365 모니터링**</span><span class="sxs-lookup"><span data-stu-id="75d8c-111">**Use System Center to Monitor Microsoft 365**</span></span> <br/> |<span data-ttu-id="75d8c-112">Microsoft System Center를 사용하는 경우 Office [365용 System Center 관리](https://www.microsoft.com/download/details.aspx?id=43708) 팩을 다운로드하여 Microsoft 365 모니터링을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d8c-112">If you're using Microsoft System Center, you can download the [System Center Management Pack for Office 365](https://www.microsoft.com/download/details.aspx?id=43708) to begin monitoring Microsoft 365 today.</span></span> <span data-ttu-id="75d8c-113">자세한 지침은 [System Guidance Operations Manager를 사용하여 Office365 모니터링](https://blogs.msdn.com/b/mvpawardprogram/archive/2015/07/08/office365-monitoring-using-system-centre-operations-manager.aspx) 후 관리 팩 작업 가이드 또는 이 블로그를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="75d8c-113">For more detailed guidance, please see the management pack operations guide or this blog post [Office365 Monitoring using System Centre Operations Manager](https://blogs.msdn.com/b/mvpawardprogram/archive/2015/07/08/office365-monitoring-using-system-centre-operations-manager.aspx)</span></span> <br/> |
|<span data-ttu-id="75d8c-114">**Azure ExpressRoute** 의 상태 모니터링</span><span class="sxs-lookup"><span data-stu-id="75d8c-114">**Monitoring the health of Azure ExpressRoute**</span></span> <br/> |<span data-ttu-id="75d8c-115">Microsoft 365용 Azure ExpressRoute를 사용하여 Microsoft 365에 연결하는 경우 Microsoft 365 서비스 상태 대시보드와 [Azure](https://azure.microsoft.com/blog/reduce-troubleshooting-time-with-azure-resource-health/) 리소스 상태의 문제 해결 시간을 모두 사용하는지 확인하려는 경우</span><span class="sxs-lookup"><span data-stu-id="75d8c-115">If you are connecting to Microsoft 365 using Azure ExpressRoute for Microsoft 365, you'll want to ensure that you're using both the Microsoft 365 Service Health Dashboard as well as the Azure [Reducing troubleshooting time with Azure Resource health](https://azure.microsoft.com/blog/reduce-troubleshooting-time-with-azure-resource-health/)</span></span> <br/> |
|<span data-ttu-id="75d8c-116">**AD FS와 Azure Active Directory Connect Health 사용**</span><span class="sxs-lookup"><span data-stu-id="75d8c-116">**Using Azure AD Connect Health with AD FS**</span></span> <br/> |<span data-ttu-id="75d8c-117">Microsoft 365에서 Single Sign-On AD FS를 사용하는 경우 [Azure AD Connect Health를](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect-health-adfs/)사용하여 AD FS 인프라를 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75d8c-117">If you're using AD FS for Single Sign-On with Microsoft 365, you'll want to begin [using Azure AD Connect Health to monitor your AD FS infrastructure](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect-health-adfs/).</span></span>  <br/> |
|<span data-ttu-id="75d8c-118">**프로그래밍식으로 Microsoft 365 모니터링**</span><span class="sxs-lookup"><span data-stu-id="75d8c-118">**Programmatically monitor Microsoft 365**</span></span> <br/> |<span data-ttu-id="75d8c-119">[Microsoft 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)관리 API에 대한 지침을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="75d8c-119">Refer to our guidance on the [Microsoft 365 Management API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview).</span></span>  <br/> |

<span data-ttu-id="75d8c-120">다음의 간단한 링크를 사용할 수 있습니다. [https://aka.ms/monitorconnectivity365](https://aka.ms/monitorconnectivity365)</span><span class="sxs-lookup"><span data-stu-id="75d8c-120">Here's a short link you can use to come back: [https://aka.ms/monitorconnectivity365](https://aka.ms/monitorconnectivity365)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="75d8c-121">관련 항목</span><span class="sxs-lookup"><span data-stu-id="75d8c-121">Related topics</span></span>

[<span data-ttu-id="75d8c-122">Microsoft 365 Enterprise 서비스 및 응용 프로그램 구성</span><span class="sxs-lookup"><span data-stu-id="75d8c-122">Configure Microsoft 365 Enterprise services and applications</span></span>](configure-services-and-applications.md)
  
[<span data-ttu-id="75d8c-123">조직에서 Microsoft 365 Enterprise 준비</span><span class="sxs-lookup"><span data-stu-id="75d8c-123">Get your organization ready for Microsoft 365 Enterprise</span></span>](get-your-organization-ready-for-office-365.md)
  
[<span data-ttu-id="75d8c-124">Microsoft 365의 네트워크 계획 및 성능 조정</span><span class="sxs-lookup"><span data-stu-id="75d8c-124">Network planning and performance tuning for Microsoft 365</span></span>](network-planning-and-performance.md)
  
[<span data-ttu-id="75d8c-125">Microsoft 365와의 통합(프레미스 환경)</span><span class="sxs-lookup"><span data-stu-id="75d8c-125">Microsoft 365 integration with on-premises environments</span></span>](microsoft-365-integration.md)
  
[<span data-ttu-id="75d8c-126">Microsoft 365 끝점 관리</span><span class="sxs-lookup"><span data-stu-id="75d8c-126">Managing Microsoft 365 endpoints</span></span>](managing-office-365-endpoints.md)
