---
title: 관리자를 위한 Application Guard for Office 365 (공용 미리 보기)
keywords: 응용 프로그램 보호, 보호, 격리, 격리 된 컨테이너, 하드웨어 격리
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: 하드웨어 기반 격리의 최신 버전을 다운로드 합니다. 악용 또는 악성 링크와 같은 현재 및 신흥 공격을 방지 하 여 직원의 생산성 및 기업 보안을 방해 하지 않도록 합니다.
ms.openlocfilehash: 3a20649338bbcd58ad86f70142c2bd9f1c2fd948
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48197576"
---
# <a name="application-guard-for-office-public-preview-for-admins"></a>관리자를 위한 Application Guard for Office (공용 미리 보기)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]



**적용 대상:** Word, Excel 및 PowerPoint for Microsoft 365, Windows 10 Enterprise

>[!IMPORTANT]
>일부 정보는 상업적으로 출시 되기 전에 크게 수정 될 수 있는 prereleased 제품과 관련 되어 있습니다. Microsoft makes no warranties, express or implied, with respect to the information provided here.


Microsoft Defender Application Guard for Office (Application Guard for office)를 사용 하면 신뢰할 수 없는 파일이 신뢰할 수 있는 리소스에 액세스 하지 못하도록 방지 하 여 기업이 새로운 공격 으로부터 안전 하 게 보호 되도록 할 수 있습니다. 이 문서에서는 Office 용 응용 프로그램 보호를 미리 볼 장치를 설정 하는 관리자를 안내 합니다. 장치에서 Office 용 Application Guard를 사용 하도록 설정 하는 시스템 요구 사항 및 설치 단계에 대 한 정보를 제공 합니다.

## <a name="prerequisites"></a>필수 구성 요소

### <a name="minimum-hardware-requirements"></a>최소 하드웨어 요구 사항

* **CPU**: 64 비트, 4 코어 (실제 또는 가상), 가상화 확장 (Intel VT-x 또는 AMD-V), 핵심 i5가 동일 하거나 더 권장 됩니다.
* **실제 메모리**: 8gb RAM
* **하드 디스크**: 시스템 드라이브에 10gb의 사용 가능한 공간 (SSD 권장)

### <a name="minimum-software-requirements"></a>최소 소프트웨어 요구 사항

* **Windows 10**: Windows 10 Enterprise Edition, 클라이언트 빌드 버전 2004 (20H1) 빌드 19041
* **Office**: Office 베타 채널 빌드 버전 2008 16.0.13212 이상
* **업데이트 패키지**: Windows 10 누적 월별 보안 업데이트 [KB4571756](https://support.microsoft.com/help/4571756/windows-10-update-KB4571756) 

시스템 요구 사항에 대 한 자세한 내용은 [Microsoft Defender Application Guard에 대 한 시스템 요구 사항을](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard)참조 하세요. Office Insider Preview 빌드에 대 한 자세한 내용은 [Office 참가자 빌드 배포 시작](https://insider.office.com/business/deploy)을 참조 하세요.

### <a name="licensing-requirements"></a>라이선스 요구 사항
* Microsoft 365 E5 또는 Microsoft 365 E5 보안

## <a name="deploy-application-guard-for-office"></a>Office 용 응용 프로그램 보호 배포

### <a name="enable-application-guard-for-office"></a>Office 용 응용 프로그램 보호 사용

1.  **Windows 10 누적 월별 보안 업데이트 KB4571756**를 다운로드 하 여 설치 합니다. 

2.  Windows 기능에서 **Microsoft Defender Application Guard** 를 선택 하 고 **확인을**선택 합니다. 응용 프로그램 보호 기능을 사용 하도록 설정 하면 시스템을 다시 부팅 하 라는 메시지가 표시 됩니다. 시작 하거나 3 단계를 수행한 후에 다시 부팅 하도록 선택할 수 있습니다.

    ![AG가 표시 된 Windows 기능 대화 상자](../../media/ag03-deploy.png)
    
    다음 PowerShell 명령을 관리자 권한으로 실행 하 여이 기능을 사용 하도록 설정할 수도 있습니다. 

    ```powershell
    Enable-WindowsOptionalFeature -online -FeatureName Windows-Defender-ApplicationGuard 
    ```

3.  **컴퓨터 구성 \\ 관리 템플릿 \\ Windows 구성 요소 \\ microsoft defender Application Guard**에 있는 관리 되는 모드 그룹 정책에서 microsoft defender application guard를 찾아보십시오. 옵션 아래의 값을 **2** 또는 **3** 으로 설정 하 고 **확인** 또는 **적용**을 선택 하 여이 정책을 설정 합니다.

    ![관리 모드에서 AG 설정](../../media/ag04-deploy.png)
  
    또는 해당 하는 CSP 정책을 설정할 수 있습니다. 

    OMA-URI: **./Device/Vendor/MSFT/WindowsDefenderApplicationGuard/Settings/AllowWindowsDefenderApplicationGuard** 
    <br>데이터 형식: **정수** 
    <br>값: **2**


4.  시스템을 재부팅 합니다.

### <a name="set-diagnostics--feedback-to-send-full-data"></a>전체 데이터를 보낼 수 있도록 진단 & 피드백 설정

이 단계를 수행 하면 문제를 식별 하 고 해결 하는 데 필요한 데이터가 Microsoft에 도달 하 게 됩니다. 다음 단계에 따라 Windows 장치에서 진단을 사용 하도록 설정 합니다.

1.  시작 메뉴에서 **설정을** 엽니다.

    ![시작 메뉴](../../media/ag05-diagnostic.png)

2.  **Windows 설정**에서 **개인 정보**를 선택 합니다.

    ![Windows 설정 메뉴](../../media/ag06-diagnostic.png)

3.  개인 정보 아래에서 **진단 & 피드백** 을 선택 하 고 **선택적 진단 데이터**를 선택 합니다.

    ![진단 및 피드백 메뉴](../../media/ag07a-diagnostic.png)

Windows 진단 설정 구성에 대 한 자세한 내용은 [조직에서 windows 진단 데이터 구성을](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enterprise-management)참조 하십시오.

### <a name="confirm-that-application-guard-for-office-is-enabled-and-working"></a>Office 용 Application Guard가 사용 하도록 설정 및 작동 하는지 확인

Office 용 응용 프로그램 보호가 사용 하도록 설정 되어 있는지 확인 하기 전에 정책이 배포 된 장치에서 Word, Excel 또는 PowerPoint를 실행 합니다. Office가 정품 인증 되었는지 확인 합니다. 먼저 회사 id를 사용 하 여 Office 제품을 정품 인증 해야 할 수도 있습니다.

이제 Office 용 Application Guard가 사용 하도록 설정 되어 있는지 확인 하려면 Word, Excel 또는 PowerPoint를 실행 하 고 신뢰할 수 없는 문서를 엽니다. 예를 들어 인터넷에서 다운로드 한 문서를 열거나 조직 외부의 사용자가 보낸 전자 메일 첨부 파일을 열 수 있습니다.

신뢰할 수 없는 파일을 처음 실행할 때 아래와 같은 Office 시작 화면이 표시 될 수 있습니다. Office 용 Application Guard가 활성화 되 고 파일이 열리는 동안 잠시 동안 표시 될 수 있습니다. 이후에 신뢰할 수 없는 파일을 시작 하는 것이 더 빠릅니다.

![Office 앱 시작 화면](../../media/ag08-confirm.png)


파일이 열릴 때 파일에는 Office 용 Application Guard에서 파일을 연 몇 가지 시각적 표시기가 표시 됩니다.

* 리본 메뉴의 설명선

    ![Small App 보호 메모를 보여 주는 문서 파일](../../media/ag09-confirm.png)
* 작업 표시줄의 방패를 포함 하는 응용 프로그램 아이콘 

    ![작업 표시줄의 아이콘](../../media/ag12-limitations.png)



## <a name="configure-application-guard-for-office"></a>Office 용 응용 프로그램 보호 구성
Office는 다음 정책을 지원 하 여 Office 용 응용 프로그램 보호 기능을 구성할 수 있도록 합니다. 이러한 정책은 그룹 정책 또는 Office 클라우드 정책 서비스를 통해 구성할 수 있습니다. 

>[!NOTE] 
> 이러한 정책은 곧 제공 될 예정입니다.
>또한 이러한 정책을 구성 하면 Office 용 Application Guard에서 열린 파일에 대 한 일부 기능을 사용 하지 않도록 설정할 수 있습니다.

| 정책                                                                          | 설명                                                                                                                                                                                                                                                                                             |
|---------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Office 용 Application Guard 사용 안 함                                            | 이 정책을 사용 하도록 설정 하면 Word, Excel 및 PowerPoint가 Office 용 응용 프로그램 보호 대신 보호 된 보기 격리 컨테이너를 사용 합니다. 이 정책을 사용 하 여에 지에 문제가 있는 경우 Office 용 Application Guard를 일시적으로 사용 하지 않도록 설정할 수 있습니다.                                  |
| Application Guard에서 연 문서에 대해 복사/붙여넣기 사용 안 함                    | 이 정책을 사용 하도록 설정 하면 사용자가 Office 용 Application Guard에서 연 문서의 콘텐츠를 복사 하 여 해당 문서 외부에서 열린 문서에 붙여 넣을 수 없습니다.                                                                                                                                   |
| 사용자가 파일에서 Application Guard 보호를 제거 하지 못하도록 차단               | 이 정책을 사용 하면 응용 프로그램 보호 기능을 사용 하지 않도록 설정 하거나 응용 프로그램 보호 외부에서 파일을 열 수 있는 옵션 (Office 응용 프로그램 환경 내)이 제거 됩니다. <br><br>**참고:** 사용자는 파일에서 웹 표시 속성을 수동으로 제거 하거나 문서를 신뢰할 수 있는 위치로 이동 하 여이 정책을 계속 무시할 수 있습니다. |
| Application Guard에서 연 문서에서 인쇄 제한                    | 이 정책을 사용 하면 사용자가 Office 용 Application Guard에서 연 파일에서 인쇄할 수 있는 프린터가 제한 됩니다. 예를 들어이 정책을 사용 하 여 사용자가 PDF로만 인쇄 하도록 제한할 수 있습니다.                              |
| Application Guard에서 열린 문서에 대해 카메라 및 마이크 액세스 끄기 | 이 정책을 사용 하면 Office 용 응용 프로그램 보호 내의 카메라 및 마이크에 대 한 Office 액세스가 제거 됩니다.                                                                                                                                                                                                     |
>[!NOTE] 
>다음 정책을 적용 하려면 사용자가 로그 오프 하 고 Windows에 다시 로그인 해야 합니다.
> 
> *  Application Guard에서 연 문서에 대해 복사/붙여넣기 사용 안 함
>*  Application Guard에서 열린 문서에 대해 인쇄 제한
> *  Application Guard에서 열린 문서에 대 한 카메라 및 마이크 액세스 끄기


## <a name="submit-feedback"></a>의견 제출

### <a name="submit-feedback-via-feedback-hub"></a>피드백 허브를 통해 피드백 제출

Office 용 응용 프로그램 보호를 시작할 때 문제가 발생 하면 피드백 허브를 통해 피드백을 제출 하는 것이 좋습니다.

1.  **의견 허브 앱** 을 열고 로그인 합니다.

2.  Application Guard를 시작 하는 동안 오류 대화 상자가 나타나면 오류 대화 상자에서 **Microsoft에 보고** 를 선택 하 여 새 피드백 제출을 시작 합니다. 그렇지 않은 경우로 이동 하 여 <https://aka.ms/wdagoffice-fb> 응용 프로그램 보호를 위한 올바른 범주를 선택한 다음 + 오른쪽 상단에 **새 의견 추가** 를 선택 합니다.

3.  사용자 의견을 **요약** 상자에 입력 합니다 (아직 채워져 있지 않은 경우).

4.  발생 한 문제에 대 한 자세한 설명과, 수행한 단계를 **자세히 설명 하** 고 **다음**을 선택 합니다.

5.  문제 옆에 있는 거품을 선택 합니다. 선택한 범주가 **보안 및 개인 정보 \> Microsoft Defender application Guard**인지 확인 하 고 **다음**을 선택 합니다.

6.  **새 의견**을 선택한 후 **다음**을 선택 합니다.

7.  문제에 대 한 추적을 수집 합니다.

    1. **내 문제 다시 만들기** 타일을 확장 합니다.

    2.  응용 프로그램 보호가 실행 되는 동안 문제가 발생 하면 Application Guard 인스턴스를 엽니다. 이렇게 하면 응용 프로그램 보호 컨테이너 내에서 추가 추적을 수집할 수 있습니다.

    3.  **녹음 시작** 을 선택 하 고 타일이 회전을 중지할 때까지 기다린 후 *녹음 중지*를 말합니다.

    4.  Application Guard에서 문제를 완전히 재현 합니다. 여기에는 응용 프로그램 보호 인스턴스를 시작 하 고 오류가 발생할 때까지 기다리거나 실행 중인 Application Guard 인스턴스에서 문제를 재현할 수 있습니다.

    5.  **녹음 중지** 타일을 선택 합니다.

    6.  제출 후 몇 분까지 실행 되는 모든 응용 프로그램 보호 인스턴스를 열린 상태로 유지 하 여 컨테이너 진단을도 수집할 수 있도록 합니다.

8.  문제와 관련 된 모든 관련 스크린샷 또는 파일을 첨부 합니다.

9.  **전송**을 선택합니다.



### <a name="submit-feedback-via-office-customer-voice"></a>Office 고객 음성을 통해 사용자 의견 제출

Office 문서를 Application Guard에서 열면 문제가 발생 하는 경우 Office 내에서 사용자 의견을 제출할 수도 있습니다. 의견을 제출 하려면 [Office 참가자](https://insider.office.com/handbook) 소개 서를 참조 하세요.

## <a name="integration-with-microsoft-defender-atp-and-office-atp"></a>Microsoft Defender ATP 및 Office ATP와의 통합

Office 용 application Guard는 Microsoft의 ATP (고급 위협 보호)와 통합 되어 격리 된 환경에서 악의적인 작업에 대 한 모니터링 및 경고를 제공 합니다.

Microsoft Defender ATP는 엔터프라이즈 네트워크가 고급 위협에 대해 예방, 감지, 조사 및 대응 하는 데 도움이 되는 보안 플랫폼입니다. 이 플랫폼에 대 한 자세한 내용을 보려면 [Microsoft Defender Advanced Threat Protection](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp) 페이지를 방문 하세요. 이 플랫폼의 온 보 딩 장치에 대 한 자세한 내용은 [온보드 장치에서 Microsoft DEFENDER ATP 서비스에](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/onboard-configure)대해 알아보세요.

Microsoft Defender ATP와 함께 작동 하도록 Office 365 ATP를 구성할 수도 있습니다. [Office 365 ATP와 Microsoft DEFENDER Atp 통합](https://docs.microsoft.com/microsoft-365/security/office-365-security/integrate-office-365-ti-with-wdatp?view=o365-worldwide)을 참조 하세요.

## <a name="limitations-and-considerations"></a>제한 및 고려 사항

* Office 용 application Guard는 신뢰할 수 없는 문서와 트러스트 된 회사 리소스, 인트라넷, 사용자의 id 및 컴퓨터에 있는 임의의 파일에 액세스 하는 기능을 격리 하는 제한 모드입니다. 따라서 사용자가 디스크에 있는 로컬 파일에서 그림을 삽입 하는 등 해당 액세스에 대 한 종속성이 있는 기능에 액세스 하려고 하면 오류가 발생 하 고 아래와 같은 메시지가 표시 됩니다. 신뢰할 수 없는 문서에서 트러스트 된 리소스에 액세스할 수 있도록 하려면 사용자가 문서에서 Application Guard 보호를 제거 해야 합니다.

    ![안전 하 게 유지 하는 데 도움이 되는 대화 상자는 사용할 수 없습니다.](../../media/ag10-limitations.png)

    >[!NOTE]    
    >파일 및 해당 원본 또는 출처를 신뢰 하는 경우에만 보호를 제거 하도록 사용자에 게 알립니다.

* Office 용 Application Guard에서 매크로 및 ActiveX 컨트롤과 같은 문서의 활성 콘텐츠를 사용할 수 없습니다. 사용자가 활성 콘텐츠를 사용 하도록 하려면 Application Guard 보호를 제거 해야 합니다.

* 네트워크 공유에서 열린 신뢰할 수 없는 파일 또는 OneDrive에서 공유 된 파일, 비즈니스용 OneDrive 또는 다른 조직에서 SharePoint Online은 Application Guard에서 읽기 전용으로 열립니다. 사용자는 이러한 파일의 로컬 복사본을 저장 하 여 계속 해 서 컨테이너에서 작업 하거나 원본 파일을 직접 사용 하도록 보호 기능을 제거할 수 있습니다.

* IRM (정보 권한 관리)으로 보호 되는 파일은 제한 된 보기에서 계속 열립니다.
* Office 용 Application Guard에서 Office 응용 프로그램에 대 한 모든 사용자 지정은 사용자가 로그 오프 한 후 다시 로그인 하거나 장치를 부팅 한 후에 유지 되지 않습니다. 

* UIA framework를 사용 하는 접근성 도구 에서만 Office 용 Application Guard에서 연 파일에 대 한 액세스 가능 환경을 제공할 수 있습니다.

* 설치 후 응용 프로그램 보호를 처음 시작할 때 네트워크 연결이 필요 합니다. 이는 응용 프로그램 보호를 통해 라이선스의 유효성을 검사 하는 데 필요 합니다.
* 문서 정보 섹션에서 *마지막으로 수정한 사람* 속성은 사용자로 서 Wdag유틸리티 계정을 표시할 수 있습니다. 데스크톱 사용자의 id가 Application Guard 컨테이너 내에서 공유 되지 않는 경우 Application Guard에 구성 된 익명 사용자입니다. 

## <a name="performance-optimizations-for-application-guard"></a>응용 프로그램 보호에 대 한 성능 최적화 

이 섹션에서는 Office 용 Application Guard에서 사용 되는 성능 최적화의 개요를 제공 합니다. 이 정보는 관리자가 응용 프로그램 가드가 사용 하도록 설정 된 경우 Office의 성능과 전체 시스템에 관련 된 사용자의 보고서를 진단 하는 데 도움이 될 수 있습니다. 

Application Guard는 가상화 된 컨테이너를 사용 하 여 신뢰할 수 없는 문서를 시스템에서 분리 합니다. 컨테이너를 만들고 응용 프로그램 보호 컨테이너를 설정 하 여 Office 문서를 열도록 하면 사용자가 신뢰할 수 없는 문서를 열 때 사용자 환경에 부정적인 영향을 줄 수 있는 성능 오버 헤드가 발생 합니다. 


사용자에 게 예상 되는 파일 열기 환경을 제공 하기 위해 응용 프로그램 가드는 시스템에서 다음 휴리스틱이 충족 될 때 논리를 사용 하 여 컨테이너를 미리 만들고, 사용자가 제한 된 보기 또는 이전 28 일 동안 응용 프로그램 가드에서 파일을 열었습니다. 

이 경험적 접근이 충족 되 면 Office는 Windows에 로그인 한 후 사용자에 대 한 응용 프로그램 보호 컨테이너를 미리 만듭니다. 이 미리 만들기 작업을 진행 중인 경우 시스템 성능이 저하 될 수 있습니다. 이 작업은 작업이 완료 되는 즉시 해결 됩니다. 


>[!NOTE] 
>컨테이너를 미리 만들기 위해 사용 하는 추론에 필요한 힌트는 사용자가 사용 하는 Office 응용 프로그램에 의해 생성 됩니다. 사용자가 응용 프로그램 보호를 사용할 수 있는 새 시스템에 Office를 설치 하는 경우 Office에서는 사용자가 시스템에서 신뢰할 수 없는 문서를 처음으로 열 때까지 컨테이너를 미리 만들지 않습니다. 사용자가 응용 프로그램 보호에서이 첫 번째 파일을 여는 데 시간이 오래 걸리는 것을 볼 수 있습니다. 

## <a name="known-issues-in-preview"></a>미리 보기의 알려진 문제

* 웹 링크 (또는)를 클릭 하면 ```http``` ```https``` 브라우저가 열리지 않습니다. 
* .NET 업데이트가 응용 프로그램 보호에서 파일이 열리지 않게 합니다. 이 문제를 해결 하기 위해 사용자는이 문제가 발생 했을 때 장치를 다시 부팅할 수 있습니다.
    [Windows Defender Application Guard 또는 Windows 샌드박스를 열려고 할 때 오류 메시지가 수신 될 때 발생](https://support.microsoft.com/help/4575917/receiving-an-error-message-when-attempting-to-open-windows-defender-ap)하는 문제에 대해 자세히 알아보세요.
