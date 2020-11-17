---
title: Autopilot 및 등록 상태 페이지의 첫 실행 환경
description: ESP 환경을 배포 하는 방법, 사용 된 설정 및 구성 변경 사항
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 5e2340c7c0bf00165bb43740d3d095b5b0402fc0
ms.sourcegitcommit: 0402d3275632fceda9137b6abc3ce48c8020172a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2020
ms.locfileid: "49126628"
---
# <a name="first-run-experience-with-autopilot-and-the-enrollment-status-page"></a>Autopilot 및 등록 상태 페이지의 첫 실행 환경

Microsoft Managed Desktop은 [Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot) 와 Microsoft Intune의 [등록 상태 페이지 (ESP)](https://docs.microsoft.com/windows/deployment/windows-autopilot/enrollment-status) 를 모두 사용 하 여 사용자에 게 최적의 첫 실행 환경을 제공 합니다.

등록 상태 페이지가 현재 공개 미리 보기에 있습니다.

## <a name="initial-deployment"></a>초기 배포

ESP 환경을 제공 하려면 Microsoft Managed Desktop service에서 장치를 등록 해야 합니다. 등록에 대 한 자세한 내용은 [직접 새 장치 등록](../get-started/register-devices-self.md) 또는 [파트너가 장치를 등록 하는 단계](../get-started/register-devices-partner.md)를 참조 하세요.

장치가 서비스에 등록 되 면 [관리 포털](https://portal.azure.com/)을 통해 지원 티켓을 저장 하 여 Microsoft Managed Desktop 장치에 대해 ESP를 사용 하도록 설정할 수 있습니다. 먼저 티켓을 파일 할 때 ESP 구성을 테스트 그룹에 배포 합니다. 이 파일은 24 시간 마다 처음, 빠르고, 광범위 한 다른 후속 배포 그룹에 배포 됩니다. 배포를 일시 중지 하려면 보류할 작업을 요청 하는 다른 티켓을 파일에 저장 합니다.

## <a name="autopilot-profile-settings"></a>Autopilot 프로필 설정

Microsoft Managed Desktop은 사용자 장치에 사용 되는 Autopilot 프로필에서 이러한 설정을 사용 합니다.


|설정  |값  |
|---------|---------|
|배포 모드 |  사용자 제어       |
|Azure AD에 연결     |  Azure AD 가입 됨       |
|언어 (지역)     | 운영 체제 기본값        |
|자동으로 키보드 구성     | 아니요        |
|Microsoft 소프트웨어 사용 조건     |  숨겨지고       |
|개인 정보 설정     | 숨겨지고        |
|계정 변경 옵션 숨기기     | 나타내려면        |
|사용자 계정 유형     |  Standard       |
|흰색 Glove OOBE 허용     |  예       |
|장치 이름 서식 파일 적용     | 예        |
|이름 입력     | MMD-% RAND: 11%        |

> [!NOTE]
> ESP가 설정 된 고객만 "white glove" 프로 비전을 사용할 수 있지만,이 기능은 현재 Microsoft Managed Desktop에서 지원 되지 않습니다.

## <a name="enrollment-status-page-settings"></a>등록 상태 페이지 설정

Microsoft Managed Desktop은 등록 상태 페이지 환경에 이러한 설정을 사용 합니다.


|설정  |값  |
|---------|---------|
|앱 및 프로필 구성 진행률 표시     | 예        |
|지정 된 시간 (분) 보다 더 오래 걸릴 경우 오류 표시     |  60       |
|시간 제한 오류가 발생할 때 사용자 지정 메시지 표시     |  예       |
|오류 메시지     | 예, 예상 보다 더 짧은 장치를 설정 하는 데 시간이 조금 걸립니다. 시작 하려면 아래를 클릭 하 고 백그라운드에서 설정을 완료 합니다.        |
|사용자가 설치 오류에 대 한 로그를 수집할 수 있도록 허용     |  예       |
|OOBE (기본 제공 경험)로 프로 비전 된 장치에만 페이지를 표시 합니다.     | 예        |
|모든 앱 및 프로필이 설치 될 때까지 장치 사용 차단     |  예       |
|설치 오류가 발생 하는 경우 사용자가 장치를 다시 설정할 수 있도록 허용     |  예       |
|설치 오류가 발생 하는 경우 사용자가 장치를 사용할 수 있도록 허용     |  예       |
|사용자/장치에 할당 된 경우 이러한 필수 앱이 설치 될 때까지 장치 사용을 차단 합니다.     |  현대 작업 시간 수정       |



등록 상태 페이지 환경은 세 단계로 진행 됩니다. 자세한 내용은 [등록 상태 페이지 추적 정보](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status#enrollment-status-page-tracking-information)를 참조 하세요.

환경이 다음과 같이 진행 됩니다.

1. Autopilot 환경이 시작 되 고 사용자가 자격 증명을 입력 합니다.
2. 장치에서 등록 상태 페이지가 열리고 장치 준비 및 장치 설정 단계가 진행 됩니다. 사용자 ESP가 사용 하지 않도록 설정 되어 있기 때문에 현재 Microsoft 관리 데스크톱 구성에서 세 번째 단계 (계정 설정)가 *생략* 됩니다. 장치가 다시 시작 됩니다.
3. 다시 시작 되 면 장치에서 **다른 사용자** 와의 Windows 로그인 페이지를 엽니다.
4. 사용자가 자격 증명을 다시 입력 하 고 바탕 화면이 열립니다.

> [!NOTE]
> Win32 앱은 Windows 10 버전이 1903 이상인 경우 ESP를 실행 하는 동안에만 배포 됩니다.

!["장치 준비" 및 "장치 설치" 단계가 표시 되는 Autopilot 설치 프로그램의 시작 페이지입니다.](../../media/mmd-autopilot-screenshot.png)

## <a name="white-glove-provisioning"></a>흰색 glove 프로 비전

Microsoft Managed Desktop은 현재 Windows Autopilot의 "흰색 glove" 기능을 지원 하지 않습니다.

## <a name="change-to-autopilot-and-enrollment-status-page-settings"></a>Autopilot 및 등록 상태 페이지 설정으로 변경

Microsoft Managed Desktop에서 사용 하는 설치가 사용자의 요구에 정확 하 게 일치 하지 않는 경우에는 [관리 포털](https://portal.azure.com/)을 통해 지원 티켓을 파일에 추가할 수 있습니다. 다음은 필요한 구성 유형의 몇 가지 예입니다.

### <a name="autopilot-settings-change"></a>Autopilot 설정 변경

다른 장치 이름 템플릿을 요청 해야 할 수도 있습니다. 그러나 배포 모드를 변경 하거나, Azure AD에 가입 하거나, 개인 정보 설정 또는 사용자 계정 유형을 변경할 수는 없습니다.

### <a name="enrollment-status-page-settings-change"></a>등록 상태 페이지 설정 변경

- "설치가 지정 된 시간 (분) 보다 오래 걸릴 경우 오류 표시" 설정이 더 긴 시간 (분)입니다.
- 표시 되는 오류 메시지
- "사용자/장치에 할당 된 경우 이러한 필수 앱이 설치 될 때까지 장치 사용 차단" 설정에서 응용 프로그램을 추가 또는 제거 합니다.

## <a name="required-applications"></a>필수 응용 프로그램

- 최신 작업 공간 *장치 그룹* 테스트, 먼저, 빠른 속도 및 광범위 한 응용 프로그램의 대상을 지정 해야 합니다. 응용 프로그램은 "시스템" 컨텍스트에서 설치 해야 합니다. 모든 그룹에 할당 하기 전에 테스트 그룹에서 ESP를 사용 하 여 테스트를 완료 해야 합니다.
- 응용 프로그램에서 장치를 다시 시작 해야 하는 것은 아닙니다. 다시 시작 해야 하는 경우 응용 프로그램 패키지를 작성할 때 응용 프로그램을 "아무 작업도 하지 않음"으로 설정 하는 것이 좋습니다.
- 필수 응용 프로그램을 사용자가 장치에 로그인 할 때 즉시 필요한 핵심 응용 프로그램 으로만 제한 합니다.
- 응용 프로그램 설치 단계가 진행 되는 동안 시간 제한을 방지 하려면 모든 응용 프로그램의 전체 크기를 집합적으로 1gb 미만으로 유지 합니다.
- 이상적으로는 앱에 종속성이 없어야 합니다. 종속성 *이 필요한 앱* 이 있는 경우 ESP 평가의 일부로 구성, 테스트 및 유효성 검사를 수행 해야 합니다.
- "사용자" 컨텍스트 (예: 팀)가 필요한 응용 프로그램은 ESP 공개 미리 보기에 포함 될 수 없습니다.
