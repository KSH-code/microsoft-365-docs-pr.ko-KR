---
title: Autopilot 및 등록 상태 페이지의 첫 실행 환경
description: ESP 환경, 사용되는 설정 및 구성 변경을 배포하는 방법
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

Microsoft Managed Desktop은 [Windows Autopilot과](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot) Microsoft Intune의 [ESP(등록 상태 페이지)를](https://docs.microsoft.com/windows/deployment/windows-autopilot/enrollment-status) 모두 사용하여 사용자에게 최상의 첫 실행 환경을 제공합니다.

등록 상태 페이지가 현재 공개 미리 보기 상태입니다.

## <a name="initial-deployment"></a>초기 배포

ESP 환경을 제공하려면 Microsoft Managed Desktop 서비스에 장치를 등록해야 합니다. 등록에 대한 자세한 [](../get-started/register-devices-self.md) 내용은 새 디바이스를 직접 등록하거나 파트너가 디바이스를 등록하는 [단계를 참조하세요.](../get-started/register-devices-partner.md)

디바이스가 서비스에 등록된 후 관리 포털을 통해 지원 티켓을 작성하여 Microsoft Managed Desktop 디바이스에 대해 ESP를 사용하도록 설정할 [수 있습니다.](https://portal.azure.com/) 처음에 티켓을 제출할 때 테스트 그룹에 ESP 구성을 배포합니다. 24시간마다 다른 후속 배포 그룹(첫 번째, 빠르기 및 광범위)에 배포됩니다. 배포를 일시 중지하기 위해 Operations에 보류를 요청하는 다른 티켓을 제출합니다.

## <a name="autopilot-profile-settings"></a>Autopilot 프로필 설정

Microsoft Managed Desktop은 사용자 장치에 사용되는 Autopilot 프로필에서 다음 설정을 사용합니다.


|설정  |값  |
|---------|---------|
|배포 모드 |  사용자 기반       |
|Azure AD에 다음으로 가입     |  Azure AD 가입       |
|언어(지역)     | 운영 체제 기본값        |
|키보드 자동 구성     | 아니요        |
|Microsoft 소프트웨어 사용 조건     |  숨기기       |
|개인 정보 설정     | 숨기기        |
|변경 계정 옵션 숨기기     | 표시        |
|사용자 계정 유형     |  Standard       |
|화이트 글러브 OOBE 허용     |  예       |
|장치 이름 템플릿 적용     | 예        |
|이름 입력     | MMD-%RAND:11%        |

> [!NOTE]
> "흰색 글러브" 프로비저닝은 ESP가 켜져 있는 고객에 한해 사용하도록 설정되어 있는 동안에는 현재 Microsoft Managed Desktop에서 지원되지 않습니다.

## <a name="enrollment-status-page-settings"></a>등록 상태 페이지 설정

Microsoft Managed Desktop은 등록 상태 페이지 경험에 대해 다음 설정을 사용합니다.


|설정  |값  |
|---------|---------|
|앱 및 프로필 구성 진행률 표시     | 예        |
|지정된 시간(분)보다 설치 시간이 오래 걸리는 경우 오류 표시     |  60       |
|시간 제한 오류가 발생할 때 사용자 지정 메시지 표시     |  예       |
|오류 메시지     | 예. 장치를 예상보다 설정하는 데 시간이 좀 더 오래 필요합니다. 시작하려면 아래를 클릭하면 백그라운드에서 설정이 완료됩니다.        |
|사용자가 설치 오류에 대한 로그를 수집하도록 허용     |  예       |
|OOBE(Out-of-Box Experience)를 통해 프로비전된 장치에만 페이지 표시     | 예        |
|모든 앱 및 프로필이 설치될 때까지 디바이스 사용 차단     |  예       |
|설치 오류가 발생하는 경우 사용자가 디바이스를 초기화하도록 허용     |  예       |
|설치 오류가 발생하는 경우 사용자가 디바이스를 사용할 수 있도록 허용     |  예       |
|사용자/장치에 할당된 필수 앱이 설치될 때까지 장치 사용 차단     |  최신 작업 공간 - 시간 수정       |



등록 상태 페이지 환경은 세 단계로 진행됩니다. 자세한 내용은 [등록 상태 페이지 추적 정보를 참조하세요.](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status#enrollment-status-page-tracking-information)

환경은 다음과 같이 진행됩니다.

1. Autopilot 환경이 시작되면 사용자가 자격 증명을 입력합니다.
2. 장치가 등록 상태 페이지를 열고 장치 준비 및 장치 설정 단계를 진행합니다. 사용자 ESP가 사용하지  않도록 설정되어 있기 때문에 세 번째 단계(계정 설정)는 현재 Microsoft Managed Desktop 구성에서 건너뜁니다. 장치가 다시 시작됩니다.
3. 다시 시작하면 장치가 다른 사용자와 함께 Windows 로그인 **페이지를 니다.**
4. 사용자가 자격 증명을 다시 입력하면 바탕 화면이 열립니다.

> [!NOTE]
> Windows 10 버전이 1903 이상인 경우 Win32 앱은 ESP 중에만 배포됩니다.

!["장치 준비" 및 "장치 설정" 단계를 보여주는 Autopilot 설치의 시작 페이지입니다.](../../media/mmd-autopilot-screenshot.png)

## <a name="white-glove-provisioning"></a>흰색 글러브 프로비전

Microsoft Managed Desktop은 현재 Windows Autopilot의 "흰색 글러브" 기능을 지원하지 않습니다.

## <a name="change-to-autopilot-and-enrollment-status-page-settings"></a>Autopilot 및 등록 상태 페이지 설정 변경

Microsoft Managed Desktop에서 사용하는 설정이 요구와 정확히 일치하지 않는 경우 관리 포털을 통해 지원 티켓을 [제출할 수 있습니다.](https://portal.azure.com/) 다음은 필요할 수 있는 구성 유형의 몇 가지 예입니다.

### <a name="autopilot-settings-change"></a>Autopilot 설정 변경

다른 장치 이름 템플릿을 요청할 수 있습니다. 그러나 배포 모드, Azure AD As에 가입, 개인 정보 설정 또는 사용자 계정 유형을 변경할 수는 없습니다.

### <a name="enrollment-status-page-settings-change"></a>등록 상태 페이지 설정 변경

- "지정한 시간(분)보다 오래 걸리는 경우 오류 표시" 설정의 시간(분)이 길습니다.
- 표시된 오류 메시지
- "사용자/장치에 할당된 필수 앱이 설치될 때까지 장치 사용 차단" 설정에서 응용 프로그램을 추가하거나 제거합니다.

## <a name="required-applications"></a>필수 응용 프로그램

- 최신 작업 공간 장치 그룹 *Test,* First, Fast 및 Broad에서 응용 프로그램을 대상으로 지정해야 합니다. 응용 프로그램은 "시스템" 컨텍스트에서 설치해야 합니다. 모든 그룹에 ESP를 할당하기 전에 테스트 그룹에서 ESP로 테스트를 완료해야 합니다.
- 어떤 응용 프로그램도 장치를 다시 시작할 필요가 없습니다. 응용 프로그램을 다시 시작해야 하는 경우 응용 프로그램 패키지를 빌드할 때 응용 프로그램을 "아무 것도 하지 말 것"으로 설정하는 것이 좋습니다.
- 필요한 응용 프로그램을 사용자가 장치에 로그인할 때 즉시 필요한 핵심 응용 프로그램으로만 제한합니다.
- 응용 프로그램 설치 단계의 시간 제한을 방지하기 위해 모든 응용 프로그램의 총 크기를 1GB 미만으로 유지하십시오.
- 앱에 종속되지 않는 것이 가장 이상적입니다. 종속성 있어야  하는 앱이 있는 경우 ESP 평가의 일부로 앱을 구성, 테스트 및 유효성을 검사해야 합니다.
- "사용자" 컨텍스트(예: Teams)가 필요한 응용 프로그램은 ESP의 공개 미리 보기에 포함될 수 없습니다.
