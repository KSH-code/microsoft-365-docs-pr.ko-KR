---
title: Microsoft 365 엔터프라이즈 비즈니스 연속성 관리 완화
author: chrfox
ms.author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Microsoft 365 서비스 인시던트 시나리오에 대한 몇 가지 샘플 완화
ms.openlocfilehash: c2eaa51bd6980893780f6e0534f33cac636ad716
ms.sourcegitcommit: c5ca71d6feb0f033b50ccd4de816fd59b0925007
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/04/2019
ms.locfileid: "39831979"
---
# <a name="service-incident-mitigation-strategies"></a>서비스 인시던트 완화 전략

다음은 Microsoft 365 서비스 인시던트가 비즈니스 프로세스에 미치는 영향을 완화하는 방법을 보여 주는 몇 가지 전략 및 시나리오입니다.

## <a name="service-incident-scenarios-and-potential-mitigations"></a>서비스 인시던트 시나리오 및 잠재적 완화

|Microsoft 365 의존 관계|잠재적 완화|
|---------|---------|
|인시던트 관리 시스템은 Exchange Online을 사용하여 출장 엔지니어 및 인시던트 관리자와 연락합니다.|인시던트 관리 시스템에서 병렬 메일, 전화 통화, SMS 알림 등과 같은 다중 채널 통신을 지원하는지 확인하고 기본 통화에 참여하지 않는 경우에는 시스템에서 자동으로 백업이 진행되도록 트리 계층 구조를 호출합니다. 또한 백업 통신 방법을 쉽게 참조할 수 있도록 모든 알림에 백업 연락 방법을 포함합니다. 인시던트 관리 서비스를 사용할 수 없는 경우 Yammer와 같은 대체 통신 방법을 응급 공동 작업에 사용할 수 있습니다.|
|Microsoft Teams는 클라이언트를 통해 액세스되는 파일을 저장하는 데 사용됩니다.|Teams는 클라이언트에 업로드된 파일을 SharePoint Online 문서 라이브러리에 저장합니다. SharePoint Online을 통해 파일에 계속 액세스할 수 있습니다. SharePoint Online 내 파일 위치를 사용자에게 알려줍니다.|
|일반 통신 및 인시던트 관리 분류의 경우 Microsoft Teams 전화 회의가 사용됩니다.|타사 공급자와 함께 백업 회의 솔루션을 구축합니다.|
|VoIP 전화는 보조 통신 방법으로 사용됩니다.|특히, 인시던트 중 네트워크 및 서비스 작업을 위해 PSTN 통화를 지원하는 비 VoIP 전화를 구현합니다. 셀룰러 네트워크를 통해 주요 담당자에게 연락할 수 있도록 직원 휴대폰 번호를 회사 디렉터리에 추가합니다.|
|파일 저장 및 사용자 생산성을 위해 비즈니스용 OneDrive를 사용합니다. [요청 시 파일](https://techcommunity.microsoft.com/t5/Microsoft-OneDrive-Blog/OneDrive-Files-On-Demand-For-The-Enterprise/ba-p/117234)은 로컬 사용자 드라이브의 공간을 확보하도록 구성되어 있습니다.|OneDrive 동기화는 관리자가 특정 콘텐츠를 로컬로 동기화하거나 원하는 경우 공간을 확보할 수 있는 그룹 정책을 제공합니다. 문서에 액세스할 수 없는 위험을 완화하려면 중요 문서를 로컬로 동기화하도록 이 정책을 구성합니다. 주요 문서에 대해 "이 장치에 항상 유지" 설정을 수동으로 적용하도록 사용자를 교육합니다.|
|고객 및 공급업체에 대한 비즈니스 중단 통신에는 Exchange Online을 사용합니다.|공개 타사 소셜 네트워크를 대중 통신의 대체 방법으로 사용할 수 있습니다.

## <a name="leveraging-mobile-app-access"></a>모바일 앱 액세스 활용

모바일 사용의 확산으로 연결을 유지하는 새로운 방법이 생겨나고 Microsoft 365 모바일 응용 프로그램이 전략의 핵심 부분이 될 수 있습니다. 이 응용 프로그램은 셀룰러 공급자 네트워크를 통해 클라우드 서비스에 연결하므로, 조직의 네트워크 인프라에 종속되지 않습니다.

Outlook을 예로 들어 보겠습니다. 사용자는 사용 중인 이메일 앱에 따라 다른 네트워크 프로토콜(https 또는 MAPI)을 통해 Exchange Online 사서함에 연결할 수 있습니다. 프로토콜 중 하나가 포함된 서비스 인시던트가 발생한 경우(데스크톱 클라이언트에 사용되는 인시던트의 경우 MAPI) 사용자는 Outlook 모바일 앱이나 웹의 Outlook을 통해 사서함에 계속해서 연결할 수 있습니다.
  
사용자가 모바일 장치를 통해 Microsoft 365 서비스에 연결하도록 허용하려면 Microsoft Intune을 사용하여 해당 장치를 안전하게 구성하고 관리할 수 있습니다. 사용자 계정과 장치를 모바일 관리 솔루션에 등록한 후 앱이 다운로드되어 구성되었는지 확인합니다.
