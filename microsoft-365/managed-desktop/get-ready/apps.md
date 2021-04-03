---
title: Microsoft Managed Desktop의 앱
description: 앱을 패키지화, 배포 및 지원하는 방법을 포함하여 앱 처리 방법에 대해 설명
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: d970ac1a28c62703f648e4fbf6f66e2f825a6188
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574622"
---
# <a name="apps-in-microsoft-managed-desktop"></a>Microsoft Managed Desktop의 앱

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
## <a name="apps-generally"></a>일반적으로 앱

Microsoft에는 Microsoft Managed Desktop에 참여하는 데 필요한 Microsoft 365 E3 또는 E5 라이선스와 함께 특정 주요 앱이 포함되어 있습니다. 그러나 이러한 앱을 제공하겠지만 여전히 완료할 특정 책임과 작업이 있습니다.

또한 Microsoft Intune의 배포 파이프라인을 사용하여 회사 포털 또는 필수 백그라운드 설치를 통해 셀프 서비스를 위해 Microsoft가 아닌 다른 앱을 사용자에게 배포할 수도 있습니다. 전문 지식이 있는 경우 필요한 앱을 마이그레이션할 수 있습니다. 또는 MCS(Microsoft Consulting Services) 또는 비 Microsoft 공급업체가 패키징 및 마이그레이션 프로젝트를 지원할 수 있습니다. MCS 사용에 대한 자세한 내용은 Microsoft Consulting Services 작업을 [참조하세요.](apps-MCS.md)


## <a name="apps-provided-by-microsoft"></a>Microsoft에서 제공하는 앱

Microsoft Managed Desktop 라이선스에 포함된 앱의 64비트 버전은 엔터프라이즈용 Microsoft 365 앱 Standard Suite(Word, Excel, PowerPoint, Outlook, Publisher, Access, 비즈니스용 Skype 및 OneNote)입니다. Microsoft Project 및 Visio의 Click-to-Run 버전은 기본적으로 포함되지 않지만 추가를 요청할 수 있습니다.  이러한 앱에 대한 자세한 내용은 Microsoft Managed Desktop 장치에 Microsoft Project 또는 [Microsoft Visio 설치를 참조하세요.](../get-started/project-visio.md)

### <a name="what-microsoft-does-to-support-the-apps-we-provide"></a>Microsoft에서 제공하는 앱을 지원하기 위해 Microsoft가 하는 일

Microsoft는 포함된 엔터프라이즈용 Microsoft 365 앱의 배포, 업데이트 및 지원을 위한 전체 서비스를 제공합니다. Microsoft Project 및 Visio의 Click-to-Run 버전은 기본적으로 포함되지 않지만 Microsoft Managed Desktop은 IT 관리자가 라이선스를 관리하고 조직에 적합한 응용 프로그램을 배포할 수 있도록 배포 그룹을 제공합니다.  Microsoft는 Microsoft Managed Desktop 지원 채널을 통해 이러한 응용 프로그램의 사용자를 지원합니다.

### <a name="what-you-need-to-do-to-support-the-apps-we-provide"></a>제공한 앱을 지원하기 위해 필요한 일

이러한 앱에서는 여전히 몇 가지 작업을 해야 합니다.

- **라이선스 할당** - 엔터프라이즈용 Microsoft 365 앱의 사용자에게 적절한 라이선스를 획득하고 할당할 책임이 있습니다.
- **보안 그룹에** 사용자 추가 - Microsoft Project 또는 Visio를 사용하는 경우 IT 관리자가 해당 사용자를 적절한 배포 그룹에 추가해야 합니다. 또한 IT 관리자는 퇴사하는 경우 해당 사용자로부터 라이선스를 취득할 책임이 있습니다.
- **Microsoft 365** 추가 기능 배포 - 엔터프라이즈용 Microsoft 365 앱에 대한 추가 기능을 필요로 하는 경우 다른 Windows 32 앱처럼 중앙에서 배포합니다. 

## <a name="apps-you-provide"></a>제공하는 앱

비즈니스 작업에 필요한 다른 앱이 있는 것일 수 있습니다. 이러한 앱은 Microsoft Intune의 배포 파이프라인을 사용하여 Microsoft Managed Desktop 장치에만 배포할 수 있습니다. 앱이 필요한 경우 공급업체(Microsoft가 아닌 공급업체 또는 MCS(Microsoft Consulting Services)일 수 있는)에서 패키지로 제공하거나, 필요한 경우 패키지로 직접 패키지할 수 있습니다. 그런 다음 이러한 패키지를 Microsoft Managed Desktop 포털에 추가하고 Azure Active Directory 그룹에 할당하여 배포를 트리거합니다. 

현재 Microsoft Endpoint Configuration Manager를 사용하여 앱을 배포하는 경우 Microsoft Managed Desktop은 앱을 평가하는 쿼리를 제공하고 Microsoft Intune으로 마이그레이션할 준비가 된 쿼리와 일부 조정이 필요할 수 있는 앱을 검색할 수 있습니다.


### <a name="preparing-your-own-apps-for-inclusion-in-microsoft-managed-desktop"></a>Microsoft Managed Desktop에 포함하기 위해 자체 앱 준비
앱을 검토하여 다음을 검사합니다.

- [Microsoft Managed Desktop](../service-description/mmd-app-requirements.md)앱 요구 사항에 설명된 바와 같이 금지되거나 제한된 동작이 없는 앱은 없습니다.
- Microsoft Intune에서 앱을 관리하기 위해 준비해야 합니다. 이 항목에 대한 자세한 내용은 [Microsoft Intune을 사용하여 Windows 10](/intune/apps-windows-10-app-deploy) 앱 배포 및 Microsoft [Intune에 앱 추가를 참조하세요.](/intune/apps-add)
- 라이선스 키 제공, 사용 조건 계약 및 서버 연결 사전 설정과 같은 기타 패키징 전 요구 사항

### <a name="decide-how-to-package-apps"></a>앱을 패키지하는 방법 결정

일부 독립 소프트웨어 게시자는 앱을 중앙에서 배포하기 전에 패키지해야 할 수 있습니다. "패키징"은 앱을 백그라운드에서 설치할 수 있도록 앱의 설치 관리자를 라이선스 키, 원격 서버 위치 또는 데스크톱 바로 가기와 같은 설정으로 구성하는 것입니다.

앱을 패키지로 다운로드하는 세 가지 옵션이 있습니다. 


- 직접 앱을 패키지로 구성할 수 있습니다.
- Microsoft가 아닌 공급업체와 함께 작업할 수 있습니다.
- MCS와 함께 앱을 패키지로 구성할 수 있습니다. Microsoft 계정 담당자와 함께 작업합니다. 자세한 내용은 Microsoft Consulting Services 작업을 [참조하세요.](apps-MCS.md)



## <a name="deploying-apps"></a>앱 배포

앱을 패키지로 다운로드하는 데 사용하는 모든 방법을 완료하면 [Microsoft Managed Desktop](../get-started/deploy-apps.md)디바이스에 앱 배포의 단계를 따를 수 있습니다.


## <a name="steps-to-get-ready"></a>준비 단계

1. Microsoft Managed Desktop의 선행 [준비를 검토합니다.](prerequisites.md)
2. 준비 [평가 도구를 사용합니다.](readiness-assessment-tool.md)
3. [게스트 계정에 대한 필수 구성 요소](guest-accounts.md)
4. [Microsoft Managed Desktop의 네트워크 구성](network.md)
5. [Microsoft Managed Desktop 인증서 및 네트워크 프로필 준비](certs-wifi-lan.md)
6. [Microsoft Managed Desktop의 온-프레미스 리소스 액세스 준비](authentication.md)
7. [Microsoft Managed Desktop의](apps.md) 앱(이 문서)
8. [Microsoft Managed Desktop의 매핑된 드라이브 준비](mapped-drives.md)
9. [Microsoft Managed Desktop의 인쇄 리소스 준비](printing.md)
