---
title: Microsoft Managed Desktop의 필수 구성 요소
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: b729712a188c105fdf8a38e208124c2ef4c27a33
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42085877"
---
# <a name="prerequisites-for-microsoft-managed-desktop"></a>Microsoft Managed Desktop의 필수 구성 요소

<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/prereq-azure); do not delete.-->
<!--from Prerequisites -->

이 항목에서는 Microsoft Managed Desktop의 성공을 보장 하기 위해 충족 해야 하는 인프라 요구 사항에 대해 간략하게 설명 합니다. 

Microsoft FastTrack은 이러한 요구 사항을 충족 하 고 Microsoft Managed Desktop에 참여 하기 위해 준비 하는 데 도움이 되는 정보를 제공 합니다. 자세한 내용은 [Microsoft FastTrack](https://fasttrack.microsoft.com/about)를 참조 하세요. 

영역 | 필수 구성 요소 정보
--- | ---
라이선싱 |Microsoft Managed Desktop에는 다음 Microsoft 365 라이선스 중 하나가 필요 합니다.<br>-Microsoft 365 E5<br>-Microsoft 365 E5 보안 추가 기능을 포함 하는 마이크로소프트 365 E3<br><br>Microsoft Managed Desktop의 특정 서비스 계획 및 해당 역할에 대 한 자세한 내용은이 항목의 [라이선스에 대 한 자세한](#more-about-licenses) 내용을 참조 하십시오.<br>사용 가능한 라이선스에 대 한 자세한 내용은 [Microsoft 365 license](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)를 참조 하십시오.
연결 |  모든 Microsoft 관리 데스크톱 장치에는 회사 네트워크의 수많은 Microsoft 서비스 끝점에 대 한 연결이 필요 합니다.<br><br>필요한 Ip 및 Url의 전체 목록은 [네트워크 구성을](../get-ready/network.md)참조 하십시오. 
Azure Active Directory |    Azure Active Directory (Azure AD)는 모든 사용자 계정에 대 한 기관의 출처 이거나, 지원 되는 최신 버전의 Azure AD Connect를 사용 하 여 온-프레미스 Active Directory에서 사용자 계정을 동기화 해야 합니다.<br><br>Microsoft Managed Desktop users에 대해 [엔터프라이즈 상태 로밍을](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-overview) 사용 하도록 설정 해야 합니다.<br><br>자세한 내용은 [AZURE AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect)를 참조 하세요.<br><br>지원 되는 Azure AD Connect 버전에 대 한 자세한 내용은 [AZURE Ad connect: 버전 릴리스 기록을](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-version-history)참조 하세요.
인증 |    Azure AD가 사용자 계정에 대 한 기관의 원본이 아닌 경우 Azure AD Connect에서 다음 중 하나를 구성 해야 합니다.<br>-암호 해시 동기화<br>-통과 인증<br>-ADFS를 사용한 페더레이션<br><br>Azure AD Connect를 사용 하 여 인증 옵션을 설정 하는 경우 암호 쓰기 저장도 권장 됩니다. 자세한 내용은 [암호 쓰기 저장](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback)를 참조 하세요. <br><br>Azure AD를 사용한 인증 옵션에 대 한 자세한 내용은 [AZURE Ad Connect 사용자 로그인 옵션](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-user-signin)을 참조 하세요.
Office 365 |    Microsoft Managed Desktop users에 대해 비즈니스용 OneDrive를 사용 하도록 설정 해야 합니다.<br><br>Microsoft Managed Desktop에 등록 하는 것은 아니지만 다음 서비스를 클라우드로 마이그레이션하는 것이 좋습니다.<br>-전자 메일: 클라우드 기반 사서함으로 마이그레이션, Exchange online 또는 exchange Online Hybrid (온-프레미스 2013 포함)를 사용 하 여 구성 합니다.<br>-파일 및 폴더: 비즈니스용 OneDrive 또는 SharePoint Online으로 마이그레이션합니다.<br>-온라인 공동 작업 도구: 팀으로 마이그레이션
장치 관리 | Microsoft Managed Desktop 장치는 Microsoft Intune을 사용 하 여 관리 해야 합니다. Intune은 모바일 장치 관리 기관으로 설정 해야 합니다.<br><br>자세한 내용은 [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune)을 참조 하십시오. 
데이터 백업 및 복구 | Microsoft Managed Desktop을 사용 하려면 보호를 위해 비즈니스용 OneDrive에 파일을 동기화 해야 합니다. 비즈니스용 OneDrive와 동기화 되지 않은 파일은 Microsoft Managed Desktop이 보장 되지 않으며 장치를 교환 하거나 장치를 다시 설정 해야 하는 지원 통화 중에 손실 될 수 있습니다.<br><br>필수는 아니지만 Microsoft Managed Desktop은 매핑된 네트워크 드라이브에서 적절 한 클라우드 솔루션으로의 마이그레이션을 적극 권장 합니다. 자세한 내용은 [Prepare mapped drives For Microsoft Managed Desktop](mapped-drives.md) 를 참조 하세요.

Microsoft Managed Desktop을 시작할 준비가 되 면 Microsoft 계정 관리자에 게 문의 하세요. 

## <a name="more-about-licenses"></a>라이선스에 대 한 자세한 정보

Microsoft Managed Desktop을 작동 하려면 특정 라이선스 옵션이 필요 합니다. 이러한 옵션은 여러 다양 한 라이센스 번들에서 사용할 수 있으며, 그 중 일부는 이미 소유 하 고 있을 것입니다. 이 표에서는 Microsoft Managed Desktop에서 사용 가능한 필수 옵션을 보여 주고 해당 역할을 요약 하 여 설명 합니다.

> [!TIP]
> 이러한 라이선스 옵션을 특정 사용자에 게 할당 하려면 Azure Active Directory의 [그룹 기반 라이선스 기능](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal) 을 활용 하는 것이 좋습니다.



|라이선스 옵션 |다음 라이선스 *제품에서 사용* 가능 |Microsoft Managed Desktop이 사용 하는 방법|
|-------------|-------------|-------------|
|Azure Active Directory Premium P1     |-Microsoft 365 E5<br>-Microsoft 365 E3 + Microsoft 365 *E5* 보안 추가 기능<br>-Enterprise Mobility + Security E5<br>-Enterprise Mobility + Security E3<br>-Azure Active Directory Premium P1|  Microsoft 클라우드 서비스에 대 한 액세스를 제공 합니다. AutoPilot에서 장치를 등록할 수 있도록 허용      |
|Microsoft Intune | -Microsoft 365 E5<br>-Microsoft 365 E3 + Microsoft 365 *E5* 보안 추가 기능<br>-Enterprise Mobility + Security E5<br>-Enterprise Mobility + Security E3<br>-Microsoft Intune  |  장치를 등록 하 고, 업데이트를 배포 하 고, 장치를 관리 하는 데 필요       |
|Windows 10 Enterprise  |-Microsoft 365 E5<br>-Microsoft 365 E3 + Microsoft 365 *E5* 보안 추가 기능<br>-Windows 10 Enterprise E3<br>-Windows 10 Enterprise E5 | Windows 10의 엔터프라이즈 기능을 제공 합니다.       |
|Microsoft Defender Advanced Threat Protection | -Microsoft 365 E5<br>-Microsoft 365 E3 + Microsoft 365 *E5* 보안 추가 기능<br>-Windows 10 Enterprise E5<br>-Microsoft Defender Advanced Threat Protection   |  검색, 모니터링, 경고 및 위협에 대 한 대응 제공  |
|Office 365 ProPlus  |-Microsoft 365 E5<br>-Microsoft 365 E3<br>-Office 365 E5<br>-Office 365 E3| Office 및 생산성 및 공동 작업 도구를 활성화 합니다.    |

> [!TIP]
> Microsoft 계정 관리자는 현재 라이선스 및 서비스 계획을 검토 하 고, 중복을 방지 하면서 필요한 추가 라이선스 또는 서비스 계획을 얻을 수 있는 가장 효율적인 경로를 확인 하는 데 도움이 됩니다.
