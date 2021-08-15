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
description: 비즈니스를 새로운 비즈니스로 이동하는 Microsoft 365 Business Premium Microsoft 365 E3.
ms.openlocfilehash: d3030518f7f4467c7b2e16897dc7b100764d9d5a36c50169b58f1adcd7bef209
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "53837650"
---
# <a name="migrate-from-microsoft-365-business-premium-to-microsoft-365-e3"></a>Microsoft 365 Business Premium에서 Microsoft 365 E3로 마이그레이션

Microsoft 365 Business Premium 중소기업에 필요한 모든 것이 있으며, 직원이 최고의 작업을 할 수 있도록 하는 간단한 장치 관리 및 보안과 동급 최고의 클라우드 기반 생산성 앱을 결합합니다. 그러나 경우에 따라 Microsoft 365 Business Premium 구독을 마이그레이션해야 할 Microsoft 365 E3.

예를 들어 비즈니스가 성장하여 300개 이상의 라이선스가 필요합니다(축하합니다.

또는 비즈니스에 엔터프라이즈 기능(예: 엔터프라이즈용 Microsoft 365 앱, Windows 10 Enterprise E3 또는 ENTERPRISE 클라이언트 액세스 라이선스)이 필요합니다.

업그레이드는 관리 센터에서 쉽게 시작할 [수 있습니다.](../commerce/subscriptions/upgrade-to-different-plan.md) 현재 구독의 모든 데이터 및 구성이 유지 관리됩니다. 마이그레이션을 준비하기 위해 할 수 있는 것은 아니며, 새 기능을 활용하는 것 외에는 그 이후에 할 일도 없습니다.

> [!NOTE]
> 최대 300개 Microsoft 365 Business Premium 사용자 수에 대해 Microsoft 365 E3 구독을 사용할 수 있습니다. 그러나 Microsoft Defender for Office 365 포함된 Microsoft 365 E3. 계속해서 위협 방지를 위해 Office 365 대한 Defender의 범위에 있는 모든 사용자에게 라이선스가 부여될 수 있도록 Office 365 Defender를 추가해야 합니다.

## <a name="differences-between-microsoft-365-business-premium-and-microsoft-365-enterprise"></a>Microsoft 365 Business Premium 및 Microsoft 365 Enterprise

다음 표에서는 두 가지 차이점을 Microsoft 365 Business Premium Microsoft 365 E3.

| 기능    | 지원 Microsoft 365 Business Premium    | 지원 Microsoft 365 E3 |
|:-------|:-----|:-----|
| **On-premises**        | | |
| Windows 10    | Windows 10 Business  |     Windows 10 Enterprise E3|
| Office 앱*    | [비즈니스용 Microsoft 365 앱](#office-365-business)    | 엔터프라이즈용 Microsoft 365 앱 |
| **클라우드 생산성 앱**        | | |
| Exchange Online Outlook    | 사서함당 50GB 저장소 제한 및 무제한 Exchange Online 보관    | 사서함당 100GB 저장소 제한 및 무제한 Exchange Online 보관 |
| Teams    | ![포함된 Microsoft 365 Business Premium](../media/check-mark.png)    | ![포함된 Microsoft 365 E3](../media/check-mark.png) |
| 비즈니스용 OneDrive    | 사용자당 1 TB 저장소 제한    | 무제한 |
| Yammer, SharePoint Online, Planner, Stream    | ![포함된 Microsoft 365 Business Premium](../media/check-mark.png)    | ![포함된 Microsoft 365 E3](../media/check-mark.png) |
| **위협 방지**        | | |
| 공격 표면 감소 기능    | [이 목록 보기](#threat-protection) | Enterprise 대한 하드웨어 기반의 고지서 Microsoft Edge |
| Office 365용 Defender 플랜 1 | ![포함된 Microsoft 365 Business Premium](../media/check-mark.png)    | 포함되지 않지만 에 추가할 수 있습니다. |
| **ID 관리**        | | |
| 하이브리드 AZURE ACTIVE DIRECTORY(Azure AD) 계정, Azure AD MFA(다단계 인증), 조건부 액세스,온-프레미스 ID에 대한 암호 쓰기 저장에 대한 셀프 서비스 암호 재설정|     ![포함된 Microsoft 365 Business Premium](../media/check-mark.png)    | ![포함된 Microsoft 365 E3](../media/check-mark.png) |
| Cloud App Discovery, Azure AD 커넥트 Health    |     | ![포함된 Microsoft 365 E3](../media/check-mark.png) |
| Azure AD Office 365 SSO(Single Sign-On): 사용자당 앱 10개(Salesforce와 같은 갤러리 SaaS 앱)* | ![포함된 Microsoft 365 Business Premium](../media/check-mark.png)    | ![포함된 Microsoft 365 E3](../media/check-mark.png) |
| Azure AD Premium 1 SSO: 제한 없음(Azure AD 응용 프로그램 프록시를 통한 Self-Service 앱 통합 템플릿을 사용하는 비 갤러리 앱)    |     | ![포함된 Microsoft 365 E3](../media/check-mark.png) |
| **장치 및 앱 관리**        | | |
| Microsoft Intune, Windows Autopilot|     ![포함된 Microsoft 365 Business Premium](../media/check-mark.png)    | ![포함된 Microsoft 365 E3](../media/check-mark.png) |
|VDA(가상 데스크톱 액세스)    |  |     ![포함된 Microsoft 365 E3](../media/check-mark.png) |
|Windows WVD(가상 데스크톱)    | ![포함된 Microsoft 365 Business Premium](../media/check-mark.png) |     ![포함된 Microsoft 365 E3](../media/check-mark.png) |
|SCA(공유 컴퓨터 정품 인증)    | ![포함된 Microsoft 365 Business Premium](../media/check-mark.png) |     ![포함된 Microsoft 365 E3](../media/check-mark.png) |
| Microsoft 데스크톱 최적화 패키지    | |     ![포함된 Microsoft 365 E3](../media/check-mark.png) |
| **정보 보호**        | | |
| Office 365 데이터 손실 방지, Azure Information Protection 계획 1    | ![포함된 Microsoft 365 Business Premium](../media/check-mark.png)    | ![포함된 Microsoft 365 E3](../media/check-mark.png) |
| 끝점 DLP에 대한 창 정보 보호    | ![포함된 Microsoft 365 Business Premium](../media/check-mark.png)    | ![포함된 Microsoft 365 E3](../media/check-mark.png) |
| **CAL(클라이언트 액세스 라이선스)**    | | |
| Enterprise CAL 제품군(Exchange, SharePoint, Skype, Windows, Microsoft Endpoint Configuration Manager, Windows Rights Management)| |         ![포함된 Microsoft 365 E3](../media/check-mark.png) |
| **규정 준수**        | | |
| 무제한 전자 메일 보관    | ![포함된 Microsoft 365 Business Premium](../media/check-mark.png)    | ![포함된 Microsoft 365 E3](../media/check-mark.png) |
| 규정 관리자    | ![포함된 Microsoft 365 Business Premium](../media/check-mark.png)    | ![포함된 Microsoft 365 E3](../media/check-mark.png) |
| eDiscovery    | ![포함된 Microsoft 365 Business Premium](../media/check-mark.png)    | ![포함된 Microsoft 365 E3](../media/check-mark.png) |
| In-place hold and litigation hold    | ![포함된 Microsoft 365 Business Premium](../media/check-mark.png)    | ![포함된 Microsoft 365 E3](../media/check-mark.png) |
| MRM(메시징 레코드 관리) 보존 태그 및 보존 정책    | ![포함된 Microsoft 365 Business Premium](../media/check-mark.png)    | ![포함된 Microsoft 365 E3](../media/check-mark.png) |
||||

\* SaaS 앱에 대한 액세스 권한이 할당된 사용자는 최대 10개 앱에 대한 SSO 액세스 권한을 얻을 수 있습니다. 관리자는 SSO를 구성하고 다른 SaaS 앱에 대한 사용자 액세스를 변경할 수 있지만 SSO 액세스는 사용자당 한 10개 앱만 허용됩니다. 모든 Office 365 앱은 단일 앱으로 계산됩니다.

## <a name="migration"></a>마이그레이션

마이그레이션하려면 파트너와 협력하여 Microsoft 365 Business Premium 라이선스가 있는 적절한 Microsoft 365 E3 구독으로 이동하세요.

다음 섹션에서는 변경해야 하는 사항, 변경 내용(있는 경우) 및 마이그레이션 후 할 수 있는 작업을 설명합니다.

### <a name="microsoft-365-subscription-configuration-and-data"></a>Microsoft 365 구성 및 데이터 관리

마이그레이션하기 전에 다음을 포함하는 현재 구독 또는 데이터를 변경할 필요가 없습니다.

- 구독 구성(예: DNS 도메인 이름)
- 사용자 및 그룹 계정 및 인증 설정(예: 다단계 인증 또는 조건부 액세스 정책)
- 생산성 서비스 구성 및 데이터(예: Teams, Exchange Online 사서함, SharePoint Online 사이트, 비즈니스용 OneDrive 폴더 및 전자 필기장 OneNote).

이제 사용자는 사서함 및 Exchange Online 폴더에서 무제한 저장소를 비즈니스용 OneDrive 있습니다.

10개 이상의 앱에 대해 Cloud App Discovery, Azure AD 커넥트 상태 및 SSO 사용을 시작할 수 있습니다.

<a name="threat-protection"></a>
### <a name="threat-protection"></a>위협 방지

Windows 10 Business 포함된 보호는 다음과 같습니다.

- 운영 체제 부팅 프로세스의 무결성 적용
- 중요한 운영 구성 요소의 무결성 적용
- 고급 취약성 및 제로 데이 악용 완화
- Microsoft Edge, Internet Explorer 및 Chrome에 대한 신뢰도 기반 네트워크 보호
- 호스트 기반 방화벽
- 랜섬웨어 완화
- 사용자에 대한 하드웨어 기반 Microsoft Edge
- 지능형 보안 기능으로 지원되는 응용 프로그램 Graph
- 디바이스 제어(USB)
- 웹 기반 위협에 대한 네트워크 보호
- 호스트 침입 방지 규칙

Windows 10 Enterprise E3에는 하드웨어 기반의 하드웨어 기반의 엔터프라이즈 관리도 포함되어 Microsoft Edge.

> [!NOTE]
> 마이그레이션된 사용자는 Microsoft 365 E3 보호를 위해 각각 microsoft Defender for Office 365 라이선스가 필요합니다. 추가 Defender를 구입하여 Office 365 대한 Defender의 범위에 있는 모든 사용자가 라이선스가 Office 365 수 있도록 합니다.

### <a name="device-management-with-intune"></a>Intune을 사용하여 장치 관리

등록된 장치와 장치 및 앱 설정을 포함하는 마이그레이션 전에 현재 Intune 구성을 변경할 필요가 없습니다.

### <a name="windows-10"></a>Windows 10

Microsoft 365 Business Premium AutoPilot을 Windows 10 Business 설치할 수 있는 Windows 포함되어 있습니다. 사용자 라이선스로 마이그레이션할 Microsoft 365 E3 각 사용자 라이선스에는 Windows 10 Enterprise E3가 포함되어 Autopilot을 사용하여 설치할 Windows 있습니다.

<a name="office-365-business"></a>
###  <a name="microsoft-365-apps-for-business"></a>비즈니스용 Microsoft 365 앱

장치에 비즈니스용 Microsoft 365 앱 클라이언트가 자동으로 클라이언트의 기능을 사용하기 엔터프라이즈용 Microsoft 365 앱. 마이그레이션 후 다음을 사용할 수 있습니다.

- 그룹 정책 지원
- 스프레드시트 비교 및 문의
- 비즈니스 인텔리전스
