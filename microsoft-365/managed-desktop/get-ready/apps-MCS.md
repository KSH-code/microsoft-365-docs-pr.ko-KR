---
title: Microsoft 컨설팅 서비스 활용
description: MCS와 함께 앱을 패키지하기 위한 준비 및 단계
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 설명서, 앱, MCS, 패키징
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: f8c4e427c536577ea2fc768d4930b9d4db6ac697
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841426"
---
# <a name="working-with-microsoft-consulting-services"></a>Microsoft 컨설팅 서비스 활용

MCS(Microsoft Consulting Services)에 참여하여 Microsoft Managed Desktop에서 사용하기 위해 패키지된 앱을 다운로드할 수 있습니다. 정확한 세부 정보는 계정 담당자와 함께 MCS에 문의하고 특정 앱 패키징 프로젝트의 범위를 지정합니다.

## <a name="roles-and-responsibilities"></a>역할 및 책임

MCS 앱 패키징을 사용하려면 **다음 요소를 제공해야 합니다.**

- 원본 설치 관리자 파일(예: setup.exe 또는 .msi)입니다.
- 최종 설치의 모양에 대한 세부 정보를 지정하는 설치 지침입니다. 예를 들어 앱에 대한 데스크톱 바로 가기가 있나요? 앱의 가시성은 어떻게 해야 하나요? 앱이 서버에 연결해야 하는 경우 어떤 서버가 연결하나요? 자세한 내용은 응용 프로그램 패키징 [요청 템플릿을 참조합니다.](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx)
- 직접 승인 테스트를 수행하여 앱이 사용자 환경에서 필요할 때 작동하는지 확인해야 합니다.

**MCS는 다음 작업을 관리합니다.**

- Microsoft Managed Desktop 환경에서 앱이 금지되거나 제한되어 있는지를 검사합니다.
- Windows 10과의 호환성을 보장하기 위해 앱 설치, 시작 및 제거 테스트 MCS가 호환성 문제를 발견하면 수정을 위해 [Desktop App Assure](https://docs.microsoft.com/fasttrack/win-10-desktop-app-assure) 프로그램에 앱을 제공합니다.
- 앱을 사양에 패키징한 다음 Microsoft Intune을 사용하여 앱 배포를 테스트합니다.

## <a name="app-delivery-schedule"></a>앱 배달 일정

Microsoft Managed Desktop 포털에 앱 정보를 업로드하여 패키징 프로세스를 시작하세요. 패키징 팀은 매주 목요일에 새 제출을 검토합니다. 검토 및 패키징 후 패키지된 앱은 다음 금요일에 제공됩니다. 시작을 위해 일주일에 최대 5개의 앱을 패키지로 구성할 수 있지만 서비스는 요구에 따라 확장할 수 있습니다.

![목요일(이 예의 21일), 미디어 유효성 검사, 다음 주 월요일(25일) 패키징, 다음 금요일(29일) 앱 배달을 보여주는 일정](../../media/MCS-cal.png)

앱이 제공된 후 알림을 하게 됩니다. 이때 Microsoft Managed Desktop 포털에서 승인 테스트를 수행하고 작업을 승인할 수 있는 21일이 있습니다. 수락 테스트 중에 앱에 문제가 발견되면 Microsoft Managed Desktop 포털에서 앱을 거부하고 MCS 패키지러와 전자 메일을 통해 연결하여 문제를 이해하고 해결합니다.

## <a name="testing-accounts-and-environment"></a>계정 및 환경 테스트

패키징 팀이 Microsoft Intune으로의 마이그레이션을 완료하려면 다음의 특정 권한을 제공하는 것이 좋습니다.
 
-   패키지 패키지에서 앱을 추가하고 할당할 수 있는 Microsoft Intune의 앱 배포 기능에 대한 액세스 
-   패키지러가 앱을 테스트할 수 있는 테스트 그룹, 사용자 계정 및 라이선스

MCS는 이러한 사용 권한을 사용하여 다음 작업을 수행하게 됩니다.
 
-   Microsoft Managed Desktop에 대해 구성된 가상 머신에서 앱이 작동하는지 보장
-   사용자에게 배포하기 위해 Microsoft Intune에 앱 업로드

이러한 사용 권한이 없는 경우 MCS가 진행할 수 있지만 해당 환경으로 응용 프로그램을 업로드할 수 없습니다.


