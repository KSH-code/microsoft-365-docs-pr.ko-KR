---
title: 서비스 변경 및 통신
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 설명서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 00d1cb409364c017585c6afcd10a236ecbcdc3a0
ms.sourcegitcommit: 53148fc3663bdcfa9605684317785cb19f37e141
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2019
ms.locfileid: "37697905"
---
# <a name="service-changes-and-communication"></a>서비스 변경 및 통신

Microsoft에서 Microsoft Managed Desktop이 작동 하는 방식에 대 한 세부 정보를 변경 해야 할 수도 있습니다. 마찬가지로 서비스에도 영향을 주는 변경 작업을 수행 해야 할 수도 있습니다. 이러한 변경은 주요 정도에 따라 다르게 처리 됩니다. 이 항목에서는 주요 변경 사항을 정의 하 고,이를 처리 하는 방법과 기타 변경 사항에 대해 설명 합니다.



## <a name="changes-made-by-microsoft"></a>Microsoft에서 변경한 내용

작업을 수행 해야 하는 주요 변경 사항에 대 한 최소 30 일 이상까지 통보 됩니다. Microsoft Managed Desktop Administration portal 메시징 시스템을 사용 하 여 알려 드리겠습니다.

**주요 변경 내용은** 다음 영역에 영향을 줄 수 있습니다.
- 일일 생산성에 영향을 주는 변경 사항
- 사용자 지정 된 기능 및 응용 프로그램에 대 한 변경 내용
- 가시 용량 증가 또는 감소
- 사용자의 혼란을 야기 하거나 헬프데스크 프로세스 및 참조 자료 나 Url에서 변경 될 수 있는 제품 브랜딩 변경 사항
- 문제를 방지 하거나 해결 하는 작업을 제외 하 고 일상적인 작업을 위해 서비스에서 필요한 권한 이상의 권한이 필요한 변경 내용
- 데이터가 저장 되는 위치에 대 한 변경 내용
- 서비스 범위에 새 구성 요소 서비스 또는 응용 프로그램 추가
- 서비스 범위에서 구성 요소 서비스 또는 응용 프로그램 제거
- 서비스에 새 기능 추가

> [!NOTE]
> 30 일 알림 정책에서 제외 되는 인시던트 또는 보안 문제를 완화 하기 위해 변경 작업을 수행 해야 할 수 있습니다.

사용자 환경, 보안, 안정성 및 보고를 개선 하기 위해 정기적으로 서비스에 대 한 다른 변경을 수행 합니다. 이러한 변경의 몇 가지 예는 다음과 같습니다.

- Windows 및 Office 업데이트 설치
- 장치에 적용 된 보안 기준에 대 한 업데이트
- [Supported devices](device-list.md)

설정 된 채널을 사용 하 여 이러한 변경 내용을 전달 합니다. 변경 사항에 대 한 질문이 있는 경우 Microsoft Managed Desktop [Operations 팀](../working-with-managed-desktop/admin-support.md)에 문의 하세요. 서비스에 대 한 변경 내용은 필요에 따라 [변경 내역](../change-history-managed-desktop.md)에도 문서화 됩니다.

Microsoft Managed Desktop 변경 및 통신은 다음과 같은 두 가지 Microsoft 정책에 따라 제어 됩니다.
- [최신 수명 주기 정책](https://support.microsoft.com/help/30881/modern-lifecycle-policy)
- [Microsoft 365 변경 통신 정책](https://docs.microsoft.com/office365/admin/manage/message-center?redirectSourcePath=%252fen-us%252farticle%252fMessage-center-in-Office-365-38FB3333-BFCC-4340-A37B-DEDA509C2093&view=o365-worldwide)

## <a name="changes-you-make"></a>변경한 내용

사용자 환경에서 수행할 수 있는 몇 가지 변경 사항이 Microsoft Managed Desktop에 영향을 줄 수 있습니다. 이러한 주요 변경 사항에 대 한 자세한 내용은 Microsoft Managed Desktop Admin 포털에서 서비스 요청을 제출 하 여 30 일 이상 공지를 제공 해 주시기 바랍니다. 지침은 [Microsoft Managed Desktop에 대 한 관리자 지원을](../working-with-managed-desktop/admin-support.md) 참조 하십시오. 이렇게 하면 중단 되지 않도록 적절 한 시간에 변경을 계획 하 고 준비할 수 있습니다.

주요 변경 내용은 다음 영역에 영향을 줄 수 있습니다.

- Id 시스템 및 그룹
- 네트워킹 및 네트워크 제어 (예: 방화벽, 프록시 또는 캐싱, VPN 시스템)
- 클라우드 서비스 구성에 액세스 하기 위한 컨트롤
- Id 또는 네트워크 서비스 보안 유지에 사용 되는 사용자 또는 장치 인증서
- 서비스와 상호 작용 하는 관리 시스템
- 서비스와 상호 작용 하는 보안 시스템 또는 에이전트
- 서비스에 연결 된 Microsoft 365 클라우드 서비스의 구성

이러한 변경 내용은 방해가 되지 않을 수 있으므로 사전에 대 한 정보를 미리 알릴 필요가 없습니다.

- 고아 개체 정리
- 서비스에서 사용자 추가 또는 제거
- Microsoft Managed Desktop의 배달에 재료가 영향을 받지 않는 시스템 구성
- VPN 또는 프록시 응용 프로그램을 제외 하 고 응용 프로그램 버전 업데이트


