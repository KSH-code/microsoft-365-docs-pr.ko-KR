---
title: Microsoft 365 Business에서 Microsoft 365 E3로 마이그레이션
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 5b4ba843-24b8-4526-8e1f-f9b9eab89d06
description: Microsoft 365 Business에서 Microsoft 365 E3으로 비즈니스를 이동 하는 방법을 알아봅니다.
ms.openlocfilehash: 1cf6aa741c7f0b427a434d472df7169ef37c5418
ms.sourcegitcommit: 03a83ff76c8162b850c4c552759c49f2a4750574
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/26/2020
ms.locfileid: "41558045"
---
# <a name="migrate-from-microsoft-365-business-to-microsoft-365-e3"></a>Microsoft 365 Business에서 Microsoft 365 E3로 마이그레이션

Microsoft 365 Business에는 최고의 비즈니스에 필요한 모든 것이 있으며, 최상의 클라우드 기반 생산성 앱을 간단한 장치 관리 및 보안과 함께 사용 하 여 직원 들이 최고의 작업을 수행할 수 있도록 합니다. 그러나 경우에 따라 Microsoft 365 비즈니스 구독을 Microsoft 365 E3으로 마이그레이션해야 할 수도 있습니다. 

예를 들어 비즈니스가 성장 했으며 300 개 이상의 라이선스가 필요 합니다 (방식으로 축 하 합니다).

또는 회사에 Office 365 ProPlus, Windows 10 Enterprise E3 또는 엔터프라이즈 Cal (클라이언트 액세스 라이선스)과 같은 enterprise 기능이 필요 합니다.

업그레이드는 [관리 센터에서](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/upgrade-to-different-plan?view=o365-worldwide)업그레이드를 시작할 수 있습니다. 현재 구독의 모든 데이터와 구성이 유지 됩니다. 새 기능을 사용 하는 경우를 제외 하 고는 마이그레이션을 준비 하 고 나중에 수행 해야 하는 작업이 없습니다. 

>[!Note]
>또한 최대 300의 사용자를 위해 Microsoft 365 비즈니스 구독을 사용할 수 있으며, 300 명 보다 더 많은 Microsoft 365 E3 구독을 받을 수도 있습니다. 그러나 Office 365 ATP는 Microsoft 365 E3에 포함 되어 있지 않습니다. 계속 해 서 위협 방지를 위해 office 365 ATP 정책 범위에 있는 모든 사용자에 게 라이선스가 있도록 Office 365 ATP 라이선스를 추가 해야 합니다.
>

## <a name="differences-between-microsoft-365-business-and-microsoft-365-enterprise"></a>Microsoft 365 비즈니스 및 Microsoft 365 Enterprise의 차이점

이 표에서는 Microsoft 365 Business 및 Microsoft 365 E3의 차이점을 보여 줍니다.

| 기능   | Microsoft 365 Business의 지원 | Microsoft 365 E3의 지원 | 
|:-------|:-----|:-----|
| **온-프레미스**       | | | 
| Windows 10    | Windows 10 Business  |    Windows 10 Enterprise E3| 
| Office 앱 *  | [Office 365 Business](#office-365-business)   | Office 365 ProPlus | 
| **클라우드 생산성 앱**       | | | 
| Exchange Online 및 Outlook   | 사서함 당 50 GB 저장소 제한 및 무제한 Exchange 온라인 보관   | 사서함 당 100 GB 저장소 제한 및 무제한 Exchange 온라인 보관 | 
| Teams | ![Microsoft 365 Business에 포함](./media/check-mark.png)   | ![Microsoft 365 E3에 포함](./media/check-mark.png) | 
| 비즈니스용 OneDrive | 사용자 당 1TB 저장소 제한   | 무제한 | 
| Yammer, SharePoint Online, Planner, 스트림    | ![Microsoft 365 Business에 포함](./media/check-mark.png)   | ![Microsoft 365 E3에 포함](./media/check-mark.png) | 
| StaffHub  | ![Microsoft 365 Business에 포함](./media/check-mark.png)   | ![Microsoft 365 E3에 포함](./media/check-mark.png) | 
| Outlook 고객 관리자, MileIQ  | ![Microsoft 365 Business에 포함](./media/check-mark.png)   | | 
| **위협 방지**     | | | 
| 공격 표면 축소 기능 | [이 목록 보기](#threat-protection) | Microsoft Edge에 대 한 하드웨어 기반 격리의 엔터프라이즈 관리 | 
| Office 365 ATP (Advanced Threat Protection) 계획 1 | ![Microsoft 365 Business에 포함](./media/check-mark.png)  | 포함 되지 않지만 추가할 수 있음 | 
| **Id 관리**       | | | 
| 하이브리드 Azure Active Directory에 대 한 셀프 서비스 암호 재설정 (Azure AD) 계정, Azure MFA (다단계 인증), 조건부 액세스, 온-프레미스 id에 대 한 암호 쓰기 저장|    ![Microsoft 365 Business에 포함](./media/check-mark.png) | ![Microsoft 365 E3에 포함](./media/check-mark.png) | 
| Cloud App Discovery, Azure AD Connect Health  |   | ![Microsoft 365 E3에 포함](./media/check-mark.png) | 
| Azure AD Office 365 앱 SSO (Single Sign-on): 사용자 당 10 개의 앱 (예: Salesforce와 같은 SaaS 응용 프로그램) * | ![Microsoft 365 Business에 포함](./media/check-mark.png) | ![Microsoft 365 E3에 포함](./media/check-mark.png) | 
| Azure AD Premium 1 SSO: 제한 없음 (셀프 서비스 앱 통합 서식 파일을 사용 하는 Azure AD 응용 프로그램 프록시 및 비 갤러리 앱을 통한 온-프레미스 앱)  |   | ![Microsoft 365 E3에 포함](./media/check-mark.png) | 
| **장치 및 앱 관리**     | | | 
| Microsoft Intune, Windows Autopilot|  ![Microsoft 365 Business에 포함](./media/check-mark.png) | ![Microsoft 365 E3에 포함](./media/check-mark.png) | 
|VDA (가상 데스크톱 액세스)   |  |    ![Microsoft 365 E3에 포함](./media/check-mark.png) | 
|WVD (Windows 가상 데스크톱)  | ![Microsoft 365 Business에 포함](./media/check-mark.png) |     ![Microsoft 365 E3에 포함](./media/check-mark.png) | 
|SCA (공유 컴퓨터 활성화)   | ![Microsoft 365 Business에 포함](./media/check-mark.png) |     ![Microsoft 365 E3에 포함](./media/check-mark.png) | 
| Microsoft 데스크톱 최적화 패키지    | |     ![Microsoft 365 E3에 포함](./media/check-mark.png) | 
| **정보 보호**        | | | 
| Office 365 데이터 손실 방지, Azure Information Protection 계획 1  | ![Microsoft 365 Business에 포함](./media/check-mark.png)   | ![Microsoft 365 E3에 포함](./media/check-mark.png) | 
| 끝점 DLP에 대 한 창 정보 보호    | ![Microsoft 365 Business에 포함](./media/check-mark.png)   | ![Microsoft 365 E3에 포함](./media/check-mark.png) | 
| **클라이언트 액세스 라이선스 (CAL 권한)**    | | |   
| Enterprise CAL Suite (Exchange, SharePoint, Skype, Windows, Microsoft Endpoint Configuration Manager, Windows Rights Management)| |       ![Microsoft 365 E3에 포함](./media/check-mark.png) | 
| **규정 준수**        | | | 
| 무제한 전자 메일 보관 | ![Microsoft 365 Business에 포함](./media/check-mark.png)   | ![Microsoft 365 E3에 포함](./media/check-mark.png) | 
| 준수 점수/준수 관리자   | ![Microsoft 365 Business에 포함](./media/check-mark.png)   | ![Microsoft 365 E3에 포함](./media/check-mark.png) | 
| eDiscovery    | ![Microsoft 365 Business에 포함](./media/check-mark.png)   | ![Microsoft 365 E3에 포함](./media/check-mark.png) | 
| 원본 위치 유지 및 소송 보존 | ![Microsoft 365 Business에 포함](./media/check-mark.png)   | ![Microsoft 365 E3에 포함](./media/check-mark.png) | 
| MRM (메시징 레코드 관리) 보존 태그 및 보존 정책  | ![Microsoft 365 Business에 포함](./media/check-mark.png)   | ![Microsoft 365 E3에 포함](./media/check-mark.png) | 
||||

\*SaaS 앱에 대 한 액세스 권한이 할당 된 사용자는 최대 10 개의 앱에 대 한 SSO 액세스를 받을 수 있습니다. 관리자는 SSO를 구성 하 고 다른 SaaS 앱에 대 한 사용자 액세스를 변경할 수 있지만 SSO 액세스는 사용자 당 10 개의 앱에 한 번에 하나씩만 허용 됩니다. 모든 Office 365 앱은 단일 앱으로 계산 됩니다.

## <a name="migration"></a>마이그레이션

마이그레이션하기 위해 파트너와 협력 하 여 Microsoft 365 비즈니스 구독 및 라이선스를 해당 라이선스와 함께 적절 한 Microsoft 365 E3 구독으로 이동 합니다.

다음 섹션에서는 마이그레이션 후에 수행 해야 하는 작업 및 변경 내용에 대해 설명 합니다.

### <a name="microsoft-365-subscription-configuration-and-data"></a>Microsoft 365 구독 구성 및 데이터

마이그레이션을 수행 하기 전에 다음을 비롯 하 여 현재 구독 또는 데이터를 변경할 필요는 없습니다.

- 구독 구성 (예: DNS 도메인 이름)
- 사용자 및 그룹 계정 및 인증 설정 (예: 다단계 인증 또는 조건부 액세스 정책)
- 팀, Exchange Online 사서함, SharePoint Online 사이트, 비즈니스용 OneDrive 폴더, OneNote 전자 필기장 등의 생산성 서비스 구성 및 데이터

이제 사용자는 Exchange Online 사서함 및 비즈니스용 OneDrive 폴더에 무제한 저장소를 사용할 수 있습니다.

앱을 10 개 넘게 사용 하려면 Cloud App Discovery, Azure AD Connect Health 및 SSO를 사용할 수 있습니다.

>[!Note]
>Microsoft 365 E3으로 마이그레이션된 사용자는 더 이상 Outlook 고객 관리자 및 MileIQ를 사용할 수 없습니다.
>

<a name="threat-protection"></a>
### <a name="threat-protection"></a>위협 방지

Windows 10 Business에는 다음과 같은 보호 기능이 포함 되어 있습니다.

- 운영 체제 부팅 프로세스의 무결성 적용
- 중요 한 운영 구성 요소의 무결성 적용
- Advanced 취약성 및 제로 일 악용 완화
- Microsoft Edge, Internet Explorer 및 Chrome에 대 한 신뢰도 기반 네트워크 보호
- 호스트 기반 방화벽
- 랜 섬 웨어 완화
- Microsoft Edge에 대 한 하드웨어 기반 격리
- 지능형 보안 그래프로 인해 응용 프로그램 제어
- 장치 컨트롤 (USB)
- 웹 기반 위협에 대 한 네트워크 보호
- 호스트 침입 방지 규칙

Windows 10 Enterprise e 3에는 Microsoft Edge에 대 한 하드웨어 기반 격리의 엔터프라이즈 관리도 포함 됩니다.

>[!Note]
>Microsoft 365 E3로 마이그레이션된 사용자에 게는 계속 해 서 위협 방지를 위해 Office 365 ATP 라이선스가 필요 합니다. Office 365 ATP 정책 범위에 있는 모든 사용자에 게 라이선스가 있도록 추가 Office 365 ATP 라이선스를 구입 해야 합니다. 
>

### <a name="device-management-with-intune"></a>Intune을 사용한 장치 관리

마이그레이션 전에 현재 Intune 구성을 변경할 필요가 없습니다 (등록 된 장치 및 장치 및 앱 설정 포함).

### <a name="windows-10"></a>Windows 10

Microsoft 365 Business에는 windows AutoPilot를 사용 하 여 설치할 수 있는 Windows 10 Business가 포함 되어 있습니다. Microsoft 365 E3로 마이그레이션하는 경우 각 사용자 라이선스에는 windows Autopilot를 사용 하 여 설치할 수도 있습니다.

<a name="office-365-business"></a>
### <a name="office-365-business"></a>Office 365 Business

장치에 설치 된 Office 365 Business 클라이언트는 자동으로 Office 365 ProPlus의 기능을 사용 하기 시작 합니다. 마이그레이션 후에는 다음을 사용할 수 있습니다.

 - 그룹 정책을 통한 볼륨 정품 인증
 - 앱 원격 분석
 - 업데이트 컨트롤
 - 스프레드시트 비교 및 조회
 - 비즈니스 인텔리전스

