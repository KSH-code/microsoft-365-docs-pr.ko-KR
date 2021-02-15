---
title: Microsoft 365 관리자를 위한 통합 앱 및 Azure AD
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection: M365-subscription-management
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: cb2250e3-451e-416f-bf4e-363549652c2a
description: 전역 관리자 수준에서 앱 권한 부여를 허용하여 Azure AD에서 Office 365 통합 앱을 등록하고 관리하는 방법을 설명합니다.
ms.openlocfilehash: 1e84b5e6f82848bf1d100004bcd2711ad2e9ed39
ms.sourcegitcommit: 11d1044c6600b1f568b6dc8a53db9b07f2f0ad1c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/08/2020
ms.locfileid: "48384903"
---
# <a name="integrated-apps-and-azure-ad-for-microsoft-365-administrators"></a>Microsoft 365 관리자를 위한 통합 앱 및 Azure AD

앱에 대한 사용자 동의를 관리하는 것 이상으로 통합 앱을 [관리할 수 있습니다.](https://docs.microsoft.com/microsoft-365/admin/misc/integrated-apps) Microsoft 365 REST API가 제공될 때 사용자는 메일, 일정, 연락처, 사용자, 그룹, 파일 및 폴더와 같은 Microsoft 365 데이터에 대한 액세스 권한을 앱에 부여할 수 있습니다. 기본적으로 사용자는 각 앱에 대한 사용 권한을 개별적으로 부여해야 합니다. 

그러나 전역 관리자 수준에서 앱에 권한을 한 번만 승인하고 앱 시작 관리자를 통해 전체 조직에 앱을 롤아웃하려는 경우 이 확장이 잘 진행되지 않습니다. 이렇게하려면 Azure AD(Azure Active Directory)에 앱을 등록해야 합니다. Azure AD에서 앱을 등록하기 전에 몇 가지 단계를 수행하고 Microsoft 365 조직에서 앱을 관리하는 데 도움이 될 수 있는 몇 가지 백그라운드 정보를 알아야 합니다.
  
## <a name="azure-ad-resources-for-microsoft-365-admins"></a>Microsoft 365 관리자를 위한 Azure AD 리소스

Azure AD에서 Microsoft 365 앱을 관리하기 전에 이러한 두 작업을 수행해야 합니다.
  
|필수 구성 요소|설명|
|:-----|:-----|
|[무료 Azure AD 구독 사용](https://docs.microsoft.com/microsoft-365/compliance/use-your-free-azure-ad-subscription-in-office-365) <br/> |Microsoft 365에 대한 모든 유료 구독에는 Azure AD 무료 구독이 제공됩니다. Azure AD를 사용하여 앱을 관리하고 사용자 및 그룹 계정을 만들고 관리할 수 있습니다. Azure AD를 사용하려면 Azure Portal로 이동하여 Microsoft 365 계정을 사용하여 [https://portal.azure.com](https://portal.azure.com) 로그인하면 됩니다.  <br/> |
|[앱에 대한 사용자 동의 관리](https://docs.microsoft.com/microsoft-365/admin/misc/integrated-apps) <br/> |타사 앱이 사용자 Microsoft 365 정보에 액세스하고 Azure AD에 앱을 등록할 수 있도록 허용하려면 앱에 대한 사용자 동의를 관리해야 합니다. 예를 들어 사용자가 타사 앱을 사용하는 경우 해당 앱은 사용자의 일정에 액세스하고 OneDrive 폴더에 있는 파일을 편집하는 권한을 요청할 수 있습니다.  <br/> |
   
Microsoft 365 앱을 관리하려면 Azure AD의 앱에 대한 지식이 필요합니다. 다음 문서를 사용하여 필요한 배경 정보를 제공해야 합니다.
  
|문서|설명|
|:-----|:-----|
|[Microsoft 365 앱 시작 실행 프로그램 충족](https://support.microsoft.com/office/meet-the-microsoft-365-app-launcher-79f12104-6fed-442f-96a0-eb089a3f476a) <br/> |앱 시작 프로그램을 새로 사용하는 경우 앱 시작과 사용 방법에 대해 궁금할 수 있습니다. 앱 시작 프로그램은 Microsoft 365의 어디에서나 앱에 액세스하는 데 도움이 하도록 디자인됩니다.  <br/> |
|[Office 365 관리 API 개요](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview) <br/> |Microsoft 365 관리 API를 사용하면 메일, 일정, 연락처, 사용자 및 그룹, 파일, 폴더 등 Microsoft 365 데이터에 대한 액세스를 제공할 수 있습니다. <br/> |
|[Azure AD에서 응용 프로그램 통합](https://docs.microsoft.com/azure/active-directory/develop/quickstart-v1-add-azure-ad-app) <br/> | Azure AD와 통합된 응용 프로그램과 응용 프로그램을 등록하고, 등록된 응용 프로그램의 개념을 이해하고, 다중 테넌트 응용 프로그램에 대한 브랜드 지침에 대해 자세히 알아보십시오.  <br/> |
|[앱 시작러에 사용자 지정 타일 추가](https://docs.microsoft.com/office365/admin/manage/customize-the-app-launcher)  <br/> |Microsoft 365의 앱 시작 프로그램을 사용하면 사용자가 앱을 더 쉽게 찾아서 액세스할 수 있습니다. 이 문서에서는 개발자가 사용자의 앱 시작 도우미에 앱을 표시하는 방법을 설명하고 Microsoft 365 자격 증명을 사용하여 사용자에게 SSO(Single Sign-On) 환경을 제공합니다.  <br/> |
|[Azure AD 통합 자습서](https://docs.microsoft.com/azure/active-directory/saas-apps/tutorial-list) <br/> |이 자습서의 목표는 타사 SaaS 응용 프로그램에 대해 Azure AD SSO를 구성하는 방법을 보여 주도록 하는 것입니다.  <br/> |
|[Azure AD에 대한 인증 시나리오](https://go.microsoft.com/fwlink/?LinkId=617145) <br/> |Azure AD는 ID를 서비스로 제공하여 개발자를 위한 인증을 간소화하고, OAuth 2.0 및 OpenID Connect와 같은 업계 표준 프로토콜과 코딩을 빠르게 시작하는 데 도움이 되는 여러 플랫폼에 대한 오픈 소스 라이브러리를 지원합니다. 이 문서는 Azure AD에서 지원하는 다양한 시나리오를 이해하고 시작하는 방법을 보여 주며,  <br/> |
|[응용 프로그램 액세스](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-access-management) <br/> |Azure AD를 사용하면 오늘날 많이 사용하는 많은 SaaS(Software as a Service) 응용 프로그램에 쉽게 통합할 수 있습니다. ID 및 액세스 관리를 제공하며, 사용자가 사용하는 응용 프로그램 액세스와 SSO를 사용하여 응용 프로그램에 액세스할 수 있는 위치를 검색할 수 있는 액세스 패널을 제공합니다. 이 문서에서는 Azure AD의 응용 프로그램 액세스 개선 사항 및 이러한 리소스에 기여하는 방법에 대해 자세히 알아보는 데 사용할 수 있는 관련 리소스에 대한 링크를 제공합니다.  <br/> |
|[Office 365 환경 개인 설정](https://support.microsoft.com/office/personalize-your-office-365-experience-eb34a21b-52fa-4fbf-a8d5-146132242985) <br/> |Microsoft 365 앱 시작 앱에서 앱을 추가하거나 제거하여 매일 사용하는 앱에 빠르게 액세스할 수 있습니다.  <br/> |

