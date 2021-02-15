---
title: Microsoft Managed Desktop의 인쇄 리소스 준비
description: 인쇄가 원활하게 작동할 수 있도록 하는 중요한 단계
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: b6e809505fed8b1f84eb502dc08751ad1f0b587c
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841402"
---
# <a name="prepare-printing-resources-for-microsoft-managed-desktop"></a>Microsoft Managed Desktop의 인쇄 리소스 준비

Microsoft Managed Desktop에 등록할 준비가 되면 인쇄 요구 사항을 평가하고 환경에 적합한 방법을 결정해야 합니다. 다음 세 가지 옵션이 있습니다.
 
- Microsoft Managed Desktop 장치가 프린터를 쉽게 검색할 수 있도록 Microsoft 유니버설 인쇄 솔루션을 배포합니다. 자세한 내용은 유니버설 [인쇄를 참조하십시오.](https://docs.microsoft.com/universal-print/fundamentals/universal-print-whatis)
- 사용자 지정 PowerShell 스크립트를 사용하여 프린터를 직접 배포합니다. 로컬 프린터 설정 [섹션의](#set-up-local-printers) 단계를 따릅니다.
- Azure Active Directory 도메인에 가입된 Windows 10 장치와 호환되는 Microsoft가 아닌 클라우드 인쇄 솔루션을 사용하세요. 솔루션은 Microsoft Managed Desktop의 소프트웨어 요구 사항을 충족해야 합니다. 자세한 내용은 Microsoft Managed Desktop 앱 요구 [사항을 참조하세요.](../service-description/mmd-app-requirements.md)
 
모든 경우에 프린터 드라이버를 Microsoft Update 또는 Microsoft Store에서 사용할 수 없는 경우 프린터 드라이버를 직접 얻어 Microsoft Intune을 사용하여 Microsoft Managed Desktop 디바이스에 배포하기 위해 패키지로 제공해야 합니다. 자세한 내용은 [Intune 독립 실행형 - Win32 앱 관리를 참조하세요.](https://docs.microsoft.com/mem/intune/apps/apps-win32-app-management)

## <a name="set-up-local-printers"></a>로컬 프린터 설정

사용자 지정 PowerShell 스크립트를 사용하여 프린터를 배포하기로 결정하고 인쇄 리소스를 준비한 경우 다음 단계에 따라 공유 프린터를 배포합니다.

1.  Microsoft Managed Desktop 포털로 이동합니다.
2.  다음 세부 정보를  제공하는 요청  레이블이 붙은 프린터 배포를 관리 포털의 지원 > 지원 요청 섹션에 제출합니다.
    - Microsoft Managed Desktop 장치에 배포해야 하는 공유 프린터 위치에 대한 모든 UNC 경로
    - 이러한 공유 프린터에 액세스해야 하는 사용자 그룹
3.  관리 포털을 사용하여 요청이 완료된 경우를 알 수 있습니다. 처음에는 테스트 배포 그룹의 장치에만 구성을 배포합니다.
4.  구성이 예상처럼 작동하는지 테스트하고 확인해야 합니다. 테스트가 완료된 경우 지원 요청의 토론 탭을 사용하여 회신합니다. 
5.  그런 다음 구성을 다른 배포 그룹에 배포합니다.
