---
title: Microsoft Managed Desktop의 인쇄 리소스 준비
description: 인쇄가 원활하게 작동하기 위한 중요 단계
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 81de89a704c8ff8717439d83e70504ba2fe8e410
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60188916"
---
# <a name="prepare-printing-resources-for-microsoft-managed-desktop"></a>Microsoft Managed Desktop의 인쇄 리소스 준비

응용 프로그램에 등록할 준비가 Microsoft Managed Desktop 인쇄 요구 사항을 평가하고 환경에 적합한 방법을 결정해야 합니다. 다음과 같은 세 가지 옵션이 있습니다.

- Microsoft 유니버설 인쇄 솔루션을 배포하여 Microsoft Managed Desktop 쉽게 검색할 수 있습니다. 자세한 내용은 유니버설 인쇄 [를 참조하세요.](/universal-print/fundamentals/universal-print-whatis)
- 사용자 지정 PowerShell 스크립트를 사용하여 프린터를 직접 배포합니다. 로컬 프린터 설정 [섹션의 단계를](#set-up-local-printers) 따릅니다.
- Windows 10 도메인에 가입된 디바이스와 호환되는 Microsoft가 아닌 클라우드 인쇄 Azure Active Directory 사용 이 솔루션은 해당 솔루션에 대한 소프트웨어 요구 사항을 Microsoft Managed Desktop. 자세한 내용은 앱 요구 [Microsoft Managed Desktop 참조하세요.](../service-description/mmd-app-requirements.md)
 
모든 경우 프린터 드라이버를 Microsoft Update 또는 Microsoft Store 사용할 수 없는 경우 프린터 드라이버를 직접 확보하고 프린터가 있는 Microsoft Managed Desktop 장치로 배포하기 위해 패키지로 Microsoft Intune. 자세한 내용은 [Intune 독립 실행형 - Win32 앱 관리를 참조하세요.](/mem/intune/apps/apps-win32-app-management)

## <a name="set-up-local-printers"></a>로컬 프린터 설정

사용자 지정 PowerShell 스크립트를 사용하여 프린터를 배포하기로 결정하고 인쇄 리소스를 준비한 경우 다음 단계에 따라 공유 프린터를 배포합니다.

1. 검색 포털로 Microsoft Managed Desktop 이동합니다.
2. 관리 포털의  지원 >  지원 요청 섹션에서 레이블이 붙은 프린터 배포 요청을 제출하여 다음 세부 정보를 제공합니다.
    - 공유 프린터 위치에 대해 배포해야 하는 공유 프린터 위치에 대한 모든 UNC Microsoft Managed Desktop 경로
    - 이러한 공유 프린터에 액세스해야 하는 사용자 그룹
3. 관리 포털을 사용하여 요청이 완료된 경우 이를 알 수 있습니다. 처음에는 테스트 배포 그룹의 장치에만 구성을 배포합니다.
4. 구성이 예상한 결과로 작동하는지 테스트하고 확인해야 합니다. 테스트 완료  시 알려주기 위해 지원 요청의 토론 탭을 사용하여 회신합니다.
5. 그런 다음 구성을 다른 배포 그룹에 배포합니다.

## <a name="steps-to-get-ready"></a>준비 단계

1. [Microsoft Managed Desktop의 필수 구성 요소](prerequisites.md)를 감토하세요.
2. [준비 상태 평가 도구](readiness-assessment-tool.md)를 실행하세요.
1. [회사 포털](../get-started/company-portal.md)을 구입하세요.
1. [게스트 계정에 대한 필수 구성 요소](guest-accounts.md)를 검토합니다.
1. [네트워크 구성](network.md)을 확인합니다.
1. [인증서 및 네트워크 프로필을 준비](certs-wifi-lan.md)합니다.
1. [데이터에 대한 사용자 액세스를 준비](authentication.md)합니다.
1. [앱을 준비](apps.md)합니다.
1. [매핑된 드라이브를 준비](mapped-drives.md)합니다.
1. 인쇄 리소스 준비(이 문서).
1. [장치 이름](address-device-names.md)을 기입합니다.
