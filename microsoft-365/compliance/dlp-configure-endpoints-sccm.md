---
title: Configuration Manager를 사용 하는 온보드 Windows 10 장치
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Configuration Manager를 사용 하 여 장치에 구성 패키지를 배포 하 여 서비스에 등록 되도록 합니다.
ms.openlocfilehash: ea1b0cba10dc3e7120192e0c0ee87e2e354f1cc2
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769476"
---
# <a name="onboard-windows-10-devices-using-configuration-manager"></a>Configuration Manager를 사용 하는 온보드 Windows 10 장치

**적용 대상:**

- [Microsoft 365 Endpoint data 손실 방지 (DLP)](/microsoft-365/compliance/endpoint-dlp-learn-about)
- System Center 2012 R2 Configuration Manager

### <a name="onboard-devices-using-system-center-configuration-manager"></a>System Center Configuration Manager를 사용 하는 온보드 장치

1. 서비스 온 보 딩 마법사에서 다운로드 한 Configuration Manager 구성 패키지 .zip 파일 ( *DeviceComplianceOnboardingPackage.zip* )을 엽니다. [Microsoft 준수 센터](https://compliance.microsoft.com/)에서 패키지를 가져올 수도 있습니다.

2. 탐색 창에서 **설정**  >  **장치 온 보**  >  **딩 온** 을 선택 합니다.

3. **배포 방법** 필드에서 **Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602** 을 선택 합니다.
 
4. **패키지 다운로드** 를 선택 하 고 .zip 파일을 저장 합니다.

5. 패키지를 배포할 네트워크 관리자가 액세스할 수 있는 공유, 읽기 전용 위치에 .zip 파일의 내용을 추출 합니다. *Devicecomplianceonboardingscript* 라는 파일이 있어야 합니다.

6. [System Center 2012 R2 Configuration Manager 문서의 패키지 및 프로그램](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\)) 에 나와 있는 단계에 따라 패키지를 배포 합니다.

7. 패키지를 배포할 미리 정의 된 장치 모음을 선택 합니다.

> [!NOTE]
> Microsoft 365 Endpoint data 손실 방지는 [OOBE (기본 제공 경험)](https://answers.microsoft.com/en-us/windows/wiki/windows_10/how-to-complete-the-windows-10-out-of-box/47e3f943-f000-45e3-8c5c-9d85a1a0cf87) 단계 중에 온 보 딩을 지원 하지 않습니다. Windows 설치 또는 업그레이드를 실행 한 후 사용자에 게 OOBE가 완료 되었는지 확인 합니다.

>[!TIP]
> 장치를 온 보 딩 한 후에는 검색 테스트를 실행 하 여 장치가 제대로 등록 서비스에 올바르게 작동 하는지 확인할 수 있습니다. 자세한 내용은 [새로 등록 Microsoft DEFENDER ATP 장치에서 검색 테스트 실행](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)을 참조 하십시오.
>
> 장치가 등록 된 경우 Configuration Manager 응용 프로그램에 대 한 검색 규칙이 계속 해 서 확인 되도록 만들 수 있습니다. 응용 프로그램은 패키지와 프로그램에 해당 하는 것과 다른 유형의 개체입니다.
> 장치가 아직 등록 되지 않은 경우 (OOBE 완료 또는 기타 이유로 인해) Configuration Manager는 규칙이 상태 변경을 감지할 때까지 장치를 다시 활성화 합니다.
> 
> "OnboardingState" 레지스트리 값 (REG_DWORD 유형) = 1 인 경우 검색 규칙 확인을 만들어이 동작을 수행할 수 있습니다.
> 이 레지스트리 값은 "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status" 아래에 있습니다.
자세한 내용은 [System Center 2012 R2 Configuration Manager에서 검색 방법 구성을](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682159\(v=technet.10\)#step-4-configure-detection-methods-to-indicate-the-presence-of-the-deployment-type)참조 하세요.

### <a name="configure-sample-collection-settings"></a>예제 모음 설정 구성

각 장치에 대해 구성 값을 설정 하 여 Microsoft Defender 보안 센터를 통해 요청을 수행할 때 심층 분석을 위해 파일을 전송 하도록 장치에서 샘플을 수집할 수 있는지 여부를 설정할 수 있습니다.

>[!NOTE]
>이러한 구성 설정은 일반적으로 Configuration Manager를 통해 수행 됩니다. 

구성 관리자에서 구성 항목에 대 한 준수 규칙을 설정 하 여 장치에 대 한 예제 공유 설정을 변경할 수 있습니다.

이 규칙은 대상 장치에 대 한 레지스트리 키의 값을 설정 하는 *수정* 규정 준수 규칙 구성 항목 이어야 합니다.

구성은 다음 레지스트리 키 항목을 통해 설정 됩니다.

```
Path: “HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection”
Name: "AllowSampleCollection"
Value: 0 or 1
```
여기서,<br>
키 유형이 D 단어입니다. <br>
가능한 값은 다음과 같습니다.
- 0-이 장치에서의 예제 공유 허용 안 합니다.
- 1-이 장치에서 모든 파일 형식을 공유할 수 있습니다.

레지스트리 키가 없는 경우의 기본값은 1입니다.

System Center Configuration Manager 준수에 대 한 자세한 내용은 [System center 2012 R2 Configuration Manager의 준수 설정 소개](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\))를 참조 하세요.


## <a name="other-recommended-configuration-settings"></a>기타 권장 되는 구성 설정
서비스에 온 보 딩 장치를 설치한 후에는 다음과 같은 권장 구성 설정을 사용 하 여 포함 된 위협 방지 기능을 활용 하는 것이 중요 합니다.

### <a name="device-collection-configuration"></a>장치 모음 구성
끝점 구성 관리자, 버전 2002 이상을 사용 중인 경우에는 서버 또는 하위 수준 클라이언트를 포함 하도록 배포를 넓힐 수 있습니다.


### <a name="next-generation-protection-configuration"></a>차세대 보호 구성

권장 되는 구성 설정은 다음과 같습니다.

**스캔**

- USB 드라이브와 같은 이동식 저장 장치 검사: 예

**실시간 보호**

- 동작 모니터링 사용: 예
- 다운로드 및 설치 전에 잠재적으로 원치 않는 응용 프로그램에 대 한 보호 사용: 예

**클라우드 보호 서비스**

- 클라우드 보호 서비스 멤버 자격 유형: 고급 멤버 자격

**공격 노출 영역 감소** 사용 가능한 모든 규칙을 감사 하도록 구성 합니다.

>[!NOTE]
> 이러한 활동을 차단 하면 합법적인 비즈니스 프로세스가 중단 될 수 있습니다. 가장 좋은 방법은 모든 내용을 감사로 설정 하 여 안전 하 게 켤 수 있는 것을 식별 한 다음 가양성 검색을 수행 하지 않는 끝점에서 해당 설정을 사용 하는 것입니다.

**네트워크 보호**

감사 또는 차단 모드에서 네트워크 보호를 사용 하도록 설정 하기 전에 [지원 페이지](https://support.microsoft.com/en-us/help/4560203/windows-defender-anti-malware-platform-binaries-are-missing)에서 구할 수 있는 맬웨어 방지 플랫폼 업데이트를 설치 했는지 확인 합니다.


**제어 되는 폴더 액세스**

최소 30 일 동안 감사 모드에서 기능을 사용 하도록 설정 합니다. 이 기간 후에 검색을 검토 하 고 보호 된 디렉터리에 쓸 수 있는 응용 프로그램 목록을 만듭니다.

자세한 내용은 제어 되는 [폴더 액세스 평가](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/evaluate-controlled-folder-access)를 참조 하세요.


## <a name="offboard-devices-using-configuration-manager"></a>Offboard 장치 사용 구성 관리자

보안상의 이유로, 보드 장치에 사용 된 패키지는 다운로드 한 날짜 로부터 30 일 후에 만료 됩니다. 만료 된 오프 보 딩 패키지가 장치로 전송 됩니다. 오프 보 딩 패키지를 다운로드 하면 패키지 만료 날짜에 대 한 알림을 받게 되며 패키지 이름에도 포함 됩니다.

> [!NOTE]
> 온 보 딩 및 오프 보 딩 정책은 동시에 같은 장치에 배포 해서는 안 되며 그렇지 않으면 예기치 않은 충돌이 발생 합니다.

### <a name="offboard-devices-using-microsoft-endpoint-configuration-manager-current-branch"></a>Microsoft Endpoint Configuration Manager 현재 분기를 사용 하는 offboard 장치

Microsoft Endpoint Configuration Manager 현재 분기를 사용 하는 경우에 [는 오프 보 딩 구성 파일 만들기](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#create-an-offboarding-configuration-file)를 참조 하세요.

### <a name="offboard-devices-using-system-center-2012-r2-configuration-manager"></a>System Center 2012 R2 Configuration Manager를 사용 하는 offboard 장치

1. [Microsoft 준수 센터](https://compliance.microsoft.com/)에서 오프 보 딩 패키지를 다운로드 합니다.

2. 탐색 창에서 **설정**  >   **장치 온 보** 딩을 선택 >  **Offboarding** 합니다.

3. 운영 체제로 Windows 10을 선택 합니다.

4. **배포 방법** 필드에서 **Microsoft Endpoint Configuration Manager 2012/2012 R2/1511/1602** 을 선택 합니다.
    
5. **패키지 다운로드** 를 선택 하 고 .zip 파일을 저장 합니다.

6. 패키지를 배포할 네트워크 관리자가 액세스할 수 있는 공유, 읽기 전용 위치에 .zip 파일의 내용을 추출 합니다. *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD* 라는 파일이 있어야 합니다.

7. [System Center 2012 R2 Configuration Manager 문서의 패키지 및 프로그램](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg699369\(v=technet.10\)) 에 나와 있는 단계에 따라 패키지를 배포 합니다.

8. 패키지를 배포할 미리 정의 된 장치 모음을 선택 합니다.

> [!IMPORTANT]
> 오프 보 딩은 장치에서 포털에 센서 데이터를 전송 하지 않고 장치에서 가져온 데이터에 대 한 참조를 포함 하 여 최대 6 개월 동안 보존 되도록 합니다.


## <a name="monitor-device-configuration"></a>장치 구성 모니터링

Microsoft Endpoint Configuration Manager 현재 분기를 사용 중인 경우 Configuration Manager 콘솔에서 기본 제공 되는 Microsoft Defender ATP 대시보드를 사용 합니다. 자세한 내용은 [Microsoft Defender Advanced Threat Protection-모니터](https://docs.microsoft.com/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection#monitor)를 참조 하세요.

System Center 2012 R2 Configuration Manager를 사용 하는 경우 모니터링은 다음 두 부분으로 구성 됩니다.

1. 네트워크의 장치에서 구성 패키지가 올바르게 배포 되었으며 실행 중이거나 성공적으로 실행 되 고 있는지 확인

2. 장치가 Microsoft 365 끝점 데이터 손실 방지 서비스와 호환 되는지 확인 (장치에서 온 보 딩 프로세스를 완료 하 여 서비스에 대 한 데이터를 계속 보고할 수 있는지 확인)

### <a name="confirm-the-configuration-package-has-been-correctly-deployed"></a>구성 패키지가 올바르게 배포 되었는지 확인

1. Configuration Manager 콘솔의 탐색 창 아래쪽에서 **모니터링** 을 클릭 합니다.

2. **개요** 를 선택한 다음 **배포** 를 선택 합니다.

3. 패키지 이름을 사용 하 여 배포를 선택 합니다.

4. **완료 통계** 및 **콘텐츠 상태** 에서 상태 표시기를 검토 합니다.

    배포에 실패 한 경우 ( **오류가 발생** 한 장치, **요구 사항이 충족 되지** 않거나 **실패 한 상태** )가 있으면 장치 문제를 해결 해야 할 수 있습니다. 자세한 내용은 [Microsoft Defender Advanced Threat Protection 온 보 딩 문제 해결](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)을 참조 하세요.

    ![오류 없이 성공적인 배포를 보여 주는 Configuration Manager](../media/sccm-deployment.png)

### <a name="check-that-the-devices-are-compliant-with-the-microsoft-365-endpoint-data-loss-prevention-service"></a>장치가 Microsoft 365 끝점 데이터 손실 방지 서비스와 호환 되는지 확인 합니다.

System Center 2012 R2 Configuration Manager에서 구성 항목에 대 한 준수 규칙을 설정 하 여 배포를 모니터링할 수 있습니다.

> [!NOTE]
> 이 절차와 레지스트리 항목은 Advanced Threat Protection 뿐만 아니라 끝점 DLP에도 적용 됩니다.

이 규칙은 대상 장치에서 레지스트리 키의 값을 모니터링 하는 *비 수정* 규정 준수 규칙 구성 항목 이어야 합니다.

다음 레지스트리 키 항목을 모니터링 합니다.
```
Path: “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status”
Name: “OnboardingState”
Value: “1”
```
자세한 내용은 [System Center 2012 R2 Configuration Manager의 준수 설정 소개](https://docs.microsoft.com/previous-versions/system-center/system-center-2012-R2/gg682139\(v=technet.10\))를 참조 하세요.

## <a name="related-topics"></a>관련 항목
- [그룹 정책을 사용 하는 온보드 Windows 10 장치](dlp-configure-endpoints-gp.md)
- [모바일 장치 관리 도구를 사용 하는 온보드 Windows 10 장치](dlp-configure-endpoints-mdm.md)
- [로컬 스크립트를 사용 하는 온보드 Windows 10 장치](dlp-configure-endpoints-script.md)
- [온보드 VDI (가상 데스크톱 인프라) 장치 (비영구)](dlp-configure-endpoints-vdi.md)
- [새로 등록 Microsoft Defender ATP 장치에서 검색 테스트 실행](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [Microsoft Defender Advanced Threat Protection 온 보 딩 문제 해결](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
