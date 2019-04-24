---
title: Microsoft Managed Desktop 역할 및 책임
description: 이 항목에서는 microsoft Managed Desktop에 대해 microsoft에서 제공 하는 역할 및 책임에 대해 설명 합니다.
keywords: microsoft Managed Desktop, microsoft 365, 서비스, 설명서
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.collection: M365-modern-desktop
ms.openlocfilehash: 161be07907754cdd7a0cd88dd3342d4b5e3c72e4
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283561"
---
# <a name="microsoft-managed-desktop-roles-and-responsibilities"></a>Microsoft Managed Desktop 역할 및 책임


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/admin-access); do not delete.-->
<!-- from Roles and responsibilities -->

조직이 microsoft Managed Desktop에 등록 되 면 microsoft에서 어떤 작업을 수행 하나요? 조직의 책임은 무엇 인가요?

## <a name="microsofts-roles-and-responsibilities"></a>Microsoft의 역할 및 책임

다음은 Microsoft에서 제공 하는 몇 가지 주요 역할과 책임입니다.

역할 또는 책임 | 설명
--- | ---
MDM 정책 관리 | Microsoft는 모범 사례에 따라 MDM 정책을 적용 하 고 정책 변경에 대 한 요청을 고려 합니다. 또한 [장치 정책](../service-description/device-policies.md)에 지정 된 대로 테 넌 트를 변경 하 게 됩니다.
최종 사용자 지원 | microsoft는 모든 microsoft 관리 데스크톱 장치에 설치 된 도움말 보기 앱을 통해 등록 된 모든 사용자의 장치, Windows 및 Office 제품군에 대 한 최종 사용자 지원을 제공 합니다. 
Microsoft Managed Desktop 서비스 지원 | microsoft는 microsoft 관리 데스크톱 운영 팀을 통해 고객 IT 부서에 지원을 제공 합니다. 이 팀은 고객의 Microsoft Managed Desktop 환경에 대 한 기술 문제 해결, 변경 요청 및 문제 관리를 지원 합니다. 자세한 내용은 [Microsoft Managed Desktop에 대 한 관리자 지원을](../working-with-managed-desktop/admin-support.md)참조 하세요.
보안 모니터링 | microsoft는 Windows Defender ATP를 사용 하 여 microsoft Managed Desktop 장치를 모니터링 합니다. microsoft Managed SOC (데스크톱 보안 운영 센터)에서 위협이 검색 되 면 microsoft는 고객에 게 알리고, 장치를 격리 하 고, 원격으로 문제를 해결 합니다. 자세한 내용은 [Security](../service-description/security.md)를 참조 하십시오.
모니터링 및 관리 업데이트 | microsoft는 고객 microsoft 관리 데스크톱 장치를 적극적으로 모니터링 하 여 microsoft Windows 및 microsoft Office에 대 한 최신 품질 및 기능 업데이트가 설치 되어 있는지 확인 합니다. 자세한 내용은 [업데이트를 처리 하는 방법을](../service-description/updates.md)참조 하세요.
사용자 및 장치 그룹화 | Microsoft Managed Desktop operations team은 IT 작업의 일부로 필요한 장치 및 사용자 그룹을 만들고 관리 합니다. 이러한 그룹에는 멤버 자격 또는 구성 변경이 허용 되지 않습니다. 이러한 그룹을 변경 하면 예기치 않은 장치를 구성 하 고 기능 손실을 유발할 수 있습니다. 이러한 그룹에 대 한 문제나 의문 사항이 일단 설정 되 면 IT 관리자는 Microsoft Managed Desktop 작업에 문의할 수 있습니다. 자세한 내용은 [Microsoft Managed Desktop에 대 한 관리자 지원을](../working-with-managed-desktop/admin-support.md)참조 하세요.

## <a name="your-roles-and-responsibilities"></a>사용자의 역할 및 책임

다음은 Microsoft에서 제공 하지 않지만 성공적인 배포를 위해 필요한 추가 일반적인 역할 및 책임 집합입니다. 이 기능은 포괄적이 지는 않지만 대부분의 조직에 적용 됩니다. Microsoft와 고객이 공유 하는 몇 가지 항목이 responsibilties 있습니다. 

역할 또는 책임 | 설명
--- | ---
변경 관리 | microsoft는 microsoft의 관리 되는 데스크톱 환경을 변경 해야 하는 경우이에 대 한 알림을 고객에 게 미리 알립니다. 고객은 자신의 변경 관리 프로세스를 수행 하 고 Microsoft Managed Desktop Operations team을 사용 하 여 연락처를 설정 해야 합니다. 또한 고객에 게 이러한 변경 내용을 검토 하 고 승인 하는 리소스가 있어야 합니다. 자세한 내용은 [작업 및 모니터링](../service-description/operations-and-monitoring.md)를 참조 하세요.  
id 관리 | 고객은 사용자 계정을 만들고 그룹에 사용자를 할당 하 고 메타 데이터를 최신 상태로 유지 하는 일을 담당 합니다. 
Office 365 구성 및 관리 | Microsoft는 최종 사용자에 게 Office 응용 프로그램을 배포 하 고 해당 응용 프로그램을 최신 상태로 유지 하 고 있는지를 담당 합니다. <br><br> 고객은 Exchange Online 관리 책임을 포함 하 여 Office 365 서비스 및 정책 관리를 담당 합니다.<br>-전자 메일 관리<br>-사서함 및 규칙 구성<br>-Exchange 온-프레미스 관리<br><br>또한 고객은 Office 365 관리 포털에 설정 된 공동 작업 도구, SharePoint server 관리, 도메인 관리, 보안 및 정보 정책을 담당 합니다. 
최종 사용자 지원 | 고객은 다음에 대 한 최종 사용자 지원을 제공 해야 합니다. <br>-사이트 인프라: 모든 네트워크 및 인터넷 연결, VPN 인프라 및 클라이언트 구성, 로컬 전화 회의 대화방 장비, 프린터, 프록시 서버 및 구성, 방화벽<br><br>-회사 전체의 클라우드 리소스: 전자 메일, SharePoint, 공동 작업 서비스 및 회사 전체의 기술 공간과 관련 된 기타 클라우드 인프라<br><br>-비즈니스 및 기타 모든 회사 관련 응용 프로그램입니다.
앱 | Microsoft는 요청 시 Intune을 사용 하 여 승인 된 응용 프로그램에 대 한 배포 지침을 제공 합니다.<br><br>고객은 다음을 담당 합니다.<br>-조직에 대 한 앱 목록을 제공 합니다 (Office 365 앱 외부).<br>-앱 라이선스 관리<br>– 라이선스의 올바른 유형 및 수량 보유<br>-앱 할당<br>-Azure AD 사용자 그룹에 앱 할당<br>-App 업데이트<br>-앱 기능 및 보안 업데이트 모니터링, 패키징 및 배포<br>-사용자 응용 프로그램 테스트 (UAT)<br>-적절 한 배포 가능한 패키지 제공<br><br>자세한 내용은 [Apps](../get-ready/apps.md) 를 참조 하세요.
보안 모니터링 및 대응 | 고객은 타사 관리 데스크톱 장치에 대 한 인시던트를 조사 및 해결 하 고 microsoft 관리 데스크톱 운영 팀이 서비스에 영향을 줄 수 있는 문제에 대 한 정보를 제공 하는지 확인 해야 합니다.
운영 지원 | 고객은 기본 설정 고객 연락처 및 주제별 전문가 목록을 제공 해야 합니다. microsoft는 타사 관리 데스크톱 운영 인시던트가 있는 경우 이러한 요구 사항을 충족 해야 합니다. <br><br>또한 고객은 microsoft의 관리 되지 않는 데스크톱 장치 및 서비스에 대 한 인시던트를 조사 및 해결 하 고 microsoft 관리 되는 데스크톱 운영 팀이 항상 통보 되도록 해야 합니다.
VPN을 포함 한 네트워크 인프라 | 고객은 인터넷 연결, 네트워크 제어, 프록시 구성 및 원격을 비롯 한 모든 네트워킹 관련 인프라 및 서비스의 설치, 구성 및 관리 (문제 해결 및 디버깅 포함)를 담당 합니다. 연결 인프라<br><br>프록시 (하드웨어 또는 소프트웨어)가 구성 된 경우에는 프록시에서 허용 해야 하는 url의 컬렉션이 있습니다. 고객은 여러 프록시로 인해 충돌이 나 비 호환성 문제를 해결 해야 합니다. 구성 가능한 설정을 사용 하 여 조직에 특정 한 네트워크 프록시를 추가할 수 있습니다. 자세한 내용은 [구성 가능한 설정을](../working-with-managed-desktop/config-setting-ref.md#proxy)참조 하십시오.<br><br>자세한 내용은 [프록시 구성을](../get-ready/network.md)참조 하세요.
인쇄할 | 고객은 프린터 및 인쇄 큐 설치, 유지 관리 및 관리를 담당 합니다. 클라우드 인쇄는 권장 되는 솔루션 이지만 필수 사항은 아닙니다. 




