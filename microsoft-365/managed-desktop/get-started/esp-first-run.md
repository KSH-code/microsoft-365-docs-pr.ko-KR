---
title: Autopilot 및 등록 상태 페이지의 첫 실행 환경
description: ESP 환경, 사용되는 설정 및 구성 변경 내용을 배포하는 방법
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 3037225e2d628345b672bfae145bcba570cbbc23
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59187707"
---
# <a name="first-run-experience-with-autopilot-and-the-enrollment-status-page"></a>Autopilot 및 등록 상태 페이지의 첫 실행 환경

Microsoft Managed Desktop [Windows Autopilot과](/windows/deployment/windows-autopilot/windows-autopilot) Microsoft Intune [ESP(등록](/windows/deployment/windows-autopilot/enrollment-status) 상태 페이지)를 모두 사용하여 사용자에게 최상의 첫 실행 환경을 제공합니다.

## <a name="initial-deployment"></a>초기 배포

ESP 환경을 제공하려면 서비스에서 장치를 Microsoft Managed Desktop 합니다. 등록에 대한 자세한 [](../get-started/register-devices-self.md) 내용은 직접 새 장치 등록 또는 장치를 등록하는 파트너 단계를 [참조하세요.](../get-started/register-devices-partner.md)
사전 프로비전된 배포에 대한 등록 상태 페이지 및 Autopilot은 기본적으로 Microsoft Managed Desktop.

## <a name="autopilot-profile-settings"></a>Autopilot 프로필 설정

Microsoft Managed Desktop 사용자 장치에 사용되는 Autopilot 프로필에서 다음 설정을 사용합니다.

<br>

****

|설정|값|
|---|---|
|배포 모드|사용자 기반|
|Azure AD에 다음으로 가입|Azure AD 가입|
|언어(지역)|사용자 선택|
|키보드 자동 구성|아니요|
|Microsoft 소프트웨어 사용 조건|숨기기|
|개인 정보 설정|숨기기|
|계정 변경 옵션 숨기기|표시|
|사용자 계정 유형|Standard|
|흰색 글러브 OOBE 허용|예|
|장치 이름 템플릿 적용|예|
|이름 입력|MMD-%RAND:11%|
|

## <a name="enrollment-status-page-settings"></a>등록 상태 페이지 설정

Microsoft Managed Desktop 상태 페이지 환경의 경우 다음 설정을 사용합니다.

<br>

****

|설정|값|
|---|---|
|앱 및 프로필 구성 진행률 표시|예|
|지정한 시간(분)보다 설치 시간이 오래 걸리는 경우 오류 표시|60|
|시간 제한 오류가 발생할 때 사용자 지정 메시지 표시|아니요|
|사용자가 설치 오류에 대한 로그를 수집하도록 허용|예|
|OOBE(Out-of-Box Experience)에서 프로비전한 장치에만 페이지 표시|예|
|모든 앱 및 프로필이 설치될 때까지 장치 사용 차단|예|
|설치 오류가 발생하는 경우 사용자가 디바이스를 초기화할 수 있도록 허용|예|
|설치 오류가 발생하는 경우 사용자가 디바이스를 사용할 수 있도록 허용|예|
|사용자/장치에 할당된 필수 앱이 설치될 때까지 장치 사용 차단|최신 작업 공간 - 시간 수정|최신 작업 공간 - 클라이언트 라이브러리|


등록 상태 페이지 환경은 세 단계로 진행됩니다. 자세한 내용은 등록 상태 [페이지 추적 정보를 참조하세요.](/mem/intune/enrollment/windows-enrollment-status#enrollment-status-page-tracking-information)

환경은 다음과 같이 진행됩니다.

1. Autopilot 환경이 시작되면 사용자가 자격 증명을 입력합니다.
2. 장치가 등록 상태 페이지를 열고 장치 준비 및 장치 설정 단계를 진행합니다. 사용자 ESP가 사용하지  않도록 설정되어 있기 때문에 Microsoft Managed Desktop 구성에서 세 번째 단계(계정 설정)를 건너뜁니다. 장치가 다시 시작됩니다.
3. 다시 시작하면 장치가 다른 사용자와 Windows 로그인 페이지를 **니다.**
4. 사용자가 자격 증명을 다시 입력하면 바탕 화면이 열립니다.

> [!NOTE]
> Win32 앱은 ESP 중에만 배포됩니다Windows 10 버전이 1903 이상인 경우.

!["장치 준비" 및 "장치 설정" 단계를 보여준 Autopilot 설치의 시작 페이지입니다.](../../media/mmd-autopilot-screenshot.png)


## <a name="additional-prerequisites-for-autopilot-for-pre-provisioned-deployment"></a>사전 프로비전된 배포를 위한 Autopilot의 추가 선행 구성

- 장치에 유선 네트워크 연결이 있어야 합니다.
- 2020년 8월 전에 Microsoft Managed Desktop 포털을 사용하여 등록한 장치가 있는 경우 등록을 다시 해지하고 다시 등록합니다.
- 장치에는 적절한 설치로 2020년 11월 누적 업데이트 [19H1/19H2 2020.11C](https://support.microsoft.com/topic/november-19-2020-kb4586819-os-builds-18362-1237-and-18363-1237-preview-25cbb849-74af-b8b8-29b8-68aa925e8cc3) 또는 [20H1 2020.11C가](https://support.microsoft.com/topic/november-30-2020-kb4586853-os-builds-19041-662-and-19042-662-preview-8fb07fb8-a7dd-ea62-d65e-3305da09f92e) 포함된 출하 시 이미지가 있어야 합니다. 또는 최신 Microsoft Managed Desktop 이미지로 이미지를 다시 설치해야 합니다.
- 실제 장치는 TPM 2.0 및 장치 attestation을 지원해야 합니다. 가상 컴퓨터는 지원되지 않습니다. 사전 프로비전 프로세스에서는 Autopilot 자체 Windows 기능을 사용하게 있으므로 TPM 2.0이 필요합니다. 또한 TPM 확인 프로세스를 수행하려면 각 TPM 공급자에 고유한 HTTPS URL 집합에 액세스해야 합니다. 자세한 내용은 Autopilot 자체 배포 모드 및 Autopilot의 사전 프로비전된 배포에 대한 항목을 Windows [참조하세요.](/mem/autopilot/networking-requirements#tpm)

## <a name="sequence-of-events-in-autopilot-for-pre-provisioned-deployment"></a>사전 프로비전된 배포를 위한 Autopilot의 이벤트 시퀀스

1. IT 관리자는 필요한 경우 장치를 다시 설치하거나 다시 설정합니다.
2. IT 관리자는 장치를 부팅하고, 첫 경험에 도달하고, Windows 키를 니다.
3. IT 관리자는 Autopilot Windows 선택한 다음 계속을 **선택합니다.** Autopilot Windows 화면에 장치에 대한 정보가 표시됩니다.
4. IT 관리자가 **프로비전을 선택하여** 프로비저닝 프로세스를 시작합니다.
5. 디바이스가 ESP를 시작하고 장치 준비 및 설정 단계를 진행합니다. 장치 설정 단계에서는 ESP 프로필의 정확한 구성에 따라 x의 앱 설치 **x가** 표시됩니다.
6. 사용자 ESP를 사용하지 않도록 설정하기 때문에 현재 Microsoft Managed Desktop 구성에서 계정 설정 단계를 건너뜁니다.
7. 장치가 다시 시작됩니다.

다시 시작하면 디바이스에 다시 연결 단추와 함께 녹색 상태 **화면이** 표시됩니다.

> [!IMPORTANT]
> 알려진 문제:
>
> - 미리 프로비전된 배포 재시도 기능에 대한 Autopilot이 실행된 후에도 ESP가 다시 실행되지 않습니다.
> - 사전 프로비전된 배포를 위해 Autopilot에서 디바이스의 이름을 바치지 않습니다. ESP 사용자 흐름을 거치고 나면 디바이스의 이름만 변경됩니다.

## <a name="change-to-autopilot-and-enrollment-status-page-settings"></a>Autopilot 및 등록 상태 페이지 설정으로 변경

사용자가 사용하는 설정이 Microsoft Managed Desktop 정확히 일치하지 않는 경우 관리 포털을 통해 지원 티켓을 [제출할 수 있습니다.](https://portal.azure.com/) 다음은 필요할 수 있는 구성 유형의 몇 가지 예입니다.

### <a name="autopilot-settings-change"></a>Autopilot 설정 변경

다른 장치 이름 템플릿을 요청할 수 있습니다. 그러나 배포 모드, Azure AD As에 가입, 개인 정보 보호 또는 사용자 계정 설정 변경할 수는 없습니다.

### <a name="enrollment-status-page-settings-change"></a>등록 상태 페이지 설정 변경

- "설치에 지정된 시간(분) 보다 오래 걸리는 경우 오류 표시" 설정의 시간(분)이 길습니다.
- 오류 메시지가 표시됩니다.
- "사용자/디바이스에 할당된 경우 이러한 필수 앱이 설치될 때까지 장치 사용 차단" 설정에서 응용 프로그램을 추가하거나 제거합니다.

## <a name="required-applications"></a>필수 응용 프로그램

- 최신 작업 공간 장치 그룹 *Test,* First, Fast 및 Broad에서 응용 프로그램을 대상으로 지정해야 합니다. 응용 프로그램은 "시스템" 컨텍스트에서 설치해야 합니다. 모든 그룹에 할당하기 전에 테스트 그룹에서 ESP로 테스트를 완료해야 합니다.
- 어떤 응용 프로그램도 장치를 다시 시작해야 합니다. 응용 프로그램을 다시 시작해야 하는 경우 응용 프로그램 패키지를 빌드할 때 응용 프로그램을 "아무 것도 하지 말 것"으로 설정하는 것이 좋습니다.
- 필요한 응용 프로그램을 사용자가 장치에 로그인할 때 즉시 필요한 핵심 응용 프로그램으로만 제한합니다.
- 응용 프로그램 설치 단계의 시간 제한을 방지하기 위해 모든 응용 프로그램의 총 크기를 1GB 미만으로 유지하십시오.
- 앱에 종속성은 없는 것이 가장 이상적입니다. 종속성 있는  앱이 있는 경우 ESP 평가의 일부로 앱을 구성, 테스트 및 유효성 검사해야 합니다.
- Microsoft Teams ESP에 포함될 수 없습니다.

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Microsoft Managed Desktop을 시작하기 위한 단계

1. [관리 포털](access-admin-portal.md)에 액세스합니다.
1. [관리 포털의 관리자 연락처를 추가하고 확인합니다](add-admin-contacts.md).
1. [등록 후 설정을 조정합니다](conditional-access.md).
1. [Intune 회사 포털](company-portal.md)을 배포하고 할당합니다.
1. [라이선스를 할당합니다](assign-licenses.md).
1. [앱을 배포합니다](deploy-apps.md).
1. [디바이스를 설정합니다](set-up-devices.md).
1. Autopilot 및 등록 상태 페이지(이 문서)를 통해 첫 실행 환경을 설정할 수 있습니다.
1. [사용자 지원 기능을 사용하도록 설정합니다](enable-support.md).
1. [사용자가 디바이스를 사용할 수 있도록 준비합니다](get-started-devices.md).
1. [앱 컨트롤을 시작합니다](get-started-app-control.md).