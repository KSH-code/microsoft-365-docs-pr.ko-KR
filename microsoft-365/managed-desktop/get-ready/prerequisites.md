---
title: Microsoft Managed Desktop의 필수 구성 요소
description: Microsoft Managed Desktop에 등록하기 전에 설정할 라이선스, Azure 계정, 인증 설정 및 Microsoft 365 설정
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 79ae949d9624021121492edb811a4ea5bfcc729a
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659143"
---
# <a name="prerequisites-for-microsoft-managed-desktop"></a>Microsoft Managed Desktop의 필수 구성 요소

<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/prereq-azure); do not delete.-->
<!--from Prerequisites -->

이 항목에서는 Microsoft Managed Desktop의 성공을 보장하기 위해 충족해야 하는 인프라 요구 사항에 대해 간략하게 설명합니다. 


영역 | 선행 사항 세부 정보
--- | ---
라이선싱 |Microsoft Managed Desktop에는 Microsoft Defender for Endpoint 및 Azure Active Directory Premium 2(또는 그와 동등한 라이선스)가 있는 Microsoft 365 E3 라이선스가 필요합니다.<br>특정 서비스 계획에 대한 자세한 내용은 [이](#more-about-licenses) 항목의 라이선스에 대한 자세한 내용을 참조하세요.<br>사용 가능한 라이선스에 대한 자세한 내용은 [Microsoft 365 라이선스를 참조하세요.](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)
연결 |  모든 Microsoft Managed Desktop 디바이스는 회사 네트워크에서 다양한 Microsoft 서비스 끝점에 연결해야 합니다.<br><br>필요한 IPS 및 URL의 전체 목록은 네트워크 구성을 [참조하세요.](../get-ready/network.md) 
Azure Active Directory |    Azure AD(Azure Active Directory)는 모든 사용자 계정에 대한 권한의 원본이거나, 지원되는 최신 버전의 Azure AD Connect를 사용하여 사용자 계정을 On-premises Active Directory에서 동기화해야 합니다.<br><br>[Microsoft Managed Desktop](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-overview) 사용자에 대해 엔터프라이즈 상태 로밍을 사용하도록 설정해야 합니다.<br><br>자세한 내용은 [Azure AD Connect를 참조하세요.](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect)<br><br>지원되는 Azure AD Connect 버전에 대한 자세한 내용은 [Azure AD Connect:버전 릴리스 기록을 참조하세요.](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-version-history)
인증 |    Azure AD가 사용자 계정에 대한 기본 인증의 원본이 아닌 경우 Azure AD Connect에서 다음 중 하나를 구성해야 합니다.<br>- 암호 해시 동기화<br>- 통과 인증<br>- Azure AD 통합 요구 사항을 충족하도록 구성된 외부 ID 공급자(Windows Server ADFS 및 비 Microsoft IDP 포함) 자세한 내용은 [지침을](https://www.microsoft.com/download/details.aspx?id=56843) 참조하세요. <br><br>Azure AD Connect를 사용하여 인증 옵션을 설정할 때 암호 쓰기 저장도 권장됩니다. 자세한 내용은 암호 쓰기 [저장을 참조하십시오.](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback) <br><br>외부 ID 공급자가 구현된 경우 솔루션의 유효성을 검사해야 합니다.<br>- Azure AD 통합 요구 사항 충족<br>- Microsoft Managed Desktop 장치 준수 정책을 구성할 수 있는 Azure AD 조건부 액세스를 지원<br>- Microsoft Managed Desktop의 일부로 필요한 Microsoft 365 서비스 또는 기능을 장치 등록 및 사용할 수 있습니다. <br><br>Azure AD를 사용하는 인증 옵션에 대한 자세한 내용은 Azure AD Connect 사용자 로그인 옵션을 [참조하세요.](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-user-signin)
Microsoft 365 | Microsoft Managed Desktop 사용자에 대해 비즈니스용 OneDrive를 사용하도록 설정해야 합니다.<br><br>Microsoft Managed Desktop에 등록할 필요는 없는 경우 다음 서비스를 클라우드로 마이그레이션하는 것이 좋습니다.<br>- 전자 메일: 클라우드 기반 사서함, Exchange Online으로 마이그레이션하거나 Exchange 2013 이상을 통해 Exchange Online 하이브리드를 사용하여 구성합니다.<br>- 파일 및 폴더: 비즈니스용 OneDrive 또는 SharePoint Online으로 마이그레이션<br>- 온라인 공동 작업 도구: Teams로 마이그레이션
디바이스 관리 | Microsoft Managed Desktop 장치는 Microsoft Intune을 사용하여 관리해야 합니다. Intune은 모바일 장치 관리 기관으로 설정해야 합니다.<br><br>자세한 내용은 [Microsoft Intune을 참조하세요.](https://www.microsoft.com/cloud-platform/microsoft-intune) 
데이터 백업 및 복구 |  Microsoft Managed Desktop을 사용하려면 파일을 보호를 위해 비즈니스용 OneDrive에 동기화해야 합니다. 비즈니스용 OneDrive와 동기화되지 않은 파일은 Microsoft Managed Desktop에서 보장되지 않고 장치 교환 또는 장치 초기화가 필요한 지원 통화 중에 손실될 수 있습니다.<br><br>필수는 아니어도 Microsoft Managed Desktop은 매핑된 네트워크 드라이브에서 적절한 클라우드 솔루션으로 마이그레이션하는 것이 좋습니다. 자세한 내용은 [Microsoft Managed Desktop용 매핑된 드라이브 준비를 참조하세요.](mapped-drives.md)

Microsoft Managed Desktop을 시작할 준비가 되면 Microsoft 계정 관리자에게 문의하세요. 

## <a name="more-about-licenses"></a>라이선스에 대한 자세한 내용은

Microsoft Managed Desktop을 사용하려면 특정 라이선스 옵션이 필요합니다. 이러한 라이선스가 사용되는 방법에 대한 자세한 내용은 [Microsoft Managed Desktop](../intro/technologies.md) 기술을 참조하세요.

> [!TIP]
> 특정 사용자에게 이러한 라이선스 옵션을 할당하기 위해 Azure [](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal) Active Directory의 그룹 기반 라이선싱 기능을 활용하는 것이 좋습니다.

- Azure Active Directory Premium P2
- Microsoft Intune 
- Windows 10 Enterprise  
- 엔드포인트용 Microsoft Defender
- 엔터프라이즈용 Microsoft 365 앱
- Microsoft Teams
- [SharePoint Online 계획 2](https://www.microsoft.com/microsoft-365/sharepoint/compare-sharepoint-plans)
- [Exchange Online 계획 2](https://www.microsoft.com/microsoft-365/exchange/compare-microsoft-exchange-online-plans) 


> [!TIP]
> Microsoft 계정 관리자는 현재 라이선스 및 서비스 계획을 검토하고 중복을 방지하면서 필요한 추가 라이선스 또는 서비스 계획을 얻을 수 있는 가장 효율적인 경로를 찾는 데 도움을 줄 수 있습니다.
