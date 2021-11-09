---
title: 사용 권한의 & - 위협 및 취약성 관리
description: 사용자 위협 및 취약성 관리 시작하기 전에 관련 구성 및 사용 권한이 있는지 확인해야 합니다.
keywords: 위협 & 취약성 관리 사용 권한 선행 위협 및 취약성 관리, Microsoft Defender for Endpoint TVM 사용 권한 선행 취약성 관리
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: d3684d8b13020605fbca20e67093c28d3e782da2
ms.sourcegitcommit: e09ced3e3628bf2ccb84d205d9699483cbb4b3b0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/09/2021
ms.locfileid: "60881747"
---
# <a name="prerequisites--permissions---threat-and-vulnerability-management"></a>사용 권한의 & - 위협 및 취약성 관리

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**

- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)
- [위협 및 취약성 관리](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-portaloverview-abovefoldlink)

장치가 다음을 하는지 확인:

- 끝점용 Microsoft Defender에 온보딩

- 지원되는 [운영 체제 및 플랫폼 실행](tvm-supported-os.md)

- 취약성 평가 감지 비율을 높이기 위해 네트워크에 다음과 같은 필수 업데이트를 설치하고 배포합니다.

  > 릴리스 | 보안 업데이트 KB 번호 및 링크
  > :---|:---
  > Windows 10 버전 1709 | [KB4493441](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441) 및 [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)
  > Windows 10 버전 1803 | [KB4493464](https://support.microsoft.com/help/4493464) 및 [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)
  > Windows 10 버전 1809 | [KB 4516077](https://support.microsoft.com/help/4516077/windows-10-update-kb4516077)
  > Windows 10 버전 1903 | [KB 4512941](https://support.microsoft.com/help/4512941/windows-10-update-kb4512941)

- 보안 센터에서 [발견된 위협을](/mem/intune/fundamentals/what-is-intune) Microsoft Intune [Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection-configure) 수 있도록 위협 및 취약성 관리. Configuration Manager를 사용하는 경우 콘솔을 최신 버전으로 업데이트합니다.

  > [!NOTE]
  > Intune 연결을 사용하도록 설정한 경우 수정 요청을 만들 때 Intune 보안 작업을 만드는 옵션이 제공됩니다. 연결이 설정되어 있지 않은 경우 이 옵션이 나타나지 않습니다.

- 장치 페이지에서 볼 수 있는 보안 권장 설정 하나 이상

- 태그가 지정되거나 공동 관리로 표시

## <a name="relevant-permission-options"></a>관련 권한 옵션

1. 보안 관리자 Microsoft 365 Defender 전역 관리자 역할이 할당된 계정을 사용하여 Microsoft 365 Defender 포털에 로그인합니다.
2. 탐색 창에서 역할 **설정 > 끝점 > 선택합니다.**

자세한 내용은 역할 기반 액세스 제어에 대한 역할 만들기 [및 관리를 참조하세요.](user-roles.md)

### <a name="view-data"></a>데이터 보기

- **보안 작업** - 포털의 모든 보안 작업 데이터 보기
- **위협 및 취약성 관리** - 포털에서 위협 및 취약성 관리 데이터 보기

### <a name="active-remediation-actions"></a>활성 수정 작업

- **보안 작업** - 대응 조치 수행, 보류 중인 수정 작업 승인 또는 해지, 자동화 및 표시기를 위한 허용/차단 목록 관리
- **위협 및 취약성 관리 - 예외** 처리 - 새 예외 만들기 및 활성 예외 관리
- **위협 및 취약성 관리 -** 수정 처리 - 새 수정 요청을 제출하고, 티켓을 만들고, 기존 수정 활동을 관리합니다.

자세한 내용은 [RBAC 사용 권한 옵션을 참조하세요.](user-roles.md#permission-options)

## <a name="related-articles"></a>관련 문서

- [위협 및 취약성 관리 개요](next-gen-threat-and-vuln-mgt.md)
- [지원되는 운영 체제 및 플랫폼](tvm-supported-os.md)
- [장치 값 할당](tvm-assign-device-value.md)
- [위협 및 취약성 관리 대시보드](tvm-dashboard-insights.md)

