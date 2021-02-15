---
title: Office 2010을 Microsoft 365로 업그레이드 - Microsoft 365 관리자
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.custom:
- fwlink 824861; CampaignID
- O365_Comm_SR_UpgradeOffice
- seo-marvel-may2020
- fwlink 824861; CampaignID O365_Comm_SR_UpgradeOffice
- AdminSurgePortfolio
ms.assetid: f6b00895-b5fd-4af6-a656-b7788ea20cbb
description: 조직의 사용자를 위해 Microsoft Office Office 클라이언트로 업그레이드하는 방법에 대해 자세히 알아보습니다.
ms.openlocfilehash: 3f8ea0d16e1c27414b5f3e11e842e336fadb3e75
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233321"
---
# <a name="upgrade-your-microsoft-365-for-business-users-to-the-latest-office-client"></a>비즈니스용 Microsoft 365 사용자를 최신 Office 클라이언트로 업그레이드

## <a name="office-2010-reaches-end-of-support"></a>Office 2010 지원 종료

Office 2010은 2020년 10월 13일 지원이 종료됩니다. Microsoft는 더 이상 다음을 제공하지 않습니다.

- 문제에 대한 기술 지원

- 발견된 문제에 대한 버그 수정

- 발견된 취약점에 대한 보안 수정

자세한 [내용은 Office 2010](https://docs.microsoft.com/deployoffice/endofsupport/office-2010-end-support-roadmap) 지원 종료 로드맵을 참조하세요.

 **이 항목은 적합한가요?**
  
 조직의 비즈니스용 Microsoft 365 구독을 담당하는 관리자인 경우 올바른 장소에 있습니다. 관리자는 일반적으로 사용자 관리, 암호 재설정, Office 설치 관리, 라이선스 추가 또는 제거와 같은 작업을 담당합니다.

 관리자가 아니며 [Microsoft 365](https://support.microsoft.com/office/28cbc8cf-1332-4f04-9123-9b660abb629e#BKMK_OfficePlans) 패밀리 제품이 있는 경우 이전 가정용 Office 버전을 업그레이드하는 방법에 대한 자세한 내용은 [Office를](https://support.microsoft.com/office/ee68f6cf-422f-464a-82ec-385f65391350) 업그레이드하는 방법을 참조하세요.

## <a name="get-ready-to-upgrade-to-microsoft-365"></a>Microsoft 365로 업그레이드 준비

관리자는 조직의 사용자가 설치할 수 있는 Office 버전을 제어합니다. 조직의 사용자가 Office 2010, Office 2013 또는 Office 2016과 같은 이전 버전의 Office를 최신 버전으로 업그레이드하여 보안 및 생산성 향상을 활용하는 것이 좋습니다.

## <a name="upgrade-steps"></a>업그레이드 단계

아래 단계에서는 사용자를 최신 Office 데스크톱 클라이언트로 업그레이드하는 프로세스를 안내합니다. 업그레이드 프로세스를 시작하기 전에 이러한 단계를 읽어보는 것이 좋습니다.
  
## <a name="step-1---check-system-requirements"></a>1단계 - 시스템 요구 사항 확인

[Office의 시스템](https://www.microsoft.com/microsoft-365/microsoft-365-and-office-resources) 요구 사항을 확인하여 장치가 최신 버전의 Office와 호환되는지 확인합니다. 예를 들어 최신 버전의 Office는 Windows XP 또는 Windows Vista를 실행하는 컴퓨터에 설치할 수 없습니다.
  
> [!TIP]
> 조직의 사용자가 PC 또는 노트북에서 이전 버전의 Windows를 실행하는 경우 Windows 10으로 업그레이드하는 것이 좋습니다. Windows 7의 지원이 종료됩니다. 자세한 [내용은 2020년 1월에 Windows 7에](https://www.microsoft.com/microsoft-365/windows/end-of-windows-7-support?rtc=1) 대한 지원이 종료됩니다.

[Windows 10](https://www.microsoft.com/windows/windows-10-specifications) 시스템 요구 사항을 확인하여 운영 체제를 업그레이드할 수 있는지 확인합니다.

### <a name="check-application-compatibility"></a>응용 프로그램 호환성 확인

업그레이드를 성공적으로 진행하려면 VBA 스크립트, 매크로, 타사 추가 기능, 복잡한 문서 및 스프레드시트를 비롯한 Office 응용 프로그램을 식별하고 최신 버전의 Office와의 호환성을 평가하는 것이 좋습니다.
  
예를 들어 현재 Office 설치에서 타사 추가 기능을 사용하는 경우 제조업체에 문의하여 최신 버전의 Office와 호환되는지를 문의합니다.
  
## <a name="step-2---check-your-existing-subscription-plan"></a>2단계 - 기존 구독 계획 확인

일부 Microsoft 365 요금제에는 Office의 전체 데스크톱 버전이 포함되어 없습니다. 요금제에 Office가 포함되어하지 않는 경우 업그레이드 단계가 다릅니다.
  
어떤 구독 요금제가 있는지 잘 모르겠나요? 비즈니스용 [Microsoft 365 구독에 대한 자세한 내용은 다음을 참조하세요.](../admin-overview/what-subscription-do-i-have.md)
  
기존 계획에 Office가 포함되어 있는 경우 [3단계 - Office 제거로 진행합니다.](#step-3---uninstall-office)
  
기존 계획에 Office가 포함되어하지 않는 경우 아래 옵션에서 선택합니다.
  
### <a name="upgrade-options-for-plans-that-dont-include-office"></a>Office를 포함하지 않는 계획에 대한 업그레이드 옵션

 **옵션 1: Office 구독 전환**

Office를 포함하는 구독으로 전환합니다. 다른 [비즈니스용 Microsoft 365 요금제로 전환을 참조합니다.](../../commerce/subscriptions/switch-to-a-different-plan.md)

**옵션 2: Office의 개별, 일회성 구매 구입 또는 볼륨 라이선스를 통해 Office 구입**

 - Office의 개인 일회성 구매를 구입합니다. [Office Home &amp; Business 또는](https://products.office.com/home-and-business) Office Professional [참조](https://products.office.com/professional)

     또는

 - 볼륨 라이선스를 통해 여러 Office 복사본을 구입합니다. 볼륨 [라이선싱을 통해 사용할 수 있는 제품군을 비교합니다.](https://products.office.com/business/microsoft-office-volume-licensing-suites-comparison)

## <a name="step-3---uninstall-office"></a>3단계 - Office 제거

최신 버전의 Office를 설치하기 전에 이전 버전의 Office를 모두 제거하는 것이 좋습니다. 그러나 Office 업그레이드에 대한 마음이 바뀌면 Office를 제거한 후 다시 설치하지 못하게 될 다음 인스턴스를 참고하십시오.
  
타사 추가 기능을 사용할 경우 제조업체에 문의하여 최신 버전의 Office에서 작동할 업데이트가 있는지 문의하는 것이 좋습니다.

> [!TIP]
> Office를 제거하는 동안 문제가 있는 경우 Microsoft 지원 및 복구 도우미 도구를 사용하여 Office 제거: Microsoft 지원 및 복구 도우미 다운로드 및 실행을 지원할 [수 있습니다.](https://go.microsoft.com/fwlink/?LinkID=2155008)

### <a name="select-the-version-of-office-you-want-to-uninstall"></a>제거하려는 Office 버전 선택

- [PC에서](https://support.microsoft.com/office/9dd49b83-264a-477a-8fcc-2fdf5dbf61d8)

- [Mac에서](https://support.microsoft.com/office/eefa1199-5b58-43af-8a3d-b73dc1a8cae3)
  
### <a name="known-issues-trying-to-reinstall-older-versions-of-office-after-an-uninstall"></a>제거 후 이전 버전의 Office를 다시 설치하려는 알려진 문제

 **볼륨 라이선스를 통한 Office** 이러한 볼륨 라이선스 버전의 Office의 원본 파일에 더 이상 액세스할 수 없는 경우 다시 설치하지 못합니다.

 **컴퓨터에 미리 설치된 Office** 디스크 또는 제품 키가 더 이상 없는 경우(Office와 함께 온 경우) 다시 설치할 수 없습니다.

 **지원되지 않는 구독** Office 365 Small Business Premium 또는 Office 365 Mid-Size Business와 같은 중단된 구독을 통해 Office 복사본을 얻은 경우 구독과 함께 제공된 제품 키가 없는 경우 이전 버전의 Office를 설치할 수 없습니다.

이전 버전의 Office를 최신 버전과 나란히 설치하려면 이 버전이 지원되는 버전 목록을 볼 수 있으며, 동일한 [PC에서 다른 버전의 Office를](https://support.microsoft.com/office/6ebb44ce-18a3-43f9-a187-b78c513788bf)설치 및 사용할 수 있습니다. 예를 들어 이전 버전의 Office와 함께 사용하는 타사 추가 기능을 설치한 경우 최신 버전과 호환되는지 아직 확실하지 않은 경우 함께 설치하는 것이 좋습니다.

## <a name="step-4---assign-office-licenses-to-users"></a>4단계 - 사용자에게 Office 라이선스 할당

아직 Office를 설치해야 하는 조직의 사용자에게 라이선스를 할당하지 않은 경우 [비즈니스용 Microsoft 365의](../manage/assign-licenses-to-users.md)사용자에게 라이선스 할당을 참조합니다.
  
## <a name="step-5---install-office"></a>5단계 - Office 설치

라이선스가 있는 모든 사용자를 업그레이드하려는 사용자를 확인한 후 마지막 단계는 Office를 설치하도록 하는 것입니다. PC 또는 Mac에 Office 다운로드 및 설치 또는 다시 설치를 [참조합니다.](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)
  
> [!TIP]
> 사용자가 직접 Office를 설치하지 못하게 하려는 경우 [Office 365에서](https://docs.microsoft.com/DeployOffice/manage-software-download-settings-office-365)소프트웨어 다운로드 설정 관리를 참조하세요. Office 배포 [도구를](https://docs.microsoft.com/DeployOffice/overview-office-deployment-tool) 사용하여 Office 소프트웨어를 로컬 네트워크에 다운로드한 다음 일반적으로 사용하는 소프트웨어 배포 방법을 사용하여 Office를 배포할 수 있습니다.
