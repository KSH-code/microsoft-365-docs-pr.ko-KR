---
title: Microsoft 컨설팅 서비스 활용
description: MCS와 함께 앱을 패키지로 구성하기 위한 준비 및 단계
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 2b68d9d36e52e84867bf6411f4e723e7551fa55b
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60211552"
---
# <a name="working-with-microsoft-consulting-services"></a>Microsoft 컨설팅 서비스 활용

MCS(Microsoft Consulting Services)에 참여하여 앱 패키지로 패키지된 앱을 다운로드할 수 Microsoft Managed Desktop. 정확한 정보를 확인하려면 계정 담당자와 함께 MCS에 문의하고 특정 앱 패키징 프로젝트의 범위를 지정합니다.

## <a name="roles-and-responsibilities"></a>역할 및 책임

MCS 앱 패키징을 사용하려면 **다음 요소를 제공해야 합니다.**

- 원본 설치 관리자 파일(예: setup.exe 또는 .msi.
- 최종 설치의 모양에 대한 세부 정보를 지정하는 설치 지침입니다. 예를 들어 앱에 대한 데스크톱 바로 가기가 있나요? 앱의 표시 여부는 어떻게 하나요? 앱이 서버에 연결해야 하는 경우 어떤 서버가 연결하나요? 자세한 내용은 응용 프로그램 패키징 요청 [템플릿 을 참조합니다.](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/app-packaging-template.docx)
- 사용자 환경에서 앱이 필요한 경우 작동하는지 확인하기 위해 자체 승인 테스트를 수행해야 합니다.

**MCS는 다음 작업을 관리합니다.**

- 앱의 사용이 금지되거나 제한되어 있는지 Microsoft Managed Desktop 검사합니다.
- 앱 설치, 시작 및 제거 테스트로 앱과의 호환성을 Windows 10. MCS가 호환성 문제를 발견하면 수정을 위해 [앱을 App Assure](/fasttrack/products-and-capabilities#app-assure) 프로그램으로 제공합니다.
- 앱을 사양에 패키징한 다음 앱을 사용하여 앱 배포를 Microsoft Intune.

## <a name="app-delivery-schedule"></a>앱 배달 일정

앱 정보를 앱 포털에 업로드하여 패키징 Microsoft Managed Desktop 시작하세요. 패키징 팀은 매주 목요일에 새 제출을 검토합니다. 검토 및 패키징 후 패키지된 앱은 다음 금요일에 배달됩니다. 시작을 위해 일주일에 최대 5개의 앱을 패키지로 구성할 수 있지만, 서비스는 요구에 따라 확장할 수 있습니다.

![목요일(이 예제의 21일), 미디어 유효성 검사, 다음 주 월요일(25일)에 패키징, 다음 금요일(29일)에 앱 배달을 표시하는 일정](../../media/MCS-cal.png)

앱이 제공된 후 알림을 하게 됩니다. 이때 승인 테스트를 수행하고 21일이 지난 후 포털에서 작업을 Microsoft Managed Desktop 있습니다. 수용 테스트 중에 앱에 문제가 발견되면 Microsoft Managed Desktop 포털에서 앱을 거부하고 MCS 패키지러와 전자 메일을 통해 연결하여 문제를 이해하고 해결합니다.

## <a name="testing-accounts-and-environment"></a>계정 및 환경 테스트

패키징 팀에서 마이그레이션을 완료하기 위해 Microsoft Intune 권한을 제공하는 것이 좋습니다.

- 패키지 Microsoft Intune 할당하기 위한 앱 배포 기능에 대한 액세스
- 패키지러가 앱을 테스트할 수 있도록 테스트 그룹, 사용자 계정 및 라이선스

MCS는 해당 사용 권한을 사용하여 다음 작업을 수행하게 됩니다.

- 앱에 대해 구성된 가상 머신에서 앱이 작동하는지 Microsoft Managed Desktop
- 사용자에게 배포할 Microsoft Intune 앱 업로드

이러한 권한이 없는 경우 MCS가 앞으로 이동할 수 있지만 응용 프로그램을 사용자 환경에 업로드할 수 없습니다.
