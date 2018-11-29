---
title: Microsoft Managed Desktop의 필수 구성 요소
description: ''
keywords: Microsoft 관리 되는 데스크톱, Microsoft 365 서비스, 설명서
ms.service: m365-md
author: jdeckerms
ms.localizationpriority: normal
ms.date: 11/1/2018
ms.openlocfilehash: a7e82c0f4301b00e3d9e923dca10d1630744b8c0
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870231"
---
# <a name="prerequisites-for-microsoft-managed-desktop"></a>Microsoft Managed Desktop의 필수 구성 요소

<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/prereq-azure); do not delete.-->
<!--from Prerequisites -->

성공와 데스크톱을 관리 하는 Microsoft 고객의 인프라에 대 한 잘 알려진 및, 문서화, 합의 요구 사항으로 시작 합니다. 이 섹션에서는 이러한 필수 구성 요소에 설명 합니다. 

Microsoft FastTrack는 이러한 요구 사항을 충족 하 고 서비스로 현대 직장 참여할 수 있도록 준비 하는데 도움이 되는 고객을 위해 사용할 수 있습니다. 자세한 내용은 [Microsoft FastTrack](https://fasttrack.microsoft.com/about)을 참조 하십시오. 

영역 | 필수 구성 요소 세부 정보
--- | ---
라이선스 | Microsoft 365 e 5 라이선스 또는 해당 하는 라이선스는 필요 합니다.<br><br>이 라이선스에는 Office 365 e 5, Windows 10 엔터프라이즈 E5 & Enterprise 이동성 + 보안 (EMS) e 5에 포함 합니다. 자세한 내용은 [Microsoft 365 라이선스](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)를 참조 하십시오.
연결 |  모든 Microsoft 관리 되는 데스크톱 장치를 조직의 내부 네트워크에서 다양 한 Microsoft 서비스 끝점에 연결 필요 포함 합니다.<br>Windows 업데이트<br>비즈니스를 위한 Microsoft 저장소<br>-Azure Active Directory<br>Windows 오류 보고<br>-온라인 크래시 분석<br>-연결 된 사용자 경험 및 원격 분석<br>-Windows 10 OneDrive 응용 프로그램<br><br>문서의 전체 목록은 IP의 필수 및 [프록시 구성](../get-ready/network.md)에서 Url을 확인할 수 있습니다. 
Azure Active Directory |    Azure Active Directory (Azure AD) 모든 사용자 계정에 대 한 권한 원본을 같아야 또는 Azure AD 연결, 1.1.654.0 버전을 사용 하 여 온-프레미스 Active Directory에서 사용자 계정 동기화 되어야 합니다 이상입니다. 자세한 내용은 [Azure AD 연결](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)을 참조 하십시오.
인증 |    Azure AD 사용자 계정에 대 한 권한 원본을 없으면 Azure AD 연결에서 다음 중 하나를 구성 해야 합니다.<br>-암호 해시 동기화 (권장)<br>-통과 인증<br>-ADFS와의 페더레이션<br><br>Azure AD 연결 암호 쓰기 저장 된 인증 옵션을 설정 때도 필요 합니다. 자세한 내용은 [암호 쓰기 저장](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback)을 참조 하십시오.<br><br>Azure AD 사용한 인증 옵션에 대 한 자세한 내용은 [Azure AD 연결 사용자 로그인 옵션](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-user-signin)을 참조 하십시오.
Office 365 |    다음 서비스는 클라우드로 마이그레이션할 수는 것이 좋습니다.<br>-전자 메일-클라우드 기반 사서함을 Exchange online으로 마이그레이션하거나 Exchange Online 하이브리드 Exchange 2013 이상, 온-프레미스를 사용 하 여 구성 합니다.<br>-파일 및 폴더 –을 SharePoint Online/Office 365를 마이그레이션합니다.<br>--비즈니스용 Skype 마이그레이션하려면 Skype 비즈니스에 대 한 온라인 합니다.<br>-장치 관리-Microsoft Intune A 클라우드 전용 MDM 솔루션 (비 하이브리드)가 필요, IT 관리자가 아무곳 이나 전세계의에서 액세스할 수 있는 웹 콘솔을 사용 하 여 Microsoft 관리 되는 데스크톱 장치를 관리할 수 있습니다. Microsoft Intune는 필요한 MDM 솔루션입니다.<br><br>자세한 내용은 [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune)를 참조 하십시오. 
데이터 백업 및 복구 | Microsoft 관리 되는 데스크톱 파일 보호를 위해 비즈니스용 OneDrive를 동기화 할 필요 합니다. 모든 비즈니스용 OneDrive를 동기화 되지 되지 않을 수도 Microsoft 관리 되는 데스크톱으로 파일과 장치 교환 또는 지원 전화 장치 재설정을 필요로 하는 동안 손실 될 수 있습니다. Microsoft 관리 되는 데스크톱에서 매핑된 네트워크 드라이브를 지원 하지 않습니다.  

[Microsoft 관리 되는 데스크톱 등록을 위한 필수 구성 요소를 충족 하는 방법에 알아봅니다.](../get-ready/index.md)

Microsoft 관리 되는 데스크톱을 사용 하는 준비 되 면, Microsoft 계정 관리자에 게 문의 합니다. 