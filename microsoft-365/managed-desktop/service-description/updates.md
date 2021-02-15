---
title: Microsoft Managed Desktop에서 업데이트 처리 방법
description: Microsoft Managed Desktop을 최신으로 유지하는 것은 속도와 안정성의 균형을 유지하는 것입니다.
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 4d8de363cc9111fade719fdf5384519d1236f431
ms.sourcegitcommit: 05657b39eaafc0503b01c6adcc5d8a5e615dc02c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/27/2021
ms.locfileid: "50031342"
---
# <a name="how-updates-are-handled-in-microsoft-managed-desktop"></a>Microsoft Managed Desktop에서 업데이트 처리 방법


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/update-rings); do not delete.-->

<!--Update management -->

Microsoft Managed Desktop은 모든 장치를 최신 클라우드 기반 인프라에 연결합니다. Windows, Office, 드라이버, 펌웨어 및 비즈니스용 Microsoft Store 응용 프로그램을 최신으로 유지하는 것은 속도와 안정성의 균형입니다. 배포 그룹은 운영 체제 업데이트 및 정책이 안전한 방식으로 롤아웃되도록 하는 데 사용됩니다. 자세한 내용은 [Microsoft Managed Desktop Change and Release Process 비디오를 참조하세요.](https://www.microsoft.com/videoplayer/embed/RE4mWqP)

Microsoft에서 릴리스한 업데이트는 누적되어 있으며 품질 또는 기능 업데이트로 분류됩니다.
자세한 내용은 [비즈니스용 Windows 업데이트: 업데이트 형식을 참조하세요.](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#update-types) 

## <a name="update-groups"></a>그룹 업데이트

Microsoft Managed Desktop은 4개의 Azure AD 그룹을 사용하여 업데이트를 관리합니다.

- **테스트:** Microsoft Managed Desktop 정책 변경, 운영 체제 업데이트, 기능 업데이트 및 테넌트에 푸시된 기타 변경 내용의 유효성을 검사하는 데 사용됩니다. 테스트 그룹에 배치된 사용자는 없습니다. 테스트 그룹은 확립된 서비스 수준 계약 및 사용자 지원에서 제외됩니다. 이 그룹은 새 정책 또는 운영 체제 변경과 응용 프로그램의 호환성을 검사하는 데 사용할 수 있습니다.  
- **첫** 번째: 사전 릴리스 업데이트가 적용될 수 있는 초기 소프트웨어 채택자 및 장치를 포함 테스트 링에서 테스트하는 동안 다루지 않은 시나리오가 있는 경우 이 그룹의 장치가 정전될 수 있습니다.
- **빠른** 속도: 안정성보다 속도 우선 순위를 지정합니다. 광범위 그룹에 제공되기 전에 품질 문제를 감지하는 데 유용합니다. 이 그룹은 다음 유효성 검사 계층으로 사용되지만 일반적으로 Test 및 First 그룹보다 안정적입니다. 
- **광범위**: 기능 및 품질 업데이트를 사용할 수 있는 마지막 그룹입니다. 이 그룹은 테넌트의 대부분의 사용자를 포함하므로 배포 속도보다 안정성을 선호합니다. 환경이 가장 안정적이기 위해 여기에서 앱 테스트를 완료해야 합니다. 

### <a name="moving-devices-between-update-groups"></a>업데이트 그룹 간에 장치 이동
일부 장치에서 마지막으로 업데이트를 받게 하려는 장치와 먼저 이동하려는 다른 장치를 원할 수 있습니다. 이러한 장치를 적절한 업데이트 그룹으로 이동하기 위해 [관리자](https://docs.microsoft.com/microsoft-365/managed-desktop/working-with-managed-desktop/admin-support?view=o365-worldwide) 지원 요청을 제출하고 디바이스를 자동으로 이동합니다. 

> [!NOTE]
> 사용자를 다른 업데이트 그룹으로 이동해야 하는 경우 지원 요청을 제출합니다. 업데이트 그룹 간에 장치를 직접 이동하지 마십시오. 장치를 잘못 이동하면 심각한 결과가 발생할 수 있습니다. 장치가 예기치 않게 업데이트될 수 있으며 정책이 충돌하여 장치 구성이 변경될 수 있습니다.

이러한 배포 그룹 내의 역할 및 책임에 대한 자세한 내용은 [Microsoft Managed Desktop Roles and responsibilities을 참조하세요.](../intro/roles-and-responsibilities.md)

### <a name="using-microsoft-managed-desktop-update-groups"></a>Microsoft Managed Desktop 업데이트 그룹 사용 
앱 배포와 같이 관리되는 서비스의 일부가 있습니다. 관리되는 모든 장치를 대상으로 지정하는 데 필요한 경우도 있습니다. 이러한 경우 업데이트 그룹을 사용하여 해당 그룹의 구성원 자격을 추가, 제거 또는 변경할 수 없다는 이해를 통해 해당 사용자에게 도달하는 것이 합리적입니다. 

## <a name="how-update-deployment-works"></a>업데이트 배포의 작동 방식:
1. Microsoft Managed Desktop은 다음 표에 지정된 일정에 따라 새 기능 또는 품질 업데이트를 배포합니다.
2. 배포 중에 Microsoft Managed Desktop은 진단 데이터 및 사용자 지원 시스템을 기반으로 오류 또는 중단의 징후를 모니터링합니다. 검색된 경우 모든 현재 및 향후 그룹에 대한 배포를 즉시 일시 중지합니다.
    - 예: 첫 번째 그룹에 품질 업데이트를 배포하는 동안 문제가 발견되면 문제가 해결될 때까지 배포를 First, Fast 및 Broad로 업데이트합니다.
    - Microsoft Managed Desktop Admin 포털에서 티켓을 신고하여 호환성 문제를 보고할 수 있습니다.
    - 기능 및 품질 업데이트는 독립적으로 일시 중지됩니다. 일시 중지는 기본적으로 35일 동안 적용되지만 문제의 수정 여부에 따라 축소 또는 확장될 수 있습니다.
3. 그룹이 일시 중지되지 않은 경우 테이블의 일정에 따라 배포가 다시 시작됩니다.

이 배포 프로세스는 기능 업데이트와 품질 업데이트 모두에 적용 지만 시간 표시 막대는 각각에 따라 다릅니다.




<table>
    <tr><th colspan="5">배포 설정 업데이트</th></tr>
    <tr><th>업데이트 유형</th><th>테스트</th><th>첫 번째</th><th>빠르기</th><th>광범위</th></tr>
    <tr><td>운영 체제의 품질 업데이트</td><td>0일</td><td>0일</td><td>0일</td><td>3일</td></tr>
    <tr><td>운영 체제에 대한 기능 업데이트</td><td>0일</td><td>30일</td><td>60일</td><td>90일</td></tr>
    <tr><td>드라이버/펌웨어</td><td colspan="4">품질 업데이트 일정을 따르는 경우</td></tr>
    <tr><td>바이러스 백신 정의</td><td colspan="4">각 검사로 업데이트</td></tr>
    <tr><td>엔터프라이즈용 Microsoft 365 앱</td><td colspan="4"><a href="https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/m365-apps#updates-to-microsoft-365-apps">자세한 정보</a></td></tr>
    <tr><td>Microsoft Edge</td><td colspan="4"><a href="https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/edge-browser-app#updates-to-microsoft-edge">자세한 정보</a></td></tr>
    <tr><td>Microsoft Teams</td><td colspan="4"><a href="https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/teams#updates">자세한 정보</a></td></tr>
</table>

>[!NOTE]
>이러한 지연 기간은 모든 사용자에 대해 높은 보안 및 성능 표준을 보장하도록 의도적으로 디자인되었습니다. 또한 모든 Microsoft Managed Desktop 장치에서 수집된 데이터와 업데이트의 다양한 범위 및 영향에 따라 Microsoft Managed Desktop은 임의 및 모든 배포 그룹에 대해 위 지연 기간의 기간을 임의로 수정할 수 있습니다.
>
>Microsoft Managed Desktop은 각 Windows 기능 릴리스에 대한 독립적인 평가를 수행하여 관리되는 테넌트에 대한 유용성 및 해당 기능을 평가합니다. 따라서 Microsoft Managed Desktop은 일부 Windows 기능 업데이트를 배포하거나 배포하지 않을 수 있습니다. 

## <a name="windows-insider-program"></a>Windows 참가자 프로그램

Microsoft Managed Desktop은 Windows Insider 프로그램에 속하는 디바이스를 지원하지 않습니다. Windows Insider 프로그램은 사전 릴리스 Windows 소프트웨어의 유효성을 검사하는 데 사용하며 중요하지 않은 디바이스를 위한 것입니다. Microsoft는 중요한 Microsoft 이니셔티브지만 프로덕션 환경에서 광범위한 배포를 위한 것이 아닙니다. 

Windows Insider 빌드로 찾은 디바이스는 테스트 그룹에 추가될 수 있으며 Microsoft Managed Desktop의 업데이트 서비스 수준 계약 및 사용자 지원에서 제외됩니다.

## <a name="bandwidth-management"></a>대역폭 관리

모든 운영 [체제 및](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization) 드라이버 업데이트에 배달 최적화를 사용 합니다. 이렇게 하면 회사 네트워크 내의 피어로부터 업데이트를 검색하여 Windows 업데이트 서비스에서 다운로드 크기를 최소화할 수 있습니다.

