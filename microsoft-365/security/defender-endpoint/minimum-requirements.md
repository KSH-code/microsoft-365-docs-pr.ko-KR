---
title: 끝점용 Microsoft Defender에 대한 최소 요구 사항
description: 서비스에 대한 장치 온보드에 대한 라이선스 요구 사항 및 요구 사항 이해
keywords: 최소 요구 사항, 라이선스, 비교 표
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: c6afa48fcee80c0b8fb7ed0563264932566b6321
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185794"
---
# <a name="minimum-requirements-for-microsoft-defender-for-endpoint"></a>끝점용 Microsoft Defender에 대한 최소 요구 사항

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 끝점용 Microsoft Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


장치에 서비스를 온보드하기 위한 몇 가지 최소 요구 사항이 있습니다. 서비스에 장치를 온보드하기 위한 라이선스, 하드웨어 및 소프트웨어 요구 사항 및 기타 구성 설정에 대해 자세히 알아보습니다.

> 끝점용 Microsoft Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-minreqs-abovefoldlink)

> [!TIP]
> - Endpoint용 Defender: Endpoint 기술 커뮤니티용 [Defender의 최신 향상에 대해 자세히 알아보습니다.](https://techcommunity.microsoft.com/t5/Windows-Defender-Advanced-Threat/ct-p/WindowsDefenderAdvanced)
> - Endpoint용 Defender는 최근 MITRE 평가에서 업계를 선도하는 광학 및 감지 기능을 보여 주었다. 읽기: [MITRE ATT의 인사이트&CK 기반 평가.](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/)

## <a name="licensing-requirements"></a>라이선스 요구 사항
끝점용 Microsoft Defender에는 다음 Microsoft 볼륨 라이선스 제품 중 하나가 필요합니다.

- Windows 10 Enterprise E5
- Windows 10 Education A5
- Windows 10 Enterprise E5를 포함하는 Microsoft 365 E5(M365 E5)
- Microsoft 365 A5(M365 A5)
- Microsoft 365 E5 Security
- Microsoft 365 A5 보안
- 엔드포인트용 Microsoft Defender

> [!NOTE]
> 적격 라이선스 사용자는 최대 5개의 동시 장치에서 끝점용 Microsoft Defender를 사용할 수 있습니다.
> 끝점용 Microsoft Defender는 클라우드 솔루션 공급자(CSP)에서 구입할 수 있습니다.

서버용 끝점용 Microsoft Defender에는 다음 라이선스 옵션 중 하나가 필요합니다.

- [Azure Defender가 활성화된 Azure 보안 센터](https://docs.microsoft.com/azure/security-center/security-center-pricing)
- 서버용 Microsoft Defender for Server(대상 서버당 1개)

> [!NOTE]
> 고객은 다음 사용자 라이선스 중 하나 이상에 대해 최소 50개 이상의 라이선스를 합한 경우 서버용 끝점용 Microsoft Defender에 대한 서버 라이선스(대상 서버당 OSE(운영 체제 환경))를 취득할 수 있습니다.
>
> * 엔드포인트용 Microsoft Defender
> * Windows E5/A5
> * Microsoft 365 E5/A5
> * Microsoft 365 E5/A5 보안

자세한 라이선스 정보는 제품 사용권 사이트를 참조하고 계정 팀과 함께 사용 약관에 대해 자세히 알아보는 방법을 참조하세요. [](https://www.microsoft.com/licensing/terms/)

Windows 10 버전 기능 배열에 대한 자세한 내용은 [Windows 10 버전 비교를 참조하세요.](https://www.microsoft.com/windowsforbusiness/compare)

Windows 10 상업용 버전 비교에 대한 자세한 비교 표는 비교 [PDF 를 참조하세요.](https://wfbdevicemanagementprod.blob.core.windows.net/windowsforbusiness/Windows10_CommercialEdition_Comparison.pdf)

## <a name="browser-requirements"></a>브라우저 요구 사항
끝점용 Defender에 대한 액세스는 다음 브라우저를 지원하여 브라우저를 통해 수행됩니다.

- Microsoft Edge
- Internet Explorer 버전 11
- Google Chrome

> [!NOTE]
> 다른 브라우저가 작동할 수 있는 반면 언급된 브라우저는 지원되는 브라우저입니다.


## <a name="hardware-and-software-requirements"></a>하드웨어 및 소프트웨어 요구 사항

### <a name="supported-windows-versions"></a>지원되는 Windows 버전
- Windows 7 SP1 Enterprise(지원을 위해[ESU가 필요합니다.)](https://docs.microsoft.com/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq)
- Windows 7 SP1 Pro(지원을 위해[ESU가 필요합니다.)](https://docs.microsoft.com/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq)
- Windows 8.1 Enterprise
- Windows 8.1 Pro
- Windows 10 Enterprise
- [Windows 10 Enterprise LTSC](https://docs.microsoft.com/windows/whats-new/ltsc/)
- Windows 10 Education
- Windows 10 Pro
- Windows 10 Pro Education
- Windows 서버
  - Windows Server 2008 R2 SP1
  - Windows Server 2012 R2
  - Windows Server 2016
  - Windows Server, 버전 1803 이상
  - Windows Server 2019
- Windows Virtual Desktop

네트워크의 장치는 이러한 버전 중 하나를 실행해야 합니다.

디바이스의 Endpoint용 Defender에 대한 하드웨어 요구 사항은 지원되는 버전에서 동일합니다.

> [!NOTE]
> 모바일 버전의 Windows(예: Windows CE 및 Windows 10 Mobile)를 실행하는 컴퓨터는 지원되지 않습니다.
>
> Windows 10 Enterprise 2016 LTSB를 실행하는 가상 컴퓨터는 비 Microsoft 가상화 플랫폼에서 실행되는 경우 성능 문제가 발생할 수 있습니다.
>
> 가상 환경의 경우 Windows 10 Enterprise LTSC 2019 이상을 사용하는 것이 좋습니다.


### <a name="other-supported-operating-systems"></a>기타 지원되는 운영 체제
- Android
- Linux
- macOS

> [!NOTE]
> 통합을 위해 Endpoint용 Defender와 호환되는 정확한 Linux 배포 및 Android 및 macOS 버전을 알아야 합니다.



### <a name="network-and-data-storage-and-configuration-requirements"></a>네트워크 및 데이터 저장소 및 구성 요구 사항
온보딩 마법사를 처음 실행할 때 끝점 관련 정보에 대한 Microsoft Defender가 저장되는 위치(유럽 연합, 영국 또는 미국 데이터 센터)를 선택해야 합니다.

> [!NOTE]
> - 처음 설치한 후 데이터 저장소 위치를 변경할 수 없습니다.
> - Microsoft에서 데이터를 저장하는 위치 및 방법에 대한 자세한 내용은 Endpoint 데이터 저장소 및 개인 정보 보호를 위한 [Microsoft Defender를](data-storage-privacy.md) 검토하세요.


### <a name="diagnostic-data-settings"></a>진단 데이터 설정

> [!NOTE]
> 끝점용 Microsoft Defender는 사용하도록 설정된 경우 특정 진단 수준이 필요하지 않습니다.

조직의 모든 장치에서 진단 데이터 서비스가 사용하도록 설정되어 있는지 확인합니다.
기본적으로 이 서비스는 사용하도록 설정되어 있습니다. 센서 데이터를 얻을 수 있도록 하는 것이 좋습니다.

**명령줄을 사용하여 Windows 10 진단** 데이터 서비스 시작 유형을 확인할 수 있습니다.

1. 디바이스에서 상승된 명령줄 프롬프트를 니다.

   1.  **시작**(으)로 이동하고 **cmd** 를 입력하십시오.

   1.  **명령 프롬프트** 을(를) 마우스 오른쪽 버튼으로 클릭하고 **관리자**(으)로 실행을 선택합니다.

2. 다음 명령을 입력하고 **Enter를 누를 수 있습니다.**

   ```console
   sc qc diagtrack
   ```

   서비스가 사용하도록 설정된 경우 결과는 다음 스크린샷과 같아야 합니다.

   ![diagtrack에 대한 sc 쿼리 명령의 결과](images/windefatp-sc-qc-diagtrack.png)


서비스가 에 대해 로 설정되지 않은  경우 START_TYPE 자동으로 시작 **AUTO_START.**


**명령줄을 사용하여 Windows 10 진단 데이터 서비스가 자동으로 시작될 수 있도록 설정합니다.**

1.  끝점에서 상승된 명령줄 프롬프트를 여는 경우:

    1. **시작**(으)로 이동하고 **cmd** 를 입력하십시오.

    1. **명령 프롬프트** 을(를) 마우스 오른쪽 버튼으로 클릭하고 **관리자**(으)로 실행을 선택합니다.

2.  다음 명령을 입력하고 **Enter를 누를 수 있습니다.**

    ```console
    sc config diagtrack start=auto
    ```

3.  성공 메시지가 표시됩니다. 다음 명령을 입력하여 변경을 확인하고 **Enter를 누르고 :**

    ```console
    sc qc diagtrack
    ```


#### <a name="internet-connectivity"></a>인터넷 연결
직접 또는 프록시를 통해 디바이스에서 인터넷에 연결해야 합니다.

Endpoint용 Defender 센서는 일별 평균 대역폭 5MB를 사용하여 Endpoint 클라우드 서비스용 Defender와 통신하고 사이버 데이터를 보고할 수 있습니다. 파일 업로드 및 조사 패키지 컬렉션과 같은 일회성 활동은 이 일별 평균 대역폭에 포함되지 않습니다.

추가 프록시 구성 설정에 대한 자세한 내용은 장치 프록시 및 인터넷 연결 설정 [구성을 참조하세요.](configure-proxy-internet.md)

장치를 온보드하기 전에 진단 데이터 서비스를 사용하도록 설정해야 합니다. 서비스는 Windows 10에서 기본적으로 사용하도록 설정되어 있습니다.


## <a name="microsoft-defender-antivirus-configuration-requirement"></a>Microsoft Defender 바이러스 백신 구성 요구 사항
Endpoint용 Defender 에이전트는 Microsoft Defender 바이러스 백신이 파일을 검색하고 해당 파일에 대한 정보를 제공하는 기능을 사용하는지 여부에 따라 달라 습니다.

Microsoft Defender 바이러스 백신이 활성 맬웨어 방지인지 여부에 관계 없는 끝점 장치용 Defender에서 보안 인텔리전스 업데이트를 구성합니다. 자세한 내용은 Microsoft Defender 바이러스 백신 업데이트 관리 및 [기준 적용을 참조하세요.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus)

Microsoft Defender 바이러스 백신이 조직에서 활성 맬웨어 방지가 아니고 Endpoint 서비스용 Defender를 사용하는 경우 Microsoft Defender 바이러스 백신은 수동 모드로 전환됩니다.

조직에서 그룹 정책 또는 기타 방법을 통해 Microsoft Defender 바이러스 백신을 해제한 경우 온보딩된 장치를 이 그룹 정책에서 제외해야 합니다.

온보딩 서버가 Microsoft Defender 바이러스 백신이 서버에서 활성 맬웨어 방지가 아닌 경우 수동 모드로 전환하거나 제거하도록 Microsoft Defender 바이러스 백신을 구성해야 합니다. 구성은 서버 버전에 따라 다릅니다. 자세한 내용은 [Microsoft Defender 바이러스 백신 호환성을 참조하세요.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus-compatibility.md)

> [!NOTE]
> 일반 그룹 정책은 변조 방지에 적용되지 않습니다. 변조 방지가 설정될 때 Microsoft Defender 바이러스 백신 설정에 대한 변경 내용은 무시됩니다.


## <a name="microsoft-defender-antivirus-early-launch-antimalware-elam-driver-is-enabled"></a>Microsoft Defender 바이러스 백신 ELAM(맬웨어 방지 조기 실행) 드라이버가 사용하도록 설정되어 있습니다.
장치에서 Microsoft Defender 바이러스 백신을 기본 맬웨어 방지 제품으로 실행하는 경우 끝점용 Defender 에이전트가 성공적으로 온보딩됩니다.

타사 맬웨어 방지 클라이언트를 실행하고 모바일 장치 관리 솔루션 또는 Microsoft Endpoint Manager(현재 분기)를 사용하는 경우 Microsoft Defender 바이러스 백신 ELAM 드라이버를 사용하도록 설정해야 합니다. 자세한 내용은 정책에서 Microsoft Defender 바이러스 백신이 사용하지 [않도록 설정되지 않은지 확인을 참조하세요.](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)


## <a name="related-topics"></a>관련 항목
- [끝점 배포를 위한 Microsoft Defender 설정](production-deployment.md)
- [장치 온보드](onboard-configure.md)
