---
title: Microsoft Managed Desktop의 필수 구성 요소
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 설명서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 11/1/2018
ms.collection: M365-modern-desktop
ms.openlocfilehash: 19bd7c553840b0de51f7b26a8f1206a9c5d7b3af
ms.sourcegitcommit: b27650d1388ca136f85fcc662fe3ba069e9ee895
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/02/2019
ms.locfileid: "33560057"
---
# <a name="prerequisites-for-microsoft-managed-desktop"></a>Microsoft Managed Desktop의 필수 구성 요소

<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/prereq-azure); do not delete.-->
<!--from Prerequisites -->

성공적인 Microsoft Managed Desktop은 고객 인프라에 대해 잘 알려져 있고 문서화 되었으며 합의 된 요구 사항으로 시작 됩니다. 이 섹션에서는 이러한 infastructure 요구 사항에 대해 간략하게 설명 합니다. 

Microsoft FastTrack을 사용 하 여 고객이 이러한 요구 사항을 충족 하 고 Microsoft Managed Desktop에 참여 하도록 준비할 수 있도록 도울 수 있습니다. 자세한 내용은 [Microsoft FastTrack](https://fasttrack.microsoft.com/about)를 참조 하세요. 

영역 | 필수 구성 요소 정보
--- | ---
라이선스 |Microsoft Managed Desktop을 사용 하려면 다음 Microsoft 365 라이선싱 (또는 equivalencies)이 필요 합니다.<br>-Microsoft 365 E5<br>-Microsoft 365 E3 + Security E5<br><br>사용 가능한 라이선스에 대 한 자세한 내용은 [Microsoft 365 license](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)를 참조 하십시오.
연결 |  모든 Microsoft 관리 데스크톱 장치에는 회사 네트워크의 수많은 Microsoft 서비스 끝점에 대 한 연결이 필요 합니다.<br><br>필요한 Ip 및 Url의 전체 목록은 [네트워크 구성을](../get-ready/network.md)참조 하십시오. 
Azure Active Directory |    Azure Active Directory (Azure AD)는 모든 사용자 계정에 대 한 기관의 출처 이거나, 지원 되는 최신 버전의 Azure AD Connect를 사용 하 여 온-프레미스 Active Directory에서 사용자 계정을 동기화 해야 합니다.<br><br>Azure AD Connect에 대 한 자세한 내용은 [AZURE Ad connect](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect)를 참조 하세요.<br><br>지원 되는 Azure AD Connect 버전에 대 한 자세한 내용은 [AZURE Ad connect: 버전 릴리스 기록을](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-version-history)참조 하세요.
인증 |    Azure AD가 사용자 계정에 대 한 기관의 원본이 아닌 경우 Azure AD Connect에서 다음 중 하나를 구성 해야 합니다.<br>-암호 해시 동기화<br>-통과 인증<br>-ADFS를 사용한 페더레이션<br><br>Azure AD Connect를 사용 하 여 인증 옵션을 설정 하는 경우 암호 쓰기 저장도 필요 합니다. 자세한 내용은 [암호 쓰기 저장](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback)를 참조 하세요. <br><br>Azure AD를 사용한 인증 옵션에 대 한 자세한 내용은 [AZURE Ad Connect 사용자 로그인 옵션](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-user-signin)을 참조 하세요.
Office 365 |    Microsoft Managed Desktop에 등록 하는 것은 필요 하지 않지만 다음 서비스를 클라우드로 마이그레이션하는 것이 좋습니다.<br>-전자 메일-클라우드 기반 사서함으로 마이그레이션하거나 exchange online 또는 exchange online 2013 Hybrid (온-프레미스)를 사용 하 여 구성 해야 합니다.<br>-파일 및 폴더-비즈니스용 OneDrive/SharePoint Online으로 마이그레이션<br>-온라인 공동 작업 도구-팀으로 마이그레이션
장치 관리 | Microsoft Managed Desktop 장치는 Microsoft Intune을 사용 하 여 관리 해야 합니다. Intune은 모바일 장치 관리 기관으로 설정 해야 합니다.<br><br>자세한 내용은 [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune)을 참조 하십시오. 
데이터 백업 및 복구 | Microsoft Managed Desktop을 사용 하려면 보호를 위해 비즈니스용 OneDrive에 파일을 동기화 해야 합니다. 비즈니스용 OneDrive와 동기화 되지 않은 파일은 Microsoft Managed Desktop에 의해 보장 되지 않으며 장치 교환 중에 손실 되거나 장치를 다시 설정 해야 하는 지원 요청을 받을 수 있습니다.<br><br>필수는 아니지만 Microsoft Managed Desktop은 매핑된 네트워크 드라이브에서 적절 한 클라우드 솔루션으로의 마이그레이션을 적극 권장 합니다.  

Microsoft Managed Desktop을 시작할 준비가 되 면 Microsoft 계정 관리자에 게 문의 하세요. 
