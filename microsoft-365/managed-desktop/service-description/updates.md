---
title: Microsoft Managed Desktop에서 업데이트를 처리 하는 방법
description: Microsoft Managed Desktop을 최신 상태로 유지 하는 것은 속도와 안정성의 조화입니다.
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 설명서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 01/09/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 7709779c73293a4523bf3cc381d0b59f7fbca325
ms.sourcegitcommit: d137cb1bd67a79d8af84357dc156824830d35aa7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/29/2019
ms.locfileid: "35924871"
---
# <a name="how-updates-are-handled-in-microsoft-managed-desktop"></a>Microsoft Managed Desktop에서 업데이트를 처리 하는 방법


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/update-rings); do not delete.-->

<!--Update management -->

Microsoft Managed Desktop은 모든 장치를 최신 클라우드 기반 인프라에 연결 합니다. Windows, Office, 드라이버, 펌웨어 및 Microsoft Store for Business 응용 프로그램 업데이트를 최신 상태로 유지 하려면 속도와 안정성을 조화 해야 합니다. 배포 그룹은 OS 및 정책이 안전한 방식으로 롤아웃 되도록 하는 데 사용 됩니다. 

Microsoft에서 릴리스된 업데이트는 누적 되며 품질 또는 기능 업데이트로 분류 됩니다.
자세한 내용은 [Windows update For Business: update types](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#update-types)를 참조 하십시오. 

## <a name="update-groups"></a>업데이트 그룹

Microsoft Managed Desktop은 다음과 같은 네 가지 Azure AD 그룹을 사용 하 여 업데이트를 관리 합니다.

- **Test**: Microsoft Managed Desktop policy 변경 사항, OS 업데이트, 기능 업데이트 및 테 넌 트로 푸시된 기타 변경 내용을 확인 하는 데 사용 됩니다. 최종 사용자가 테스트 그룹에 있는 경우는 안 됩니다. 테스트 그룹은 설정 된 Sla 및 최종 사용자 지원에서 제외 됩니다. 이 그룹은 새 정책 또는 OS 변경 사항과 함께 응용 프로그램의 호환성을 검사 하는 데 사용할 수 있습니다.  
- **첫 번째**: 시험판 업데이트를 적용할 수 있는 초기 소프트웨어 사용권 및 장치를 포함 합니다. 테스트 링에서 테스트 중에 다루지 않았던 시나리오가 있는 경우이 그룹의 장치가 중단 될 수 있습니다.
- **Fast**: 안정성 보다 빠른 우선 순위를 갖습니다. 광범위 한 그룹에 제공 되기 전에 품질 문제를 검색 하는 데 유용 합니다. 이 그룹은 다음 유효성 검사 계층의 역할을 하지만 일반적으로 테스트 및 첫째 그룹 보다 더 안정적입니다. 
- **광범위**: 기능 및 품질 업데이트를 사용할 수 있는 마지막 그룹입니다. 이 그룹에는 테 넌 트에 있는 대다수의 사용자가 포함 되므로 배포 속도에 따른 안정성에 우위를 갖습니다. 환경이 안정화 될 때까지 앱 테스트를 여기서 수행 해야 합니다. 

이러한 배포 그룹의 역할 및 책임에 대 한 자세한 내용은 [Microsoft Managed Desktop roles and 의무](../intro/roles-and-responsibilities.md) 를 참조 하십시오.

업데이트 배포 작동 방식:
- Microsoft Managed Desktop은 아래 지정 된 일정에 따라 새로운 기능 또는 품질 업데이트를 배포 합니다.
- 배포 중에 Microsoft Managed Desktop은 진단 데이터 신호 및 최종 사용자 지원 시스템을 기반으로 하는 실패 또는 장애의 징후를 모니터링 합니다. 검색 된 경우 모든 현재 및 미래의 그룹에 대 한 배포가 즉시 일시 중지 됩니다.
    - 예: 첫 번째 그룹에 품질 업데이트를 배포 하는 동안 문제가 발견 되 면 문제가 해결 될 때까지 처음, 빠른 및 광범위 하 게 업데이트를 일시 중지 합니다.
    - Microsoft Managed Desktop IT 관리자 포털에 티켓을 저장 하 여 호환성 문제를 보고할 수 있습니다.
- 기능 및 품질 업데이트는 독립적으로 일시 중지 됩니다. 일시 중지가 기본적으로 35 일 동안 적용 되지만 문제가 재구성 되는지 여부에 따라 줄이거나 연장할 수 있습니다.
- 그룹을 일시 중지 하 고 나면 아래 일정에 따라 배포가 다시 시작 됩니다.
- 이 배포 프로세스는 기능 및 품질 업데이트 둘 다에 적용 되지만 timeline은 각각에 따라 다릅니다.

<table>
<tr><th colspan="5">배포 설정 업데이트</th></tr>
<tr><th>업데이트 유형</th><th>테스트</th><th>가장</th><th>신속한</th><th>폭</th></tr>
<tr><td>운영 체제에 대 한 품질 업데이트</td><td>0 일</td><td>0 일</td><td>0 일</td><td>3 일</td></tr>
<tr><td>운영 체제용 기능 업데이트</td><td>0 일</td><td>30일</td><td>60일</td><td>90일</td></tr>
<tr><td>드라이버/펌웨어</td><td colspan="4">품질 업데이트 일정을 따릅니다.</td></tr>
<tr><td>바이러스 백신 정의</td><td colspan="4">각 검색에서 업데이트</td></tr>
</table>

>[!NOTE]
>이러한 지연 기간은 모든 사용자에 대 한 높은 보안 및 성능 표준을 보장 하도록 의도적으로 설계 되었습니다. 또한 모든 Microsoft Managed Desktop 장치에서 수집 된 데이터와 업데이트의 다양 한 범위 및 영향을 기반으로 하는 Microsoft Managed Desktop은 ad의 모든 배포 그룹에 대해 위의 지연 기간 길이를 수정 하는 유연성을 예비 합니다. ad-hoc을 기반으로 합니다.
>
>Microsoft Managed Desktop은 각 Windows 기능 릴리스와 독립적으로 평가 하 여 관리 되는 테 넌 트에 대 한 필요 및 유용성을 평가 합니다. 따라서 Microsoft Managed Desktop이 모든 Windows 기능 업데이트를 배포할 수도 있고 배포 하지 않을 수도 있습니다. 

## <a name="windows-insider-program"></a>Windows 참가자 프로그램

Microsoft Managed Desktop은 Windows 참가자 프로그램의 일부인 장치를 지원 하지 않습니다. Windows 참가자 프로그램은 시험판 Windows 소프트웨어의 유효성을 검사 하는 데 사용 되며 업무상 중요 하지 않은 장치를 위한 것입니다. 이는 중요 한 Microsoft 이니셔티브 이지만 프로덕션 환경에서는 광범위 한 배포를 위한 것이 아닙니다. 

Windows 참가자 빌드가 포함 된 모든 장치는 테스트 그룹에 포함 될 수 있으며, Sla (서비스 수준 계약) 및 Microsoft Managed Desktop의 최종 사용자 지원에서 제외 됩니다.

## <a name="bandwidth-management"></a>대역폭 관리

모든 운영 체제 및 드라이버 업데이트에 대해 배달 최적화가 사용 됩니다. 회사 네트워크 내의 피어에서 업데이트를 검색 하 여 Windows Update service에서 다운로드 크기를 최소화 합니다.


