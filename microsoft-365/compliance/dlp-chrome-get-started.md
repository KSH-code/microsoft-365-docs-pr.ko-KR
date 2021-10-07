---
title: Microsoft 규정 준수 확장 시작
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: Microsoft 규정 준수 확장을 준비하고 배포합니다.
ms.openlocfilehash: acfadd7ad57b12f4dabf2719457f96e96a5c3f69
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60175230"
---
# <a name="get-started-with-microsoft-compliance-extension"></a>Microsoft 규정 준수 확장 시작하기

이 절차를 사용하여 Microsoft 규정 준수 확장을 배포합니다.

## <a name="before-you-begin"></a>시작하기 전에

Microsoft 규정 준수 확장을 사용하려면 장치가 엔드포인트 DLP에 온보드되어야 합니다. DLP 또는 엔드포인트 DLP를 처음 사용하는 경우 이 문서를 검토합니다.

- [Microsoft 규정 준수 확장에 대해 알아보기](dlp-chrome-learn-about.md)
- [데이터 손실 방지에 대해 알아보기](dlp-learn-about-dlp.md)
- [DLP 정책 생성, 테스트 및 조정](create-test-tune-dlp-policy.md)
- [서식 파일에서 DLP 정책 만들기](create-a-dlp-policy-from-a-template.md)
- [끝점 데이터 손실 방지에 대한 자세한 정보](endpoint-dlp-learn-about.md)
- [끝점 데이터 손실 방지 시작](endpoint-dlp-getting-started.md)
- [Windows 10 장치용 온보딩 도구 및 방법](dlp-configure-endpoints.md)
- [끝점 DLP에 대한 장치 프록시 및 인터넷 연결 설정 구성하기](endpoint-dlp-configure-proxy.md)
- [엔드포인트 데이터 손실 방지 사용](endpoint-dlp-using.md)

### <a name="skusubscriptions-licensing"></a>SKU/구독 라이선싱

시작하기 전에 [Microsoft 365 구독](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)과 추가 기능을 확인해야 합니다. Endpoint DLP 기능에 액세스하고 사용하려면 다음 구독 또는 추가 기능 중 하나가 있어야 합니다.

- Microsoft 365 E5
- Microsoft 365 A5(EDU)
- Microsoft 365 E5 compliance
- Microsoft 365 A5 compliance
- Microsoft 365 E5 Information Protection 및 거버넌스
- Microsoft 365 A5 Information Protection 및 거버넌스

자세한 라이선싱에 대한 지침은 [보안 및 준수에 대한 Microsoft 365 라이선스 지침](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)을 참조하세요.

- 조직에는 엔드포인트 DLP에 대한 라이선스가 있어야 합니다.
- 장치에서 Windows 10 x64 빌드 1809 이상을 실행해야 합니다.
- 장치에는 Antimalware Client 버전이 4.18.2101.9 이상이 있어야 합니다. **Windows 보안** 앱을 열고, **설정** 아이콘을 선택한 다음 **정보** 를 선택하여 현재 버전을 확인합니다.


### <a name="permissions"></a>사용 권한

엔드포인트 DLP의 데이터는 [활동 탐색기](data-classification-activity-explorer.md)에서 볼 수 있습니다. 활동 탐색기에 대한 사용 권한을 부여하는 7개의 역할이 있습니다. 데이터에 액세스하는 데 사용하는 계정은 해당 역할 중 하나의 구성원이어야 합니다.

- 전역 관리자
- 준수 관리자
- 보안 관리자
- 준수 데이터 관리자
- 전역 읽기 권한자
- 보안 읽기 권한자
- 보고서 읽기 권한자

### <a name="overall-installation-workflow"></a>전체 설치 워크플로

Microsoft 규정 준수 확장 배포는 다단계 프로세스입니다. 한 번에 한 컴퓨터에 설치하거나 조직 전체의 배포를 위해 Microsoft Endpoint Manager 또는 그룹 정책을 사용할 수 있습니다.

1. [장치 준비](#prepare-your-devices)
2. [기본 설정 단일 컴퓨터 셀프호스트](#basic-setup-single-machine-selfhost)
3. [Microsoft Endpoint Manager를 사용하여 배포](#deploy-using-microsoft-endpoint-manager)
4. [그룹 정책을 사용하여 배포](#deploy-using-group-policy)
5. [확장 테스트](#test-the-extension)
6. [경고 관리 대시보드를 사용하여 Chrome DLP 경고 보기](#use-the-alerts-management-dashboard-to-viewing-chrome-dlp-alerts)
7. [활동 탐색기에서 Chrome DLP 데이터 보기](#viewing-chrome-dlp-data-in-activity-explorer)

### <a name="prepare-infrastructure"></a>인프라 준비

모니터링되는 모든 Windows 10 장치에 Microsoft 규정 준수 확장을 배포하는 경우, 허용되지 않는 앱 및 허용되지 않는 브라우저 목록에서 Google Chrome을 제거해야 합니다. 자세한 내용은 [허용되지 않는 브라우저](endpoint-dlp-using.md#unallowed-browsers)를 참조하세요. 일부 장치에만 배포하는 경우, 허용되지 않은 브라우저 또는 허용되지 않는 앱 목록에 Chrome을 남겨둘 수 있습니다. Microsoft 규정 준수 확장은 앱이 설치된 컴퓨터의 두 목록 모두의 제한을 무시합니다.

### <a name="prepare-your-devices"></a>장치 준비

1. 다음 항목의 절차를 사용하여 장치를 온보드합니다.
    1. [끝점 데이터 손실 방지 시작](endpoint-dlp-getting-started.md)
    1. [Windows 10 장치용 온보딩 도구 및 방법](dlp-configure-endpoints.md)
    1. [끝점 DLP에 대한 장치 프록시 및 인터넷 연결 설정 구성하기](endpoint-dlp-configure-proxy.md)

### <a name="basic-setup-single-machine-selfhost"></a>기본 설정 단일 컴퓨터 셀프호스트

이 방법을 사용하는 것이 좋습니다.

1. Microsoft 규정 준수 확장을 설치하려는 Windows 10 컴퓨터에 로그인하고 이 PowerShell 스크립트를 관리자로 실행합니다.

   ```powershell
   Get-Item -path "HKLM:\SOFTWARE\Microsoft\Windows Defender\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
   ```

2. [Microsoft 규정 준수 확장 - Chrome Web Store(google.com)](https://chrome.google.com/webstore/detail/microsoft-compliance-exte/echcggldkblhodogklpincgchnpgcdco)으로 이동합니다.

3. Chrome Web Store 페이지의 지침을 사용하여 확장을 설치합니다.

### <a name="deploy-using-microsoft-endpoint-manager"></a>Microsoft Endpoint Manager를 사용하여 배포

조직 전체 배포에 이 설정 방법을 사용합니다.

##### <a name="enabling-required-registry-key-via-microsoft-endpoint-manager"></a>Microsoft Endpoint Manager를 통해 필수 레지스트리 키 사용

1. 다음 내용으로 PowerShell 스크립트를 만듭니다.

    ```powershell
    Get-Item -path "HKLM:\SOFTWARE\Microsoft\Windows Defender\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
    ```

2. [Microsoft Endpoint Manager 관리 센터](https://endpoint.microsoft.com)에 로그인합니다.

3. **장치** > **스크립트** 로 이동한 다음 **추가** 를 선택합니다.

4. 메시지가 표시되면 만든 스크립트의 위치로 이동합니다.

5. 다음 설정을 선택합니다.
    1. 로그인된 자격 증명을 사용하여 이 스크립트를 실행: 아니요
    1. 스크립트 서명 검사 강제: 아니요
    1. 64비트 PowerShell 호스트에서 스크립트 실행: 예

6. 적절한 장치 그룹을 선택하고 정책을 적용합니다.

#### <a name="microsoft-endpoint-manager-force-install-steps"></a>Microsoft Endpoint Manager 강제 설치 단계

강제 설치된 확장 목록에 Microsoft 규정 준수 확장을 추가하기 전에 Chrome ADMX를 입수하는 것이 중요합니다. Microsoft Endpoint Manager의 이 프로세스에 대한 단계는 Google: [Microsoft Intune으로 Chrome 브라우저 관리 - Google Chrome Enterprise 도움말](https://support.google.com/chrome/a/answer/9102677?hl=en#zippy=%2Cstep-ingest-the-chrome-admx-file-into-intune)에 나와 있습니다.

 ADMX를 입수한 후 아래 단계를 따라 이 확장에 대한 구성 프로필을 만들 수 있습니다.

1. Microsoft Endpoint Manager 관리 센터(https://endpoint.microsoft.com))에 로그인합니다.

2. 구성 프로필로 이동합니다.

3. **프로필 만들기** 를 선택합니다.

4. **Windows 10** 을 플랫폼으로 선택합니다.

5. **사용자 지정** 을 사용자 유형으로 선택합니다.

6. **설정** 탭을 선택합니다.

7. **추가** 를 선택합니다.

8. 다음 정책 정보를 입력합니다.

    OMA-URI: `./Device/Vendor/MSFT/Policy/Config/Chrome~Policy~googlechrome~Extensions/ExtensionInstallForcelist`<br/>
    데이터 형식: `String`<br/>
    값: `<enabled/><data id="ExtensionInstallForcelistDesc" value="1&#xF000; echcggldkblhodogklpincgchnpgcdco;https://clients2.google.com/service/update2/crx"/>`

9. 만들기를 클릭합니다.

### <a name="deploy-using-group-policy"></a>그룹 정책을 사용하여 배포

Microsoft Endpoint Manager를 사용하지 않으려면 그룹 정책을 사용하여 조직 전체에 Microsoft 규정 준수 확장을 배포할 수 있습니다.

1. 장치는 그룹 정책을 통해 관리할 수 있어야 하며 모든 Chrome ADMX를 그룹 정책 중앙 저장소로 가져와야 합니다. 자세한 내용은 [Windows의 그룹 정책 관리 서식 파일에 대한 중앙 저장소를 만들고 관리하는 방법](/troubleshoot/windows-client/group-policy/create-and-manage-central-store)을 참조하세요.

2. 다음 PowerShell 명령을 사용하여 PowerShell 스크립트를 작성합니다.

    ```powershell
    Get-Item -path "HKLM:\SOFTWARE\Microsoft\Windows Defender\Miscellaneous Configuration" | New-ItemProperty -Name DlpDisableBrowserCache -Value 0 -Force
    ```

3. **그룹 정책 관리 콘솔** 을 열고 OU(조직 구성 단위)로 이동합니다.

4. 마우스 오른쪽 단추를 클릭하고 **이 도메인에 GPO를 만들고 여기에 연결** 을 선택합니다. 메시지가 표시되면 이 GPO(그룹 정책 개체)에 설명 이름을 지정하고 만들기를 완료합니다.

5. GPO를 마우스 오른쪽 단추로 클릭하고 **편집** 을 선택합니다.

6. **컴퓨터 구성** > **기본 설정** > **제어판 설정** > **예약된 작업** 으로 이동합니다.

7. 마우스 오른쪽 단추를 클릭하고 **새로 만들기** > **즉시 작업(최소 Windows 7)** 을 선택하고 새 즉시 작업을 만듭니다.

8. 작업에 이름 및 설명을 지정합니다.

9. 해당 계정을 선택하여 즉시 작업을 실행합니다(예: NT Authority).

10. **가장 높은 수준의 권한으로 실행** 을 선택합니다.

11. Windows 10에 대한 정책을 구성합니다.

12. **작업** 탭에서 **프로그램 시작** 작업을 선택합니다.

13. 1단계에서 만든 프로그램/스크립트의 경로를 입력합니다.

14. **적용** 을 선택합니다.

#### <a name="adding-the-chrome-extension-to-the-forceinstall-list"></a>ForceInstall 목록에 Chrome 확장을 추가합니다.

1. 그룹 정책 관리 편집기에서 OU로 이동합니다.

2. 다음 경로를 확장합니다. **컴퓨터/사용자 구성** > **정책** > **관리 서식 파일** > **클래식 관리 서식 파일** > **Google** > **Google Chrome** > **확장**. 이 경로는 구성에 따라 다를 수 있습니다.

3. **강제로 설치된 확장 목록을 구성** 을 선택합니다.

4. 마우스 오른쪽 단추를 클릭하고 **편집** 을 선택합니다.

5. **사용하도록 설정** 을 선택합니다.

6. **표시** 를 선택합니다.

7. **값** 에서 다음 입력을 추가합니다. `echcggldkblhodogklpincgchnpgcdco;https://clients2.google.com/service/update2/crx`

8. **확인**, **적용** 을 차례로 선택합니다.

### <a name="test-the-extension"></a>확장 테스트

#### <a name="upload-to-cloud-service-or-access-by-unallowed-browsers-cloud-egress"></a>클라우드 서비스로 업로드 또는 허용되지 않은 브라우저 Cloud Egress에서 액세스

1. 중요한 항목을 만들거나 가져오고 조직의 제한된 서비스 도메인 중 하나에 파일을 업로드합니다. 중요한 데이터는 기본 제공되는 [중요한 정보 유형](sensitive-information-type-entity-definitions.md) 또는 조직의 중요한 정보 유형 중 하나와 일치해야 합니다. 파일이 열려 있을 경우 이 작업이 허용되지 않는다는 것을 보여주는 DLP 토스트 알림을 테스트하는 장치에서 받게 됩니다.

#### <a name="testing-other-dlp-scenarios-in-chrome"></a>Chrome에서 다른 DLP 테스트 시나리오

이제 허용되지 않는 브라우저/앱 목록에서 Chrome을 제거했으므로 아래 시나리오를 테스트하여 조직의 요구 사항을 충족하는지 확인할 수 있습니다.

- 클립보드를 사용하여 중요한 항목의 데이터를 다른 문서로 복사
  - 테스트하려면 Chrome 브라우저에서 클립보드 작업에 복사되지 않도록 보호된 파일을 열고 파일에서 데이터를 복사하려고 시도합니다.
  - 예상 결과: 파일이 열려 있는 경우 이 작업이 허용되지 않는 경우를 보여 주는 DLP 토스트 알림을 받습니다.
- 문서 인쇄
  - 테스트하려면 Chrome 브라우저에서 인쇄 작업으로부터 보호되는 파일을 열고 파일을 인쇄합니다.
  - 예상 결과: 파일이 열려 있는 경우 이 작업이 허용되지 않는 경우를 보여 주는 DLP 토스트 알림을 받습니다.
- USB 이동식 미디어에 복사
  - 테스트하려면 파일을 이동식 미디어 저장소에 저장합니다.
  - 예상 결과: 파일이 열려 있는 경우 이 작업이 허용되지 않는 경우를 보여 주는 DLP 토스트 알림을 받습니다.
- 네트워크 공유 위치에 복사
  - 테스트하려면 파일을 네트워크 공유 위치에 저장합니다.
  - 예상 결과: 파일이 열려 있는 경우 이 작업이 허용되지 않는 경우를 보여 주는 DLP 토스트 알림을 받습니다.

### <a name="use-the-alerts-management-dashboard-to-viewing-chrome-dlp-alerts"></a>경고 관리 대시보드를 사용하여 Chrome DLP 경고 보기

1. [Microsoft 365 규정 준수 센터](https://compliance.microsoft.com)에서 **데이터 손실 방지** 페이지를 열고 **경고** 를 선택합니다.

2. 엔드포인트 DLP 정책에 대한 경고를 보려면 [DLP 정책을 구성하고 경고를 보는 방법](dlp-configure-view-alerts-policies.md)의 절차를 참조하세요.

### <a name="viewing-chrome-dlp-data-in-activity-explorer"></a>활동 탐색기에서 Chrome DLP 데이터 보기

1. Microsoft 365 규정 준수 센터에서 도메인에 대한 [데이터 분류 페이지](https://compliance.microsoft.com/dataclassification?viewid=overview)를 열고 **활동 탐색기** 를 선택합니다.

2. [활동 탐색기 시작하기](data-classification-activity-explorer.md)의 절차를 참조하여 엔드포인트 장치에 대한 모든 데이터에 액세스하고 테이터를 필터링합니다.

   > [!div class="mx-imgBorder"]
   > ![엔드포인트 장치에 대한 활동 탐색기 필터.](../media/endpoint-dlp-4-getting-started-activity-explorer.png)

### <a name="known-issues-and-limitations"></a>알려진 문제점 및 제한 사항

1. 클라우드 송신에 대한 오버라이드 실행은 지원되지 않습니다.
2. Incognito 모드는 지원되지 않으며 사용하지 않도록 설정해야 합니다.

## <a name="next-steps"></a>다음 단계

이제 온보딩된 장치가 있고 활동 탐색기에서 활동 데이터를 볼 수 있으므로 중요한 항목을 보호하는 DLP 정책을 만드는 다음 단계를 진행할 준비가 되었습니다.

- [엔드포인트 데이터 손실 방지 사용](endpoint-dlp-using.md)

## <a name="see-also"></a>참고 항목

- [끝점 데이터 손실 방지에 대한 자세한 정보](endpoint-dlp-learn-about.md)
- [엔드포인트 데이터 손실 방지 사용](endpoint-dlp-using.md)
- [데이터 손실 방지에 대해 알아보기](dlp-learn-about-dlp.md)
- [DLP 정책 만들기, 테스트 및 조정](create-test-tune-dlp-policy.md)
- [활동 탐색기 시작하기](data-classification-activity-explorer.md)
- [엔드포인트용 Microsoft Defender](/windows/security/threat-protection/)
- [Windows 10 컴퓨터용 온보딩 도구 및 방법](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [Microsoft 365 구독](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [Azure AD 가입 장치](/azure/active-directory/devices/concept-azure-ad-join)
- [Chromium 기반 새 Microsoft Edge 다운로드하기](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
