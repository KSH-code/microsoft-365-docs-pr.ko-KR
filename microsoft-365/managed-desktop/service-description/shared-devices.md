---
title: '공유 디바이스:'
description: 공유 장치 모드 사용 방법 및 사용 방법
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: c369f070d7dd166ede57bd51d6df4c5dcbba1d51
ms.sourcegitcommit: da11ffdf7a09490313dfc603355799f80b0c60f9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/26/2021
ms.locfileid: "60588531"
---
# <a name="shared-devices"></a>공유 디바이스:

Microsoft Managed Desktop 를 사용하면 에서 제공하는 공유 장치 모드와 유사한 "공유 장치 모드"로 장치를 등록할 [Microsoft Intune.](/mem/intune/configuration/shared-user-device-settings) 이 모드의 장치는 사용자가 단일 책상에 연결되지 않은 경우와 자주 변경되는 장치( 일반적으로 은행 직원 또는 간호 직원과 같은 일선 직원)에 최적화되어 있습니다. 이 모드에서 디바이스에 Microsoft Managed Desktop 프로필을 적용할 수 있습니다. [](profiles.md) 이 모드로 등록된 디바이스에는 몇 가지 중요한 차이점이 있습니다.

- [디바이스 저장소는](#device-storage) 공유 사용자에 맞게 최적화되어 있습니다.
- [비활성 계정이](#deletion-of-inactive-accounts) 삭제됩니다.
- [게스트 계정은](#guest-accounts) 기본적으로 지원되지 않습니다.
- [Microsoft 365 라이선싱용](#microsoft-365-apps-for-enterprise) 응용 프로그램은 공유 장치에 최적화되어 있습니다.

Microsoft Managed Desktop 등록 시점에 공유 디바이스 모드를 사용하기로 선택하기 때문에 나중에 이 모드에서 변경하려면 등록을 해지했다가 다시 등록해야 합니다.

## <a name="when-to-use-shared-device-mode"></a>공유 장치 모드를 사용하는 경우

사용자가 장치를 자주 변경하는 상황

예를 들어 은행 출장자는 한 위치에서 저축을 관리하지만 고객을 지원하기 위해 백 사무실로 이동할 수 있습니다. 이러한 각 위치에서 장치는 서로 다른 응용 프로그램을 실행하며, 여러 사용자가 사용하나 이러한 작업에 최적화되어 있습니다.

간호사는 일반적으로 환자와 상호 작용할 때 회의실과 사무실 간에 이동하여 사무실의 작업실에 로그인할 수 있지만 원격 데스크톱에 연결하고 메모를 작성하여 다른 환자와 함께 다른 방에서 반복하기만 합니다.

## <a name="when-not-to-use-shared-device-mode"></a>공유 장치 모드를 사용하지 않는 경우

다음 상황에서는 공유 장치 모드를 선택하지 않는 것이 좋습니다.

- 사용자의 파일을 클라우드가 아닌 로컬에 저장해야 하는 경우
- 사용자 환경이 디바이스의 다른 사용자에 대해 달라야 하는 경우
- 각 사용자가 필요로 하는 응용 프로그램 집합이 크게 다른 경우

## <a name="enroll-new-devices-in-shared-device-mode"></a>공유 장치 모드로 새 장치 등록

사용자 또는 파트너가 등록을 처리하는지 여부에 관계 없는 경우 공유 장치 모드를 사용할 수 있습니다.

장치를 직접 등록하는 경우 직접 새 [](../get-started/register-devices-self.md)장치 등록의 단계를 수행한 다음 최신 작업 공간 **장치-공유** 장치 모드 그룹에 추가합니다. 

> [!WARNING]
> 기존 Microsoft Managed Desktop 장치를 이 그룹에 추가하여 공유 장치 모드로 변환하지 않습니다. 적용된 정책으로 인해 파일이 영구적으로 OneDrive 수 있습니다.

파트너 등록 장치를 사용 중이면 다음 표에 나와 있는 [단계에](../get-started/register-devices-partner.md)따라 디바이스를 등록하지만 **-Shared를** 그룹 태그에 추가합니다.


|장치 프로필  |그룹 태그(표준 모드)  |그룹 태그(공유 장치 모드)  |
|---------|---------|---------|
|중요한 날짜 | Microsoft365Managed_SensitiveData        |  Microsoft365Managed_SensitiveData-Shared       |
| 파워 사용자         | Microsoft365Managed_PowerUser        | 지원되지 않음        |
|Standard     | Microsoft365Managed_Standard        | Microsoft365Managed_Standard-Shared  |

## <a name="consequences-of-shared-device-mode"></a>공유 장치 모드의 결과

### <a name="device-storage"></a>장치 저장소

공유 장치의 사용자는 데이터를 클라우드에 백업해야 다른 장치로 데이터를 팔로우할 수 있습니다. 디바이스를 공유 장치 모드로 등록한 후 필요한 파일 OneDrive 폴더 [](https://support.microsoft.com/office/save-disk-space-with-onedrive-files-on-demand-for-windows-10-0e6860d3-d9f3-4971-b321-7092438fb38e#:~:text=%20Turn%20on%20Files%20On-Demand%20%201%20Make,files%20as%20you%20use%20them%20box.%20More%20) 리디렉션 기능을 사용하도록 [설정해야](/onedrive/redirect-known-folders) 합니다. 이 방법은 각 사용자 프로필이 장치 저장소에 미치는 영향을 최소화합니다. 공유 장치 모드의 장치는 사용되지 않는 디스크 공간이 25% 미만으로 떨어질 경우 사용자 프로필을 자동으로 삭제합니다. 이 활동은 저장소가 매우 제한되지 않는 한 디바이스의 현지 시간 자정에 예약됩니다.

Microsoft Managed Desktop [SharedPC](/mem/intune/configuration/shared-user-device-settings-windows) CSP를 사용하여 이러한 작업을 수행하기 때문에 이러한 CSP를 직접 사용하지 마십시오.

> [!IMPORTANT]
> 사용자가 큰 파일을 다운로드한 후 사용자가 로그인하기 전에 파일에 녹색 확인 아이콘이 표시 한다고 사용자에게 교육합니다. 계정이 정리 작업의 일부로 삭제되고 파일이 OneDrive 영구적으로 손실됩니다.

### <a name="deletion-of-inactive-accounts"></a>비활성 계정의 지우기

공유 장치 모드는 30일 이상 로그인하지 않은 모든 계정을 제거합니다.

### <a name="guest-accounts"></a>게스트 계정

공유 장치 모드의 장치는 도메인에 가입된 계정만 허용합니다. 디바이스에 게스트 계정이 필요한 경우 변경 [](../working-with-managed-desktop/admin-support.md) 요청을 제출하여 사용하도록 요청할 수 있습니다.

### <a name="microsoft-365-apps-for-enterprise"></a>엔터프라이즈용 Microsoft 365 앱

[엔터프라이즈용 Microsoft 365 앱](/microsoft-365/managed-desktop/get-started/m365-apps) 일반적으로 특정 사용자가 5개의 장치에만 해당 앱을 동시에 설치할 수 있도록 허용합니다. 공유 디바이스 모드에서 앱은 제한에 계산되지 않습니다. 따라서 디바이스 간에 로밍하는 동안 사용할 수 있습니다. 배포 및 업데이트는 엔터프라이즈용 Microsoft 365 앱 작업을 합니다.

### <a name="device-profiles"></a>장치 프로필

공유 디바이스 모드에서는 특정 디바이스에 하나의 장치 [프로필만](profiles.md) 사용할 수 있습니다. 또한 Power 사용자 장치 프로필은 현재 공유 장치 모드에서 지원되지 않습니다.

### <a name="apps-and-policies-assigned-to-users"></a>사용자에게 할당된 앱 및 정책

공유 장치에서는 사용자 그룹이 아닌 장치 그룹에 관리하고 있는 앱 또는 정책을 할당해야 합니다. 이렇게 하면 각 사용자가 보다 일관된 환경을 사용할 수 있습니다. 예외는 [에 회사 포털.](#deploying-apps-with-company-portal)

## <a name="limitations-of-shared-device-mode"></a>공유 장치 모드의 제한 사항

### <a name="windows-hello"></a>Windows Hello

Windows Hello 사용하여 사용자 [PI를](/windows/security/identity-protection/hello-for-business/hello-faq)안전하게 캐시하여 사용자가 인증해야 하는 횟수를 최소화합니다. 그러나 Windows 디바이스에서 한 번만 스마트 카드를 10개 허용할 수 있습니다. 11번째 사용자가 처음 로그인하면 기존 계정 중 하나에서 스마트 카드가 손실됩니다. 로그인할 수 있지만 PIN은 캐시되지 않습니다.

### <a name="universal-print"></a>유니버설 인쇄

유니버설 인쇄가 공유 장치에 단일 사용자에 대한 프린터를 설치하면 해당 장치의 모든 사용자가 프린터를 사용할 수 있습니다. 공유 디바이스에서 사용자 간에 프린터를 격리할 수 있는 방법은 없습니다.

## <a name="limitations-of-shared-device-mode-in-the-public-preview-release"></a>공개 미리 보기 릴리스의 공유 장치 모드 제한 사항

### <a name="primary-user"></a>기본 사용자

각 Microsoft Intune 디바이스에는 Autopilot에서 디바이스를 설정할 때 할당되는 기본 사용자가 있습니다. 그러나 디바이스를 공유하는 경우 Intune을 사용하려면 기본 사용자를 제거해야 합니다.

> [!IMPORTANT]
> 공유 장치 모드가 공개 미리 보기에 있는 동안 Microsoft Endpoint Manager 관리 센터에 로그인하고 장치 모든 장치를 선택한 다음 속성 기본 사용자 제거를 선택한 다음 여기에 나열된 사용자를 삭제하여 기본 사용자를 제거해야 >   > 합니다.

### <a name="deploying-apps-with-company-portal"></a>사용자와 함께 앱 회사 포털
일부 앱은 모든 디바이스에 존재할 필요가 없는 것일 수 있으므로 사용자가 에서 필요한 앱만 설치하도록 [회사 포털.](/mem/intune/user-help/install-apps-cpapp-windows) Microsoft Managed Desktop 디바이스 회사 포털 디바이스에 대해 기본적으로 이 설정을 사용하지 않도록 설정됩니다. 사용하도록 회사 포털 변경 요청을 제출할 수 [](../working-with-managed-desktop/admin-support.md)있지만 이 공개 미리 보기에서 이 기능에 대한 몇 가지 제한 사항을 알고 있어야 합니다.

- 사용자가 앱을 사용할 수 있도록 회사 포털 Intune에서 해당 앱에 사용자 그룹을 할당한 다음 해당 사용자 그룹에 각 사용자를 추가합니다. [](/mem/intune/apps/apps-deploy)
- 디바이스에 기본 사용자를 사용할 [수 없습니다.](#primary-user)
- 사용자가 앱을 통해 설치한 앱을 제거하려면 회사 포털 디바이스의 모든 사용자에서 앱을 제거해야 합니다.

> [!CAUTION]
> 회사 포털 장치 그룹에 할당된 응용 프로그램을 사용할 수 없습니다. 

### <a name="redeployment-of-microsoft-365-apps-for-enterprise"></a>엔터프라이즈용 Microsoft 365 앱
공개 미리 보기 Microsoft 365 앱 다시 설치해야 하는 경우 사용자는 로컬 지원 담당자에게 문의하여 해당 디바이스에 에이전트 승강을 요청하고 엔터프라이즈용 Microsoft 365 앱 다시 설치해야 합니다.

### <a name="microsoft-teams"></a>Microsoft Teams
사용자가 처음으로 Teams 시작하면 앱을 업데이트하라는 메시지가 표시되면 앱을 사용할 수 있습니다. 사용자가 업데이트를 허용하면 Teams 백그라운드에서 자동으로 업데이트됩니다.



