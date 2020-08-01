---
title: Microsoft Managed Desktop의 인쇄 리소스 준비
description: 인쇄 작업을 원활 하 게 하기 위한 중요 한 단계
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: 1588a2c91bcbe0bd381acb6be4f9bd5562810860
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2020
ms.locfileid: "46530250"
---
# <a name="prepare-printing-resources-for-microsoft-managed-desktop"></a>Microsoft Managed Desktop의 인쇄 리소스 준비

Microsoft Managed Desktop에서 등록할 준비가 되 면 인쇄 요구 사항을 평가 하 고 사용자 환경에 적합 한 접근 방식을 결정 해야 합니다. 다음 세 가지 옵션을 사용할 수 있습니다.
 
- Microsoft 하이브리드 클라우드 인쇄 솔루션을 배포 하 여 마이크로소프트의 관리 되는 데스크톱 장치가 프린터를 쉽게 검색할 수 있도록 합니다. 자세한 내용은 [Windows Server 하이브리드 클라우드 인쇄 배포](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy)를 참조 하세요.
- 사용자 지정 PowerShell 스크립트를 사용 하 여 프린터를 직접 배포 합니다. 이 작업을 수행 하려면 [로컬 프린터 설정](#set-up-local-printers) 섹션에 나와 있는 단계를 수행 합니다.
- Azure Active Directory 도메인에 가입 된 Windows 10 장치와 호환 되는 타사 클라우드 인쇄 솔루션을 사용 합니다. 이 솔루션은 Microsoft Managed Desktop의 소프트웨어 요구 사항을 충족 해야 합니다. 자세한 내용은 [Microsoft Managed Desktop app 요구 사항을](../service-description/mmd-app-requirements.md)참조 하세요.
 
Microsoft 업데이트나 Microsoft Store에서 사용할 수 없는 프린터 드라이버를 사용 하는 경우에는 사용자를 직접 구입 하 여 microsoft Intune을 사용 하 여 Microsoft Managed Desktop devices 배포를 위해 패키지화 되도록 해야 합니다. 자세한 내용은 [Intune 독립 실행형-Win32 앱 관리](https://docs.microsoft.com/mem/intune/apps/apps-win32-app-management) 를 참조 하세요.

## <a name="set-up-local-printers"></a>로컬 프린터 설정

사용자 지정 PowerShell 스크립트를 사용 하 여 프린터를 배포 하기로 결정 하 고 인쇄 리소스를 준비한 후에는 다음 단계를 수행 하 여 공유 프린터를 배포 해야 합니다.

1.  Microsoft Managed Desktop 포털로 이동 합니다.
2.  다음 세부 정보를 제공 하 여 관리 포털의 **지원 > 지원 요청** 섹션에서 *프린터 배포* 라는 요청을 제출 합니다.
    - Microsoft Managed Desktop 장치용으로 배포 해야 하는 공유 프린터 위치의 모든 UNC 경로
    - 이러한 공유 프린터에 액세스 해야 하는 사용자 그룹
3.  관리자 포털을 사용 하면 요청이 완료 된 시기를 알 수 있습니다. 처음에는 테스트 배포 그룹의 장치에만 구성을 배포 합니다.
4.  구성이 예상 대로 작동 하는지 여부를 테스트 하 고 확인 해야 합니다. 지원 요청의 **토론** 탭을 사용 하 여 회신 하 여 테스트를 완료 한 시기를 알려주세요.
5.  그런 다음 구성을 다른 배포 그룹에 배포 합니다.
