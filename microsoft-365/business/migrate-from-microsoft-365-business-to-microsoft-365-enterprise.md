---
title: Microsoft 365 Business에서 Microsoft 365 E3로 마이그레이션
f1.keywords:
- NOCSH
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 5b4ba843-24b8-4526-8e1f-f9b9eab89d06
description: Microsoft 365 Business Premium에서 Microsoft 365 E3로 비즈니스를 이동하는 방법을 자세히 알아보고
ms.openlocfilehash: 019a422bb879389f42a32cf30f9a8094f776078a
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126204"
---
# <a name="migrate-from-microsoft-365-business-premium-to-microsoft-365-e3"></a>Microsoft 365 Business Premium에서 Microsoft 365 E3로 마이그레이션

Microsoft 365 Business Premium에는 중소기업에 필요한 모든 것이 있으며, 직원이 최고의 작업을 할 수 있도록 하는 간단한 장치 관리 및 보안과 동급 최고의 클라우드 기반 생산성 앱을 결합합니다. 그러나 경우에 따라 Microsoft 365 Business Premium 구독을 Microsoft 365 E3로 마이그레이션해야 할 수 있습니다. 

예를 들어 비즈니스가 커지고 300개가 넘는 라이선스가 필요합니다(축하합니다.

또는 비즈니스에 엔터프라이즈용 Microsoft 365 앱, Windows 10 Enterprise E3 또는 ENTERPRISE CA(클라이언트 액세스 라이선스)를 요구하는 엔터프라이즈 기능이 필요합니다.

업그레이드는 간단합니다. 관리 센터에서 업그레이드를 시작할 [수 있습니다.](../commerce/subscriptions/upgrade-to-different-plan.md) 현재 구독의 모든 데이터 및 구성이 유지 관리됩니다. 새 기능을 활용하는 것 외에는 마이그레이션을 준비할 수 있는 것은 아니며 이후에는 할 일도 없습니다.

>[!Note]
>최대 300명까지 Microsoft 365 Business Premium 구독을 사용할 수 있으며 300개가 넘는 사용자 수에 대해 Microsoft 365 E3 구독을 받을 수 있습니다. 그러나 Office 365용 Microsoft Defender는 Microsoft 365 E3에 포함되어 있지 않습니다. 계속 위협 방지를 위해 Office 365용 Defender의 범위에 있는 모든 사용자에게 라이선스가 부여될 수 있도록 Office 365 라이선스에 대한 Defender를 추가해야 합니다.
>

## <a name="differences-between-microsoft-365-business-premium-and-microsoft-365-enterprise"></a>Microsoft 365 Business Premium과 Microsoft 365 Enterprise의 차이점

다음 표에는 Microsoft 365 Business Premium과 Microsoft 365 E3의 차이점이 표시됩니다.

| 기능    | Microsoft 365 Business Premium 지원    | Microsoft 365 E3의 지원 | 
|:-------|:-----|:-----|
| **On-premises**        | | | 
| Windows 10    | Windows 10 Business  |     Windows 10 Enterprise E3| 
| Office 앱*    | [비즈니스용 Microsoft 365 앱](#office-365-business)    | 엔터프라이즈용 Microsoft 365 앱 | 
| **클라우드 생산성 앱**        | | | 
| Exchange Online 및 Outlook    | 사서함당 50GB 저장소 제한 및 무제한 Exchange Online 보관    | 사서함당 100GB 저장소 제한 및 무제한 Exchange Online 보관 | 
| Teams    | ![Microsoft 365 Business Premium에 포함](../media/check-mark.png)    | ![Microsoft 365 E3에 포함](../media/check-mark.png) | 
| 비즈니스용 OneDrive    | 사용자당 1 TB 저장소 제한    | 무제한 | 
| Yammer, SharePoint Online, Planner, Stream    | ![Microsoft 365 Business Premium에 포함](../media/check-mark.png)    | ![Microsoft 365 E3에 포함](../media/check-mark.png) | 
| MileIQ    | ![Microsoft 365 Business Premium에 포함](../media/check-mark.png)    | | 
| **위협 방지**        | | | 
| 공격 표면 감소 기능    | [이 목록 참조](#threat-protection) | Microsoft Edge에 대한 하드웨어 기반 고리의 엔터프라이즈 관리 | 
| Office 365 계획 1용 Defender | ![Microsoft 365 Business Premium에 포함](../media/check-mark.png)    | 포함되지 않지만 추가할 수 있습니다. | 
| **ID 관리**        | | | 
| 하이브리드 Azure AD(Azure Active Directory) 계정, Azure AD MFA(다단계 인증), 조건부 액세스,온-프레미스 ID에 대한 암호 쓰기 저장에 대한 셀프 서비스 암호 재설정|     ![Microsoft 365 Business Premium에 포함](../media/check-mark.png)    | ![Microsoft 365 E3에 포함](../media/check-mark.png) | 
| Cloud App Discovery, Azure AD Connect Health    |     | ![Microsoft 365 E3에 포함](../media/check-mark.png) | 
| Azure AD Office 365 앱 SSO(Single Sign-On): 사용자당 앱 10개(Salesforce와 같은 갤러리 SaaS 앱)* | ![Microsoft 365 Business Premium에 포함](../media/check-mark.png)    | ![Microsoft 365 E3에 포함](../media/check-mark.png) | 
| Azure AD Premium 1 SSO: 제한 없음(앱 통합 템플릿을 사용하는 Azure AD 응용 프로그램 프록시 및 Self-Service 갤러리 앱을 통한 Self-Service 앱)    |     | ![Microsoft 365 E3에 포함](../media/check-mark.png) | 
| **장치 및 앱 관리**        | | | 
| Microsoft Intune, Windows Autopilot|     ![Microsoft 365 Business Premium에 포함](../media/check-mark.png)    | ![Microsoft 365 E3에 포함](../media/check-mark.png) | 
|VDA(가상 데스크톱 액세스)    |  |     ![Microsoft 365 E3에 포함](../media/check-mark.png) | 
|WVD(Windows Virtual Desktop)    | ![Microsoft 365 Business Premium에 포함](../media/check-mark.png) |     ![Microsoft 365 E3에 포함](../media/check-mark.png) | 
|SCA(공유 컴퓨터 정품 인증)    | ![Microsoft 365 Business Premium에 포함](../media/check-mark.png) |     ![Microsoft 365 E3에 포함](../media/check-mark.png) | 
| Microsoft 데스크톱 최적화 패키지    | |     ![Microsoft 365 E3에 포함](../media/check-mark.png) | 
| **정보 보호**        | | | 
| Office 365 데이터 손실 방지, Azure Information Protection 계획 1    | ![Microsoft 365 Business Premium에 포함](../media/check-mark.png)    | ![Microsoft 365 E3에 포함](../media/check-mark.png) | 
| 끝점 DLP에 대한 창 정보 보호    | ![Microsoft 365 Business Premium에 포함](../media/check-mark.png)    | ![Microsoft 365 E3에 포함](../media/check-mark.png) | 
| **CAL(클라이언트 액세스 라이선스)**    | | |     
| Enterprise CAL Suite(Exchange, SharePoint, Skype, Windows, Microsoft Endpoint Configuration Manager, Windows Rights Management)| |         ![Microsoft 365 E3에 포함](../media/check-mark.png) | 
| **규정 준수**        | | | 
| 무제한 전자 메일 보관    | ![Microsoft 365 Business Premium에 포함](../media/check-mark.png)    | ![Microsoft 365 E3에 포함](../media/check-mark.png) | 
| 규정 관리자    | ![Microsoft 365 Business Premium에 포함](../media/check-mark.png)    | ![Microsoft 365 E3에 포함](../media/check-mark.png) | 
| eDiscovery    | ![Microsoft 365 Business Premium에 포함](../media/check-mark.png)    | ![Microsoft 365 E3에 포함](../media/check-mark.png) | 
| In-place hold and litigation hold    | ![Microsoft 365 Business Premium에 포함](../media/check-mark.png)    | ![Microsoft 365 E3에 포함](../media/check-mark.png) | 
| MRM(메시징 레코드 관리) 보존 태그 및 보존 정책    | ![Microsoft 365 Business Premium에 포함](../media/check-mark.png)    | ![Microsoft 365 E3에 포함](../media/check-mark.png) | 
||||

\* SaaS 앱에 대한 액세스 권한이 할당된 사용자는 최대 10개 앱에 대한 SSO 액세스를 얻을 수 있습니다. 관리자는 SSO를 구성하고 다른 SaaS 앱에 대한 사용자 액세스를 변경할 수 있지만, SSO 액세스는 한 시기에 사용자당 10개 앱에 한해 허용됩니다. 모든 Office 365 앱은 단일 앱으로 계산됩니다.

## <a name="migration"></a>마이그레이션

마이그레이션하려면 파트너와 협력하여 라이선스가 있는 적절한 Microsoft 365 E3 구독으로 Microsoft 365 Business Premium 구독 및 라이선스를 이동하세요.

다음 섹션에서는 변경해야 하는 사항, 변경이 있는 경우 및 마이그레이션 후 할 수 있는 작업을 설명합니다.

### <a name="microsoft-365-subscription-configuration-and-data"></a>Microsoft 365 구독 구성 및 데이터

마이그레이션하기 전에 다음을 포함하는 현재 구독 또는 데이터를 변경할 필요가 없습니다.

- 구독 구성(예: DNS 도메인 이름)
- 사용자 및 그룹 계정 및 인증 설정(예: 다단계 인증 또는 조건부 액세스 정책)
- 생산성 서비스 구성 및 해당 데이터(예: Teams, Exchange Online 사서함, SharePoint Online 사이트, 비즈니스용 OneDrive 폴더 및 OneNote 전자 필기장)

이제 사용자는 Exchange Online 사서함 및 비즈니스용 OneDrive 폴더에서 무제한 저장소를 사용할 수 있습니다.

10개 이상의 앱에 대해 Cloud App Discovery, Azure AD Connect Health 및 SSO를 사용할 수 있습니다.

>[!Note]
>Microsoft 365 E3로 마이그레이션된 사용자는 더 이상 MileIQ를 사용할 수 없습니다.
>

<a name="threat-protection"></a>
### <a name="threat-protection"></a>위협 방지

Windows 10 Business에는 다음 보호가 포함됩니다.

- 운영 체제 부팅 프로세스의 무결성 적용
- 중요한 운영 구성 요소의 무결성 적용
- 고급 취약성 및 제로 데이 악용 완화
- Microsoft Edge, Internet Explorer 및 Chrome에 대한 신뢰도 기반 네트워크 보호
- 호스트 기반 방화벽
- 랜섬웨어 완화
- Microsoft Edge에 대한 하드웨어 기반의 고리
- 지능형 보안 그래프를 통해 지원된 응용 프로그램 컨트롤
- 디바이스 제어(USB)
- 웹 기반 위협에 대한 네트워크 보호
- 호스트 침입 방지 규칙

Windows 10 Enterprise E3에는 Microsoft Edge에 대한 하드웨어 기반의 고리에 대한 엔터프라이즈 관리도 포함되어 있습니다.

>[!Note]
>Microsoft 365 E3로 마이그레이션된 사용자에게는 지속적으로 위협 방지를 위해 각각 Office 365용 Microsoft Defender 라이선스가 필요합니다. Office 365용 Defender의 범위에 있는 모든 사용자에게 라이선스가 부여될 수 있도록 Office 365용 추가 Defender 라이선스를 구입해야 합니다. 
>

### <a name="device-management-with-intune"></a>Intune을 사용하여 장치 관리

등록된 장치와 장치 및 앱 설정을 포함하는 마이그레이션 전에 현재 Intune 구성을 변경할 필요가 없습니다.

### <a name="windows-10"></a>Windows 10

Microsoft 365 Business Premium에는 Windows AutoPilot과 함께 설치할 수 있는 Windows 10 Business가 포함되어 있습니다. Microsoft 365 E3로 마이그레이션할 때 각 사용자 라이선스에는 Windows Autopilot과 함께 설치할 수 있는 Windows 10 Enterprise E3가 포함됩니다.

<a name="office-365-business"></a>
###  <a name="microsoft-365-apps-for-business"></a>비즈니스용 Microsoft 365 앱

장치에 설치된 비즈니스용 Microsoft 365 앱 클라이언트는 엔터프라이즈용 Microsoft 365 앱의 기능을 자동으로 사용하기 시작됩니다. 마이그레이션 후 다음을 사용할 수 있습니다.

 - 그룹 정책 지원
 - 스프레드시트 비교 및 문의
 - 비즈니스 인텔리전스

