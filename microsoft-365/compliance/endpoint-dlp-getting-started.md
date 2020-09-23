---
title: Microsoft 365 Endpoint 데이터 손실 방지(미리 보기) 시작하기
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
description: Microsoft 365 Endpoint 데이터 손실 방지를 설정하여 파일 활동을 모니터링하고 해당 파일에 대한 보호 작업을 엔드포인트에 구현합니다.
ms.openlocfilehash: 08e2bd43b4337087b401244b7dc4cf80a26aaf06
ms.sourcegitcommit: fdb5f9d865037c0ae23aae34a5c0f06b625b2f69
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/18/2020
ms.locfileid: "48131672"
---
# <a name="get-started-with-endpoint-data-loss-prevention-preview"></a>Endpoint 데이터 손실 방지(미리 보기) 시작하기

Microsoft Endpoint 데이터 손실 방지(Endpoint DLP)는 Microsoft 365 서비스에서 중요 한 항목을 검색하고 보호하는 데 사용할 수 있는 Microsoft 365의 DLP(데이터 손실 방지) 제품군의 일부입니다. 모든 Microsoft의 DLP 제공에 대한 자세한 내용은 [데이터 손실 방지 개요](data-loss-prevention-policies.md)를 참조하세요. Endpoint DLP에 대한 자세한 내용은 [Endpoint 데이터 손실 방지(미리 보기)에 대한 자세한 정보](endpoint-dlp-learn-about.md)를 참조하세요.

Microsoft Endpoint DLP를 사용하면 Windows 10 장치를 모니터링하고 중요한 항목이 사용되고 공유되는 때를 탐지할 수 있습니다. 이를 통해 중요한 항목이 올바르게 사용되며 보호하고 위험을 초래할 수 있는 위험한 행동을 방지하는 데 필요한 가시성과 제어 기능을 제공합니다.

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

### <a name="prepare-your-endpoints"></a>엔드포인트 준비하기

Endpoint DLP를 배포하는 데 사용할 Windows 10 장치가 다음 요구 사항을 충족하는지 확인하세요.

1. Windows 10 빌드 1809 이상을 실행해야 합니다.
2. 모든 장치가 [AAD(Azure Active Directory)에 가입](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join)되어 있거나 Hybrid Azure AD에 가입되어 있어야 합니다.
3. 엔드 포인트 장치에 Microsoft Chromium Edge 브라우저를 설치하여 클라우드로 업로드 활동에 대한 정책 작업을 적용하세요. [Chromium 기반 새 Microsoft Edge 다운로드하기](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)를 참조하세요.

## <a name="onboarding-devices-into-device-management"></a>장치 관리에 장치 온보딩

 장치에서 중요한 항목을 모니터링하고 보호하려면 장치 모니터링을 사용하도록 설정하고 엔드포인트를 온보딩해야 합니다. 이러한 작업은 모두 Microsoft 365 규정 준수 포털에서 수행됩니다.

아직 온보딩되지 않은 장치를 온보딩하려는 경우 적절한 스크립트를 다운로드하여 해당 장치에 배포합니다. [장치 온보딩 절차](endpoint-dlp-getting-started.md#onboarding-devices)를 따르세요.

이미 [엔드포인트용 Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/)에 온보딩된 장치가 있으면 해당 장치가 관리되는 장치 목록에 표시됩니다. [엔드포인트용 Microsoft Defender에 온보딩된 장치 절차](endpoint-dlp-getting-started.md#with-devices-onboarded-into-microsoft-defender-for- endpoint)를 따릅니다.

### <a name="onboarding-devices"></a>온보딩 장치

이 배포 시나리오에서는 아직 온보딩되지 않은 장치를 온보드하고, Windows 10 장치의 의도하지 않은 공유에서 중요한 항목을 모니터링하고 보호하려고 합니다.

1. [Microsoft 규정 준수 센터](https://compliance.microsoft.com)를 엽니다.
2. 규정 준수 센터 설정 페이지를 열고 **장치 온보딩**을 선택합니다. 

   ![장치 관리 사용하도록 설정하기](../media/endpoint-dlp-learn-about-1-enable-device-management.png)

   > [!NOTE]
   > 일반적으로 장치 온보딩이 활성화되는 데 60초 정도 소요되지만, Microsoft 지원에 연락하기 전에 30분까지 기다려보세요.

3. **장치 관리**를 선택하여 **장치** 목록을 엽니다. 목록은 장치가 온보딩될 때까지 비어 있습니다.
4. **온보딩**을 선택하여 온보딩 프로세스를 시작합니다.
5. **배포 방법** 목록에서 이러한 추가 장치에 배포할 방법을 선택한 다음 **패키지를 다운로드합니다**.

   ![배포 방법](../media/endpoint-dlp-getting-started-3-deployment-method.png)
6. [Windows 10 컴퓨터용 온보딩 도구와 방법](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)의 해당 절차를 따르세요. 이 링크를 누르면 5단계에서 선택한 배포 패키지와 일치하는 엔드포인트용 Microsoft Defender에 액세스할 수 있는 랜딩 페이지로 이동합니다.
    - 그룹 정책을 사용하여 Windows 10 컴퓨터 온보딩하기
    - Microsoft Endpoint Configuration Manager를 사용하여 Windows 컴퓨터 온보딩하기
    - 모바일 장치 관리 도구를 사용하여 Windows 10 컴퓨터 온보딩하기
    - 로컬 스크립트를 사용하여 Windows 10 컴퓨터 온보딩하기
    - 비영구적 VDI(가상 데스크톱 인프라) 머신 온보딩하기

작업이 완료되고 엔드포인트가 온보딩되면 장치 목록에 표시되고 감사 활동 로그를 활동 탐색기에 보고하기 시작해야 합니다.

> [!NOTE]
> 이 환경은 라이선스 적용하에 있습니다. 필수 라이선스가 없으면 데이터가 표시되지 않거나 테이터에 액세스할 수 없습니다.

### <a name="with-devices-onboarded-into-microsoft-defender-for-endpoint"></a>엔드포인트용 Microsoft Defender에 온보딩된 장치 사용

이 시나리오에서 엔드포인트용 Microsoft Defender는 이미 배포되었으며 엔드포인트 보고가 있습니다. 이러한 모든 엔드포인트는 관리되는 장치 목록에 나타납니다. [장치 온보딩 절차](endpoint-dlp-getting-started.md#onboarding-devices)를 사용하여 새 장치를 Endpoint DLP로 계속해서 온보딩하여 범위를 확장할 수 있습니다.

1. [Microsoft 규정 준수 센터](https://compliance.microsoft.com)를 엽니다.
2. 규정 준수 센터 설정 페이지를 열고 **장치 모니터링 사용**을 선택합니다.
3. **장치 관리**를 선택하여 **장치** 목록을 엽니다. 이미 엔드포인트용 Microsoft Defender에 보고하고 있는 장치 목록이 표시되어야 합니다. ![장치 관리](../media/endpoint-dlp-getting-started-2-device-management.png)
4. 추가 디바이스를 온보딩해야 하는 경우에는 **온보딩**을 선택합니다.
5. **배포 방법** 목록에서 이러한 추가 장치에 배포할 방법을 선택한 다음 **패키지를 다운로드합니다**.
6. [Windows 10 컴퓨터용 온보딩 도구와 방법](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)의 해당 절차를 따르세요. 이 링크를 누르면 5단계에서 선택한 배포 패키지와 일치하는 엔드포인트용 Microsoft Defender에 액세스할 수 있는 랜딩 페이지로 이동합니다.
    - 그룹 정책을 사용하여 Windows 10 컴퓨터 온보딩하기
    - Microsoft Endpoint Configuration Manager를 사용하여 Windows 컴퓨터 온보딩하기
    - 모바일 장치 관리 도구를 사용하여 Windows 10 컴퓨터 온보딩하기
    - 로컬 스크립트를 사용하여 Windows 10 컴퓨터 온보딩하기
    - 비영구적 VDI(가상 데스크톱 인프라) 머신 온보딩하기

작업이 완료되고 엔드포인트가 온보딩되면 **장치** 표에 표시되고 감사 로그를 **활동 탐색기**에 보고하기 시작해야 합니다.

> [!NOTE]
>이 환경은 라이선스 적용하에 있습니다. 필수 라이선스가 없으면 데이터가 표시되지 않거나 테이터에 액세스할 수 없습니다.

### <a name="viewing-endpoint-dlp-data-in-activity-explorer"></a>활동 탐색기에서 Endpoint DLP 데이터 보기

1. Microsoft 365 규정 준수 센터에서 도메인에 대한 [데이터 분류 페이지](https://compliance.microsoft.com/dataclassification?viewid=overview)를 열고 활동 탐색기를 선택합니다.
2. [활동 탐색기 시작하기](data-classification-activity-explorer.md)의 절차를 참조하여 엔드포인트 장치에 대한 모든 데이터에 액세스하고 테이터를 필터링합니다.

![엔드포인트 장치에 대한 활동 탐색기 필터](../media/endpoint-dlp-4-getting-started-activity-explorer.png)

## <a name="next-steps"></a>다음 단계
이제 온보딩된 장치가 있고 활동 탐색기에서 활동 데이터를 볼 수 있으므로 중요한 항목을 보호하는 DLP 정책을 만드는 다음 단계를 진행할 준비가 되었습니다.

- [Endpoint 데이터 손실 방지(미리 보기) 사용하기](endpoint-dlp-using.md)

## <a name="see-also"></a>참고 항목

- [Endpoint 데이터 손실 방지(미리 보기)에 대한 자세한 정보](endpoint-dlp-learn-about.md)
- [Endpoint 데이터 손실 방지(미리 보기) 사용하기](endpoint-dlp-using.md)
- [데이터 손실 방지 개요](data-loss-prevention-policies.md)
- [DLP 정책 생성, 테스트 및 조정](create-test-tune-dlp-policy.md)
- [활동 탐색기 시작하기](data-classification-activity-explorer.md)
- [Microsoft Defender Advanced Threat Protection(Microsoft Defender ATP)](https://docs.microsoft.com/windows/security/threat-protection/)
- [Windows 10 컴퓨터용 온보딩 도구 및 방법](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [Microsoft 365 구독](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [Azure Active Directory(AAD) 가입](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join)
- [Chromium 기반 새 Microsoft Edge 다운로드하기](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
