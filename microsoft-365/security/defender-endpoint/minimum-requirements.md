---
title: 끝점용 Microsoft Defender에 대한 최소 요구 사항
description: 서비스에 대한 장치 온보드에 대한 라이선스 요구 사항 및 요구 사항 이해
keywords: 최소 요구 사항, 라이선스, 비교 표
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 4779a0c40cd8282d8e05fde84ae72827531810d9
ms.sourcegitcommit: d78553deeba23d2f8238f10e64c2e27f235dc37f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/05/2021
ms.locfileid: "60124269"
---
# <a name="minimum-requirements-for-microsoft-defender-for-endpoint"></a>끝점용 Microsoft Defender에 대한 최소 요구 사항

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**

- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-minreqs-abovefoldlink)

장치에 서비스를 온보드하기 위한 몇 가지 최소 요구 사항이 있습니다. 서비스에 장치를 온보드하기 위한 라이선스, 하드웨어 및 소프트웨어 요구 사항 및 기타 구성 설정에 대해 자세히 알아보습니다.

> [!TIP]
>
> - 이 문서에서는 끝점 계획 2용 Microsoft Defender의 최소 요구 사항에 대해 설명합니다. Endpoint 요금제 1용 Defender(미리 보기)에 대한 정보를 찾고 있는 경우 [Endpoint 요금제 1(미리 보기)에](mde-p1-setup-configuration.md#review-the-requirements)대한 요구 사항을 참조하세요.
> - Endpoint용 Defender: [Endpoint용 Defender Tech](https://techcommunity.microsoft.com/t5/Windows-Defender-Advanced-Threat/ct-p/WindowsDefenderAdvanced)Community.
> - Endpoint용 Defender는 최근 MITRE 평가에서 업계를 선도하는 광학 및 감지 기능을 보여 주었다. 읽기: [MITRE ATT&CK 기반 평가의 인사이트](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).

## <a name="licensing-requirements"></a>라이선스 요구사항

끝점용 Microsoft Defender에는 다음 Microsoft 볼륨 라이선스 제품 중 하나가 필요합니다.

- Windows 11 Enterprise E5
- Windows 11 Education A5
- Windows 10 Enterprise E5
- Windows 10 Education A5
- Microsoft 365 E5 (M365 E5)(Windows 10 Enterprise E5 또는 Windows 11 Enterprise E5 포함)
- Microsoft 365 A5(M365 A5)
- Microsoft 365 E5 Security
- Microsoft 365 A5 보안
- 끝점용 Microsoft Defender

> [!NOTE]
> 적격 라이선스 사용자는 최대 5개의 동시 장치에서 끝점용 Microsoft Defender를 사용할 수 있습니다.
> Microsoft Defender for Endpoint는 CSP(Microsoft Defender for Endpoint)에서 클라우드 솔루션 공급자 사용할 수 있습니다.
> RDSH VM에는 별도의 Endpoint용 Defender 라이선스가 필요하지 않습니다.

서버용 끝점용 Microsoft Defender에는 다음 라이선스 옵션 중 하나가 필요합니다.

- [Azure Defender가 활성화된 Azure 보안 센터](/azure/security-center/security-center-pricing)
- 서버용 Microsoft Defender for Server(대상 서버당 1개)

> [!NOTE]
> 고객은 다음 사용자 라이선스 중 하나 이상에 대해 최소 50개 이상의 라이선스를 합한 경우 서버용 끝점용 Microsoft Defender에 대한 서버 라이선스(대상 서버당 OSE(운영 체제 환경))를 취득할 수 있습니다.
>
> - 끝점용 Microsoft Defender
> - Windows E5/A5
> - Microsoft 365 E5/A5
> - E5/A5 보안 Microsoft 365

자세한 라이선스 정보는 제품 사용권 사이트를 참조하고 계정 팀과 함께 사용 약관에 대해 자세히 알아보는 방법을 참조하세요. [](https://www.microsoft.com/licensing/terms/)

Windows 에디션의 기능 배열에 대한 자세한 내용은 에디션 [비교를 Windows 참조하세요.](https://www.microsoft.com/windowsforbusiness/compare)

## <a name="browser-requirements"></a>브라우저 요구 사항

끝점용 Defender에 대한 액세스는 다음 브라우저를 지원하여 브라우저를 통해 수행됩니다.

- Microsoft Edge
- Google Chrome

> [!NOTE]
> 다른 브라우저가 작동할 수 있는 반면 언급된 브라우저는 지원되는 브라우저입니다.

## <a name="hardware-and-software-requirements"></a>하드웨어 및 소프트웨어 요구 사항

### <a name="supported-windows-versions"></a>지원되는 Windows 버전

- Windows 7 SP1[Enterprise(지원하려면 ESU가 필요합니다.)](/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq)
- Windows 7 SP1 Pro(지원을 위해[ESU가 필요합니다.)](/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq)
- Windows 8.1 Enterprise
- Windows 8.1 Pro
- Windows 11 Enterprise
- Windows 11 Education
- Windows 11 Pro
- Windows 11 Pro Education
- Windows 10 Enterprise
- [Windows 10 Enterprise LTSC 2016 이상](/windows/whats-new/ltsc/)
- Windows 10 Education
- Windows 10 Pro
- Windows 10 Pro Education
- Windows 서버
  - Windows Server 2008 R2 SP1
  - Windows Server 2012 R2
  - Windows Server 2016
  - Windows 서버, 버전 1803 이상
  - Windows Server 2019
  - Windows Server 2022
- Windows Virtual Desktop

네트워크의 장치는 이러한 버전 중 하나를 실행해야 합니다.

디바이스의 Endpoint용 Defender에 대한 하드웨어 요구 사항은 지원되는 버전에서 동일합니다.

> [!NOTE]
> 모바일 버전의 Windows(예: Windows CE 및 Windows 10 Mobile)는 지원되지 않습니다.
>
> Microsoft가 아닌 Windows 10 Enterprise 2016 LTSB 플랫폼에서 실행하면 가상 컴퓨터를 실행하는 경우 성능 문제가 발생할 수 있습니다.
>
> 가상 환경의 경우 LTSC 2019 Windows 10 Enterprise 사용하는 것이 좋습니다.

### <a name="other-supported-operating-systems"></a>기타 지원되는 운영 체제

- [Android](microsoft-defender-endpoint-android.md)
- [iOS](microsoft-defender-endpoint-ios.md)
- [Linux](microsoft-defender-endpoint-linux.md)
- [macOS](microsoft-defender-endpoint-mac.md)

> [!NOTE]
> 통합을 위해 Android, iOS 및 macOS의 Linux 배포 및 버전이 Endpoint용 Defender와 호환되는지 확인해야 합니다.

### <a name="network-and-data-storage-and-configuration-requirements"></a>네트워크 및 데이터 저장소 및 구성 요구 사항

온보딩 마법사를 처음 실행할 때 끝점 관련 정보에 대한 Microsoft Defender가 저장되는 위치(유럽 연합, 영국 또는 미국 데이터 센터)를 선택해야 합니다.

> [!NOTE]
>
> - 처음 설치한 후 데이터 저장소 위치를 변경할 수 없습니다.
> - Microsoft에서 데이터를 저장하는 위치 및 방법에 대한 자세한 내용은 Endpoint 데이터 저장소 및 개인 정보 보호를 위한 [Microsoft Defender를](data-storage-privacy.md) 검토하세요.

### <a name="diagnostic-data-settings"></a>진단 데이터 설정

> [!NOTE]
> 끝점용 Microsoft Defender는 사용하도록 설정된 경우 특정 진단 수준이 필요하지 않습니다.

조직의 모든 장치에서 진단 데이터 서비스가 사용하도록 설정되어 있는지 확인합니다.
기본적으로 이 서비스는 사용하도록 설정되어 있습니다. 센서 데이터를 얻을 수 있도록 하는 것이 좋습니다.

#### <a name="use-the-command-line-to-check-the-windows-diagnostic-data-service-startup-type"></a>명령줄을 사용하여 진단 Windows 서비스 시작 유형 확인

1. 디바이스에서 상승된 명령줄 프롬프트를 니다.
   1. **시작**(으)로 이동하고 **cmd** 를 입력하십시오.
   2. **명령 프롬프트** 을(를) 마우스 오른쪽 버튼으로 클릭하고 **관리자**(으)로 실행을 선택합니다.

2. 다음 명령을 입력하고 **Enter를 누를 수 있습니다.**

   ```console
   sc qc diagtrack
   ```

   서비스가 사용하도록 설정된 경우 결과는 다음 스크린샷과 같아야 합니다.

   ![diagtrack에 대한 sc 쿼리 명령의 결과입니다.](images/windefatp-sc-qc-diagtrack.png)

서비스가 에 로 설정되어 있지 않은  경우 START_TYPE 자동으로 시작 **AUTO_START.**

#### <a name="use-the-command-line-to-set-the-windows-diagnostic-data-service-to-automatically-start"></a>명령줄을 사용하여 Windows 진단 데이터 서비스가 자동으로 시작될 수 있도록 설정

1. 끝점에서 상승된 명령줄 프롬프트를 여는 경우:
    1. **시작**(으)로 이동하고 **cmd** 를 입력하십시오.
    2. **명령 프롬프트** 을(를) 마우스 오른쪽 버튼으로 클릭하고 **관리자**(으)로 실행을 선택합니다.

2. 다음 명령을 입력하고 **Enter를 누를 수 있습니다.**

    ```console
    sc config diagtrack start=auto
    ```

3. 성공 메시지가 표시됩니다. 다음 명령을 입력하여 변경을 확인하고 **Enter를 누르고 :**

    ```console
    sc qc diagtrack
    ```

#### <a name="internet-connectivity"></a>인터넷 연결

직접 또는 프록시를 통해 디바이스에서 인터넷에 연결해야 합니다.

Endpoint용 Defender 센서는 일별 평균 대역폭 5MB를 사용하여 Endpoint 클라우드 서비스용 Defender와 통신하고 사이버 데이터를 보고할 수 있습니다. 파일 업로드 및 조사 패키지 컬렉션과 같은 일회성 활동은 이 일별 평균 대역폭에 포함되지 않습니다.

추가 프록시 구성 설정에 대한 자세한 내용은 장치 프록시 및 인터넷 연결 설정 [구성을 참조하세요.](configure-proxy-internet.md)

장치를 온보드하기 전에 진단 데이터 서비스를 사용하도록 설정해야 합니다. 서비스는 기본적으로 11에서 Windows 10 Windows 사용하도록 설정되어 있습니다.

## <a name="microsoft-defender-antivirus-configuration-requirement"></a>Microsoft Defender 바이러스 백신 구성 요구 사항

끝점용 Defender 에이전트는 파일을 검색하고 Microsoft Defender 바이러스 백신 정보를 제공할 수 있는 기능을 사용하게 됩니다.

맬웨어 방지가 활성 상태인지 여부에 Microsoft Defender 바이러스 백신용 Defender에서 보안 인텔리전스 업데이트를 구성합니다. 자세한 내용은 업데이트 관리 [및 Microsoft Defender 바이러스 백신 적용을 참조하세요.](/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus)

조직에서 Microsoft Defender 바이러스 백신 맬웨어 방지가 아닌 경우 Endpoint용 Defender 서비스를 사용하는 경우 Microsoft Defender 바이러스 백신 모드로 전환됩니다.

조직에서 그룹 정책 또는 Microsoft Defender 바이러스 백신 방법을 통해 조직을 해제한 경우 온보드된 장치를 이 그룹 정책에서 제외해야 합니다.

서버를 온보드하고 Microsoft Defender 바이러스 백신 맬웨어 방지가 서버의 활성 맬웨어 방지가 아닌 경우 Microsoft Defender 바이러스 백신 모드로 전환하거나 제거하도록 구성해야 합니다. 구성은 서버 버전에 따라 다릅니다. 자세한 내용은 호환성 [Microsoft Defender 바이러스 백신 참조하세요.](microsoft-defender-antivirus-compatibility.md)

> [!NOTE]
> 일반 그룹 정책은 변조 방지에 적용되지 않습니다. 변조 방지가 Microsoft Defender 바이러스 백신 설정에 대한 변경 내용은 무시됩니다.

## <a name="microsoft-defender-antivirus-early-launch-antimalware-elam-driver-is-enabled"></a>Microsoft Defender 바이러스 백신 ELAM(맬웨어 방지 조기 실행) 드라이버를 사용하도록 설정

장치에서 기본 Microsoft Defender 바이러스 백신 맬웨어 방지 제품으로 실행 중인 경우 Endpoint용 Defender 에이전트가 성공적으로 온보딩됩니다.

타사 맬웨어 방지 클라이언트를 실행하고 모바일 장치 관리 솔루션 또는 Microsoft Endpoint Manager(현재 분기)를 사용하는 경우 ELAM Microsoft Defender 바이러스 백신 사용하도록 설정해야 합니다. 자세한 내용은 [정책에 Microsoft Defender 바이러스 백신 사용하지 않도록 설정되어 있지 않은지 확인을 참조하세요.](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)

## <a name="related-topics"></a>관련 항목

- [끝점 배포를 위한 Microsoft Defender 설정](production-deployment.md)
- [온보딩 장치](onboard-configure.md)
