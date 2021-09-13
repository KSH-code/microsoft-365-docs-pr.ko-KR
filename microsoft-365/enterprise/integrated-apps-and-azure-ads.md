---
title: 관리자를 위한 통합 Microsoft 365 Azure AD
ms.author: kvice
author: kelleyvice-msft
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
description: '**Azure AD에서** 통합 앱을 등록하고 Office 365 관리하여 Azure AD DC 관리자 또는 전역 관리자 수준에서 앱 권한 부여를 허용하는 **방법을** 설명합니다.'
ms.openlocfilehash: ccf1e16e7e0307499e515eb3691c865d49801412
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59215982"
---
# <a name="integrated-apps-and-azure-ad-for-microsoft-365-administrators"></a>관리자를 위한 통합 Microsoft 365 Azure AD

앱에 대한 사용자 동의를 관리하는 것 이상으로 통합 [앱을 관리할 수 있습니다.](../admin/misc/user-consent.md) REST API가 Microsoft 365 사용자는 메일, 일정, 연락처, 사용자, 그룹, 파일 및 폴더와 같은 Microsoft 365 데이터에 대한 액세스 권한을 앱에 부여할 수 있습니다. 기본적으로 사용자는 각 앱에 대한 사용 권한을 개별적으로 부여해야 합니다. 

그러나 **Azure AD DC** 관리자 또는 전역 관리자 수준에서 앱을 한 번  승인하고 앱 시작 관리자를 통해 전체 조직에 앱을 롤아웃하려는 경우 이 확장이 잘되지 않습니다. 이렇게하려면 Azure AD(Azure AD)에서 앱을 Azure Active Directory 합니다. Azure AD에서 앱을 등록하기 전에 몇 가지 단계를 수행하고 조직에서 앱을 관리하는 데 도움이 될 수 있는 몇 가지 백그라운드 Microsoft 365 있습니다.
  
## <a name="azure-ad-resources-for-microsoft-365-admins"></a>관리자를 위한 Azure AD Microsoft 365 리소스

Azure AD에서 앱 앱을 관리하기 전에 Microsoft 365 작업을 수행해야 합니다.
  
|필수 구성 요소|설명|
|:-----|:-----|
|[무료 Azure AD 구독 사용](../compliance/use-your-free-azure-ad-subscription-in-office-365.md) <br/> |모든 유료 구독은 Microsoft 365 Azure AD에 대한 무료 구독과 함께 제공됩니다. Azure AD를 사용하여 앱을 관리하고 사용자 및 그룹 계정을 만들고 관리할 수 있습니다. Azure AD를 사용하려면 에서 Azure Portal로 이동하여 사용자 계정으로 [https://portal.azure.com](https://portal.azure.com) Microsoft 365 로그인합니다.  <br/> |
|[앱에 대한 사용자 동의 관리](../admin/misc/user-consent.md) <br/> |타사 앱이 사용자 액세스 및 Azure AD에서 앱을 등록할 Microsoft 365 수 있도록 앱에 대한 사용자 동의를 관리해야 합니다. 예를 들어 사용자가 타사 앱을 사용하는 경우 해당 앱은 사용자의 일정에 액세스하고 OneDrive 폴더에 있는 파일을 편집하는 권한을 요청할 수 있습니다.  <br/> |
   
앱 Microsoft 365 관리하려면 Azure AD의 앱에 대한 지식이 필요합니다. 다음 문서를 사용하여 필요한 배경 정보를 제공해야 합니다.
  
|문서|설명|
|:-----|:-----|
|[앱 Microsoft 365 시작 프로그램 충족](https://support.microsoft.com/office/meet-the-microsoft-365-app-launcher-79f12104-6fed-442f-96a0-eb089a3f476a) <br/> |앱 시작 프로그램을 새로 사용하는 경우 앱 시작 프로그램과 사용 방법에 대해 궁금할 수 있습니다. 앱 시작 프로그램은 앱의 어디에서나 앱에 액세스하는 데 도움이 하도록 Microsoft 365.  <br/> |
|[Office 365 API 개요](/office/office-365-management-api/office-365-management-apis-overview) <br/> |Microsoft 365 관리 API를 사용하면 메일, 일정, 연락처Microsoft 365 사용자 및 그룹, 파일 및 폴더 등 사용자가 가장 중요한 정보를 포함하여 Microsoft 365 데이터에 액세스할 수 있습니다. <br/> |
|[Azure AD에서 응용 프로그램 통합](/azure/active-directory/develop/quickstart-v1-add-azure-ad-app) <br/> | Azure AD와 통합된 응용 프로그램에 대해 알아보고, 응용 프로그램을 등록하고, 등록된 응용 프로그램의 개념을 이해하고, 다중 테넌트 응용 프로그램에 대한 브랜들링 지침에 대해 자세히 알아보십시오.  <br/> |
|[앱 시작러에 사용자 지정 타일 추가](/office365/admin/manage/customize-the-app-launcher)  <br/> |앱 시작 Microsoft 365 쉽게 앱을 찾아서 액세스할 수 있습니다. 이 문서에서는 개발자가 사용자의 앱 시작 도우미에 앱을 표시하는 방법을 설명하고 앱 자격 증명을 사용하여 SSO(Single Sign-On) 환경을 Microsoft 365 있습니다.  <br/> |
|[Azure AD 통합 자습서](/azure/active-directory/saas-apps/tutorial-list) <br/> |이 자습서의 목표는 타사 SaaS 응용 프로그램에 대해 Azure AD SSO를 구성하는 방법을 보여 주는 것입니다.  <br/> |
|[Azure AD에 대한 인증 시나리오](/azure/active-directory/develop/authentication-vs-authorization) <br/> |Azure AD는 ID를 서비스로 제공하여 개발자를 위한 인증을 간소화하고, OAuth 2.0 및 OpenID 커넥트 같은 업계 표준 프로토콜과 코딩을 빠르게 시작할 수 있도록 다양한 플랫폼에 대한 오픈 소스 라이브러리를 지원합니다. 이 문서는 Azure AD에서 지원하는 다양한 시나리오를 이해하고 시작하는 방법을 보여 주며,  <br/> |
|[응용 프로그램 액세스](/azure/active-directory/manage-apps/what-is-access-management) <br/> |Azure AD를 사용하면 오늘날 인기 있는 많은 SaaS(Software as a Service) 응용 프로그램에 쉽게 통합할 수 있습니다. ID 및 액세스 관리를 제공하며, 사용자가 응용 프로그램에 액세스할 수 있는 위치와 SSO를 사용하여 응용 프로그램에 액세스할 수 있는 위치를 검색할 수 있는 액세스 패널을 제공합니다. 이 문서에서는 Azure AD의 응용 프로그램 액세스 향상 및 이러한 리소스에 기여하는 방법에 대해 자세히 알아보는 데 사용할 수 있는 관련 리소스에 대한 링크를 제공합니다.  <br/> |
|[사용자 환경 Office 365 사용자 설정](https://support.microsoft.com/office/personalize-your-office-365-experience-eb34a21b-52fa-4fbf-a8d5-146132242985) <br/> |앱 시작 Microsoft 365 앱을 추가하거나 제거하여 매일 사용하는 앱에 빠르게 액세스할 수 있습니다.  <br/> |
