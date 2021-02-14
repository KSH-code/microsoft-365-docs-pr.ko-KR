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
# <a name="monitor-microsoft-365-connectivity"></a>Microsoft 365 연결 모니터링

Microsoft 365를 배포한 후 아래 도구 및 기술을 사용하여 Microsoft 365 연결을 유지할 수 있습니다. 공식 서비스 상태 및 [](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity) 연속성 지침과 저속 네트워크에서 [Microsoft 365를](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166)사용하는 모범 사례를 이해하고자 합니다. 또한 [Microsoft 365](https://blogs.office.com/2015/03/13/administer-on-the-go-with-the-updated-office-365-admin-app/) 관리자 앱을 잡고 비즈니스용 Microsoft 365 - 관리자 도움말을 책갈피로 [설정하고 싶을 것입니다.](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791)
  
## <a name="monitoring-microsoft-365-connectivity"></a>Microsoft 365 연결 모니터링

|||
|:-----|:-----|
|**새 Microsoft 365 끝점에 대한 알림을 받고** <br/> |If you're [Managing Microsoft 365 endpoints,](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)you'll want to receive notifications when we publish new endpoints, you can subscribe to our RSS feed using your favorite RSS reader. 다음은 [Outlook을 통해 구독하는 방법](https://go.microsoft.com/fwlink/p/?LinkId=532416) 또는 RSS 피드 업데이트를 전자 메일로 [전송하는 방법입니다.](https://go.microsoft.com/fwlink/p/?LinkId=532417)  <br/> |
|**System Center를 사용하여 Microsoft 365 모니터링** <br/> |Microsoft System Center를 사용하는 경우 Office [365용 System Center 관리](https://www.microsoft.com/download/details.aspx?id=43708) 팩을 다운로드하여 Microsoft 365 모니터링을 시작할 수 있습니다. 자세한 지침은 [System Guidance Operations Manager를 사용하여 Office365 모니터링](https://blogs.msdn.com/b/mvpawardprogram/archive/2015/07/08/office365-monitoring-using-system-centre-operations-manager.aspx) 후 관리 팩 작업 가이드 또는 이 블로그를 참조하세요. <br/> |
|**Azure ExpressRoute** 의 상태 모니터링 <br/> |Microsoft 365용 Azure ExpressRoute를 사용하여 Microsoft 365에 연결하는 경우 Microsoft 365 서비스 상태 대시보드와 [Azure](https://azure.microsoft.com/blog/reduce-troubleshooting-time-with-azure-resource-health/) 리소스 상태의 문제 해결 시간을 모두 사용하는지 확인하려는 경우 <br/> |
|**AD FS와 Azure Active Directory Connect Health 사용** <br/> |Microsoft 365에서 Single Sign-On AD FS를 사용하는 경우 [Azure AD Connect Health를](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect-health-adfs/)사용하여 AD FS 인프라를 모니터링할 수 있습니다.  <br/> |
|**프로그래밍식으로 Microsoft 365 모니터링** <br/> |[Microsoft 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)관리 API에 대한 지침을 참조하세요.  <br/> |

다음의 간단한 링크를 사용할 수 있습니다. [https://aka.ms/monitorconnectivity365](https://aka.ms/monitorconnectivity365)
  
## <a name="related-topics"></a>관련 항목

[Microsoft 365 Enterprise 서비스 및 응용 프로그램 구성](configure-services-and-applications.md)
  
[조직에서 Microsoft 365 Enterprise 준비](get-your-organization-ready-for-office-365.md)
  
[Microsoft 365의 네트워크 계획 및 성능 조정](network-planning-and-performance.md)
  
[Microsoft 365와의 통합(프레미스 환경)](microsoft-365-integration.md)
  
[Microsoft 365 끝점 관리](managing-office-365-endpoints.md)
