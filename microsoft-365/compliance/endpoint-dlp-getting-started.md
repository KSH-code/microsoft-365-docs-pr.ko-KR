---
title: Microsoft 365 엔드포인트 데이터 손실 방지 시작하기
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
description: Microsoft 365 Endpoint 데이터 손실 방지를 설정하여 파일 활동을 모니터링하고 해당 파일에 대한 보호 작업을 엔드포인트에 구현합니다.
ms.openlocfilehash: f6790e3c9af833c6e9e9103f68b91730c475cfb8
ms.sourcegitcommit: dc26169e485c3a31e1af9a5f495be9db75c49760
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60754860"
---
# <a name="get-started-with-endpoint-data-loss-prevention"></a>엔드포인트 데이터 손실 방지 시작하기

Microsoft Endpoint 데이터 손실 방지(Endpoint DLP)는 Microsoft 365 서비스에서 중요 한 항목을 검색하고 보호하는 데 사용할 수 있는 Microsoft 365의 DLP(데이터 손실 방지) 제품군의 일부입니다. 모든 Microsoft DLP 제공에 대한 자세한 내용은 [데이터 손실 방지에 대해 알아보기](dlp-learn-about-dlp.md)를 참조하세요. 끝점 DLP에 대해 자세히 알아보려면 [끝점 데이터 손실 방지](endpoint-dlp-learn-about.md)를 참조하세요.

Microsoft Endpoint DLP를 사용하면 Catalina 10.15 이상을 실행하는 Windows 10 장치 및 macOS 장치 *(미리 보기)* 를 모니터링할 수 있습니다. 장치가 온보딩되면 DLP는 민감한 항목이 사용 및 공유되는 시기를 감지합니다. 이를 통해 중요한 항목이 올바르게 사용되며 보호하고 위험을 초래할 수 있는 위험한 행동을 방지하는 데 필요한 가시성과 제어 기능을 제공합니다.

## <a name="before-you-begin"></a>시작하기 전에

### <a name="skusubscriptions-licensing"></a>SKU/구독 라이선싱

Endpoint DLP를 시작하기 전에 [Microsoft 365 구독](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)과 추가 기능을 확인해야 합니다. Endpoint DLP 기능에 액세스하고 사용하려면 다음 구독 또는 추가 기능 중 하나가 있어야 합니다.

- Microsoft 365 E5
- Microsoft 365 A5(EDU)
- Microsoft 365 E5 compliance
- Microsoft 365 A5 compliance
- Microsoft 365 E5 Information Protection 및 거버넌스
- Microsoft 365 A5 Information Protection 및 거버넌스

### <a name="permissions"></a>권한

장치 관리를 사용하도록 설정하려면 사용하는 계정이 다음 역할 중 하나의 구성원이어야 합니다.

- 전역 관리자
- 보안 관리자
- 준수 관리자

사용자 지정 계정을 사용하여 장치 관리 설정을 보려면 계정이 다음 역할 중 하나여야 합니다.

- 전역 관리자
- 준수 관리자
- 준수 데이터 관리자
- 전역 읽기 권한자

사용자 지정 계정을 사용하여 온보딩/오프보딩 페이지에 액세스하려면 계정이 다음 역할 중 하나여야 합니다.

- 전역 관리자
- 준수 관리자

사용자 지정 계정을 사용하여 장치 모니터링을 설정/해제하려면 계정이 다음 역할 중 하나여야 합니다.

- 전역 관리자
- 준수 관리자

Endpoint DLP의 데이터는 [활동 탐색기](data-classification-activity-explorer.md)에서 볼 수 있습니다. 활동 탐색기에 대한 사용 권한을 부여하는 네 개의 역할이 있습니다. 데이터에 액세스하는 데 사용하는 계정은 해당 역할 중 하나의 구성원이어야 합니다.

- 전역 관리자
- 준수 관리자
- 보안 관리자
- 준수 데이터 관리자

### <a name="prepare-your-windows-10-endpoints"></a>Windows 10 엔드포인트 준비

Endpoint DLP를 배포하는 데 사용할 Windows 10 장치가 다음 요구 사항을 충족하는지 확인하세요.

1. Windows 10 x64 빌드 1809 이상을 실행해야 합니다.

1. 맬웨어 방지 클라이언트 버전이 4.18.2009.7 이상입니다. Windows 보안 앱을 열고, 설정 아이콘을 선택한 다음 정보를 선택하여 현재 버전을 확인합니다. 버전 번호는 맬웨어 방지 클라이언트 버전 아래에 나열됩니다. Windows 업데이트 KB4052623을 설치하여 최신 맬웨어 방지 클라이언트 버전으로 업데이트합니다.

   > [!NOTE]
   > Windows 보안 구성 요소가 활성화되지 않아도 Windows 보안 상태와 독립적으로 끝점 DLP를 실행할 수 있습니다. 그러나 [실시간 보호 및 동작 모니터](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus)는 활성화되어야 합니다.

1. 다음 Windows 업데이트가 설치되어 있습니다.

   > [!NOTE]
   > 참고: 이 업데이트는 장치를 끝점 DLP로 온보딩하기 위한 필수 요건은 아니지만, 중요한 문제에 대한 수정을 포함하므로 제품을 사용하기 전에 설치해야 합니다.

   - Windows 10 1809의 경우 - KB4559003, KB4577069, KB4580390
   - Windows 10 1903 혹은 1909의 경우 - KB4559004, KB4577062, KB4580386
   - Windows 10 2004의 경우 - KB4568831, KB4577063
   - Office 2016(다른 Office 버전이 아님)을 실행하는 장치의 경우 - KB4577063

1. 모든 장치는 다음 중 하나에 해당해야 합니다.

   - [Azure AD(Azure Active Directory) 조인됨](/azure/active-directory/devices/concept-azure-ad-join)
   - [하이브리드 Azure AD 조인됨](/azure/active-directory/devices/concept-azure-ad-join-hybrid)
   - [AAD 등록됨](/azure/active-directory/user-help/user-help-register-device-on-network)

1. 엔드 포인트 장치에 Microsoft Chromium Edge 브라우저를 설치하여 클라우드로 업로드 활동에 대한 정책 작업을 적용하세요. [Chromium 기반 새 Microsoft Edge 다운로드하기](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)를 참조하세요. 장치에서 Chrome 브라우저를 사용하는 경우 [Microsoft 규정 준수 확장 프로그램](dlp-chrome-learn-about.md#learn-about-the-microsoft-compliance-extension)을 설치하여 클라우드 활동에 업로드하기 위한 정책 작업을 시행할 수 있습니다.

1. Microsoft 365 앱 버전 2004~2008의 월 단위 엔터프라이즈 채널을 사용하고 있는 경우 Office 콘텐츠를 분류하는 엔드포인트 DLP와 관련된 알려진 문제가 있으며 버전 2009 이상으로 업데이트해야 합니다. 현재 버전에 대한 자세한 내용은 [Microsoft 365 앱의 업데이트 기록(날짜순)](/officeupdates/update-history-microsoft365-apps-by-date)을 참조하세요. 해당 문제에 대한 자세한 내용을 보려면 [2020년 현재 채널 릴리스에 대한 릴리스 노트](/officeupdates/current-channel#version-2010-october-27)의 Office 제품군 섹션을 참조하세요.

1. 장치 프록시를 사용하여 인터넷에 연결하는 끝점이 있는 경우 [끝점 DLP에 대한 장치 프록시 및 인터넷 연결 설정 구성](endpoint-dlp-configure-proxy.md)의 절차를 따르세요.

## <a name="prepare-your-macos-devices-preview"></a>macOS 장치 준비(미리 보기)

[MacOS 장치를 Microsoft 365에 온보드 개요(미리 보기)](device-onboarding-macos-overview.md#onboard-macos-devices-into-microsoft-365-overview-preview)를 참조하세요.

## <a name="onboarding-windows-10-devices-into-device-management"></a>장치 관리에 Windows 10 장치 온보딩

장치에서 중요한 항목을 모니터링하고 보호하려면 장치 모니터링을 사용하도록 설정하고 엔드포인트를 온보딩해야 합니다. 이러한 작업은 모두 Microsoft 365 규정 준수 포털에서 수행됩니다.

아직 온보딩되지 않은 장치를 온보딩하려는 경우 적절한 스크립트를 다운로드하여 해당 장치에 배포합니다. [장치 온보딩 절차](endpoint-dlp-getting-started.md#onboarding-devices)를 따르세요.

이미 [엔드포인트용 Microsoft Defender](/windows/security/threat-protection/)에 온보딩된 장치가 있으면 해당 장치가 관리되는 장치 목록에 표시됩니다. [엔드포인트용 Microsoft Defender에 온보딩된 장치 절차](?source=docs&view=o365-worldwide#with-devices-onboarded-into-microsoft-defender-for-endpoint)를 따릅니다.

### <a name="onboarding-devices"></a>온보딩 장치

이 배포 시나리오에서는 아직 온보딩되지 않은 장치를 온보드하고, Windows 10 장치의 의도하지 않은 공유에서 중요한 항목을 모니터링하고 보호하려고 합니다.

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Microsoft 365 규정 준수 센터</a>를 엽니다.

2. 규정 준수 센터 설정 페이지를 열고 **장치 온보딩** 을 선택합니다.

   > [!div class="mx-imgBorder"]
   > ![장치 관리를 사용하도록 설정.](../media/endpoint-dlp-learn-about-1-enable-device-management.png)

   > [!NOTE]
   > 일반적으로 장치 온보딩이 활성화되는 데 60초 정도 소요되지만, Microsoft 지원에 연락하기 전에 30분까지 기다려보세요.

3. **장치 관리** 를 선택하여 **장치** 목록을 엽니다. 목록은 장치가 온보딩될 때까지 비어 있습니다.

4. **온보딩** 을 선택하여 온보딩 프로세스를 시작합니다.

5. **배포 방법** 목록에서 이러한 추가 장치에 배포할 방법을 선택한 다음 **패키지를 다운로드합니다**.

   > [!div class="mx-imgBorder"]
   > ![배포 방법.](../media/endpoint-dlp-getting-started-3-deployment-method.png)

6. [Windows 10 컴퓨터용 온보딩 도구와 방법](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)의 해당 절차를 따르세요. 이 링크를 누르면 5단계에서 선택한 배포 패키지와 일치하는 엔드포인트용 Microsoft Defender에 액세스할 수 있는 랜딩 페이지로 이동합니다.

    - 그룹 정책을 사용하여 Windows 10 컴퓨터 온보딩하기
    - Microsoft Endpoint Configuration Manager를 사용하여 Windows 컴퓨터 온보딩하기
    - 모바일 장치 관리 도구를 사용하여 Windows 10 컴퓨터 온보딩하기
    - 로컬 스크립트를 사용하여 Windows 10 컴퓨터 온보딩하기
    - 단일 세션 시나리오에서 비영구적 VDI(가상 데스크톱 인프라) 머신 온보딩하기

작업이 완료되고 엔드포인트가 온보딩되면 장치 목록에 표시되고 감사 활동 로그를 활동 탐색기에 보고하기 시작해야 합니다.

> [!NOTE]
> 이 환경은 라이선스 적용하에 있습니다. 필수 라이선스가 없으면 데이터가 표시되지 않거나 테이터에 액세스할 수 없습니다.

### <a name="with-devices-onboarded-into-microsoft-defender-for-endpoint"></a>엔드포인트용 Microsoft Defender에 온보딩된 장치 사용

이 시나리오에서 엔드포인트용 Microsoft Defender는 이미 배포되었으며 엔드포인트 보고가 있습니다. 이러한 모든 엔드포인트는 관리되는 장치 목록에 나타납니다. [장치 온보딩 절차](endpoint-dlp-getting-started.md#onboarding-devices)를 사용하여 새 장치를 Endpoint DLP로 계속해서 온보딩하여 범위를 확장할 수 있습니다.

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Microsoft 365 규정 준수 센터</a>를 엽니다.

2. 규정 준수 센터 설정 페이지를 열고 **장치 모니터링 사용** 을 선택합니다.

3. **장치 관리** 를 선택하여 **장치** 목록을 엽니다. 이미 엔드포인트용 Microsoft Defender에 보고하고 있는 장치 목록이 표시되어야 합니다.

   > [!div class="mx-imgBorder"]
   > ![장치 관리.](../media/endpoint-dlp-getting-started-2-device-management.png)

4. 추가 디바이스를 온보딩해야 하는 경우에는 **온보딩** 을 선택합니다.

5. **배포 방법** 목록에서 이러한 추가 장치에 배포할 방법을 선택한 다음 **패키지를 다운로드합니다**.

6. [Windows 10 컴퓨터용 온보딩 도구와 방법](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)의 해당 절차를 따르세요. 이 링크를 누르면 5단계에서 선택한 배포 패키지와 일치하는 엔드포인트용 Microsoft Defender에 액세스할 수 있는 랜딩 페이지로 이동합니다.
    - 그룹 정책을 사용하여 Windows 10 컴퓨터 온보딩하기
    - Microsoft Endpoint Configuration Manager를 사용하여 Windows 컴퓨터 온보딩하기
    - 모바일 장치 관리 도구를 사용하여 Windows 10 컴퓨터 온보딩하기
    - 로컬 스크립트를 사용하여 Windows 10 컴퓨터 온보딩하기
    - 비영구적 VDI(가상 데스크톱 인프라) 머신 온보딩하기

작업이 완료되고 엔드포인트가 온보딩되면 **장치** 표에 표시되고 감사 로그를 **활동 탐색기** 에 보고하기 시작해야 합니다.

> [!NOTE]
>이 환경은 라이선스 적용하에 있습니다. 필수 라이선스가 없으면 데이터가 표시되지 않거나 테이터에 액세스할 수 없습니다.

### <a name="viewing-endpoint-dlp-alerts-in-dlp-alerts-management-dashboard"></a>DLP 경고 관리 대시보드에서 끝점 DLP 경고 보기

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Microsoft 365 규정 준수 센터</a>에서 데이터 손실 방지 페이지를 열고 경고를 선택합니다.

2. 끝점 DLP 정책에 대한 경고를 보려면 [DLP 정책에 대한 경고를 구성하고 보는 방법](dlp-configure-view-alerts-policies.md)에서 절차를 참조하세요.

### <a name="viewing-endpoint-dlp-data-in-activity-explorer"></a>활동 탐색기에서 Endpoint DLP 데이터 보기

1. Microsoft 365 규정 준수 센터에서 도메인에 대한 [데이터 분류 페이지](https://compliance.microsoft.com/dataclassification?viewid=overview)를 열고 활동 탐색기를 선택합니다.

2. [활동 탐색기 시작하기](data-classification-activity-explorer.md)의 절차를 참조하여 엔드포인트 장치에 대한 모든 데이터에 액세스하고 테이터를 필터링합니다.

   > [!div class="mx-imgBorder"]
   > ![엔드포인트 장치에 대한 활동 탐색기 필터.](../media/endpoint-dlp-4-getting-started-activity-explorer.png)

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
