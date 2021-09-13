---
title: 로컬 스크립트를 사용하여 Windows 10 장치 온보딩
description: 로컬 스크립트를 사용하여 디바이스를 서비스에 온보딩할 수 있도록 디바이스에 구성 패키지를 배포합니다.
keywords: 로컬 스크립트를 사용하여 장치 구성, 장치 관리, 끝점 장치용 Microsoft Defender 구성
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: e1a681fb7d521c26327bec3d22bff233926a279f
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59221992"
---
# <a name="onboard-the-windows-10-devices-using-a-local-script"></a>로컬 스크립트를 Windows 10 장치 온보딩

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-configureendpointsscript-abovefoldlink)

개별 디바이스를 Endpoint용 Defender에 수동으로 온보딩할 수도 있습니다. 네트워크의 모든 장치를 온보드하기 전에 서비스를 테스트할 때 이 작업을 먼저 수행해야 할 수 있습니다.

> [!IMPORTANT]
> 이 스크립트는 최대 10대의 장치에서 사용하기 위해 최적화되었습니다.
>
> 대규모로 배포하기 위해 다른 [배포 옵션을 사용하세요.](configure-endpoints.md) 예를 들어 그룹 정책을 사용하여 온보딩 스크립트를 온보딩 장치에서 사용할 수 있는 스크립트를 사용하여 프로덕션의 10개가 넘는 디바이스에 배포할 [Windows 10 있습니다.](configure-endpoints-gp.md)

## <a name="onboard-devices"></a>온보딩 장치

[![다양한 배포 경로를 보여 주며 PDF의 이미지입니다.](images/onboard-script.png)](images/onboard-script.png#lightbox)

[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf) 또는 Visio [](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) 끝점용 Defender 배포에서 다양한 경로를 확인할 수 있습니다.

1. 서비스 온보더링 마법사에서 .zip ** 다운로드한 GP 구성 패키지 파일(WindowsDefenderATPOnboardingPackage.zip)을 열 수 있습니다. Defender 포털에서 [패키지를 Microsoft 365 있습니다.](https://security.microsoft.com/)
    1. 탐색 창에서 **끝점 설정** \> **관리** \>  \> **온보더링** 을 선택합니다.
    2. 운영 Windows 10 로 실행을 선택합니다.
    3. 배포 **방법 필드에서** 로컬 스크립트 **를 선택합니다.**
    4. 패키지 **다운로드를** 클릭하고 파일 .zip 저장합니다.

2. 온보더할 디바이스의 위치(예: 데스크톱)에 구성 패키지의 내용을 추출합니다. *이름이 WindowsDefenderATPLocalOnboardingScript.cmd인 파일이 있습니다.*

3. 디바이스에서 상승된 명령줄 프롬프트를 열고 스크립트를 실행합니다.
   1. **시작**(으)로 이동하고 **cmd** 를 입력하십시오.
   2. **명령 프롬프트** 을(를) 마우스 오른쪽 버튼으로 클릭하고 **관리자**(으)로 실행을 선택합니다.

    ![관리자 시작 메뉴 실행을 설정하는 창 창입니다.](images/run-as-admin.png)

4.  스크립트 파일의 위치를 입력합니다. 바탕 화면에 파일을 복사한 경우 *%userprofile%\Desktop\WindowsDefenderATPLocalOnboardingScript.cmd를 입력합니다.*

5.  Enter 키를 **누르거나** 확인을 **클릭합니다.**

장치가 규격을 확인하고 센서 데이터를 올바르게 보고하는지 수동으로 확인할 수 있는 방법에 대한 자세한 내용은 Endpoint 온보딩 문제에 [대한 Microsoft Defender 문제 해결을 참조하세요.](troubleshoot-onboarding.md)

> [!TIP]
> 장치를 온보드한 후 검색 테스트를 실행하여 장치가 서비스에 제대로 온보드되었는지 확인할 수 있습니다. 자세한 내용은 새로 온보딩된 [끝점용 Microsoft Defender](run-detection-test.md)끝점에서 검색 테스트 실행을 참조하세요.

## <a name="configure-sample-collection-settings"></a>샘플 수집 설정 구성

각 디바이스에 대해 심층 분석을 위해 파일을 제출하기 위해 요청을 할 때 장치에서 샘플을 수집할 수 있는지 여부를 Microsoft 365 Defender 구성 값을 설정할 수 있습니다.

*regedit를* 사용하거나 .reg 파일을 만들고 실행하여 디바이스에서 샘플 공유 설정을 수동으로 *구성할 수* 있습니다.

구성은 다음 레지스트리 키 항목을 통해 설정됩니다.

```console
Path: "HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection"
Name: "AllowSampleCollection"
Value: 0 or 1
```

여기서 Name 형식은 D-WORD입니다. 가능한 값은 다음과 같습니다.

- 0 - 이 장치에서 샘플 공유를 허용하지 않습니다.
- 1 - 이 장치에서 모든 파일 형식을 공유할 수 있습니다.

레지스트리 키가 없는 경우의 기본값은 1입니다.

## <a name="run-a-detection-test-to-verify-onboarding"></a>검색 테스트를 실행하여 온보더링 확인

장치를 온보드한 후 검색 테스트를 실행하여 장치가 서비스에 제대로 온보드되었는지 확인할 수 있습니다. 자세한 내용은 새로 온보딩된 끝점 디바이스용 Microsoft Defender에서 검색 테스트 [실행을 참조하세요.](run-detection-test.md)

## <a name="offboard-devices-using-a-local-script"></a>로컬 스크립트를 사용하여 디바이스 오프보딩

보안상의 이유로, 오프보드 장치에 사용된 패키지는 다운로드한 날짜 30일 후에 만료됩니다. 장치에 전송된 만료된 오프보더 패키지는 거부됩니다. 오프보더 패키지를 다운로드할 때 패키지 만료 날짜에 대한 알림을 하게 되고 패키지 이름에도 포함됩니다.

> [!NOTE]
> 온보드 및 오프보더 정책을 동일한 장치에 동시에 배포하면 안 됩니다. 그렇지 않으면 예측할 수 없는 충돌이 발생할 수 있습니다.

1. 에서 오프보더 패키지를 Microsoft 365 Defender [포털](https://security.microsoft.com/):
    1. 탐색 창에서 **끝점 설정** 관리 \>  \>  오프보링 \> **을 선택합니다.**
    2. 운영 Windows 10 로 실행을 선택합니다.
    3. 배포 **방법 필드에서** 로컬 스크립트 **를 선택합니다.**
    4. 패키지 **다운로드를** 클릭하고 파일 .zip 저장합니다.

2. 디바이스에서 액세스할 수 .zip 읽기 전용 공유 위치로 파일 콘텐츠의 추출 이름이 *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd 입니다.*

3. 디바이스에서 상승된 명령줄 프롬프트를 열고 스크립트를 실행합니다.
   1. **시작**(으)로 이동하고 **cmd** 를 입력하십시오.
   2. **명령 프롬프트** 을(를) 마우스 오른쪽 버튼으로 클릭하고 **관리자**(으)로 실행을 선택합니다.

        ![관리자 시작 메뉴 실행을 설정하는 창 창입니다.](images/run-as-admin.png)

4. 스크립트 파일의 위치를 입력합니다. 바탕 화면에 파일을 복사한 경우 *%userprofile%\Desktop\WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd를 입력합니다.*

5. Enter 키를 **누르거나** 확인을 **클릭합니다.**

> [!IMPORTANT]
> 오프보더링을 통해 디바이스가 포털에 센서 데이터 전송을 중지하지만, 디바이스에서 전송한 모든 경고에 대한 참조를 포함하여 장치의 데이터는 최대 6개월 동안 보존됩니다.

## <a name="monitor-device-configuration"></a>장치 구성 모니터링

온보딩 문제 해결의 [](troubleshoot-onboarding.md) 다양한 확인 단계를 수행하여 스크립트가 성공적으로 완료되고 에이전트가 실행되고 있는지 확인할 수 있습니다.

모니터링은 포털에서 직접 수행하거나 다른 배포 도구를 사용하여 수행될 수도 있습니다.

### <a name="monitor-devices-using-the-portal"></a>포털을 사용하여 장치 모니터링

1. 검색 포털로 Microsoft 365 Defender.
2. 장치 **인벤토리 를 클릭합니다.**
3. 장치가 나타나는지 확인

## <a name="related-topics"></a>관련 항목

- [그룹 정책을 Windows 10 장치 온보드](configure-endpoints-gp.md)
- [Windows 10 사용하여 장치 온보드 Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md)
- [모바일 장치 관리 도구를 사용하여 Windows 10 장치 온보딩](configure-endpoints-mdm.md)
- [비영구 VDI(가상 데스크톱 인프라) 장치 온보딩](configure-endpoints-vdi.md)
- [새로 온보딩된 엔드포인트 디바이스용 Microsoft Defender에서 검색 테스트 실행](run-detection-test.md)
- [끝점 온보딩 문제에 대한 Microsoft Defender 문제 해결](troubleshoot-onboarding.md)
