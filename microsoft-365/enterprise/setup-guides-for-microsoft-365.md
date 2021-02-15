---
title: Microsoft 365 및 Office 365 서비스용 설정 가이드
ms.author: josephd
author: JoeDavies-MSFT
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
description: 설치 가이드를 통해 Microsoft 365 또는 Office 365의 계획 및 구성을 가속화합니다.
ms.openlocfilehash: 9bddf24e4133dfac32a0175b754709ba0c840760
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794427"
---
# <a name="setup-guides-for-microsoft-365-and-office-365-services"></a>Microsoft 365 및 Office 365 서비스용 설정 가이드

Microsoft 365 및 Office 365 설정 가이드는 테넌트, 앱 및 서비스를 계획하고 배포하기 위한 맞춤형 지침과 리소스를 제공합니다. 이 가이드는 [Microsoft 365 FastTrack](https://www.microsoft.com/fasttrack/microsoft-365) 온보더링 전문가가 개별 상호 작용에서 공유하는 모범 사례를 사용하여 작성된 것으로, Microsoft 365 관리 센터 내의 모든 관리자가 사용할 수 있습니다. 또한 제품 설정에 대한 정보를 제공하고, 보안 기능을 사용하도록 설정하고, 공동 작업 도구를 배포하고, 고급 배포 속도를 향상하기 위한 스크립트를 제공합니다.

## <a name="how-to-access-setup-guides-in-the-microsoft-365-admin-center"></a>Microsoft 365 관리 센터에서 설정 가이드에 액세스하는 방법

설치 가이드는 Microsoft 365 관리 센터의 설치 지침 페이지에서 액세스할 수 있습니다. [](https://aka.ms/setupguidance) 진행 상황을 추적할 수 있으며, 안내를 완료하기 위해 항상 돌아올 수 있는 옵션이 제공됩니다. 설치 지침 **페이지에 연결하려면**

1. Microsoft [365](https://admin.microsoft.com/)관리 센터에서 홈 **페이지로** 이동합니다.

2. 교육 가이드 **& 찾을 수** 있습니다. 

   ![교육 & Microsoft 365 관리 센터의 교육 가이드 카드](../media/setup-guides-for-microsoft-365/adminportal-trainingandguides.png)

3. 사용자 **지정된 설정 지침을 선택합니다.**

   ![Microsoft 365 관리 센터의 설치 지침 페이지 스크린샷](../media/setup-guides-for-microsoft-365/adminportal-setupguidance.png)

>[!NOTE]
>Microsoft 365 관리 센터에 액세스하려면 테넌트 관리자 권한이 필요합니다.

## <a name="how-do-setup-guides-work-in-the-microsoft-365-admin-center"></a>Microsoft 365 관리 센터에서 설치 가이드는 어떻게 작동하나요?

각 가이드에서는 단계별 지침, 리소스, 문서 및 필요한 경우 구성을 변경하는 데 사용할 수 있는 스크립트를 제공합니다. 이 가이드에서는 소규모 및 대규모 조직의 특정 요구 사항을 반영하는 선택 사항을 제공합니다. 또한 이 지침에는 신규 관리자와 더 많은 숙련된 관리자에 대한 지원이 포함되어 있습니다.

![설정 가이드의 예](../media/setup-guides-for-microsoft-365/m365-setupguide-example.png)

이 가이드를 사용하여 계획 단계 중, 배포 및 출시 중에 특정 Microsoft 365 및 Office 365 기능에 대해 자세히 알아보거나 설정을 수정하기 위한 배포를 완료한 후 다시 참조할 수 있습니다.

## <a name="guides-for-initial-setup"></a>초기 설정 가이드

### <a name="prepare-your-environment"></a>환경 준비

환경 [준비 가이드는](https://aka.ms/prepareyourenvironment) Microsoft 365 및 Office 365 서비스를 위한 조직의 환경을 준비하는 데 도움이 됩니다. 목표에 관계없이 성공적인 배포를 위해 완료해야 하는 작업이 있습니다. 환경을 준비하는 동안 오류를 방지하려면 도메인 연결, 사용자 추가, 라이선스 할당, Exchange Online으로 전자 메일 설정, Office 앱 설치 또는 배포에 대한 단계별 지침이 제공됩니다. 

### <a name="email-setup-advisor"></a>전자 메일 설정 어드바이저

전자 [메일 설정 어드바이저는](https://aka.ms/office365setup) 조직에 대해 Exchange Online을 구성하는 데 필요한 단계별 지침을 제공합니다. 여기에는 새 전자 메일 계정 설정, 전자 메일 마이그레이션 및 전자 메일 보호 구성이 포함됩니다. 전자 메일을 성공적으로 설정하려면 이 고문을 사용하여 조직의 현재 메일 시스템, 마이그레이션되는 사서함 수 및 사용자 및 액세스 관리 방법에 따라 권장되는 마이그레이션 방법을 받게 됩니다.

### <a name="migrate-gmail-contacts-and-calendar-items"></a>Gmail 연락처 및 일정 항목 마이그레이션

Gmail 사용자의 사서함을 Microsoft 365로 마이그레이션하면 전자 메일 메시지가 마이그레이션되지만 연락처 및 일정 항목은 마이그레이션되지 않습니다. Gmail 연락처 및 [일정](https://aka.ms/gmailcontactscalendar) 고문은 Outlook, Outlook 클라이언트 또는 PowerShell에서 가져오기 및 내보내기 방법을 사용하여 Google 연락처 및 Google 일정 항목을 Microsoft 365로 가져오는 Outlook.com 단계를 제공합니다.

### <a name="microsoft-365-deployment-advisor"></a>Microsoft 365 배포 고문

[Microsoft 365 배포](https://aka.ms/microsoft365setupguide) 고문은 생산성 도구, 보안 정책 및 장치 관리 기능을 설정할 때 지침을 제공합니다. Microsoft 365 Business Premium 또는 엔터프라이즈용 Microsoft 365 구독을 사용하면 이 고문을 사용하여 조직의 장치를 설정하고 구성할 수 있습니다. 

클라우드 서비스를 사용하도록 설정하고, 디바이스를 지원되는 최신 버전의 Windows 10으로 업데이트하고, 장치를 하나의 중앙 위치에서 Azure AD(Azure Active Directory)에 가입하기 위한 지침 및 액세스 권한을 받게 됩니다.


### <a name="remote-work-setup-guide"></a>원격 작업 설정 가이드

원격 [작업](https://aka.ms/remoteworksetup) 설정 가이드는 사용자가 원격으로 작업하고 데이터를 안전하게 보호하며 사용자의 자격 증명을 보호하는 데 필요한 팁과 리소스를 조직에 제공합니다. 

클라우드의 Microsoft 365 리소스와 조직의 네트워크에 대한 원격 작업자의 장치 트래픽을 최적화하기 위한 지침을 받게 되어 원격 액세스 VPN 인프라에 대한 부담을 줄일 수 있습니다. 

### <a name="windows-virtual-desktop-setup-guide"></a>Windows 가상 데스크톱 설정 가이드

Windows Virtual Desktop은 클라우드에서 실행되는 포괄적인 데스크톱 및 앱 가상화 서비스입니다. 간소화된 관리, 다중 세션 Windows 10, Microsoft 365 앱에 대한 최적화 및 RDS(원격 데스크톱 서비스) 환경에 대한 지원을 제공하는 유일한 가상 데스크톱 인프라(VDI)입니다. 몇 분 만에 Windows 데스크톱 및 앱을 Azure로 배포 및 확장하고 기본 제공 보안 및 규정 준수 기능을 사용할 수 있습니다. 

[Windows Virtual Desktop 설치](https://aka.ms/wvdsetupguide) 가이드는 관리자에게 배포, 설정 지침 및 추가 리소스에 대한 계획 리소스 및 선행 구성을 제공합니다. 

### <a name="microsoft-edge-setup-guide"></a>Microsoft Edge 설정 가이드

Microsoft Edge는 세계적 수준의 호환성과 성능, 자격이 있는 보안 및 개인 정보 보호, 웹을 최상으로 개선하기 위해 설계된 새로운 기능을 제공하도록 새로 고안되었습니다.

[Microsoft Edge](https://aka.ms/edgeadvisor) 설정 가이드는 IE 모드를 사용하는 데 필요할 수 있는 사이트를 확인하도록 엔터프라이즈 사이트 검색을 구성하고, 중요한 보안 기능을 검토 및 구성하고, 사용자의 요구 사항에 맞게 개인 정보 취급 방침 및 추가 정책을 구성하고, 장치에서 웹 액세스를 관리하는 데 도움이 됩니다. Microsoft Edge를 개별 디바이스에 다운로드할 수도 있습니다. 또는 Configuration Manager 또는 Microsoft Intune을 사용하여 여러 사용자에게 배포하는 방법을 보여 주게 됩니다. 

### <a name="microsoft-search-setup-guide"></a>Microsoft 검색 설정 가이드

Microsoft Search를 사용하면 조직에서 작업 중 완료하는 데 필요한 정보를 찾을 수 있습니다. 사용자, 파일, 사이트 또는 일반적인 질문에 대한 답변을 검색하는지 여부에 관계 없는 경우, 작업일 전체에서 Microsoft Search를 사용하여 답변을 얻을 수 있습니다.

Microsoft 검색 설정 [가이드를](https://aka.ms/MicrosoftSearchSetup) 사용하면 사용자 그룹에 파일럿하거나 조직 내 모든 사용자에게 배포할지 여부를 Microsoft Search를 구성할 수 있습니다. 검색 관리자 및 검색 편집기를 할당한 다음 Bing 확장명을 Chrome에 추가하거나 Bing을 기본 검색 엔진으로 설정하는 등 답변 및 추가 옵션으로 사용자의 검색 환경을 사용자 지정합니다.

### <a name="intune-configuration-manager-co-management-setup-guide"></a>Intune Configuration Manager 공동 관리 설정 가이드

기존 Configuration Manager 클라이언트 장치 및 Microsoft Intune 및 Configuration Manager와 함께 관리하려는 새 인터넷 기반 장치에 대해 [Intune Configuration Manager](https://aka.ms/comanagementsetup) 공동 관리 설정 가이드를 사용하세요. 이 공동 관리 배포 가이드를 사용하면 Windows 10 디바이스를 관리하고, 두 솔루션의 이점을 모두 받는 동시에 새로운 기능을 해당 디바이스에 추가할 수 있습니다.

## <a name="guides-for-authentication-and-access"></a>인증 및 액세스 가이드

### <a name="azure-ad-setup-guide"></a>Azure AD 설정 가이드

[Azure AD 설정 가이드는](https://aka.ms/aadpguidance) 조직에 강력한 보안 기반이 되도록 하는 정보를 제공합니다. 이 가이드에서는 관리자를 위한 Azure RBAC(역할 기반 액세스 제어), On-premises 디렉터리용 Azure AD Connect 및 Azure AD Connect Health와 같은 초기 기능을 설정하여 자동화된 동기화 중에 하이브리드 ID의 상태 모니터링을 할 수 있습니다. 

또한 선택적 고급 ID 보호 및 사용자 프로비저닝 자동화를 포함하여 셀프 서비스 암호 재설정, 조건부 액세스 및 통합된 타사 로그인을 사용하도록 설정하는 데 필요한 정보도 포함되어 있습니다.

### <a name="sync-users-from-your-orgs-directory"></a>사용자의 디렉터리에서 사용자 동기화

디렉터리 [마법사의](https://aka.ms/directorysyncsetup) 동기화 사용자는 디렉터리 동기화를 켜는 방법을 안내합니다. 이렇게 하면 더 쉽게 액세스하고 관리를 간소화할 수 있도록 프레미스 및 클라우드 ID가 함께 제공됩니다. Single Sign-On, 셀프 서비스 옵션, 자동 계정 프로비전, 조건부 액세스 제어 및 규정 준수 정책과 같은 새로운 기능의 잠금을 해제합니다. 이렇게 하면 사용자가 어디에서나 필요한 리소스에 액세스할 수 있습니다.

### <a name="plan-your-passwordless-deployment"></a>암호 없는 배포 계획

사용자가 다음 암호 없는 인증 방법 중 하나를 사용하여 장치에 안전하게 액세스할 수 있도록 하는 대체 로그인 접근 방법으로 업그레이드합니다. 

- 비즈니스용 Windows Hello
- Microsoft Authenticator 앱
- 보안 키 

암호 [없는](https://aka.ms/passwordlesssetup) 배포 계획 마법사를 사용하여 암호 없는 최상의 인증 방법을 찾아 배포 방법에 대한 지침을 받을 수 있습니다. 

### <a name="plan-your-self-service-password-reset-sspr-deployment"></a>SSPR(셀프 서비스 암호 재설정) 배포 계획

사용자에게 계정이 잠겨 있는 경우 암호를 독립적으로 변경하거나 다시 설정할 수 있는 기능을 제공하거나 기술 지원 팀 엔지니어에게 연락할 필요 없이 암호를 잊어버려야 합니다. 

셀프 [](https://aka.ms/SSPRSetupGuide) 서비스 암호 재설정 배포 계획 마법사를 사용하여 환경에 SSPR을 배포하는 데 도움이 되는 적절한 Azure Portal 옵션을 구성하기 위한 관련 문서 및 지침을 받을 수 있습니다.

### <a name="active-directory-federation-services-ad-fs-deployment-advisor"></a>AD FS(Active Directory Federation Services) 배포 고문

[AD FS](https://aka.ms/adfsguidance) 배포 어드바이저는 Microsoft 365 및 Office 365 서비스에 대해 사용자를 인증하는,프레미스 AD FS 인프라 배포에 대한 단계별 지침을 제공합니다. 이 가이드를 사용하여 조직은 AD FS 구성 요소 및 요구 사항을 검토하고, 배포에 필요한 SSL 인증서를 획득 및 설치하고, 필요한 웹 응용 프로그램 프록시 서버를 설치할 수 있습니다. 

## <a name="guides-for-security-and-compliance"></a>보안 및 규정 준수 가이드

### <a name="microsoft-intune-setup-guide"></a>Microsoft Intune 설정 가이드 

조직에서 디바이스를 관리하기 위해 Microsoft Intune을 설정합니다. 회사 장치에 대한 모든 제어를 위해 Intune의 MDM(모바일 장치 관리) 기능을 사용합니다. 공유 및 개인 장치에서 조직의 데이터를 관리하기 위해 Intune의 MAM(모바일 응용 프로그램 관리) 기능을 사용할 수 있습니다. 

Microsoft [Intune 설정](https://aka.ms/intunesetupguide)가이드를 사용하여 장치 및 앱 준수 정책을 설정하고, 앱 보호 정책을 할당하고, 장치 및 앱 보호 상태를 모니터링합니다. 

### <a name="microsoft-defender-for-endpoint-advisor"></a>끝점용 Microsoft Defender 어드바이저

[끝점용 Microsoft Defender](https://aka.ms/mdatpsetup) 어드바이저는 엔터프라이즈 네트워크에서 고급 위협을 방지, 감지, 조사 및 대응하는 데 도움이 되는 지침을 제공합니다. 조직의 취약점을 정보를 통해 평가하고 가장 적합한 배포 패키지 및 구성 방법을 결정하십시오. 

>[!NOTE]
>끝점용 Microsoft Defender에는 Microsoft 볼륨 라이선스가 필요합니다.

### <a name="exchange-online-protection-setup-guide"></a>Exchange Online Protection 설정 가이드

Microsoft Exchange Online 보호(EOP)는 스팸 및 맬웨어로부터 보호하는 클라우드 기반 전자 메일 필터링 서비스로, 메시징 정책 위반으로부터 조직을 보호하는 기능을 제공합니다. 

Exchange [Online Protection](https://aka.ms/EOPguidance) 설정 가이드를 사용하여 세 가지 배포 시나리오 중 조직에 맞는 세 가지 배포 시나리오, 하이브리드(하이브리드 및 클라우드의 혼합) 사서함 또는 모든 클라우드 사서함을 선택하여 EOP를 설정할 수 &mdash; &mdash; 있습니다. 이 가이드에서는 사용자 라이선스를 설정 및 검토하고, Microsoft 365 관리 센터에서 사용 권한을 할당하고, 보안 및 준수 센터에서 조직의 맬웨어 방지 및 스팸 정책을 & 정보를 제공합니다. 

### <a name="microsoft-defender-for-office-365-advisor"></a>Microsoft Defender for Office 365 advisor

[Microsoft Defender for Office 365 advisor는](https://aka.ms/oatpsetup) 전자 메일 메시지, 링크 및 타사 공동 작업 도구를 통해 환경에 발생할 수 있는 악의적인 위협에 대해 조직을 보호합니다. 이 가이드에서는 조직의 요구에 맞게 Office 365용 Defender 계획을 준비하고 식별하는 데 도움이 되는 리소스와 정보를 제공합니다. 

### <a name="microsoft-information-protection-setup-guide"></a>Microsoft 정보 보호 설정 가이드

중요한 정보가 보호될 수 있도록 정보 보호 전략에 적용할 수 있는 기능에 대한 개요를 얻습니다. 중요한 정보를 검색, 분류, 보호 및 모니터링하는 4단계 라이프사이클 방식을 사용합니다. [Microsoft 정보 보호 설정 가이드에서는](https://aka.ms/mipsetupguide) 이러한 각 단계를 완료하기 위한 지침을 제공합니다.

### <a name="microsoft-information-governance-setup-guide"></a>Microsoft 정보 거버넌스 설정 가이드

[Microsoft 정보](https://aka.ms/migsetupguide) 거버넌스 설정 가이드에서는 설정한 특정 수명 주기 지침에 따라 데이터가 분류되고 관리되도록 조직의 거버넌스 전략을 설정하고 관리하는 데 필요한 정보를 제공합니다. 이 가이드에서는 조직의 다시 사용할 수 있는 콘텐츠 및 규정 준수 레코드에 적용되는 레이블, 레이블 정책 및 보존 정책을 작성, 자동 적용 또는 게시하는 방법을 배우게 됩니다. 또한 대량 시나리오에 대한 파일 계획으로 CSV 파일을 가져오거나 개별 문서에 수동으로 적용하는 데 대한 정보를 얻을 수 있습니다. 

## <a name="guides-for-collaboration"></a>공동 작업 가이드

### <a name="microsoft-365-apps-deployment-advisor"></a>Microsoft 365 앱 배포 어드바이저

[Microsoft 365 앱](https://aka.ms/OPPquickstartguide) 배포 어드바이저를 사용하면 Word, Excel, PowerPoint 및 OneNote와 같은 최신 버전의 Office 제품을 실행하는 사용자의 디바이스를 얻을 수 있습니다. 관리 도구를 사용하여 엔터프라이즈 배포에 손쉬운 자체 설치 옵션을 포함 하는 다양한 배포 방법에 대한 지침을 얻을 수 있습니다. 이 지침은 환경을 평가하고, 특정 배포 요구 사항을 확인하며, 성공적인 설치를 위해 필요한 지원 도구를 구현하는 데 도움이 됩니다. 

### <a name="mobile-apps-setup-guide"></a>모바일 앱 설정 가이드

모바일 [앱 설정 가이드는](https://aka.ms/officeappguidance) Windows, iOS 및 Android 모바일 장치에서 Office 앱을 다운로드하고 설치하기 위한 지침을 제공합니다. 이 가이드에서는 휴대폰 및 태블릿 장치에 Microsoft 365 및 Office 365 앱을 다운로드하고 설치하기 위한 단계별 정보를 제공합니다.

### <a name="microsoft-teams-setup-guide"></a>Microsoft Teams 설정 가이드

[Microsoft Teams](https://aka.ms/teamsguidance) 설정 가이드는 조직에 팀과 개인 통신을 위한 메시징, 통화 및 오디오 또는 비디오 모임을 통해 실시간 대화를 호스팅하는 팀 작업 영역 설정에 대한 지침을 제공합니다. Teams 관리 센터 내에서 네트워크 플래너 도구 및 Teams 관리자를 사용하여 조직의 네트워크 요구 사항을 결정하기 위한 지침을 받게 됩니다. 배포가 완료되면 Teams 사용에 유용한 리소스를 포함하는 가이드를 볼 수 있습니다.

### <a name="sharepoint-setup-guide"></a>SharePoint 설정 가이드

[SharePoint](https://aka.ms/spoguidance) 설정 가이드를 사용하면 SharePoint 문서 저장 및 콘텐츠 관리를 설정하고, 사이트를 만들고, 외부 공유를 구성하고, 데이터를 마이그레이션하고, 고급 설정을 구성하고, 조직 내에서 사용자 참여 및 통신을 유도할 수 있습니다. 콘텐츠 공유 권한 정책을 구성하기 위한 단계를 수행하고, 마이그레이션 동기화 도구를 선택하고, SharePoint 환경에 대한 보안 설정을 사용하도록 설정할 수 있습니다. 

### <a name="onedrive-setup-guide"></a>OneDrive 설정 가이드

[OneDrive 설정](https://aka.ms/ODfBquickstartguide) 가이드를 사용하여 OneDrive 파일 저장소, 공유, 공동 작업 및 동기화 기능을 시작할 수 있습니다. OneDrive는 사용자가 Microsoft 365 앱 파일을 동기화하고, 외부 공유를 구성하고, 사용자 데이터를 마이그레이션하고, 고급 보안 및 장치 액세스 설정을 구성할 수 있는 중앙 위치를 제공합니다. OneDrive 설정 가이드는 OneDrive 구독 또는 독립 실행형 OneDrive 요금제로 배포할 수 있습니다. 

### <a name="yammer-deployment-advisor"></a>Yammer 배포 고문

조직 전체에 연결하고 조직 전체에 Yammer. Yammer [배포](https://aka.ms/yammerdeploymentguide) 관리자는 도메인을 추가하고Yammer 관리자를 정의하고 네트워크 네트워크를 결합하여 Yammer 준비합니다. 사용자 지정 기능을 배포한 다음 모양을 Yammer 보안 및 규정 준수를 구성하고 설정을 구체화하는 방법에 대한 지침을 얻게 됩니다.

## <a name="advanced-wizards"></a>고급 마법사

### <a name="in-place-upgrade-with-configuration-manager"></a>Configuration Manager를 통해 전방 업그레이드

Windows 7 및 Windows 8.1 장치를 최신 버전의 Windows 10으로 업그레이드할 때 [Configuration Manager](https://aka.ms/win10upgradedemo) 가이드를 사용하여 현재 업그레이드를 사용하세요. 제공된 스크립트를 사용하여 선행 작업을 확인하고 자동으로 전제 업그레이드를 구성합니다.

### <a name="deploy-office-to-your-users"></a>사용자에게 Office 배포

Office 배포 도구를 사용하여 설치를 사용자 지정할 수 있는 기능을 사용하여 클라우드에서 Office 앱을 배포합니다. 사용자에 [Office 배포 ](https://aka.ms/proplusodt) 가이드를 사용하면 고급 설정으로 사용자 지정된 Office 구성을 만들거나 미리 작성된 권장 구성을 사용할 수 있습니다. 사용자가 자체 설치를 수행하거나 개별적으로 또는 대량으로 사용자에게 배포하는 경우 이 고급 마법사는 사용자에게 조직에 맞게 Office 설치를 제공하는 단계별 지침을 제공합니다.

### <a name="deploy-office-to-remote-users"></a>원격 사용자에게 Office 배포

이제 원격으로 작업하는 것이 규범이 되었습니다. 사용자는 내부 네트워크에 연결되어 있지 않을 때 또는 자신의 장치를 사용할 때 조직의 Office 설정을 수신해야 합니다. 

원격 [사용자에 Office](https://aka.ms/officeremoteinstall) 배포 가이드를 사용하여 사용자 지정된 Office 설치를 만든 다음 구성과 함께 Office를 원활하게 설치할 수 있는 생성된 PowerShell 스크립트를 사용자에게 전송합니다.

### <a name="deploy-and-update-microsoft-365-apps-with-configuration-manager"></a>Configuration Manager를 사용하여 Microsoft 365 앱 배포 및 업데이트

Configuration Manager를 사용하는 조직의 경우 Configuration Manager 관리자와 [함께 Microsoft 365](https://aka.ms/oppinstall) 앱 배포 및 업데이트 기능을 사용하여 FastTrack 엔지니어가 권장하는 모범 사례를 사용하여 Microsoft 365 앱 배포를 자동으로 구성하는 스크립트를 생성할 수 있습니다. 이 가이드를 사용하여 배포 그룹을 빌드하고, Office 앱 및 기능을 사용자 지정하고, 동적 또는 린트 설치를 구성한 다음 스크립트를 실행하여 배포 대상으로 지정하는 데 필요한 응용 프로그램, 자동 배포 규칙 및 장치 컬렉션을 만들 수 있습니다. 
