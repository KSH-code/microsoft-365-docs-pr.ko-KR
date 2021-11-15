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
ms.custom: admindeeplinkCOMPLIANCE
description: Microsoft 365 Endpoint 데이터 손실 방지를 설정하여 파일 활동을 모니터링하고 해당 파일에 대한 보호 작업을 엔드포인트에 구현합니다.
ms.openlocfilehash: e29db57c42081349064fd690c5c9fcebee0f8045
ms.sourcegitcommit: 8eca41cd21280ffcb1f50cafce7a934e5544f302
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2021
ms.locfileid: "60950656"
---
# <a name="get-started-with-endpoint-data-loss-prevention"></a>엔드포인트 데이터 손실 방지 시작하기

Microsoft Endpoint 데이터 손실 방지(Endpoint DLP)는 Microsoft 365 서비스에서 중요 한 항목을 검색하고 보호하는 데 사용할 수 있는 Microsoft 365의 DLP(데이터 손실 방지) 제품군의 일부입니다. 모든 Microsoft DLP 제공에 대한 자세한 내용은 [데이터 손실 방지에 대해 알아보기](dlp-learn-about-dlp.md)를 참조하세요. 끝점 DLP에 대해 자세히 알아보려면 [끝점 데이터 손실 방지](endpoint-dlp-learn-about.md)를 참조하세요.

Microsoft Endpoint DLP를 사용하면 Catalina 10.15 이상을 실행하는 [온보딩된 Windows 10, Windows 11](device-onboarding-overview.md) 및 [온보딩된 macOS 장치 *(미리 보기)*](device-onboarding-macos-overview.md)를 모니터링할 수 있습니다. 장치가 온보딩되면 DLP는 민감한 항목이 사용 및 공유되는 시기를 감지합니다. 이를 통해 중요한 항목이 올바르게 사용되며 보호하고 위험을 초래할 수 있는 위험한 행동을 방지하는 데 필요한 가시성과 제어 기능을 제공합니다.

## <a name="before-you-begin"></a>시작하기 전에

### <a name="skusubscriptions-licensing"></a>SKU/구독 라이선싱

Endpoint DLP를 시작하기 전에 [Microsoft 365 구독](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)과 추가 기능을 확인해야 합니다. Endpoint DLP 기능에 액세스하고 사용하려면 다음 구독 또는 추가 기능 중 하나가 있어야 합니다.

- Microsoft 365 E5
- Microsoft 365 A5(EDU)
- Microsoft 365 E5 compliance
- Microsoft 365 A5 compliance
- Microsoft 365 E5 Information Protection 및 거버넌스
- Microsoft 365 A5 Information Protection 및 거버넌스

전체 라이선스 세부 정보는 [정보 보호를 위한 Microsoft 365 라이선스 안내](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection-data-loss-prevention-for-exchange-online-sharepoint-online-and-onedrive-for-business)를 참조하세요.

### <a name="configure-proxy-on-the-windows-10-or-windows-11-device"></a>Windows 10 또는 Windows 11 장치에서 프록시 구성

Windows 10 또는 Windows 11 장치를 온보딩하는 경우 장치가 클라우드 DLP 서비스와 통신할 수 있는지 확인하세요. 자세한 내용은 [정보 보호를 위한 장치 프록시 및 인터넷 연결 설정 구성](device-onboarding-configure-proxy.md#configure-device-proxy-and-internet-connection-settings-for-information-protection)을 참조하세요.

## <a name="windows-10-and-windows-11-onboarding-procedures"></a>Windows 10 및 Windows 11 온보딩 절차

Windows 장치 온보딩에 대한 일반적인 소개는 다음을 참조하세요.

- [Windows 10 및 Windows 11 장치의 Microsoft 365 온보딩 개요](device-onboarding-overview.md#onboard-windows-10-and-windows-11-devices-into-microsoft-365-overview)

Windows 장치 온보딩에 대한 구체적인 지침은 다음을 참조하세요.

항목 | 설명
:---|:---
[그룹 정책을 사용하는 Windows 10 또는 11 장치 온보딩](device-onboarding-gp.md) | 그룹 정책을 사용하여 장치에 구성 패키지를 배포합니다.
[Microsoft Endpoint Configuration Manager를 사용하는 Windows 10 또는 11 장치 온보딩](device-onboarding-sccm.md) | Microsoft Endpoint Configuration Manager(현재 분기) 버전 1606 또는 Microsoft Endpoint Configuration Manager(현재 분기) 버전 1602 이하를 사용하여 장치에 구성 패키지를 배포할 수 있습니다.
[모바일 장치 관리를 사용하는 Windows 10 또는 11 장치 온보딩](device-onboarding-mdm.md) | 모바일 장치 관리 도구 또는 Microsoft Intune을 사용하여 장치에 구성 패키지를 배포합니다.
[로컬 스크립트를 사용하는 Windows 10 또는 11 장치 온보딩](device-onboarding-script.md) | 로컬 스크립트를 사용하여 엔드포인트에서 구성 패키지를 배포하는 방법을 알아봅니다.
[비영구 VDI(가상 데스크톱 인프라) 장치 온보딩](device-onboarding-vdi.md) | 구성 패키지를 사용하여 VDI 장치를 구성하는 방법을 알아봅니다.

## <a name="macos-onboarding-procedures"></a>macOS 온보딩 절차

macOS 장치 온보딩에 대한 일반적인 소개는 다음을 참조하세요.
 
- [macOS 디바이스를 Microsoft 365 개요에 온보딩(미리 보기)](device-onboarding-macos-overview.md#onboard-macos-devices-into-microsoft-365-overview-preview)

macOS 장치 온보딩에 대한 구체적인 참고 자료는 다음을 참조하세요.

항목 | 설명
:---|:---
|[Intune을 사용하여 macOS 장치를 Microsoft 365 규정 준수 솔루션에 온보딩 및 오프보딩(미리 보기)](device-onboarding-offboarding-macos-intune.md#onboard-and-offboard-macos-devices-into-microsoft-365-compliance-solutions-using-intune-preview)|Intune을 통해 관리되는 macOS 디바이스의 경우
|[엔드포인트용 Microsoft Defender 고객을 위한 Intune을 사용하여 macOS 디바이스를 규정 준수 솔루션에 온보딩 및 오프보딩(미리 보기)](device-onboarding-offboarding-macos-intune-mde.md#onboard-and-offboard-macos-devices-into-compliance-solutions-using-intune-for-microsoft-defender-for-endpoint-customers-preview) |Intune을 통해 관리되고 MDE(엔드포인트용 Microsoft Defender)가 배포된 macOS 장치의 경우
|[JAMF Pro를 사용하여 macOS 장치를 Microsoft 365 규정 준수 솔루션에 온보딩 및 오프보딩(미리 보기)](device-onboarding-offboarding-macos-jamfpro.md#onboard-and-offboard-macos-devices-into-microsoft-365-compliance-solutions-using-jamf-pro-preview) | JAMF Pro를 통해 관리되는 macOS 장치의 경우
|[엔드포인트용 Microsoft Defender 고객을 위한 JAMF Pro를 사용하여 macOS 디바이스를 규정 준수 솔루션에 온보딩 및 오프보딩(미리 보기)](device-onboarding-offboarding-macos-jamfpro-mde.md#onboard-and-offboard-macos-devices-into-compliance-solutions-using-jamf-pro-for-microsoft-defender-for-endpoint-customers-preview)|JAMF Pro를 통해 관리되고 MDE(엔드포인트용 Microsoft Defender)가 배포된 macOS 장치의 경우

장치를 온보딩하고 나면 장치가 장치 목록에 표시되고, 감사 활동을 활동 탐색기에 보고하기 시작합니다.

<!--### Permissions

To enable device management, the account you use must be a member of any one of these roles:

- Global admin
- Security admin
- Compliance admin

If you want to use a custom account to view the device management settings, it must be in one of these roles:

- Global admin
- Compliance admin
- Compliance data admin
- Global reader

If you want to use a custom account to access the onboarding/offboarding page, it must be in one of these roles:

- Global admin
- Compliance admin

If you want to use a custom account to turn on/off device monitoring, it must be in one of these roles:

- Global admin
- Compliance admin

Data from Endpoint DLP can be viewed in [Activity explorer](data-classification-activity-explorer.md). There are four roles that grant permission to activity explorer, the account you use for accessing the data must be a member of any one of them.

- Global admin
- Compliance admin
- Security admin
- Compliance data admin -->

<!-- ### Prepare your Windows 10/11 endpoints

Make sure that the Windows devices that you plan on deploying Endpoint DLP to meet these requirements.

1. Must be running Windows 10 x64 build 1809, Windows 11, or later.

1. Antimalware Client Version is 4.18.2009.7 or newer. Check your current version by opening Windows Security app, select the Settings icon, and then select About. The version number is listed under Antimalware Client Version. Update to the latest Antimalware Client Version by installing Windows Update KB4052623.

   > [!NOTE]
   > None of Windows Security components need to be active, you can run Endpoint DLP independent of Windows Security status, but the [Real-time protection and Behavior monitor](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus)) must be enabled.

1. The following Updates are installed on Windows 10 devices

   > [!NOTE]
   > These updates are not a pre-requisite to onboard a device to Endpoint DLP, but contain fixes for important issues thus must be installed before using the product.

   - For Windows 10 1809 - KB4559003, KB4577069, KB4580390
   - For Windows 10 1903 or 1909 - KB4559004, KB4577062, KB4580386
   - For Windows 10 2004 - KB4568831, KB4577063
   - For devices running Office 2016 (and not any other Office version) - KB4577063

1. All devices must be one of these:

   - [Azure Active Directory (Azure AD) joined](/azure/active-directory/devices/concept-azure-ad-join)
   - [Hybrid Azure AD joined](/azure/active-directory/devices/concept-azure-ad-join-hybrid)
   - [AAD registered](/azure/active-directory/user-help/user-help-register-device-on-network)

1. Install Microsoft Chromium Edge browser on the endpoint device to enforce policy actions for the upload to cloud activity. See, [Download the new Microsoft Edge based on Chromium](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium). If your devices use the Chrome browser, you can install the [Microsoft Compliance Extension](dlp-chrome-learn-about.md#learn-about-the-microsoft-compliance-extension) to enforce policy actions for the upload to cloud activity.

1. If you are on Monthly Enterprise Channel of Microsoft 365 Apps versions 2004-2008, there is a known issue with Endpoint DLP classifying Office content and you need to update to version 2009 or later. See [Update history for Microsoft 365 Apps (listed by date)](/officeupdates/update-history-microsoft365-apps-by-date) for current versions. To learn more about this issue, see the Office Suite section of [Release notes for Current Channel releases in 2020](/officeupdates/current-channel#version-2010-october-27).

1. If you have endpoints that use a device proxy to connect to the internet, follow the procedures in [Configure device proxy and internet connection settings for Information Protection](device-onboarding-configure-proxy.md#configure-device-proxy-and-internet-connection-settings-for-information-protection).

## Prepare your macOS devices (preview)

See, [Onboard macOS devices into Microsoft 365 overview (preview)](device-onboarding-macos-overview.md#onboard-macos-devices-into-microsoft-365-overview-preview)-->

<!--## Onboarding Windows 10 and Windows 11 devices into device management

You must enable device monitoring and onboard your endpoints before you can monitor and protect sensitive items on a device. Both of these actions are done in the Microsoft 365 Compliance portal.

When you want to onboard devices that haven't been onboarded yet, you'll download the appropriate script and deploy it to those devices. Follow the [Onboarding devices procedure](endpoint-dlp-getting-started.md#onboarding-devices).

If you already have devices onboarded into [Microsoft Defender for Endpoint](/windows/security/threat-protection/), they will already appear in the managed devices list. Follow the [With devices onboarded into Microsoft Defender for Endpoint procedure](?source=docs&view=o365-worldwide#with-devices-onboarded-into-microsoft-defender-for-endpoint).

### Onboarding devices

In this deployment scenario, you'll onboard devices that have not been onboarded yet, and you just want to monitor and protect sensitive items from unintentional sharing on Windows 10 or Windows 11 devices.

1. Open the <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Microsoft 365 compliance center</a>.

2. Choose **Settings** > **Device onboarding**.

   > [!NOTE]
   > While it usually takes about 60 seconds for device onboarding to be enabled, please allow up to 30 minutes before engaging with Microsoft support.

3. Choose **Devices** to open the **Devices** list. The list will be empty until you onboard devices.

4. Choose **Onboarding** to begin the onboarding process.

5. Choose the way you want to deploy to these additional devices from the **Deployment method** list and then **download package**.

   > [!div class="mx-imgBorder"]
   > ![deployment method.](../media/endpoint-dlp-getting-started-3-deployment-method.png)

6. Follow the appropriate procedures in [Onboarding tools and methods for Windows machines](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints). This link takes you to a landing page where you can access Microsoft Defender for Endpoint procedures that match the deployment package you selected in step 5:

    - Onboard Windows machines using Group Policy
    - Onboard Windows machines using Microsoft Endpoint Configuration Manager
    - Onboard Windows machines using Mobile Device Management tools
    - Onboard Windows machines using a local script
    - Onboard non-persistent virtual desktop infrastructure (VDI) machines in single-session scenarios

Once done and endpoint is onboarded, it should be visible in the devices list and also start reporting audit activity logs to Activity explorer.

> [!NOTE]
> This experience is under license enforcement. Without the required license, data will not be visible or accessible.

### With devices onboarded into Microsoft Defender for Endpoint

In this scenario, Microsoft Defender for Endpoint is already deployed and there are endpoints reporting in. All these endpoints will appear in the managed devices list. You can continue to onboard new devices into Endpoint DLP to expand coverage by using the [Onboarding devices procedure](endpoint-dlp-getting-started.md#onboarding-devices).

1. Open the <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Microsoft 365 compliance center</a>.

2. Open the Compliance Center settings page and choose **Enable device monitoring**.

3. Choose **Device management** to open the **Devices** list. You should see the list of devices that are already reporting in to Microsoft Defender for Endpoint.

   > [!div class="mx-imgBorder"]
   > ![device management.](../media/endpoint-dlp-getting-started-2-device-management.png)

4. Choose **Onboarding** if you need to onboard additional devices.

5. Choose the way you want to deploy to these additional devices from the **Deployment method** list and then **Download package**.

6. Follow the appropriate procedures in [Onboarding tools and methods for Windows machines](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints). This link takes you to a landing page where you can access Microsoft Defender for Endpoint procedures that match the deployment package you selected in step 5:
    - Onboard Windows machines using Group Policy
    - Onboard Windows machines using Microsoft Endpoint Configuration Manager
    - Onboard Windows machines using Mobile Device Management tools
    - Onboard Windows machines using a local script
    - Onboard non-persistent virtual desktop infrastructure (VDI) machines.

Once done and endpoint is onboarded, it should be visible under the **Devices** table and also start reporting audit logs to the **Activity Explorer**.

> [!NOTE]
>This experience is under license enforcement. Without the required license, data will not be visible or accessible.


### Viewing Endpoint DLP alerts in DLP Alerts Management dashboard

1. Open the Data loss prevention page in the <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Microsoft 365 compliance center</a> and choose Alerts.

2. Refer to the procedures in [How to configure and view alerts for your DLP policies](dlp-configure-view-alerts-policies.md) to view alerts for your Endpoint DLP policies.

### Viewing Endpoint DLP data in activity explorer

1. Open the [Data classification page](https://compliance.microsoft.com/dataclassification?viewid=overview) for your domain in the Microsoft 365 Compliance center and choose Activity explorer.

2. Refer to the procedures in [Get started with Activity explorer](data-classification-activity-explorer.md) to access and filter all the data for your Endpoint devices.

   > [!div class="mx-imgBorder"]
   > ![activity explorer filter for endpoint devices.](../media/endpoint-dlp-4-getting-started-activity-explorer.png)

## Next steps

Now that you have onboarded devices and can view the activity data in Activity explorer, you are ready to move on to your next step where you create DLP policies that protect your sensitive items.

- [Using Endpoint data loss prevention](endpoint-dlp-using.md)

## See also

- [Learn about Endpoint data loss prevention](endpoint-dlp-learn-about.md)
- [Using Endpoint data loss prevention](endpoint-dlp-using.md)
- [Learn about data loss prevention](dlp-learn-about-dlp.md)
- [Create, test, and tune a DLP policy](create-test-tune-dlp-policy.md)
- [Get started with Activity explorer](data-classification-activity-explorer.md)
- [Microsoft Defender for Endpoint](/windows/security/threat-protection/)
- [Onboarding tools and methods for Windows machines](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [Azure AD joined devices](/azure/active-directory/devices/concept-azure-ad-join)
- [Download the new Microsoft Edge based on Chromium](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
-->
