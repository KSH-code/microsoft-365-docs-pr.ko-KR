---
title: Microsoft Managed Desktop의 앱
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: a24212cf69df50d00a32f17e8daf1939657dd602
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632854"
---
# <a name="apps-in-microsoft-managed-desktop"></a>Microsoft Managed Desktop의 앱

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
## <a name="apps-generally"></a>일반적으로 앱

Microsoft에는 microsoft Managed Desktop에 참여 하는 데 필요한 Microsoft 365 E3 또는 E5 라이선스와 함께 특정 주요 앱이 포함 되어 있습니다. 그러나 이러한 앱을 제공 하더라도 완료 해야 하는 몇 가지 책임과 작업이 계속 남아 있습니다.

또한 Microsoft Intune의 배포 파이프라인을 사용 하 여 회사 포털 또는 필요한 백그라운드 설치를 통해 셀프 서비스에 대 한 타사 앱을 추가 하 여 최종 사용자에 게 배포할 수 있습니다. 전문 지식을 보유 한 경우 사용자가 필요한 앱을 마이그레이션할 수 있습니다. 또는 MCS (Microsoft 컨설팅 서비스) 또는 타사 공급 업체가 사용자에 게 패키징 및 마이그레이션 프로젝트를 제공 하는 데 도움을 드립니다. MCS에서 작업 하는 방법에 대 한 자세한 내용은 [Microsoft 컨설팅 Services 사용](apps-MCS.md)을 참조 하십시오.


## <a name="apps-provided-by-microsoft"></a>Microsoft에서 제공 하는 앱

Microsoft Managed Desktop license에는 enterprise Standard 제품군 용 Microsoft 365 앱 (Word, Excel, PowerPoint, Outlook, Publisher, Access, 비즈니스용 Skype, OneNote)에 있는 앱의 64 비트 버전을 포함 합니다. 간편 실행 버전의 Microsoft Project 및 Visio는 기본적으로 포함 되어 *있지* 않지만 추가 하도록 요청할 수 있습니다. 이러한 앱에 대 한 자세한 내용은 microsoft [Managed 데스크톱 장치에서 Microsoft Project 또는 Microsoft Visio 설치](../get-started/project-visio.md)를 참조 하세요.

### <a name="what-microsoft-does-to-support-the-apps-we-provide"></a>제공 되는 앱을 지원 하기 위해 Microsoft에서 수행 하는 작업

Microsoft는 엔터프라이즈 앱에 포함 된 Microsoft 365 앱에 대 한 배포, 업데이트 및 지원에 대 한 전체 서비스를 제공 합니다. 간편 실행 버전의 Microsoft Project 및 Visio는 기본적으로 포함 되어 *있지* 않지만 Microsoft Managed Desktop은 배포 그룹을 제공 하므로 IT 관리자가 라이선스를 관리 하 고 이러한 응용 프로그램을 조직에 적절 하 게 배포할 수 있습니다. Microsoft는 Microsoft 관리 데스크톱 지원 채널을 통해 이러한 응용 프로그램의 최종 사용자를 지원 합니다.

### <a name="what-you-need-to-do-to-support-the-apps-we-provide"></a>제공한 앱을 지원 하기 위해 수행 해야 하는 작업

이러한 앱은 여전히 수행 해야 하는 작업은 다음과 같습니다.

- **라이선스 할당** -최종 사용자에 게 적절 한 라이선스를 구하고 할당 하 여 Microsoft 365 앱 for enterprise를 사용할 책임이 있습니다.
- **보안 그룹에 사용자 추가** -Microsoft 프로젝트나 Visio를 사용 하는 경우 IT 관리자가 해당 사용자를 적절 한 배포 그룹에 추가 해야 합니다. 또한 IT 관리자는 해당 사용자가 회사를 떠날 때 라이선스를 다시 확보 해야 합니다.
- **Microsoft 365 추가 기능 배포** -엔터프라이즈 앱 용 Microsoft 365 앱에 대 한 추가 기능이 필요한 경우 다른 Windows 32 앱과 마찬가지로 중앙 집중식으로 배포 합니다. 

## <a name="apps-you-provide"></a>사용자가 제공한 앱

물론 비즈니스 작업에 필요한 다른 앱이 많이 있을 수 있습니다. 이러한 장치는 Microsoft Intune의 배포 파이프라인을 사용 하 여 Microsoft Managed Desktop devices에만 배포할 수 있습니다. 앱이 필요한 경우 공급 업체에 의해 패키지 패키지로 제공 될 수 있습니다 (Microsoft 제품이 아닌 다른 공급 업체나 Microsoft 컨설팅 서비스 (MCS) 일 수 있음) 아니면이 방법을 사용 하는 경우 직접 패키지할 수 있습니다. 그런 다음 이러한 패키지를 Microsoft Managed Desktop portal에 추가 하 고이를 Azure Active Directory 그룹에 할당 하 여 배포를 트리거합니다. 

현재 Microsoft Endpoint Configuration Manager를 사용 하 여 앱을 배포 하는 경우 Microsoft Managed Desktop은 앱을 평가 하 고 Microsoft Intune으로 마이그레이션할 준비가 된 것과 몇 가지 조정이 필요한 모든 항목을 확인할 수 있는 쿼리를 제공 합니다.


### <a name="preparing-your-own-apps-for-inclusion-in-microsoft-managed-desktop"></a>Microsoft Managed Desktop에 포함할 앱 준비
앱을 검토 하 고 다음을 확인 합니다.

- [Microsoft Managed Desktop app 요구 사항](https://aka.ms/app-req)에 설명 된 대로 어떤 앱도 금지 되거나 제한 된 동작이 있습니다.
- 앱은 Microsoft Intune을 통해 관리할 준비가 되어 있어야 합니다. 이에 대 한 자세한 내용은 [Microsoft intune을 사용 하 여 Windows 10 앱 배포](https://docs.microsoft.com/intune/apps-windows-10-app-deploy) 및 [microsoft Intune에 앱 추가](https://docs.microsoft.com/intune/apps-add)를 참조 하세요.
- 라이선스 키 제공, 사용권 조항에 대 한 계약, 사전 설정 서버 연결 등의 기타 사전 패키징 요구 사항

### <a name="decide-how-to-package-apps"></a>앱을 패키지 하는 방법을 결정 합니다.

일부 독립 소프트웨어 공급 업체에서는 앱이 중앙에서 배포 되기 전에 패키지 되도록 해야 할 수도 있습니다. "패키징"은 앱의 설치 관리자가 앱을 백그라운드에서 설치할 수 있도록 라이선스 키, 원격 서버 위치 또는 바탕 화면 바로 가기와 같은 설정으로 구성 됨을 의미 합니다.

앱을 패키지 하는 세 가지 옵션은 다음과 같습니다. 


- 앱을 직접 패키지할 수 있습니다.
- Microsoft 제품이 아닌 다른 공급 업체와 함께 작업할 수 있습니다.
- MCS를 사용 하 여 앱을 패키지할 수 있습니다. Microsoft 계정 담당자와 함께 작업 합니다. 자세한 내용은 [Microsoft 컨설팅 서비스 작업](apps-MCS.md)을 참조 하십시오.







## <a name="deploying-apps"></a>앱 배포

앱 패키지를 가져오는 데 사용 하는 방법에 관계 없이 완료 되 면 [Microsoft Managed 데스크톱 장치에 앱 배포](../get-started/deploy-apps.md)의 단계를 진행할 수 있습니다.


