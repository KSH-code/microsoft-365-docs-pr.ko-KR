---
title: Microsoft Managed Desktop의 필수 구성 요소
description: 라이선스, Azure 계정, 인증 설정 및 Microsoft 365 설정한 후 설정해야 Microsoft Managed Desktop
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 999667771bc33ff6e09b5afdff80c61c91daa601
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59212425"
---
# <a name="prerequisites-for-microsoft-managed-desktop"></a>Microsoft Managed Desktop의 필수 구성 요소

<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/prereq-azure); do not delete.-->
<!--from Prerequisites -->

이 항목에서는 요구 사항의 성공을 보장하기 위해 충족해야 하는 인프라 요구 사항에 대해 Microsoft Managed Desktop.


영역 | 선행 세부 정보
--- | ---
라이선싱 |Microsoft Managed Desktop 사용자에게 Microsoft 365 E3 Microsoft Defender for Endpoint(또는 그와 동등한) 라이선스가 필요합니다.<br>특정 서비스 계획에 대한 자세한 내용은 이 항목의 [라이선스에](#more-about-licenses) 대한 자세한 내용을 참조하세요.<br>사용 가능한 라이선스에 대한 자세한 내용은 라이선스 [Microsoft 365 참조하세요.](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans)
연결 | 모든 Microsoft Managed Desktop 장치를 사용하려면 회사 네트워크의 다양한 Microsoft 서비스 끝점에 연결해야 합니다.<br><br>필수 IP 및 URL의 전체 목록은 네트워크 구성 [을 참조하세요.](../get-ready/network.md) 
Azure Active Directory | Azure Active Directory(Azure AD)는 모든 사용자 계정에 대한 권한의 원본이 되어야 합니다. 또는 사용자 계정은 지원되는 최신 버전의 Azure AD 계정을 사용하여 사내 Active Directory에서 동기화해야 커넥트.<br><br>자세한 내용은 [Azure AD](/azure/active-directory/hybrid/whatis-azure-ad-connect)커넥트.<br><br>지원되는 Azure AD 커넥트 대한 자세한 내용은 [Azure AD 커넥트:Version 릴리스 기록을 참조하세요.](/azure/active-directory/hybrid/reference-connect-version-history)
인증 | Azure AD가 사용자 계정에 대한 기본 인증의 원본이 아닌 경우 Azure AD 계정에서 다음 중 하나를 구성해야 커넥트.<br>- 암호 해시 동기화<br>- 통과 인증<br>- Azure AD 통합 요구 사항을 Windows 구성된 외부 ID 공급자(Windows Server ADFS 및 비 Microsoft IDP 포함) 자세한 내용은 [지침을](https://www.microsoft.com/download/details.aspx?id=56843) 참조하세요. <br><br>Azure AD 2013에서 인증 옵션을 설정할 커넥트 암호 쓰기 저장도 권장됩니다. 자세한 내용은 암호 쓰기 [저장 을 참조하세요.](/azure/active-directory/authentication/howto-sspr-writeback) <br><br>외부 ID 공급자가 구현된 경우 솔루션의 유효성을 검사해야 합니다.<br>- Azure AD 통합 요구 사항 충족<br>- Azure AD 조건부 액세스를 지원하여 Microsoft Managed Desktop 준수 정책을 구성할 수 있습니다.<br>- 장치 등록 및 Microsoft 365 서비스의 일부로 필요한 기능의 사용을 Microsoft Managed Desktop <br><br>Azure AD의 인증 옵션에 대한 자세한 내용은 Azure AD 커넥트 [로그인 옵션을 참조하세요.](/azure/active-directory/connect/active-directory-aadconnect-user-signin)
Microsoft 365 | 비즈니스용 OneDrive 사용자에 대해 Microsoft Managed Desktop 합니다.<br><br>클라우드에 등록할 필요는 Microsoft Managed Desktop 다음 서비스를 클라우드로 마이그레이션하는 것이 좋습니다.<br>- 전자 메일: 클라우드 기반 사서함으로 마이그레이션하거나 온라인으로 Exchange 또는 Exchange Online 하이브리드를 사용하여 Exchange 2013 이상을 사용하여 구성합니다.<br>- 파일 및 폴더: 온라인 또는 비즈니스용 OneDrive SharePoint 마이그레이션합니다.<br>- 온라인 공동 작업 도구: 마이그레이션을 Teams.
디바이스 관리 | Microsoft Managed Desktop 장치를 사용하려면 장치를 사용하여 관리해야 Microsoft Intune. Intune은 모바일 장치 관리 기관으로 설정해야 합니다.<br><br>자세한 내용은 [를](https://www.microsoft.com/cloud-platform/microsoft-intune)Microsoft Intune.
데이터 백업 및 복구 | Microsoft Managed Desktop 보호를 위해 파일을 동기화해야 비즈니스용 OneDrive 합니다. 비즈니스용 OneDrive 동기화되지 않은 파일은 Microsoft Managed Desktop 장치 교환 또는 장치 초기화가 필요한 지원 통화 중에 손실될 수 있습니다.<br><br>필수는 Microsoft Managed Desktop 매핑된 네트워크 드라이브에서 적절한 클라우드 솔루션으로 마이그레이션하는 것이 좋습니다. 자세한 내용은 [Prepare mapped drives for Microsoft Managed Desktop](mapped-drives.md)

Microsoft 계정 관리자를 시작할 준비가 Microsoft Managed Desktop Microsoft 계정 관리자에게 문의하세요. 

## <a name="more-about-licenses"></a>라이선스에 대한 자세한 내용은

Microsoft Managed Desktop 사용하려면 특정 라이선스 옵션이 필요합니다. 이러한 [Microsoft Managed Desktop](../intro/technologies.md) 사용하는 방법에 대한 자세한 내용은 기술 정보를 참조하세요.

> [!TIP]
> 특정 사용자에게 이러한 라이선스 옵션을 할당하기 위해 특정 [](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal) 사용자의 그룹 기반 라이선싱 기능을 활용하는 Azure Active Directory.

- Azure Active Directory Premium P1
- Microsoft Intune
- Windows 10 Enterprise  
- 엔드포인트용 Microsoft Defender
- 엔터프라이즈용 Microsoft 365 앱
- Microsoft Teams
- [SharePoint Online 계획 2](https://www.microsoft.com/microsoft-365/sharepoint/compare-sharepoint-plans)
- [Exchange Online 계획 2](https://www.microsoft.com/microsoft-365/exchange/compare-microsoft-exchange-online-plans)

> [!TIP]
> Microsoft 계정 관리자를 사용하면 현재 라이선스 및 서비스 계획을 검토하고 중복을 방지하면서 필요한 추가 라이선스 또는 서비스 계획을 얻을 수 있는 가장 효율적인 경로를 찾을 수 있습니다.

## <a name="steps-to-get-ready-for-microsoft-managed-desktop"></a>준비 단계 Microsoft Managed Desktop

1. 선행조사(이 문서)를 검토합니다.
2. [준비 상태 평가 도구](readiness-assessment-tool.md)를 실행하세요.
1. [회사 포털](../get-started/company-portal.md)을 구입하세요.
1. [게스트 계정에 대한 필수 구성 요소](guest-accounts.md)를 검토합니다.
1. [네트워크 구성](network.md)을 확인합니다.
1. [인증서 및 네트워크 프로필을 준비](certs-wifi-lan.md)합니다.
1. [데이터에 대한 사용자 액세스를 준비](authentication.md)합니다.
1. [앱을 준비](apps.md)합니다.
1. [매핑된 드라이브를 준비](mapped-drives.md)합니다.
1. [인쇄 리소스를 준비](printing.md)합니다.
1. [장치 이름](address-device-names.md)을 기입합니다.