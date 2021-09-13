---
title: Microsoft 365 및 Office 365 서비스용 설정 가이드
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- M365-subscription-management
- SPO_Content
- m365initiative-coredeploy
f1.keywords:
- CSH
ms.custom: Adm_O365_Setup
search.appverid:
- MET150
- MET150
- BCS160
ms.assetid: 165f46e8-3533-4d76-be57-97f81ebd40f2
description: 테넌트 라이선스의 기능을 계획, 마이그레이션 및 구현하기 위한 단계별 도구를 얻습니다. 실행해야 하는 서비스 또는 앱을 설정하는 가이드를 찾아보세요.
ms.openlocfilehash: 3d69484cf1899fbca8994e3abc89bd49876da5cf
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59189579"
---
# <a name="setup-guides-for-microsoft-365-and-office-365-services"></a>Microsoft 365 및 Office 365 서비스용 설정 가이드

Microsoft 365 및 Office 365 설정 가이드에서는 테넌트, 앱 및 서비스를 계획하고 배포하기 위한 맞춤형 지침과 리소스를 제공합니다. 이 가이드는 [온보드](https://www.microsoft.com/fasttrack/microsoft-365) 전문가가 개별 상호 작용에서 공유하는 Microsoft 365 FastTrack 모범 사례를 사용하여 만들어지며, 이 가이드는 온보드 내의 모든 관리자가 사용할 수 Microsoft 365 관리 센터. 제품 설정에 대한 정보를 제공하고, 보안 기능을 사용하도록 설정하고, 공동 작업 도구를 배포하고, 고급 배포 속도를 향상하기 위한 스크립트를 제공합니다.

> [!NOTE]
> 전역 읽기 프로그램이 설치 가이드에 액세스하려면 전역 읽기 Microsoft 365 있어야 합니다. 전역 관리자 역할이 있는 관리자만 이 가이드를 사용하여 테넌트의 설정을 변경할 수 있습니다. 

## <a name="how-to-access-setup-guides-in-the-microsoft-365-admin-center"></a>2013의 설정 가이드에 액세스하는 Microsoft 365 관리 센터

설치 가이드는 설치 가이드의 설치 지침 페이지에서 액세스할 수 Microsoft 365 관리 센터. [](https://aka.ms/setupguidance) 진행 상태를 추적하고 항상 돌아와 가이드를 완료할 수 있습니다. 설치 지침 **페이지에 연결하려면 다음을** 실행합니다.

1. 에서 [Microsoft 365 관리 센터](https://admin.microsoft.com/)홈 **페이지로** 이동합니다.

2. 교육 & **가이드 카드를** 찾아보세요.

   ![교육 & Microsoft 365 관리 센터 가이드 카드](../media/setup-guides-for-microsoft-365/adminportal-trainingandguides.png)

3. 단계별 **가이드 를 선택합니다.**

   ![설치 지침 페이지의 스크린 Microsoft 365 관리 센터샷](../media/setup-guides-for-microsoft-365/adminportal-setupguidance.png)

## <a name="guides-for-initial-setup"></a>초기 설정 가이드

### <a name="prepare-your-environment"></a>환경 준비

환경 [준비 가이드를](https://aka.ms/prepareyourenvironment) 통해 조직에서 서비스 및 서비스 Microsoft 365 환경을 Office 365 있습니다. 목표에 따라 성공적인 배포를 위해 완료해야 할 작업이 있습니다. 환경을 준비하는 동안 오류를 방지하려면 도메인을 연결하고, 사용자를 추가하고, 라이선스를 할당하고, Exchange Online 사용하여 전자 메일을 설정하고, Office 앱을 설치 또는 배포하는 단계별 지침이 제공됩니다.

### <a name="email-setup-guide"></a>전자 메일 설정 가이드

전자 [메일 설정 가이드에서는](https://aka.ms/office365setup) 조직에 대한 구성에 필요한 단계별 Exchange Online 제공합니다. 이 지침에는 새 전자 메일 계정 설정, 전자 메일 마이그레이션 및 전자 메일 보호 구성이 포함됩니다. 전자 메일 설정이 성공하려면 이 고문을 사용하여 조직의 현재 메일 시스템, 마이그레이션되는 사서함 수 및 사용자 및 액세스 관리 방법에 따라 권장되는 마이그레이션 방법을 받게 됩니다.

### <a name="migrate-gmail-contacts-and-calendar-items"></a>Gmail 연락처 및 일정 항목 마이그레이션

Gmail 사용자의 사서함을 사서함으로 마이그레이션할 Microsoft 365 전자 메일 메시지가 마이그레이션되지만 연락처 및 일정 항목은 마이그레이션되지 않습니다. Gmail [연락처](https://aka.ms/gmailcontactscalendar) 및 일정 고문은 Microsoft 365.com, Outlook 클라이언트 또는 PowerShell에서 가져오기 및 내보내기 방법을 사용하여 Google 연락처 및 Google 일정 항목을 Outlook 가져오는 단계를 제공합니다.

### <a name="microsoft-365-deployment-advisor"></a>Microsoft 365 배포 고문

Microsoft 365 [배포](https://aka.ms/microsoft365setupguide) 고문은 생산성 도구, 보안 정책 및 장치 관리 기능을 설정할 때 지침을 제공합니다. 엔터프라이즈 Microsoft 365 Business Premium 또는 Microsoft 365 사용하여 이 고문을 사용하여 조직의 장치를 설정하고 구성할 수 있습니다.

클라우드 서비스를 사용하도록 설정하고, 지원되는 최신 버전의 Windows 10 장치로 업데이트하고, 디바이스를 하나의 중앙 위치에서 Azure Active Directory(Azure AD)에 가입하기 위한 지침과 액세스 권한을 받게 됩니다.

### <a name="remote-work-setup-guide"></a>원격 작업 설정 가이드

원격 [작업 설정](https://aka.ms/remoteworksetup) 가이드는 사용자가 원격으로 작업하고, 데이터를 안전하게 유지하며, 사용자의 자격 증명을 보호하는 데 필요한 팁과 리소스를 조직에 제공합니다.

원격 액세스 VPN 인프라에 대한 부담을 줄일 수 있도록 클라우드의 Microsoft 365 리소스와 조직의 네트워크에 대한 원격 작업자의 장치 트래픽을 최적화하는 지침을 받게 됩니다.

### <a name="windows-virtual-desktop-setup-guide"></a>Windows 가상 데스크톱 설정 가이드

Windows 가상 데스크톱은 클라우드에서 실행되는 포괄적인 데스크톱 및 앱 가상화 서비스입니다. VDI(가상 데스크톱 인프라)는 간소화된 관리, 다중 세션 Windows 10, Microsoft 365 앱 최적화 및 RDS(원격 데스크톱 서비스) 환경에 대한 지원을 제공하는 유일한 가상 데스크톱 인프라입니다. 몇 분 Windows 데스크톱 및 앱을 Azure로 배포하고 확장하고 기본 제공 보안 및 규정 준수 기능을 사용할 수 있습니다.

가상 [Windows 설치](https://aka.ms/wvdsetupguide) 가이드에서는 관리자에게 배포, 설정 지침 및 기타 리소스에 대한 계획 리소스 및 선행 구성을 제공합니다.

### <a name="microsoft-edge-setup-guide"></a>Microsoft Edge 설정 가이드

Microsoft Edge 세계적 수준의 호환성 및 성능, 자격이 있는 보안 및 개인 정보 보호 및 웹을 최상의 웹으로 가져오기 위해 설계된 새로운 기능을 제공하도록 새로 고안되었습니다.

Microsoft Edge [](https://aka.ms/edgeadvisor) 설정 가이드는 Enterprise 사이트 검색을 구성하여 IE 모드를 사용하는 데 필요할 수 있는 사이트를 확인, 중요한 보안 기능을 검토 및 구성하고, 사용자의 요구 사항에 맞게 개인 정보 취급 방침 및 규정 준수 정책을 구성하고, 장치에서 웹 액세스를 관리하는 데 도움이 됩니다. 개별 장치에 Microsoft Edge 다운로드할 수 있습니다. 또는 그룹 정책, 구성 관리자 또는 그룹 정책을 사용하여 여러 사용자에게 배포하는 방법을 Microsoft Intune.

### <a name="configure-ie-mode-for-microsoft-edge"></a>사용자에 대해 IE 모드 Microsoft Edge

이미 배포한 Microsoft Edge IE 모드만 구성하려는 경우 Microsoft Edge [IE](https://aka.ms/configureiemode) 모드 구성 가이드에서 사이트 검색 구성을 자동화하는 Enterprise 제공합니다. 또한 사용자에게 배포할 Enterprise 모드 사이트 목록을 만드는 데 도움이 되는 클라우드 기반 도구에서 IE 모드 권장 사항을 얻을 수 있습니다.

### <a name="microsoft-search-setup-guide"></a>Microsoft Search 설정 가이드

Microsoft Search 작업을 완료하는 데 필요한 정보를 찾는 데 도움이 됩니다. 사용자, 파일, 사이트 또는 일반적인 질문에 대한 답변을 검색하는지 여부에 관계 없는 경우, 작업일 전체에서 Microsoft Search 사용하여 답변을 얻을 수 있습니다.

Microsoft Search [](https://aka.ms/MicrosoftSearchSetup) 설정 가이드는 사용자 Microsoft Search 파일럿할지 또는 조직 내 모든 사용자에게 배포할지 여부를 구성하는 데 도움이 됩니다. 검색 관리자 및 검색 편집기를 할당한 다음 사용자에 대한 검색 환경을 사용자 지정합니다(예를 들어 Chrome에 Bing 확장명을 추가하거나 기본 검색 엔진으로 Bing 사용자 지정).

### <a name="intune-configuration-manager-co-management-setup-guide"></a>Intune Configuration Manager 공동 관리 설정 가이드

기존 Configuration Manager 클라이언트 장치 및 새 인터넷 기반 장치에 대해 [Intune Configuration Manager](https://aka.ms/comanagementsetup) 공동 관리 설정 가이드를 사용하여 Microsoft Intune 및 Configuration Manager를 함께 관리합니다. 이 공동 관리 배포 가이드를 통해 Windows 10 디바이스를 관리하고, 두 솔루션의 이점을 모두 받아서 새 기능을 디바이스에 추가할 수 있습니다.

## <a name="guides-for-authentication-and-access"></a>인증 및 액세스 가이드

### <a name="azure-ad-setup-guide"></a>Azure AD 설정 가이드

[Azure AD 설정 가이드는](https://aka.ms/aadpguidance) 조직에 강력한 보안 기반을 구축할 수 있는 정보를 제공합니다. 이 가이드에서는 관리자를 위한 Azure RBAC(역할 기반 액세스 제어), 커넥트 디렉터리의 Azure AD 커넥트 및 Azure AD 커넥트 Health와 같은 초기 기능을 설정하여 자동화된 동기화 중에 하이브리드 ID의 상태 모니터링을 할 수 있습니다.

또한 선택적 고급 ID 보호 및 사용자 프로비저닝 자동화를 포함하여 셀프 서비스 암호 재설정, 조건부 액세스 및 통합된 타사 로그인을 사용하도록 설정하는 데 필요한 필수 정보도 포함되어 있습니다.

### <a name="sync-users-from-your-windows-server-active-directory"></a>사용자 계정에서 Windows Server Active Directory

사용자 [동기화 Windows Server Active Directory](https://aka.ms/directorysyncsetup) 가이드에서는 디렉터리 동기화를 켜는 방법을 안내합니다. 디렉터리 동기화를 통해 더 쉽게 액세스하고 관리를 간소화할 수 있도록 프레미스와 클라우드 ID를 함께 사용할 수 있습니다. Single Sign-On, 셀프 서비스 옵션, 자동 계정 프로비전, 조건부 액세스 제어 및 규정 준수 정책과 같은 새로운 기능의 잠금을 해제합니다. 이러한 기능을 통해 사용자는 어디에서나 필요한 리소스에 액세스할 수 있습니다.

### <a name="plan-your-passwordless-deployment"></a>암호 없는 배포 계획

사용자가 다음 암호 없는 인증 방법 중 하나를 사용하여 장치에 안전하게 액세스할 수 있도록 하는 대체 로그인 방법으로 업그레이드합니다.

- 비즈니스용 Windows Hello
- Microsoft Authenticator 앱
- 보안 키

암호 없는 [배포](https://aka.ms/passwordlesssetup) 계획 가이드를 사용하여 암호 없는 최상의 인증 방법을 찾아 배포하는 방법에 대한 지침을 받을 수 있습니다.

### <a name="plan-your-self-service-password-reset-sspr-deployment"></a>SSPR(셀프 서비스 암호 재설정) 배포 계획

사용자에게 계정이 잠겨 있는 경우 암호를 독립적으로 변경하거나 다시 설정하거나 기술 지원 팀 엔지니어에게 문의할 필요 없이 암호를 잊어버려도 됩니다.

셀프 [](https://aka.ms/SSPRSetupGuide) 서비스 암호 재설정 배포 계획 가이드를 사용하여 환경에 SSPR을 배포하는 데 도움이 되는 적절한 Azure Portal 옵션을 구성하기 위한 관련 문서 및 지침을 받을 수 있습니다.

### <a name="active-directory-federation-services-ad-fs-deployment-advisor"></a>AD FS(Active Directory Federation Services) 배포 어드바이저

AD FS 배포 [고문은](https://aka.ms/adfsguidance) Microsoft 365 및 Office 365 서비스를 인증하는 사내 AD FS 인프라 배포에 대한 단계별 지침을 제공합니다. 이 가이드를 사용하여 조직은 AD FS 구성 요소 및 요구 사항을 검토하고, 배포에 필요한 SSL 인증서를 획득 및 설치하고, 필요한 웹 응용 프로그램 프록시 서버를 설치할 수 있습니다.

## <a name="guides-for-security-and-compliance"></a>보안 및 규정 준수 가이드

### <a name="microsoft-intune-setup-guide"></a>Microsoft Intune 설정 가이드

조직에서 Microsoft Intune 관리하기 위한 사용자 설정 회사 장치에 대한 모든 제어를 위해 Intune의 MDM(모바일 장치 관리) 기능을 사용할 수 있습니다. 공유 및 개인 장치에서 조직의 데이터를 관리하기 위해 Intune의 MAM(모바일 응용 프로그램 관리) 기능을 사용할 수 있습니다.

Microsoft Intune [](https://aka.ms/intunesetupguide)설정 가이드를 사용하여 장치 및 앱 준수 정책을 설정하고, 앱 보호 정책을 할당하고, 장치 및 앱 보호 상태를 모니터링합니다.

### <a name="microsoft-defender-for-endpoint-setup-guide"></a>끝점용 Microsoft Defender 설정 가이드

[끝점용 Microsoft Defender](https://aka.ms/mdatpsetup) 설정 가이드는 엔터프라이즈 네트워크에서 고급 위협을 방지, 감지, 조사 및 대응하는 데 도움이 되는 지침을 제공합니다. 조직의 취약점을 적정하게 평가하고 가장 적합한 배포 패키지 및 구성 방법을 결정하십시오.

>[!NOTE]
>끝점용 Microsoft Defender에는 Microsoft 볼륨 라이선스가 필요합니다.

### <a name="exchange-online-protection-setup-guide"></a>Exchange Online Protection 설정 가이드

Microsoft Exchange Online EOP(보호)는 스팸 및 맬웨어로부터 보호하는 클라우드 기반 전자 메일 필터링 서비스로, 메시징 정책 위반으로부터 조직을 보호하는 기능을 제공합니다.

Exchange Online Protection [](https://aka.ms/EOPguidance) 설정 가이드를 사용하여 세 가지 배포 시나리오 중 조직에 맞는 배포 시나리오, 하이브리드(사내 사서함과 클라우드의 조합) 또는 모든 클라우드 사서함을 선택하여 EOP를 &mdash; 설정할 수 &mdash; 있습니다. 이 가이드에서는 사용자 라이선스를 설정 및 검토하고, Microsoft 365 관리 센터 할당하고, 보안 및 준수 센터에서 조직의 맬웨어 방지 및 스팸 정책을 구성하기 위한 정보와 & 제공합니다.

### <a name="microsoft-defender-for-office-365-setup-guide"></a>Office 365용 Microsoft Defender 설정 가이드

Microsoft [Defender for Office 365](https://aka.ms/oatpsetup) 설정 가이드는 사용자 환경이 전자 메일 메시지, 링크 및 타사 공동 작업 도구를 통해 전달될 수 있는 악의적인 위협에 대해 조직을 보호합니다. 이 가이드에서는 조직의 요구에 맞게 계획을 세우고 Office 365 Defender를 준비하고 식별하는 데 도움이 되는 리소스와 정보를 제공합니다.

### <a name="microsoft-defender-for-identity-setup-guide"></a>Microsoft Defender for Identity 설정 가이드

Id에 [대한 Microsoft Defender](https://aka.ms/DefenderforIdentitysetup) 설정 가이드는 사용자 ID를 손상시킬 수 있는 고급 위협을 식별, 감지 및 조사하기 위한 보안 솔루션 설정 지침을 제공합니다. 여기에는 의심스러운 사용자 활동 및 조직에 대한 악의적인 내부자 작업 검색이 포함됩니다. ID 인스턴스에 대한 Defender를 만들고 조직의 Active Directory에 연결한 다음 센서, 경고, 알림을 설정하고 고유한 포털 기본 설정을 구성합니다. 

### <a name="microsoft-information-protection-setup-guide"></a>Microsoft 정보 보호 설정 가이드

중요한 정보가 보호될 수 있도록 정보 보호 전략에 적용할 수 있는 기능에 대한 개요를 얻습니다. 중요한 정보를 검색, 분류, 보호 및 모니터링하는 4단계 라이프사이클 방식을 사용합니다. [Microsoft 정보 보호 설정 가이드](https://aka.ms/mipsetupguide)는 이러한 각 단계를 완료하기 위한 지침을 제공합니다.

### <a name="microsoft-information-governance-setup-guide"></a>Microsoft 정보 거버넌스 설정 가이드

[Microsoft 정보](https://aka.ms/migsetupguide) 거버넌스 설정 가이드에서는 설정한 특정 수명 주기 지침에 따라 데이터를 분류하고 관리하기 위해 조직의 거버넌스 전략을 설정하고 관리하는 데 필요한 정보를 제공합니다. 이 가이드에서는 조직의 다시 사용할 수 있는 콘텐츠 및 규정 준수 레코드에 적용되는 레이블, 레이블 정책 및 보존 정책을 만들거나, 자동으로 적용하거나, 게시하는 방법을 배우게 됩니다. 또한 대량 시나리오에 대한 파일 계획으로 CSV 파일을 가져오거나 개별 문서에 수동으로 적용하는 데 대한 정보를 얻을 수 있습니다.

### <a name="microsoft-cloud-app-security-setup-guide"></a>Microsoft Cloud App Security 설정 가이드

이 [Microsoft Cloud App Security](https://aka.ms/cloudappsecuritysetup) 배포 및 관리 지침을 따라 클라우드 검색 솔루션을 설정하기 쉽게 제공합니다. 클라우드 검색을 사용하여 지원되는 보안 앱을 통합한 다음 트래픽 로그를 사용하여 조직에서 사용하는 클라우드 앱을 동적으로 검색하고 분석합니다. 또한 위험 사용을 식별하는 위협 감지 정책, 액세스를 정의하는 정보 보호 정책 및 활동을 모니터링하기 위한 실시간 세션 제어를 포함하여 Cloud App Security 솔루션을 통해 사용할 수 있는 기능을 설정할 수 있습니다. 이러한 기능을 사용하여 환경은 모든 Microsoft 및 타사 클라우드 서비스에서 사이버 위협을 식별하고 퇴치하기 위해 향상된 가시성, 데이터 이동 제어 및 분석을 제공합니다.

## <a name="guides-for-collaboration"></a>공동 작업 가이드

### <a name="build-your-employee-experience"></a>직원 환경 구축

직원 환경 대시보드를 사용하여 직원이 함께 작업하는 [방법을 변환합니다.](https://aka.ms/EmployeeExperienceDashboard) 원활한 팀워크를 Microsoft 365 팀을 만들어 생산성을 향상하고, 직원들이 리더십과 나머지 조직에 참여하도록 합니다. 직원들이 모든 작업 활동에 효과적이면 도움을 줄 수 있습니다. 이 가이드에서는 생산성을 높이기 위해 SharePoint, Teams 및 Yammer 사용하여 공동 작업을 구축하는 방법에 대한 지침을 제공합니다.

### <a name="microsoft-365-apps-deployment-advisor"></a>Microsoft 365 앱 배포 고문

Microsoft 365 앱 [배포](https://aka.ms/OPPquickstartguide) 어드바이저는 Word, Excel, PowerPoint 및 앱과 같은 최신 버전의 Office 제품을 실행하는 사용자의 장치를 OneNote. 관리 도구를 사용하여 엔터프라이즈 배포에 손쉬운 자체 설치 옵션이 포함된 다양한 배포 방법에 대한 지침을 얻을 수 있습니다. 이 지침은 환경을 평가하고, 특정 배포 요구 사항을 확인하며, 성공적인 설치를 위해 필요한 지원 도구를 구현하는 데 도움이 됩니다.

### <a name="mobile-apps-setup-guide"></a>모바일 앱 설정 가이드

모바일 [앱 설정](https://aka.ms/officeappguidance) 가이드는 Office, iOS 및 Android 모바일 장치에서 Windows 앱의 다운로드 및 설치에 대한 지침을 제공합니다. 이 가이드에서는 휴대폰 및 태블릿 장치에 Microsoft 365 및 Office 365 단계별 정보를 제공합니다.

### <a name="microsoft-teams-setup-guide"></a>Microsoft Teams 설정 가이드

Microsoft Teams [](https://aka.ms/teamsguidance) 설정 가이드는 조직에 팀과 개인 통신을 위한 메시징, 통화 및 오디오 또는 비디오 모임을 통해 실시간 대화를 호스팅하는 팀 작업 영역 설정에 대한 지침을 제공합니다. 이 가이드의 도구를 사용하여 PowerShell 세션을 열지 않고도 게스트 액세스를 구성하고, 팀을 만들 수 있는 사용자와 팀 구성원을 .csv 파일을 추가할 수 있습니다. 조직의 네트워크 요구 사항을 파악하고 배포를 성공적으로 완료하기 위한 모범 Teams 있습니다.

### <a name="microsoft-teams-for-education-setup-guide"></a>교육용 Microsoft Teams 설정 가이드

교육용 Microsoft Teams [](https://aka.ms/teamsedusetup) 설정 가이드는 학교에 공동 작업 강의실, 대화, 모임, 파일 및 앱을 한 장소에 함께 제공하는 지침을 제공합니다. 또한 이 가이드에서는 학교에 맞게 설정을 준비, 계획 Teams 지침도 제공합니다. 배포가 완료되면 기본 제공 도구를 사용하여 팀을 만들 수 있는 사용자 구성을 구성하고, 선택적으로 팀을 직접 만들어 구성원을 .csv 있습니다.

### <a name="sharepoint-setup-guide"></a>SharePoint 설정 가이드

SharePoint [](https://aka.ms/spoguidance) 설정 가이드는 문서 저장 및 콘텐츠 관리를 설정하고SharePoint 사이트를 만들고, 외부 공유를 구성하고, 데이터를 마이그레이션하고, 고급 설정을 구성하고, 조직 내에서 사용자 참여 및 통신을 유도하는 데 도움이 됩니다. 콘텐츠 공유 권한 정책을 구성하기 위한 단계를 수행하고, 마이그레이션 동기화 도구를 선택하고, 사용자 환경의 보안 설정을 SharePoint 있습니다.

### <a name="onedrive-setup-guide"></a>OneDrive 설정 가이드

파일 [OneDrive,](https://aka.ms/ODfBquickstartguide) 공유, 공동 작업 및 동기화 기능을 OneDrive 시작할 수 있습니다. OneDrive 파일을 동기화하고, 외부 공유를 Microsoft 365 앱, 사용자 데이터를 마이그레이션하고, 고급 보안 및 장치 액세스 설정을 구성할 수 있는 중앙 위치를 제공합니다. OneDrive 설치 가이드는 OneDrive 독립 실행형 계획 또는 독립 실행형 OneDrive 배포할 수 있습니다.

### <a name="yammer-deployment-advisor"></a>Yammer 배포 고문

커넥트 조직 전체에서 사용자 참여를 Yammer. Yammer [배포](https://aka.ms/yammerdeploymentguide) 관리자는 도메인을 추가하고Yammer 관리자를 정의하고 네트워크 네트워크를 결합하여 Yammer 준비합니다. 보안 및 규정 준수를 배포하고 Yammer 사용자 지정하고, 보안 및 규정 준수를 구성하고, 설정을 구체화하는 지침을 얻을 수 있습니다.

## <a name="advanced-guides"></a>고급 가이드

### <a name="in-place-upgrade-with-configuration-manager"></a>Configuration Manager를 통해 전사 업그레이드

Windows 7 및 Windows 8.1 장치를 최신 버전으로 업그레이드할 때 [Configuration Manager를](https://aka.ms/win10upgradedemo) 사용하여 현재 Windows 10. 제공된 스크립트를 사용하여 선행 작업을 확인하고 자동으로 전제 업그레이드를 구성합니다.

### <a name="deploy-office-to-your-users"></a>사용자에게 Office 배포

Office 도구를 사용하여 설치를 사용자 지정하는 기능을 사용하여 클라우드에서 Office 배포합니다. 사용자에게 [Office](https://aka.ms/proplusodt) 배포 가이드는 고급 설정으로 사용자 지정된 Office 구성을 만들거나 미리 작성된 권장 구성을 사용할 수 있습니다. 사용자가 자체 설치를 수행하거나 개별적으로 또는 대량으로 사용자에게 배포하는 경우 이 고급 가이드에서는 사용자에게 조직에 맞는 설치를 Office 단계별 지침을 제공합니다.

### <a name="deploy-office-to-remote-users"></a>원격 Office 배포

이제 원격으로 작업하는 것이 규범이기 때문에 사용자가 내부 네트워크에 연결되어 있지 않을 때 또는 자신의 장치를 사용할 때 조직의 Office 설정을 수신해야 합니다.

원격 [사용자에](https://aka.ms/officeremoteinstall) Office 배포 가이드를 사용하여 사용자 지정된 Office 설치를 만든 다음 구성과 함께 원활하게 설치되는 생성된 PowerShell Office 전송합니다.

### <a name="deploy-and-update-microsoft-365-apps-with-configuration-manager"></a>Configuration Manager를 Microsoft 365 앱 배포 및 업데이트

Configuration Manager를 사용하는 조직의 경우 [Configuration Manager](https://aka.ms/oppinstall) 관리자와 함께 배포 및 업데이트 Microsoft 365 앱 사용하여 Microsoft 365 앱 엔지니어가 권장하는 모범 사례를 사용하여 Microsoft 365 앱 스크립트를 생성할 FastTrack 있습니다. 이 가이드를 사용하여 배포 그룹을 빌드하고, Office 앱 및 기능을 사용자 지정하고, 동적 또는 기울이지 않은 설치를 구성한 다음 스크립트를 실행하여 배포 대상으로 지정하는 데 필요한 응용 프로그램, 자동 배포 규칙 및 장치 컬렉션을 만들 수 있습니다.

### <a name="intune-configuration-manager-co-management-setup-guide"></a>Intune Configuration Manager 공동 관리 설정 가이드

[Intune Configuration Manager](https://aka.ms/comanagementsetup) 공동 관리 설정 가이드를 사용하여 기존 Configuration Manager 클라이언트 장치 및 구성 관리자와 함께 관리하려는 새 인터넷 기반 장치를 Microsoft Intune 수 있습니다. 공동 관리를 사용하면 Windows 10 장치를 관리하고, 두 솔루션의 이점을 모두 받아서 새로운 기능을 추가할 수 있습니다.
