---
title: 관리자용 Office 365용 Application Guard
keywords: application guard, 보호, 격리, 격리된 컨테이너, 하드웨어 격리
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: 하드웨어 기반의 최신 고리형을 다운로드합니다. 악용 또는 악의적인 링크와 같은 현재 및 새로운 공격이 직원 생산성과 엔터프라이즈 보안을 방해하지 않도록 방지합니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d0fa6ad884c6b21457c8359cf82e32e4b8c100ba
ms.sourcegitcommit: 7ebed5810480d7c49f8ca03207b5ea84993d253f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/31/2021
ms.locfileid: "51488314"
---
# <a name="application-guard-for-office-for-admins"></a>관리자용 Office용 Application Guard

**다음에 적용됩니다.** Microsoft 365용 Word, Excel 및 PowerPoint, Windows 10 Enterprise

Microsoft Defender Application Guard for Office(Office용 Application Guard)는 신뢰할 수 없는 파일이 신뢰할 수 있는 리소스에 액세스하지 못하게 하여 새로운 공격으로부터 엔터프라이즈를 안전하게 보호합니다. 이 문서에서는 관리자에게 Office용 Application Guard의 미리 보기에 대한 디바이스 설정을 진행합니다. 디바이스에서 Office용 Application Guard를 사용하도록 설정하기 위한 시스템 요구 사항 및 설치 단계에 대한 정보를 제공합니다.

## <a name="prerequisites"></a>필수 구성 요소

### <a name="minimum-hardware-requirements"></a>최소 하드웨어 요구 사항

* **CPU**: 64비트, 4코어(실제 또는 가상), 가상화 확장(Intel VT-x OR AMD-V), Core i5 이상 권장
* **실제 메모리:** 8GB RAM
* **하드 디스크:** 시스템 드라이브에 10GB의 사용 공간(SSD 권장)

### <a name="minimum-software-requirements"></a>최소 소프트웨어 요구 사항

* **Windows 10:** Windows 10 Enterprise 버전, 클라이언트 빌드 버전 2004(20H1) 빌드 19041 이상
* **Office**: Office 현재 채널 및 월별 엔터프라이즈 채널, 빌드 버전 2011 16.0.13530.10000 이상. 32비트 및 64비트 버전의 Office가 모두 지원됩니다.
* **업데이트 패키지:** Windows 10 월별 누적 보안 업데이트 [KB4571756](https://support.microsoft.com/help/4571756/windows-10-update-KB4571756)

자세한 시스템 요구 사항은 [Microsoft Defender Application Guard의 시스템 요구 사항을 참조하세요.](/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard) 또한 가상화 기술을 사용하도록 설정하는 방법에 대한 컴퓨터 제조업체 가이드를 참조하세요.
Office 업데이트 채널에 대한 자세한 내용은 Microsoft 365 업데이트 채널 [개요를 참조하세요.](/deployoffice/overview-update-channels)

### <a name="licensing-requirements"></a>라이선스 요구 사항

* Microsoft 365 E5 또는 Microsoft 365 E5 보안

## <a name="deploy-application-guard-for-office"></a>Office용 Application Guard 배포

### <a name="enable-application-guard-for-office"></a>Office에 Application Guard 사용

1. Windows 10 월별 누적 보안 업데이트 **KB4571756를 다운로드하여 설치합니다.**

2. Windows **기능에서 Microsoft Defender Application Guard를** 선택하고 확인 을 **선택합니다.** Application Guard 기능을 사용하도록 설정하면 시스템 재부팅이 묻습니다. 지금 다시 시작하거나 3단계 후에 재부팅할 수 있습니다.

   ![AG를 보여 주며 Windows 기능 대화 상자](../../media/ag03-deploy.png)

   다음 PowerShell 명령을 관리자 권한으로 실행하여 이 기능을 사용할 수도 있습니다.

   ```powershell
   Enable-WindowsOptionalFeature -online -FeatureName Windows-Defender-ApplicationGuard
   ```

3. 컴퓨터 구성 관리 템플릿 Windows 구성 요소 **Microsoft Defender Application Guard의** 그룹 정책인 관리 모드에서 Microsoft **\\ \\ \\ Defender Application Guard를 검색합니다.** 옵션에서 값을 2 또는 **3으로** 설정한 다음 확인 또는 적용 **을** 선택하여 이 **정책을** **켜야 합니다.**

   ![관리 모드에서 AG 켜기](../../media/ag04-deploy.png)

   대신 해당 CSP 정책을 설정할 수 있습니다.

   > OMA-URI: **./Device/Vendor/MSFT/WindowsDefenderApplicationGuard/Settings/AllowWindowsDefenderApplicationGuard** <br> 데이터 형식: **정수** <br> 값: **2**

4. 시스템을 다시 시작합니다.

### <a name="set-diagnostics--feedback-to-send-full-data"></a>진단 & 피드백을 설정하여 전체 데이터 보내기

> [!NOTE]
> 이 요구 사항이 필요하지는 않습니다. 그러나 선택적 진단 데이터를 구성하면 보고된 문제를 진단하는 데 도움이 됩니다.

이 단계를 통해 문제를 식별하고 해결하는 데 필요한 데이터가 Microsoft에 도달하는지 확인할 수 있습니다. Windows 장치에서 진단을 사용하도록 설정하려면 다음 단계를 따르세요.

1. 시작 **메뉴에서** 설정을 니다.

   ![시작 메뉴](../../media/ag05-diagnostic.png)

2. **Windows 설정에서** 개인 정보를 **선택합니다.**

   ![Windows 설정 메뉴](../../media/ag06-diagnostic.png)

3. 개인 정보 보호에서 진단 및 **& 선택적** **진단 데이터를 선택합니다.**

   ![진단 및 피드백 메뉴](../../media/ag07a-diagnostic.png)

Windows 진단 설정 구성에 대한 자세한 내용은 조직에서 Windows 진단 [데이터 구성을 참조하세요.](/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enterprise-management)

### <a name="confirm-that-application-guard-for-office-is-enabled-and-working"></a>Office용 Application Guard가 사용하도록 설정되어 있으며 작동하고 있는지 확인

Office용 Application Guard를 사용하도록 설정되어 있는지 확인하기 전에 정책이 배포된 장치에서 Word, Excel 또는 PowerPoint를 실행합니다. Office가 정품 인증되어 있는지 확인합니다. 먼저 작업 ID를 사용하여 Office 제품을 정품 인증해야 할 수 있습니다.

Office용 Application Guard를 사용하도록 설정되어 있는지 확인하기 위해 Word, Excel 또는 PowerPoint를 시작한 다음, 트러설되지 않은 문서를 여는 것입니다. 예를 들어 인터넷에서 다운로드한 문서나 조직 외부의 사용자가 전자 메일 첨부 파일을 열 수 있습니다.

처음에 트러설이 없는 파일을 열면 다음 예와 같이 Office 시작 화면이 표시될 수 있습니다. Office용 Application Guard가 활성화되고 파일이 열리면서 일부 시간 동안 표시될 수 있습니다. 이후에는 더 빠르게 파일을 열 수 있습니다.

![Office 앱 시작 화면](../../media/ag08-confirm.png)

파일을 열면 파일이 Office용 Application Guard 내에서 열렸다는 몇 가지 시각적 표시기가 표시됩니다.

* 리본 메뉴의 콜아웃

  ![작은 App Guard 메모를 표시하는 Doc 파일](../../media/ag09-confirm.png)

* 작업 표시줄에 방패가 있는 응용 프로그램 아이콘

  ![작업 표시줄의 아이콘](../../media/ag12-limitations.png)

## <a name="configure-application-guard-for-office"></a>Office용 Application Guard 구성

Office에서는 Office용 Application Guard의 기능을 구성할 수 있도록 다음 정책을 지원합니다. 이러한 정책은 그룹 정책 또는 Office 클라우드 정책 서비스를 통해 [구성할 수 있습니다.](/DeployOffice/overview-office-cloud-policy-service)
User Configuration  **\\ Administrative Templates Microsoft Office \\ 2016 Security Settings Trust Center Application \\ Guard에서 \\ \\** 그룹 정책 설정을 검토하여 관리자가 설정한 구성을 참조하세요.


> [!NOTE]
> 이러한 정책을 구성하면 Office용 Application Guard에서 연 파일에 대해 일부 기능을 사용하지 않도록 설정할 수 있습니다.

|정책|설명|
|---|---|
|Office에 Application Guard를 사용하지 않습니다.|이 정책을 사용하도록 설정하면 Word, Excel 및 PowerPoint에서 Office용 Application Guard 대신 보호된 보기의 고리 컨테이너를 사용하도록 강제로 설정됩니다. 이 정책은 Microsoft Edge를 사용하도록 설정한 채로 두는 데 문제가 있는 경우 Office용 Application Guard를 일시적으로 사용하지 않도록 설정하는 데 사용할 수 있습니다.|
|Office 컨테이너 사전 만들기를 위한 Application Guard 구성|이 정책은 향상된 런타임 성능을 위해 Office 컨테이너용 Application Guard(트러크되지 않은 파일)를 미리 만들어야 하는지 여부를 판정합니다. 이 설정을 사용하면 컨테이너를 미리 만들기 전까지 계속할 일 수를 지정하거나 Office에서 기본 제공된 이후로 컨테이너를 미리 만들 수 있도록 할 수 있습니다.
|Office용 Application Guard에서 연 Office 문서의 복사/붙여넣기 허용 안 하도록 합니다.|이 정책을 사용하도록 설정하면 사용자가 Office용 Application Guard에서 연 문서의 콘텐츠를 복사하여 외부에서 연 문서에 붙여넣을 수 없습니다.|
|Office용 Application Guard에서 하드웨어 가속을 사용하지 않도록 설정|이 정책은 Office용 Application Guard에서 하드웨어 가속을 사용하여 그래픽을 렌더링할지 여부를 제어합니다. 이 설정을 사용하면 Office용 Application Guard는 소프트웨어 기반(CPU) 렌더링을 사용하며 타사 그래픽 드라이버를 로드하거나 연결된 그래픽 하드웨어와 상호 작용하지 않습니다.
|Office용 Application Guard에서 지원되지 않는 파일 형식 보호 해제|이 정책은 Office용 Application Guard가 지원되지 않는 파일 형식이 열리지 못하도록 차단할지 아니면 보호된 보기로 리디렉션할지 여부를 제어합니다.
|Office용 Application Guard에서 연 문서에 대한 카메라 및 마이크 액세스 끄기|이 정책을 사용하도록 설정하면 Office용 Application Guard 내부의 카메라 및 마이크에 대한 Office 액세스가 제거됩니다.|
|Office용 Application Guard에서 연 문서에서 인쇄 제한|이 정책을 사용하도록 설정하면 사용자가 Office용 Application Guard에서 연 파일에서 인쇄할 수 있는 프린터가 제한됩니다. 예를 들어 이 정책을 사용하여 사용자가 PDF로만 인쇄하도록 제한할 수 있습니다.|
|사용자가 파일에서 Office 보호를 위해 Application Guard를 제거하지 못하게 방지|이 정책을 사용하면 Office 응용 프로그램 환경 내에서 Office 보호를 위해 Application Guard를 사용하지 않도록 설정하거나 Office용 Application Guard 외부에서 파일을 여는 옵션이 제거됩니다. <p> **참고:** 사용자는 파일에서 웹 표시 속성을 수동으로 제거하거나 문서를 신뢰할 수 있는 위치로 이동하여 이 정책을 무시할 수 있습니다.|
|

> [!NOTE]
> 다음 정책을 적용하려면 사용자가 로그인한 후 Windows에 다시 로그인해야 합니다.
>
> * Office용 Application Guard에서 연 문서에 대해 복사/붙여넣기 사용 안
> * Office용 Application Guard에서 열 수 있는 문서에 대한 인쇄 제한
> * Office용 Application Guard에서 연 문서에 대한 카메라 및 마이크 액세스 끄기

## <a name="submit-feedback"></a>피드백 제출

### <a name="submit-feedback-via-feedback-hub"></a>피드백 허브를 통해 피드백 제출

Office용 Application Guard를 시작하면 문제가 발생하는 경우 피드백 허브를 통해 피드백을 제출하는 것이 좋습니다.

1. 피드백 허브 **앱을 열고** 로그인합니다.

2. Application Guard를 시작하는 동안 오류 대화 상자가 발생하는 경우 오류 대화 상자에서 **Microsoft에 보고를** 선택하여 새 피드백 제출을 시작하십시오. 그렇지 않은 경우 Application Guard에 대한 올바른 범주를 선택한 다음 오른쪽 상단 근처에서 새 <https://aka.ms/mdagoffice-fb> **+ &nbsp; 피드백** 추가를 선택합니다.

3. 사용자 의견이 아직  입력되지 않은 경우 요약 상자에 요약을 입력합니다.

4. 경험한 문제 및 자세한 내용 설명 상자에 수행한  단계에 대한 자세한 설명을 입력하고 다음 을 **선택합니다.**

5. 문제 옆에 있는 거품을 **선택합니다.** 선택한 범주가 보안 및 개인 정보 **\> 보호 Microsoft Defender Application Guard - Office인지 확인한 후** 다음 을 **선택합니다.**

6. 새 **피드백,** 다음 을 **선택합니다.**

7. 이 문제의 추적을 수집합니다.

   1. 내 문제 **다시 발생 타일을 확장합니다.**

   2. Application Guard가 실행되는 동안 발생하는 문제가 발생하면 Application Guard 인스턴스를 여는 것입니다. 인스턴스를 열면 Application Guard 컨테이너 내에서 추가 추적을 수집할 수 있습니다.

   3. 녹음 **시작 을** 선택하고 타일이 회전을 중지할 때까지 기다렸다가 기록 *중지라고 말합니다.*

   4. Application Guard에서 문제를 완전히 재현합니다. 다시 생성에는 Application Guard 인스턴스를 시작하려고 시도하고 실패할 때까지 기다리거나 실행 중인 Application Guard 인스턴스에서 문제를 재현하는 것이 포함됩니다.

   5. 녹음 중지 **타일을** 선택합니다.

   6. 컨테이너 진단을 수집할 수 있도록 제출 후 몇 분 동안에도 실행 중인 Application Guard 인스턴스를 열어 웁니다.

8. 문제와 관련된 스크린샷 또는 파일을 첨부합니다.

9. **전송** 을 선택합니다.

### <a name="submit-feedback-via-office-customer-voice"></a>Office Customer Voice를 통해 피드백 제출

Office 문서를 Application Guard에서 열 때 문제가 발생하는 경우 Office 내에서 피드백을 제출할 수도 있습니다. 피드백을 제출할 수 있는 [Office Insider Handbook을](https://insider.office.com/handbook) 참조합니다.

## <a name="integration-with-microsoft-defender-for-endpoint-and-microsoft-defender-for-office-365"></a>Endpoint용 Microsoft Defender 및 Office 365용 Microsoft Defender와의 통합

Office용 Application Guard는 격리된 환경에서 발생하는 악의적인 활동에 대한 모니터링 및 경고를 제공하기 위해 끝점용 Microsoft Defender와 통합되었습니다.

[Microsoft E365 E5의](/microsoft-365/security/office-365-security/safe-docs) 안전한 문서는 끝점용 Microsoft Defender를 사용하여 Office용 Application Guard에서 연 문서를 검사하는 기능입니다. 추가 보호 계층을 위해 사용자는 검사 결과가 결정될 때까지 Office용 Application Guard를 떠날 수 없습니다.

끝점용 Microsoft Defender는 엔터프라이즈 네트워크가 고급 위협을 방지, 감지, 조사 및 대응하는 데 도움이 하도록 설계된 보안 플랫폼입니다. 이 플랫폼에 대한 자세한 내용은 [끝점용 Microsoft Defender를 참조합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp) 이 플랫폼에 장치 온보딩에 대한 자세한 내용은 [끝점 서비스용 Microsoft Defender에](/windows/security/threat-protection/microsoft-defender-atp/onboard-configure)장치 온보딩을 참조합니다.

끝점용 Defender와 함께 작동하도록 Office 365용 Microsoft Defender를 구성할 수 있습니다. 자세한 내용은 Office [365용 Defender와 끝점용 Microsoft Defender 통합을 참조하세요.](integrate-office-365-ti-with-mde.md)

## <a name="limitations-and-considerations"></a>제한 사항 및 고려 사항

* Office용 Application Guard는 신뢰할 수 있는 회사 리소스, 인트라넷, 사용자의 ID 및 컴퓨터의 임의 파일에 액세스할 수 없는 신뢰할 수 없는 문서를 격리하는 보호 모드입니다. 따라서 사용자가 디스크에 로컬 파일에서 그림을 삽입하는 등 액세스에 종속된 기능에 액세스하면 액세스가 실패하고 다음 예제와 같은 프롬프트가 생성됩니다. 신뢰할 수 없는 문서가 신뢰할 수 있는 리소스에 액세스할 수 있도록 설정하려면 사용자가 문서에서 Application Guard 보호를 제거해야 합니다.

  ![안전한 유지를 위해 이 기능을 사용할 수 없는 경우를 설명하는 대화 상자](../../media/ag10-limitations.png)

  > [!NOTE]
  > 사용자가 파일과 해당 원본을 신뢰할 수 있는 경우 또는 보호가 어디에서 왔는지만 보호를 제거해보는 것이 좋습니다.

* Office용 Application Guard에서 매크로 및 ActiveX 같은 문서의 활성 콘텐츠를 사용할 수 없습니다. 사용자가 활성 콘텐츠를 사용하도록 설정하려면 Application Guard 보호를 제거해야 합니다.

* 다른 조직에서 네트워크 공유 또는 OneDrive, 비즈니스용 OneDrive 또는 SharePoint Online에서 공유한 파일 또는 네트워크 공유의 트러치되지 않은 파일은 Application Guard에서 읽기 전용으로 열립니다. 사용자는 이러한 파일의 로컬 복사본을 저장하여 컨테이너에서 작업을 계속하거나 보호 기능을 제거하여 원본 파일을 직접 사용할 수 있습니다.

* IRM(정보 권한 관리)으로 보호되는 파일은 기본적으로 차단됩니다. 사용자가 이러한 파일을 보호된 보기에서 열기 위해 관리자는 조직에서 지원되지 않는 파일 형식에 대한 정책 설정을 구성해야 합니다.

* Office용 Application Guard의 Office 응용 프로그램에 대한 사용자 지정은 사용자가 로그인한 후 또는 장치가 다시 시작된 후에도 지속되지 않습니다.

* UIA 프레임워크를 사용하는 접근성 도구만 Office용 Application Guard에서 열 수 있는 파일에 액세스할 수 있는 환경을 제공할 수 있습니다.

* 설치 후 Application Guard를 처음 시작하려면 네트워크 연결이 필요합니다. 라이선스의 유효성을 검사하려면 Application Guard에 연결해야 합니다.

* 문서의 정보 섹션에서 *마지막* 수정한 사용자 속성에 **WDAGUtilityAccount가** 사용자로 표시될 수 있습니다. WDAGUtilityAccount는 Application Guard에 구성된 익명 사용자입니다. 데스크톱 사용자의 ID는 Application Guard 컨테이너 내에서 공유되지 않습니다.

## <a name="performance-optimizations-for-application-guard-for-office"></a>Office용 Application Guard의 성능 최적화

이 섹션에서는 Office용 Application Guard에서 사용되는 성능 최적화에 대한 개요를 제공합니다. 이 정보는 관리자가 Application Guard를 사용하도록 설정한 경우 Office의 성능 또는 전체 시스템과 관련된 사용자의 보고서를 진단하는 데 도움이 될 수 있습니다.

Application Guard는 가상화된 컨테이너를 사용하여 시스템에서 트러운 문서를 격리합니다. Office 문서를 열기 위해 컨테이너를 만들고 Application Guard 컨테이너를 설정하는 프로세스에서는 사용자가 트러프되지 않은 문서를 열 때 사용자 경험에 부정적인 영향을 줄 수 있는 성능 오버헤드가 있습니다.

사용자에게 예상되는 파일 열기 환경을 제공하기 위해 Application Guard는 시스템에서 다음 경험적이 충족될 때 논리를 사용하여 컨테이너를 미리 만들 수 있습니다. 사용자가 지난 28일 동안 보호된 보기 또는 Application Guard에서 파일을 열었다는 것입니다.

이 언어가 충족될 경우 Office는 사용자가 Windows에 로그인한 후 사용자에 대한 Application Guard 컨테이너를 미리 생성합니다. 이 사전 만들기 작업이 진행 중이면 시스템에서 성능이 느려질 수 있지만 작업이 완료되면 즉시 효과가 해결됩니다.

> [!NOTE]
> 사용자가 컨테이너를 미리 만드는 데 필요한 힌트는 사용자가 컨테이너를 사용할 때 Office 응용 프로그램에 의해 생성됩니다. 사용자가 Application Guard를 사용하도록 설정된 새 시스템에 Office를 설치하는 경우 Office는 사용자가 시스템에서 처음으로 트러프되지 않은 문서를 열 때까지 컨테이너를 미리 만들지 않습니다. 사용자는 Application Guard에서 이 첫 번째 파일을 여는 데 시간이 더 오래 걸리는 것으로 관찰합니다.

## <a name="known-issues"></a>알려진 문제

* 웹 링크(또는 )를 선택하면 `http` `https` 브라우저가 열립니다.
* 현재 Application Guard를 사용하여 연 Office 문서의 RTF(서식 있는 텍스트) 콘텐츠 또는 이미지를 붙여 넣는 것은 지원되지 않습니다.
* 지원되지 않는 파일 형식 보호 정책의 기본 설정은 IRM(정보 권한 관리), CSV 또는 HTML의 지원되지 않는 지원되지 않는 파일 형식 열기 차단입니다.
* .NET을 업데이트하면 Application Guard에서 파일이 열리지 못할 수 있습니다. 이 해결로 사용자는 이 오류가 발생하면 장치를 다시 시작할 수 있습니다. 자세한 내용은 Application Guard 또는 Windows 샌드박스를 열 때 오류 [Windows Defender 수신을 통해 자세히 알아보실 수 있습니다.](https://support.microsoft.com/help/4575917/receiving-an-error-message-when-attempting-to-open-windows-defender-ap)
