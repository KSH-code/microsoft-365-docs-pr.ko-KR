---
title: 비즈니스 사용자를 위한 Microsoft 365를 최신 Office 클라이언트로 업그레이드
f1.keywords:
- NOCSH
ms.author: kwekuako
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
- fwlink 824861; CampaignID O365_Comm_SR_UpgradeOffice
- AdminSurgePortfolio
ms.assetid: f6b00895-b5fd-4af6-a656-b7788ea20cbb
description: 사용자를 최신 Office 클라이언트로 업그레이드 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 22fe8e12e4aff4f9afe52e913ad57d37866dbb95
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44398813"
---
# <a name="upgrade-your-microsoft-365-for-business-users-to-the-latest-office-client"></a>비즈니스 사용자를 위한 Microsoft 365를 최신 Office 클라이언트로 업그레이드

## <a name="office-2010-reaches-end-of-support"></a>Office 2010가 지원 끝에 도달 합니다.

Office 2010는 2020 년 10 월 13 일에 지원 종료에 도달 합니다. Office 2010가 지원 종료에 도달 하면 Microsoft는 더 이상 다음을 제공 하지 않습니다.

- 문제에 대 한 기술 지원

- 발견 된 문제에 대 한 버그 수정 사항

- 검색 된 취약성에 대 한 보안 수정 프로그램

자세한 내용은 [Office 2010 지원 센터의 최종 로드맵을](https://docs.microsoft.com/deployoffice/office-2010-end-support-roadmap) 참조 하세요.

 **이 항목이 적합 한 주제 입니까?**
  
 조직의 Microsoft 365 for business 구독을 담당 하는 관리자 인 경우 올바른 위치에 있습니다. 관리자는 일반적으로 사용자 관리, 암호 다시 설정, Office 설치 관리, 라이선스 추가 또는 제거와 같은 작업을 담당 합니다.

 관리자가 아닌 경우 [Microsoft 365](https://support.office.com/article/28cbc8cf-1332-4f04-9123-9b660abb629e.aspx#BKMK_OfficePlans) 제품을 사용 하는 경우 office 업그레이드에 대 한 자세한 내용을 확인 [하는 방법을](https://support.office.com/article/ee68f6cf-422f-464a-82ec-385f65391350.aspx) 참조 하세요.

## <a name="get-ready-to-upgrade"></a>업그레이드 준비

관리자는 조직에서 설치할 수 있는 Office 사용자의 버전을 제어 합니다. 조직의 사용자가 Office 2010, Office 2013 또는 Office 2016과 같은 이전 버전의 Office를 실행 하 여 보안 및 생산성 향상을 활용 하는 데 도움이 되도록 하는 것이 좋습니다.

## <a name="upgrade-steps"></a>업그레이드 단계

아래 단계에서는 사용자를 최신 Office 데스크톱 클라이언트로 업그레이드 하는 프로세스를 안내 합니다. 업그레이드 프로세스를 시작 하기 전에 이러한 단계를 읽어 보는 것이 좋습니다.
  
## <a name="step-1---check-system-requirements"></a>1 단계-시스템 요구 사항 확인

Office의 [시스템 요구 사항을 확인](https://products.office.com/office-system-requirements) 하 여 장치가 최신 버전의 office와 호환 되는지 확인 합니다. 예를 들어 Windows XP 또는 Windows Vista를 실행 하는 컴퓨터에 최신 버전의 Office를 설치할 수 없습니다.
  
> [!TIP]
> 조직의 Pc 또는 랩톱에서 이전 버전의 Windows를 실행 하는 사용자가 있는 경우 Windows 10으로 업그레이드 하는 것이 좋습니다. Windows 7이 지원 종료에 도달 했습니다. 자세한 내용은 [Windows 7에 대 한 읽기 지원이 1 월 2020 일에 끝납니다](https://www.microsoft.com/microsoft-365/windows/end-of-windows-7-support?rtc=1) .

[Windows 10 시스템 요구 사항을](https://www.microsoft.com/windows/windows-10-specifications) 확인 하 여 운영 체제를 업그레이드할 수 있는지 알아봅니다.

### <a name="check-application-compatibility"></a>응용 프로그램 호환성 검사

성공적인 업그레이드를 위해서는 VBA 스크립트, 매크로, 타사 추가 기능 및 복잡 한 문서와 스프레드시트를 비롯 하 여 Office 응용 프로그램을 확인 하 고 최신 버전의 Office와의 호환성을 평가 하는 것이 좋습니다.
  
예를 들어 현재 Office 설치와 함께 타사 추가 기능을 사용 하는 경우 제조업체에 문의 하 여 최신 버전의 Office와 호환 되는지 확인 합니다.
  
## <a name="step-2---check-your-existing-subscription-plan"></a>2 단계-기존 구독 계획 확인

일부 Microsoft 365 계획에는 전체 데스크톱 버전의 Office가 포함 되지 않으며 계획에 Office가 포함 되지 않은 경우 업그레이드 단계가 달라 집니다.
  
보유 하 고 있는 구독 계획을 확실히 알 수 없습니까? [어떤 Microsoft 비즈니스 365 for business 구독이](../admin-overview/what-subscription-do-i-have.md) 있는지 확인 하세요.
  
기존 계획에 Office가 포함 되어 있는 경우 [3 단계-Office 제거](#step-3---uninstall-office)로 이동 합니다.
  
기존 계획에 Office가 포함 되어 있지 않은 경우 아래 옵션 중에서 선택 합니다.
  
### <a name="upgrade-options-for-plans-that-dont-include-office"></a>Office를 포함 하지 않는 요금제 업그레이드 옵션

 **옵션 1: Office 구독 전환**

Office를 포함 하는 구독으로 전환 합니다. [다른 Microsoft 365 for business 요금제로 전환을](../../commerce/subscriptions/switch-to-a-different-plan.md)참조 하세요.

**옵션 2: 개별 Office 구매 구매 또는 볼륨 라이선스를 통해 Office 구입**

 - Office의 개별 일회성 구매를 구매 합니다. [Office Home &amp; Business](https://products.office.com/home-and-business) 또는 [office Professional](https://products.office.com/professional) 참조

     또는

 - 볼륨 라이선스를 통해 여러 Office 복사본을 구입 합니다. [볼륨 라이선스를 통해 사용할 수 있는 제품군 비교](https://products.office.com/business/microsoft-office-volume-licensing-suites-comparison)를 참조 하세요.

## <a name="step-3---uninstall-office"></a>3 단계-Office 제거

최신 버전의 Office를 설치 하기 전에 이전 버전의 Office를 모두 제거 하는 것이 좋습니다. 그러나 Office를 업그레이드 하는 방법에 대 한 생각이 변경 되는 경우에는 다음에 Office를 제거한 후 다시 설치할 수 없게 됩니다.
  
타사 추가 기능을 사용 하는 경우 제조업체에 문의 하 여 최신 버전의 Office에서 작동 하는 업데이트가 있는지 확인 하는 것이 좋습니다.

### <a name="select-the-version-of-office-you-want-to-uninstall"></a>제거 하려는 Office 버전을 선택 합니다.

- [PC에서](https://support.office.com/article/9dd49b83-264a-477a-8fcc-2fdf5dbf61d8.aspx)

- [Mac에서](https://support.office.com/article/eefa1199-5b58-43af-8a3d-b73dc1a8cae3.aspx)
  
### <a name="known-issues-trying-to-reinstall-older-versions-of-office-after-an-uninstall"></a>제거 후 이전 버전의 Office를 다시 설치 하려고 할 때의 알려진 문제

 **볼륨 라이선스를 통해 Office 사용** 이러한 볼륨 라이선스 버전의 Office에 대 한 액세스 권한이 더 이상 없는 경우에는 다시 설치할 수 없게 됩니다.

 **컴퓨터에 미리 설치 된 Office** 디스크 또는 제품 키가 더 이상 없는 경우에는 Office를 다시 설치할 수 없게 됩니다.

 **지원 되지 않는 구독** Office 365 Small Business Premium 또는 Office 365 중간급 기업과 같이 단종 된 구독을 통해 Office 복사본을 구입한 경우 구독에 제공 된 제품 키가 없으면 이전 버전의 Office를 설치할 수 없게 됩니다.

최신 버전을 사용 하 여 이전 버전의 Office를 설치 하려는 경우에는이 기능이 지원 되는 버전 목록을 확인 하 고 [동일한 PC에 다른 버전의 Office를 설치 하 고 사용할](https://support.office.com/article/6ebb44ce-18a3-43f9-a187-b78c513788bf.aspx)수 있습니다. 예를 들어 이전 버전의 Office에서 사용 중인 타사 추가 기능을 설치한 경우 아직 최신 버전과 호환 되지 않는 경우에는 side-by-side 설치를 선택 하는 것이 적절 합니다.

## <a name="step-4---assign-office-licenses-to-users"></a>4 단계-사용자에 게 Office 라이선스 할당

Office를 설치 해야 하는 조직의 모든 사용자에 게 라이선스를 할당 하지 않은 경우 [비즈니스에 대 한 Microsoft 365의 사용자에 게 라이선스 할당](../manage/assign-licenses-to-users.md)을 참조 하세요.
  
## <a name="step-5---install-office"></a>5 단계-Office 설치

모든 사용자에 게 라이선스를 업그레이드할지 확인 한 후에는 [PC 또는 Mac에 office를 설치 하거나 다운로드 및 설치 또는 다시](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658.aspx)설치를 참조 하세요.
  
> [!TIP]
> 사용자가 Office를 설치 하지 못하도록 하려면 [office 365에서 소프트웨어 다운로드 설정 관리](https://docs.microsoft.com/DeployOffice/manage-software-download-settings-office-365)를 참조 하세요. [Office 배포 도구](https://docs.microsoft.com/DeployOffice/overview-office-deployment-tool) 를 사용 하 여 로컬 네트워크에 office 소프트웨어를 다운로드 한 다음 일반적으로 사용 하는 소프트웨어 배포 방법을 사용 하 여 office를 배포할 수 있습니다.
