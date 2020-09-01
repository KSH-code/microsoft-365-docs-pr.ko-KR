---
title: Microsoft 365 관리 센터의 Azure Active Directory 역할
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
description: Microsoft 365 관리 센터의 Azure 관리자 역할을 관리합니다.
ms.openlocfilehash: 2295a003fa73cb1805fad3231ff62b37930d0306
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289096"
---
# <a name="azure-active-directory-roles-in-the-microsoft-365-admin-center"></a>Microsoft 365 관리 센터의 Azure Active Directory 역할

Microsoft 365 관리 센터를 통해 30개 이상의 Azure AD 역할을 관리할 수 있습니다. 그러나 이 역할은 Azure 포털에서 사용할 수 있는 역할의 하위 집합입니다. 대기업의 경우 조직 요구 사항을 충족하는 역할이 Azure 포털에 있을 수 있습니다. Azure AD에 대한 자세한 역할 설명을 찾고 있나요? [Azure Active Directory의 관리자 역할 권한](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles)을 확인하세요.

관리자 역할이 할당된 사용자는 Microsoft 365 관리 센터 또는 Azure 포털에서 역할을 할당하거나 Windows PowerShell용 Azure AD 모듈을 사용하든지와 관계 없이 조직에 가입한 클라우드 서비스에 동일한 수준의 액세스 권한을 갖습니다. 

::: moniker range="o365-worldwide"

Microsoft 365 관리 센터에서 **역할**로 이동한 다음 아무 역할이나 선택하여 세부 정보 창을 열 수 있습니다. **사용 권한** 탭을 선택하여 해당 역할에 할당된 관리자가 수행할 수 있는 작업에 대한 자세한 목록을 볼 수 있습니다. 역할에 사용자를 추가하려면 **할당된** 또는 **할당된 관리자** 탭을 선택합니다. Microsoft 365 관리 센터에서 역할을 할당하는 방법에 대한 자세한 내용은 [관리자 역할 할당하기](assign-admin-roles.md)를 참조하세요.

::: moniker-end

## <a name="all-azure-ad-roles"></a>모든 Azure AD 역할

여기에 Microsoft 365 관리 센터에서 이용 가능한 모든 관리자 역할에 대한 목록이 나와 있습니다. Microsoft 365 관리자 역할에 대한 자세한 역할 설명을 찾고 있나요? [관리자 역할 소개](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide)를 확인하세요.

|관리자 역할     |설명  |
|---------|---------|
|응용 프로그램 관리자     |    엔터프라이즈 애플리케이션, 애플리케이션 등록 및 애플리케이션 프록시 설정에 모두 액세스합니다.     |
|응용 프로그램 개발자     |    응용 프로그램 등록 및 앱 액세스에 대한 동의를 직접 만듭니다.     |
|인증 관리자     |    사용자가 MFA와 같이 비 암호 자격 증명에 대한 인증을 다시 등록하도록 요구할 수 있습니다.     |
|Azure Information Protection 관리자     |   Azure Information Protection 정책의 레이블을 관리하고, 보호 템플릿을 관리하고, 보호를 활성화합니다.       |
|대금 청구 관리자     |    구매를 진행하고 구독과 서비스 요청을 관리하고 서비스 상태를 모니터링합니다.     |
|클라우드 응용 프로그램 관리자     | 엔터프라이즈 애플리케이션 및 애플리케이션 등록에 모두 액세스합니다. 응용 프로그램 프록시가 없습니다.     |
|클라우드 장치 관리자     |    장치를 사용하거나 사용하지 않도록 설정하고 이를 삭제하며 Windows 10 BitLocker 키를 읽을 수 있습니다.     |
|준수 관리자     |    규정 요구 사항 및 eDiscovery 사례를 관리하고 위치, id 및 앱에 대한 데이터 관리를 유지 관리합니다.     |
|준수 데이터 관리자     |    데이터를 추적하고, 데이터를 보호하고, 문제에 대한 통찰력을 제공하고, 위험을 완화하는 데 도움이 됩니다.     |
|조건부 액세스 관리자     |   Azure Active Directory 조건부 액세스 설정을 관리하지만 Exchange ActiveSync 조건부 액세스 정책은 관리하지 않습니다.      |
|고객 Lockbox 액세스 승인자     |      고객 Lockbox 요청을 관리하고, 고객 Lockbox를 설정하거나 해제할 수 있습니다.   |
|데스크톱 분석 관리자     |   데스크톱 관리 도구 및 서비스에 액세스하고 관리할 수 있습니다.      |
|Dynamics 365 관리자     |  Microsoft Dynamics 365 Online에 대한 전체 액세스 권한을 부여하고 서비스 요청을 관리하며 서비스 상태를 모니터링합니다.       |
|Exchange 관리자     |  Exchange Online 전체에 액세스하고, 그룹을 만들고 관리하며 서비스 요청을 관리하고 서비스 상태를 모니터링합니다.    |
|외부 id 공급자 관리자    |     직접 페더레이션에서 사용하도록 id 공급자를 구성합니다.    |
|전역 관리자     |    모든 관리 센터에서 모든 관리 기능과 모든 데이터에 무제한으로 액세스할 수 있습니다.     |
|전역 읽기 권한자     |    관리 센터에서 모든 관리 기능과 모든 데이터에 읽기 전용으로 액세스할 수 있습니다. 이 역할의 액세스 권한 및 제한 사항에 대한 자세한 설명은 [Azure Active Directory의 관리자 역할 권한](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-reader)을 참조하십시오.    |
|그룹 관리자   |그룹을 만들고 관리 센터에서 모든 그룹 설정을 관리합니다.|
|게스트 초대자     |    Azure Active Directory B2B 게스트 사용자 초대를 관리합니다.     |
|헬프데스크 관리자     | 모든 비관리자와 일부 관리자 역할에 대해 암호를 재설정하고 다시 인증하고 서비스 요청을 관리하고 서비스 상태를 모니터링합니다.      |
|Insights 관리자     | Microsoft 365 Insights 응용 프로그램의 모든 측면을 관리하고, Azure Active Directory 정보를 읽고, 서비스 상태를 모니터링하고 서비스 요청을 만들고 관리할 수 있습니다.      |
|Insights 비즈니스 관리자     | Microsoft 365 Insights 응용 프로그램에서 보고서 및 정보를 읽습니다.      |
|Intune 관리자     | Intune 전체에 액세스하고 사용자 및 장치를 관리하여 정책을 연결하고 그룹을 만들고 관리합니다.      |
|Kaizala 관리자     |    모든 Kaizala 관리 기능 및 데이터 전체에 액세스하고 서비스 요청을 관리합니다.     |
|라이선스 관리자     |     사용자에게 라이선스를 할당하거나 제거하고 사용 위치를 편집합니다.    |
|메시지 센터 개인정보 읽기 권한자     |    메시지 센터에서 데이터 개인 정보 메시지에 액세스하고 전자 메일 알림을 받습니다.     |
|메시지 센터 읽기 권한자     | 메시지 센터에서 일반 메시지를 읽고 공유하며 매주 이메일 요약을 받고 사용자, 그룹, 도메인 및 구독에 대한 읽기 전용 액세스 권한을 갖습니다.     |
|Office 앱 관리자    |   Office에 대한 클라우드 기반 정책과 사용자가 Office 앱에서 볼 수있는 새로운 기능 콘텐츠를 관리합니다.   |
|암호 관리자    |   비관리자나 디렉터리 읽기 권한자, 게스트 초대자, 암호 관리자의 구성원인 사용자의 암호를 다시 설정합니다. 이 역할은 서비스 요청을 관리하거나 서비스 상태를 모니터링할 수 있는 권한을 부여할 수 없습니다.   |
|Power BI 관리자    |   전원 Bl 관리 작업 전체에 액세스하고 서비스 요청을 관리하고 서비스 상태를 모니터링합니다.   |
|파워 플랫폼 관리자     |    Microsoft Dynamics 365, PowerApp, 데이터 손실 방지 정책 및 Microsoft Flow에 대한 전체에 액세스합니다.     |
|권한 있는 역할 관리자     |    Privileged Identity Management의 모든 액세스 제어 기능과 역할 할당을 관리합니다.     |
|권한 있는 인증 관리자     |    비밀번호를 재설정하고 비밀번호가 아닌 자격 증명을 업데이트하며 강제로 사용을 로그 아웃시켜 서비스 상태를 모니터링하고 서비스 요청을 관리합니다.     |
|보고서 읽기 권한자     |   보고서 대시 보드, PowerBI 채택 컨텐츠 팩, 로그인 보고서 및 Microsoft Graph 보고 API에서 사용량 보고 데이터를 읽습니다.      |
|검색 관리자     |    Microsoft 검색 전체에 액세스하고 검색 관리자 및 검색 편집자 역할을 할당하고 편집 콘텐츠를 관리하고 서비스 상태를 모니터링하고 서비스 요청을 만듭니다.     |
|검색 편집자     |    책갈피, Q&A 및 위치와 같은 Microsoft Search에 대한 콘텐츠만을 만들고 편집하고 삭제할 수 있습니다.     |
|보안 관리자     |    조직의 보안을 관리하고 보안 정책을 관리하고 보안 분석 및 보고서를 검토하고 위협 요소를 모니터링합니다.     |
|보안 운영자     |    보안 경고를 조사하고 이에 응답하고 Identity Protection Center의 기능을 관리하며 서비스 상태를 모니터링합니다.     |
|보안 읽기 권한자     |    보안 기능, 로그인 보고서 및 감사 로그를 읽기 전용으로 액세스할 수 있습니다.     |
|서비스 지원 관리자     |    Azure, Microsoft 365 및 Office 365 서비스에 대한 서비스 요청을 만들고 서비스 상태를 모니터링합니다.     |
|SharePoint 관리자     |    SharePoint Online 전체에 액세스하고 Microsoft 365 그룹 및 서비스 요청을 관리하고 서비스 상태를 모니터링합니다.     |
|비즈니스용 Skype 관리자     | 모든 Teams와 Skype 기능 전체에 액세스하며 Skype 사용자 특성, 서비스 요청을 관리하 고 서비스 상태를 모니터링합니다.      |
|Teams 관리자     |    Teams & Skype 관리 센터 전체에 액세스하고 Microsoft 365 그룹과 서비스 요청을 관리하고 서비스 상태를 모니터링합니다.     |
|Teams 통신 관리자     |    전화 번호를 할당하고, 음성 및 모임 정책을 만들고 관리하고 통화 분석을 읽습니다.     |
|Teams 통신 지원 엔지니어     |    모든 통화 참가자의 통화 기록 세부 정보를 읽고 통신 문제를 해결합니다.     |
|Teams 통신 지원 전문가     |    통신 문제를 해결하기 위해 특정 사용자에 대해서만 사용자 통화 세부 정보를 읽습니다.|
|사용자 관리자     |   사용자 암호를 재설정하고, 필터를 포함하여 사용자 및 그룹을 만들고 관리하고 서비스 요청을 관리하고 서비스 상태를 모니터링합니다.|

## <a name="delegated-administration-for-microsoft-partners"></a>Microsoft 파트너를 위한 위임 된 관리

Microsoft 파트너와 함께 업무를 진행하는 경우에는 파트너에게 관리자 역할을 할당할 수 있습니다. 파트너 또한 사용자 회사 또는 파트너 회사의 사용자들에게 관리자 역할을 할당할 수 있습니다. 예를 들어 파트너가 사용자를 위해 온라인 조직을 설정하고 관리하는 경우 이 기능이 필요할 수 있습니다.
  
파트너는 다음과 같은 역할을 할당할 수 있습니다. 

- 파트너 센터를 통해 다단계 인증을 관리하는 것을 제외하고는 전역 관리자와 동등한 권한을 가진 전체 관리 기능

- 헬프데스크 관리자와 동일한 권한을 가진 제한된 관리 기능

파트너가 이러한 역할을 사용자에게 할당하기 전에 파트너를 사용자 계정에 위임된 관리자로 추가해야 합니다. 이 프로세스는 공인 파트너가 시작 합니다. 파트너는 사용자가 파트너에게 위임된 관리자 역할을 수행할 권한을 부여할 것인지 묻는 전자 메일을 보냅니다. 안내 사항은 [파트너 관계 승인 또는 제거](https://docs.microsoft.com/microsoft-365/admin/misc/add-partner)를 참조하십시오.
  
## <a name="related-articles"></a>관련 문서

[Microsoft 365 관리자 역할 정보](about-admin-roles.md)

[관리자 역할 할당](assign-admin-roles.md)
  
[Office 365 관리 센터의 활동 보고서](../activity-reports/activity-reports.md)