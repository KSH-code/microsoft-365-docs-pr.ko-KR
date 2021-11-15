---
title: Windows 10 또는 Windows 11 장치의 Microsoft 365 온보딩 개요
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
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: Windows 10 및 Windows 11 장치의 Microsoft 365 온보딩
ms.openlocfilehash: a83db434b488ce28c71df0fb7e3185be88b87b01
ms.sourcegitcommit: 8eca41cd21280ffcb1f50cafce7a934e5544f302
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2021
ms.locfileid: "60950896"
---
# <a name="onboard-windows-10-and-windows-11-devices-into-microsoft-365-overview"></a>Windows 10 및 Windows 11 장치의 Microsoft 365 온보딩 개요

**적용 대상:**

- [Microsoft 365 엔드포인트 DLP(데이터 손실 방지)](./endpoint-dlp-learn-about.md)
- [내부자 위험 관리](insider-risk-management.md#learn-about-insider-risk-management-in-microsoft-365)

Microsoft 365 엔드포인트 DLP(엔드포인트 데이터 손실 방지) 및 내부자 위험 관리를 사용하려면 모니터링 데이터를 서비스에 보낼 수 있도록 Windows 10과 Windows 11 장치를 서비스에 온보딩해야 합니다.
 
Microsoft 365 엔드포인트 DLP를 사용하면 Windows 10 또는 Windows 11 장치를 모니터링하고 중요한 항목이 사용되고 공유되는 시기를 탐지할 수 있습니다. 이를 통해 중요한 항목이 올바르게 사용되며 보호하고 위험을 초래할 수 있는 위험한 행동을 방지하는 데 필요한 가시성과 제어 기능을 제공합니다. 모든 Microsoft DLP 제공에 대한 자세한 내용은 [데이터 손실 방지에 대해 알아보기](dlp-learn-about-dlp.md)를 참조하세요. 엔드포인트 DLP에 관한 자세한 내용은 [엔드포인트 데이터 손실 방지에 관해 자세히 알아보기](endpoint-dlp-learn-about.md)를 참조하세요.

내부자 위험 관리는 다양한 서비스와 제3자 지표를 사용하여 위험한 사용자 활동을 신속하게 식별 및 심사하고 이에 대한 조치를 취할 수 있도록 합니다. Microsoft 365와 Microsoft Graph 로그를 사용해 내부자 위험 관리는 위험 지표를 식별하고 이러한 위험을 완화하기 위한 조치를 취할 수 있도록 특정 정책을 정의합니다. 자세한 내용은 [Microsoft 365의 내부 위험 관리에 관한 자세한 내용](insider-risk-management.md#learn-about-insider-risk-management-in-microsoft-365)을 참조하세요.

장치 온보딩은 Microsoft 365와 MDE(엔드포인트용 Microsoft Defender) 전체에서 공유됩니다. MDE에 이미 장치를 온보딩한 경우 해당 장치가 관리되는 장치 목록에 표시되고 해당 특정 장치를 온보딩하기 위한 추가 단계가 필요하지 않습니다. 준수 센터에서 장치를 온보딩하는 경우에도 MDE에 온보딩됩니다.

## <a name="before-you-begin"></a>시작하기 전에

### <a name="skusubscriptions-licensing"></a>SKU/구독 라이선싱

[여기](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection-data-loss-prevention-for-exchange-online-sharepoint-online-and-onedrive-for-business)에서 라이선싱 요구 사항을 확인하세요.

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

### <a name="prepare-your-windows-devices"></a>Windows 장치 준비

온보딩하려는 Windows 장치가 이 요구 사항을 충족하는지 확인하세요.

1. Windows 10 x64 빌드 1809 이상 또는 Windows 11을 실행 중이어야 합니다.

2. 맬웨어 방지 클라이언트 버전이 4.18.2009.7 이상입니다. Windows 보안 앱을 열고, 설정 아이콘을 선택한 다음 정보를 선택하여 현재 버전을 확인합니다. 버전 번호는 맬웨어 방지 클라이언트 버전 아래에 나열됩니다. Windows 업데이트 KB4052623을 설치하여 최신 맬웨어 방지 클라이언트 버전으로 업데이트합니다.

   > [!NOTE]
   > Windows 보안 구성 요소는 활성 상태일 필요는 없지만 [실시간 보호 및 동작 모니터링](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus)은 사용 설정해야 합니다.

3. 모니터링할 장치에는 다음과 같은 Windows 10용 Windows 업데이트가 설치됩니다.

   > [!NOTE]
   > 이러한 업데이트는 장치를 온보딩하기 위한 필수 조건이 아니지만 중요한 문제에 대한 수정 사항을 포함하므로 제품을 사용하기 전에 설치해야 합니다.
   >
    > - Windows 10 1809의 경우 - KB4559003, KB4577069, KB4580390
    > - Windows 10 1903 혹은 1909의 경우 - KB4559004, KB4577062, KB4580386
    > - Windows 10 2004의 경우 - KB4568831, KB4577063

4. 모든 장치는 다음 중 하나에 해당해야 합니다.

   - [Azure AD(Azure Active Directory) 조인됨](/azure/active-directory/devices/concept-azure-ad-join)
   - [하이브리드 Azure AD 조인됨](/azure/active-directory/devices/concept-azure-ad-join-hybrid)
   - [AAD 등록됨](/azure/active-directory/user-help/user-help-register-device-on-network)

5. Office 2016(다른 Office 버전이 아님)을 실행하는 장치의 경우 - KB4577063

6. Microsoft 365 앱 2004-2008 버전의 월 단위 기업 채널에 있는 경우 Office 콘텐츠를 분류하는 데 알려진 문제가 있으며 버전 2009 이상으로 업데이트해야 합니다. 현재 버전에 대한 자세한 내용은 [Microsoft 365 앱의 업데이트 기록(날짜순)](/officeupdates/update-history-microsoft365-apps-by-date)을 참조하세요. 해당 문제에 대한 자세한 내용을 보려면 [2020년 현재 채널 릴리스에 대한 릴리스 노트](/officeupdates/current-channel#version-2010-october-27)의 Office 제품군 섹션을 참조하세요.

7. 장치 프록시를 사용하여 인터넷에 연결하는 엔드포인트가 있는 경우 [Information Protection의 장치 프록시 및 인터넷 연결 구성](device-onboarding-configure-proxy.md#configure-device-proxy-and-internet-connection-settings-for-information-protection)의 절차를 따르세요.

## <a name="onboarding-windows-10-or-windows-11-devices"></a>Windows 10 또는 Windows 11 장치 온보딩

장치에서 중요한 항목을 모니터링하고 보호하려면 장치 모니터링을 사용하도록 설정하고 엔드포인트를 온보딩해야 합니다. 이러한 작업은 모두 Microsoft 365 규정 준수 포털에서 수행됩니다.

아직 온보딩되지 않은 장치를 온보딩하려는 경우 적절한 스크립트를 다운로드하여 해당 장치에 배포합니다. 아래의 장치 온보딩 절차를 따르세요.

이미 [엔드포인트용 Microsoft Defender](/windows/security/threat-protection/)에 온보딩된 장치가 있으면 해당 장치가 관리되는 장치 목록에 표시됩니다.

이 배포 시나리오에서는 아직 온보딩하지 않은 Windows 10 또는 Windows 11 장치를 온보딩합니다.

1. [Microsoft 규정 준수 센터](https://compliance.microsoft.com)를 엽니다. **설정** > **장치 모니터링 사용** 을 선택합니다.

   > [!NOTE]
   > 일반적으로 장치 온보딩이 활성화되는 데 60초 정도 소요되지만, Microsoft 지원에 연락하기 전에 30분까지 기다려보세요.

2. 규정 준수 센터 설정 페이지를 열고 **장치 온보딩** 을 선택합니다.

   > [!div class="mx-imgBorder"]
   > ![장치 관리를 사용하도록 설정.](../media/endpoint-dlp-learn-about-1-enable-device-management.png)

3. **장치 관리** 를 선택하여 **장치** 목록을 엽니다. 

> [!NOTE]
> 이전에 엔드포인트용 Microsoft Defender를 배포한 경우 해당 프로세스 중에 온보딩한 모든 장치가 **장치** 목록에 나열됩니다. 다시 온보딩할 필요가 없습니다.

4. **온보딩** 을 선택하여 온보딩 프로세스를 시작합니다.

5. **배포 방법** 목록에서 이러한 추가 장치에 배포할 방법을 선택한 다음 **패키지를 다운로드합니다**.

6. 아래 표에서 적절한 절차를 선택해서 수행하세요.

항목 | 설명
:---|:---
[그룹 정책을 사용하는 Windows 10 또는 11 장치 온보딩](device-onboarding-gp.md) | 그룹 정책을 사용하여 장치에 구성 패키지를 배포합니다.
[Microsoft Endpoint Configuration Manager를 사용하는 Windows 10 또는 11 장치 온보딩](device-onboarding-sccm.md) | Microsoft Endpoint Configuration Manager(현재 분기) 버전 1606 또는 Microsoft Endpoint Configuration Manager(현재 분기) 버전 1602 이하를 사용하여 장치에 구성 패키지를 배포할 수 있습니다.
[모바일 장치 관리를 사용하는 Windows 10 또는 11 장치 온보딩](device-onboarding-mdm.md) | 모바일 장치 관리 도구 또는 Microsoft Intune을 사용하여 장치에 구성 패키지를 배포합니다.
[로컬 스크립트를 사용하는 Windows 10 또는 11 장치 온보딩](device-onboarding-script.md) | 로컬 스크립트를 사용하여 엔드포인트에서 구성 패키지를 배포하는 방법을 알아봅니다.
[비영구 VDI(가상 데스크톱 인프라) 장치 온보딩](device-onboarding-vdi.md) | 구성 패키지를 사용하여 VDI 장치를 구성하는 방법을 알아봅니다.

장치를 온보딩하고 나면 장치가 장치 목록에 표시되고, 감사 활동 로그를 활동 탐색기에 보고하기 시작합니다.

### <a name="viewing-endpoint-dlp-alerts-in-dlp-alerts-management-dashboard"></a>DLP 경고 관리 대시보드에서 끝점 DLP 경고 보기

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Microsoft 365 규정 준수 센터</a>에서 데이터 손실 방지 페이지를 열고 경고를 선택합니다.

2. 끝점 DLP 정책에 대한 경고를 보려면 [DLP 정책에 대한 경고를 구성하고 보는 방법](dlp-configure-view-alerts-policies.md)에서 절차를 참조하세요.

### <a name="viewing-endpoint-dlp-data-in-activity-explorer"></a>활동 탐색기에서 Endpoint DLP 데이터 보기

1. Microsoft 365 규정 준수 센터에서 도메인에 대한 [데이터 분류 페이지](https://compliance.microsoft.com/dataclassification?viewid=overview)를 열고 활동 탐색기를 선택합니다.

2. [활동 탐색기 시작하기](data-classification-activity-explorer.md)의 절차를 참조하여 엔드포인트 장치에 대한 모든 데이터에 액세스하고 테이터를 필터링합니다.

   > [!div class="mx-imgBorder"]
   > ![엔드포인트 장치에 대한 활동 탐색기 필터.](../media/endpoint-dlp-4-getting-started-activity-explorer.png)


## <a name="see-also"></a>참고 항목

- [Microsoft 365의 내부 위험 관리에 관한 자세한 정보](insider-risk-management.md#learn-about-insider-risk-management-in-microsoft-365)
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
