---
title: 내부자 위험 관리 브라우저 신호 감지(미리 보기)에 대해 알아보고 구성
description: 내부자 위험 관리 브라우저 신호 검색에 대해 Microsoft 365
keywords: Microsoft 365, 내부 위험 관리, 위험 관리, 규정 준수
ms.localizationpriority: medium
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
ms.openlocfilehash: f25664c0ca9cffa3a54e0bb9fb734bb506dfdf5b
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60190764"
---
# <a name="learn-about-and-configure-insider-risk-management-browser-signal-detection-preview"></a>내부자 위험 관리 브라우저 신호 감지(미리 보기)에 대해 알아보고 구성

웹 브라우저는 사용자가 조직 내에서 중요한 파일과 중요하지 않은 파일에 모두 액세스하는 데 자주 사용됩니다. 내부자 위험 관리를 통해 조직은 조직과 [Google Chrome](https://www.google.com/chrome) 브라우저에서 볼 수 있는 실행되지 않는 모든 파일에 대한 브라우저 [유출 신호를 Microsoft Edge](https://www.microsoft.com/edge) 수 있습니다. 이러한 신호를 사용하여 분석가와 조사자는 이러한 브라우저를 사용할 때 범위 내 정책 사용자가 다음 활동 중 한 가지를 수행할 때 신속하게 작업을 수행할 수 있습니다.

- 개인 클라우드 저장소에 복사된 파일
- 로컬 또는 네트워크 장치에 인쇄된 파일
- 네트워크 공유로 전송 또는 복사된 파일
- USB 장치에 복사된 파일

이러한 이벤트에 대한 신호는 기본 Microsoft Edge 및 *Microsoft Insider Risk Extension* 추가 기능을 사용하여 검색됩니다. Google Chrome에서 고객은 *신호 감지에 Microsoft 준수 확장을* 사용 합니다.

다음 표에서는 각 브라우저에 대해 검색된 활동 및 확장 지원을 요약하여 제공합니다.

| **검색된 활동**                        | **Microsoft Edge** | **Google Chrome** |
| ---------------------------------------------- | ------------------ | ----------------- |
| 개인 클라우드 저장소에 복사된 파일         | 기본             | Extension         |
| 로컬 또는 네트워크 장치에 인쇄된 파일      | 기본             | Extension         |
| 네트워크 공유로 전송 또는 복사된 파일 | Extension          | Extension         |
| USB 장치에 복사된 파일                    | Extension          | Extension         |

## <a name="common-requirements"></a>일반적인 요구 사항

*Microsoft Insider Risk Extension* 또는 Microsoft *준수* 확장을 설치하기 전에 고객은 범위 내 정책 사용자의 장치가 다음 요구 사항을 충족하는지 확인해야 합니다.

- 최신 Windows 10 x64 빌드를 권장합니다. 신호 감지 지원을 Windows 10 x64 빌드 1809의 최소 버전입니다. 브라우저 신호 검색은 현재 브라우저가 아닌 장치에서 Windows 않습니다.
- 현재 [Microsoft 365 위험](/microsoft-365/compliance/insider-risk-management-configure#subscriptions-and-licensing) 관리 지원이 있는 구독이 있습니다.
- 장치가 [규정](/microsoft-365/compliance/insider-risk-management-settings#enable-device-indicators-and-onboard-devices) 준수 포털에 Microsoft 365 합니다.

특정 브라우저 구성 요구 사항에 대한 자세한 내용은 이 Microsoft Edge 및 Google Chrome 섹션을 참조하세요.

## <a name="configure-browser-signal-detection-for-microsoft-edge"></a>사용자에 대한 브라우저 신호 Microsoft Edge

### <a name="microsoft-edge-browser-requirements"></a>Microsoft Edge 브라우저 요구 사항

- 일반적인 요구 사항 충족
- Microsoft Edge x64, 91.0.864.41 버전 이상
- *Microsoft Insider Risk Extension* 추가 기능 버전 1.0.0.44 이상
- Edge.exe 브라우저로 구성되지 않은 경우

### <a name="option-1-basic-setup-recommended-for-testing-with-edge"></a>옵션 1: 기본 설정(Edge를 사용하여 테스트하는 경우 권장)

브라우저 신호 감지를 테스트할 때 조직의 각 장치에 대해 단일 컴퓨터 자체 고스트를 구성하려면 이 옵션을 사용합니다.

기본 설정 옵션에 대해 다음 단계를 완료합니다.

1. Microsoft [Insider Risk Extension으로 이동합니다.](https://microsoftedge.microsoft.com/addons/detail/microsoft-insider-risk-ex/lcmcgbabdcbngcbcfabdncmoppkajglo)
2. 확장을 설치합니다.

### <a name="option-2-intune-setup-for-edge"></a>옵션 2: Edge에 대한 Intune 설정

Intune을 사용하여 조직의 확장 및 요구 사항을 구성하는 데 이 옵션을 사용합니다.

Intune 설치 옵션에 대해 다음 단계를 완료합니다.

1. 관리자 권한을 사용하여 Microsoft Endpoint Manager [관리](https://endpoint.microsoft.com) 센터에 로그인합니다.
2. 구성 **프로필로 이동합니다.**
3. **프로필 만들기** 를 선택합니다.
4. 플랫폼 **Windows 10** 옵션을 선택하십시오.
5. 프로필 **유형으로** 관리 *템플릿을 선택하고* 만들기를 **선택합니다.**
6. **설정** 탭을 선택합니다.
7. **Edge 버전 77 이상을 선택합니다.**
8. 모든 확장 **관련** 설정에 대한 개요를 제공하는 확장을 검색합니다.
9. 자동으로 설치되는 확장 제어 **설정을 선택합니다.**
10. 사용 **을 선택합니다.**
11. 프롬프트가 표시될 때 확장 ID를 추가합니다. *lcmcgbabdcbngcbcfabdncmoppkajglo***.**
12. 확인을 **선택합니다.**

### <a name="option-3-group-policy-setup-for-edge"></a>옵션 3: Edge에 대한 그룹 정책 설정

이 옵션을 사용하여 그룹 정책을 사용하여 조직 전체에서 확장 및 요구 사항을 구성합니다.

그룹 정책 설정 옵션에 대해 다음 단계를 완료합니다.

**1단계: 최신 Microsoft Edge 관리 템플릿(.admx) 파일을 가져올 수 있습니다.**

그룹 정책을 사용하여 장치를 관리해야 [](https://www.microsoft.com/edge/business/download) Microsoft Edge 관리 템플릿을 그룹 정책 중앙 저장소로 가져와야 합니다. 자세한 내용은 [Windows의 그룹 정책 관리 서식 파일에 대한 중앙 저장소를 만들고 관리하는 방법](/troubleshoot/windows-client/group-policy/create-and-manage-central-store)을 참조하세요.

**2단계: *Microsoft Insider Risk Management Extension* 추가 기능을 강제 설치 목록에 *추가합니다.***

다음 단계를 완료하여 확장을 추가합니다.

1. 그룹 **정책 관리 편집기에서** OU(조직 구성 단위)로 이동합니다.
2. 다음 경로 **컴퓨터/사용자** 구성 정책 관리 템플릿 클래식 관리 템플릿 \>  \>  \>  \> **확장을 Microsoft Edge** \> **확장합니다.** 이 경로는 조직의 구성에 따라 다를 수 있습니다.
3. 자동으로 **설치되는 확장 구성을 선택합니다.**
4. 를 마우스 오른쪽 단추로 클릭하고 **편집을 선택합니다.**
5. 사용 **라디오 단추를** 확인합니다.
6. **표시** 를 선택합니다.
7. **값의** 경우 *lcmcgbabdcbngcbcfabdncmoppkajglo 항목을 추가합니다. https://edge.microsoft.com/extensionwebstorebase/v1/crx*
8. **확인을 선택하고** **적용을 선택합니다.**

## <a name="configure-browser-signal-detection-for-google-chrome"></a>Google Chrome에 대한 브라우저 신호 검색 구성

Google Chrome에 대한 내부자 위험 관리 브라우저 신호 감지 지원은 Microsoft 준수 확장을 *통해 활성화됩니다.* 이 확장은 Chrome의 끝점 DLP도 지원됩니다. 끝점 DLP 지원에 대한 자세한 내용은 Microsoft 준수 확장 시작(미리 [보기)을 참조하세요.](/microsoft-365/compliance/dlp-chrome-get-started)

### <a name="google-chrome-browser-requirements"></a>Google Chrome 브라우저 요구 사항

- 일반적인 요구 사항 충족
- 최신 버전의 Google Chrome x64
- *Microsoft 준수 확장* 버전 2.0.0.183 이상
- Chrome.exe 브라우저로 구성되지 않은 경우

### <a name="option-1-basic-setup-recommended-for-testing-with-chrome"></a>옵션 1: 기본 설정(Chrome으로 테스트하는 경우 권장)

브라우저 신호 감지를 테스트할 때 조직의 각 장치에 대해 단일 컴퓨터 자체 고스트를 구성하려면 이 옵션을 사용합니다.

기본 설정 옵션에 대해 다음 단계를 완료합니다.

**1단계: PowerShell을 사용하여 필수 레지스트리 키 사용**

```PowerShell
Get-Item -path "HKLM:\\SOFTWARE\\Microsoft\\Windows Defender\\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
```

>[!Important]
>이러한 레지스트리 키는 확장의 적절한 기능을 보장하는 데 필요합니다. 신호를 테스트하기 전에 이러한 레지스트리 키를 사용하도록 설정해야 합니다.*

**2단계: *Microsoft 준수 확장 설치***

1. Microsoft 준수 [확장으로 이동합니다.](https://chrome.google.com/webstore/detail/microsoft-compliance-exte/echcggldkblhodogklpincgchnpgcdco)
2. 확장을 설치합니다.

### <a name="option-2-intune-setup-for-chrome"></a>옵션 2: Chrome용 Intune 설정

Intune을 사용하여 조직의 확장 및 요구 사항을 구성하는 데 이 옵션을 사용합니다.

Intune 설치 옵션에 대해 다음 단계를 완료합니다.

**1단계: Intune에서 필수 레지스트리 키 사용**

1. 다음 PowerShell 스크립트를 실행합니다.

```PowerShell
Get-Item -path "HKLM:\\SOFTWARE\\Microsoft\\Windows Defender\\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
```

2. Microsoft Endpoint Manager [관리 센터에 로그인합니다.](https://endpoint.microsoft.com)
3. 장치  \> **스크립트로 이동하고** 추가를 **선택합니다.**
4. 메시지가 표시되면 만든 스크립트의 위치로 이동합니다.
5. 다음 설정을 선택합니다.

    - 로그온한 자격 증명을 사용하여 이 스크립트를 실행합니다. *예*
    - 스크립트 서명 검사 적용: *아니요*
    - 64비트 PowerShell 호스트에서 스크립트 실행: *예*

6. 적절한 장치 그룹을 선택하고 정책을 적용합니다.

**2단계: Intune 강제 설치 구성**

설치된 강제 확장 목록에 Microsoft DLP Chrome 확장을 추가하기 전에 Intune 관리용 Chrome 관리 템플릿(.admx) 파일을 설치해야 합니다. 단계별 지침은 를 사용하여 [Chrome 브라우저 Microsoft Intune.](https://support.google.com/chrome/a/answer/9102677?hl=en#zippy=%2Cstep-ingest-the-chrome-admx-file-into-intune) 관리 템플릿 파일을 설치한 후 다음 단계를 완료합니다.

1. Microsoft Endpoint Manager [관리 센터에 로그인합니다.](https://endpoint.microsoft.com)
2. 구성 **프로필로 이동합니다.**
3. **프로필 만들기** 를 선택합니다.
4. 플랫폼으로 **Windows 10** 를 *선택하십시오.*
5. 사용자 **지정을** *프로필 유형으로* 선택하십시오.
6. **설정** 탭을 선택합니다.
7. 추가를 **선택합니다.**
8. 다음 정책 정보를 입력합니다.

    - OMA-URI: *./Device/Vendor/MSFT/Policy/Config/Chrome~Policy~googlechrome~Extensions/ExtensionInstallForcelist*
    - 데이터 형식: *문자열*
    - 값: *\<enabled/\>\<data id=”ExtensionInstallForcelistDesc” value=”1&\#xF000; echcggldkblhodogklpincgchnpgcdco;https://clients2.google.com/service/update2/crx″/\>*

9. **만들기** 를 선택합니다.

### <a name="option-3-group-policy-setup-for-chrome"></a>옵션 3: Chrome에 대한 그룹 정책 설정

이 옵션을 사용하여 그룹 정책을 사용하여 조직 전체에서 확장 및 요구 사항을 구성합니다.

그룹 정책 설정 옵션에 대해 다음 단계를 완료합니다.

**1단계: Chrome 관리 템플릿 파일 가져오기**

그룹 정책을 사용하여 디바이스를 관리할 수 있어야 합니다. 모든 [Chrome](https://chromeenterprise.google/browser/download/) 관리 템플릿을 그룹 정책 중앙 저장소로 가져와야 합니다. 자세한 내용은 [Windows의 그룹 정책 관리 서식 파일에 대한 중앙 저장소를 만들고 관리하는 방법](/troubleshoot/windows-client/group-policy/create-and-manage-central-store)을 참조하세요.

**2단계: PowerShell을 사용하여 필수 레지스트리 키 사용**

1. 다음 내용으로 PowerShell 스크립트를 만듭니다.

    ```PowerShell
    Get-Item -path "HKLM:\\SOFTWARE\\Microsoft\\Windows Defender\\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
    ```

2. **그룹 정책 관리 콘솔** 을 열고 OU(조직 구성 단위)로 이동합니다.
3. 마우스 오른쪽 단추로 클릭하고 이 도메인에 **GPO 만들기를 선택하고 여기에 연결합니다.** 메시지가 표시될 때 이 GPO(그룹 정책 개체)에 설명이 있는 이름을 할당합니다. 예를 들어 *DLP Chrome 직접 실행 PowerShell 스크립트입니다.*
4. GPO를 만들고 나면 를 마우스 오른쪽 단추로 클릭하고 **편집을 선택합니다.** 이 선택을 통해 그룹 정책 개체로 진행됩니다.
5. 컴퓨터 **구성** 기본 \> **설정** \> **제어판 설정** \> **예약된 작업으로 이동합니다.**
6. 예약된 작업 아래의 빈  영역을 마우스  오른쪽 단추로 클릭하고 새 즉시 실행 작업(최소 Windows \> **7)을 선택합니다.**
7. 작업 이름 및 *설명을* *입력합니다.*
8. 직접 실행 작업을 실행하려면 해당 계정을 선택하십시오. 예: *NT Authority*.
9. **가장 높은 수준의 권한으로 실행** 을 선택합니다.
10. Windows 10에 대한 정책을 구성합니다.
11. 작업 **탭에서** 프로그램 **시작 을 선택합니다.**
12. 1단계에서 만든 프로그램/스크립트의 **경로를 입력합니다.**
13. **적용** 을 선택합니다.

**3단계: 강제 설치 목록에 Chrome 확장 추가**

1. 그룹 **정책 관리 편집기에서** OU(조직 구성 단위)로 이동합니다.
2. 다음 경로를 확장 **컴퓨터/사용자 구성** \> **정책** \> **관리 템플릿** 클래식 관리 \> **템플릿** \> **Google** \> **Google Chrome** 확장 \> **.** 이 경로는 조직의 구성에 따라 다를 수 있습니다.
3. 강제로 **설치된 확장 목록 구성을 선택합니다.**
4. 를 마우스 오른쪽 단추로 클릭하고 **편집을 선택합니다.**
5. 사용 **라디오 단추를** 선택합니다.
6. **표시** 를 선택합니다.
7. **값의** 경우 *echcggldkblhodogklpincgchnpgcdco 항목을 추가합니다. https://clients2.google.com/service/update2/crx*
8. **확인을 선택하고** **적용을 선택합니다.**

## <a name="test-and-verify-insider-risk-management-browser-signal-detections"></a>내부자 위험 관리 브라우저 신호 감지 테스트 및 확인

1. 장치 표시기를 사용하도록 설정하여 내부자 위험 관리 정책을 만들 수 있습니다.
2. 개인 클라우드 저장소에 복사된 파일에 대한 신호 검색을 테스트하려면 지원되는 클라우드 저장소 장치에서 Windows 완료합니다.

    - 신호 검색을 위해 구성한 브라우저 유형으로 파일 공유 웹 사이트(Microsoft OneDrive, Google 드라이브 등)를 열 수 있습니다.
    - 브라우저를 사용하여 실행 가능하지 않은 파일을 웹 사이트에 업로드합니다.
3. 로컬 또는 네트워크 장치에 인쇄된 파일, 네트워크 공유로 전송 또는 복사된 파일 및 USB 장치에 복사된 파일에 대한 신호 검색을 테스트하려면 지원되는 Windows 장치에서 다음 단계를 완료합니다.

    - 브라우저에서 직접 실행 가능한 파일이 열립니다. 파일을 파일 탐색기를 통해 직접 열거나 웹 페이지가 아닌 새 브라우저 탭에서 열아야 합니다.
    - 파일을 인쇄합니다.
    - USB 장치에 파일을 저장합니다.
    - 네트워크 드라이브에 파일을 저장합니다.
  
4. 첫 번째 내부자 위험 관리 정책을 만든 후 약 24시간 후에 활동 표시기에서 경고를 받기 시작하게 됩니다. 경고 [대시보드에서](/microsoft-365/compliance/insider-risk-management-activities#alert-dashboard) 테스트된 활동에 대한 내부자 위험 관리 경고를 확인할 수 있습니다.
