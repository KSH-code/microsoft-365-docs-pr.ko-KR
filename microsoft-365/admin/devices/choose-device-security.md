---
title: 다양한 장치 및 앱 데이터 보호 방법 비교
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: 다른 MDM 및 MAM 방법 중 선택
ms.openlocfilehash: c4928f272c0bdd8a7b6883f506cebf9a153e9c49
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910537"
---
# <a name="options-for-protecting-your-devices-and-app-data"></a>장치 및 앱 데이터 보호 옵션

비즈니스 및 엔터프라이즈용 Microsoft 365를 사용하여 조직의 장치와 데이터를 보호하는 여러 가지 방법이 있습니다. 다음과 같은 독립 실행형 계획을 사용할 수 있습니다.

- Intune(Microsoft Endpoint Management의 일부)
- Azure Active Directory Premium 요금제.
- 기본 이동성 및 보안(대부분의 비즈니스용 Microsoft 365 및 엔터프라이즈 요금제에 포함) 또는 이전 독립 실행형 계획의 일부 또는 전체를 포함 하는 구독을 사용 합니다.

- 300명 미만의 중소기업에 대한 보안 및 위협 방지를 포함하는 Microsoft 365 Business Premium 구독입니다.
- 고급 보안 및 위협 방지를 포함 하는 Microsoft 365 Enterprise 계획입니다.

## <a name="device-management-options"></a>장치 관리 옵션

- **기본 이동성 및 보안은** 대부분의 Microsoft 365 요금제에서 제공하며 Microsoft 365 Business Standard 및 Microsoft 365 Business Basic에 대해 제공되는 유일한 기본 제공 선택입니다. 자세한 내용은 [Basic Mobility and Security의 가용성을 참조하세요.](../basic-mobility-security/choose-between-basic-mobility-and-security-and-intune.md#availability-of-basic-mobility-and-security-and-intune) 

    Microsoft 365 Business Basic 또는 Microsoft 365 Business Standard가 있는 경우 조직에 더 복잡한 보안 요구가 있는 경우 Intune을 구입할 수도 있습니다.
 
- **Microsoft Intune은** 일부 비즈니스용 Microsoft 365 또는 엔터프라이즈 요금제에도 포함된 독립 실행형 요금제입니다. Intune이 독립 실행형 또는 구독의 일부로 있는 경우 장치 및 앱 데이터 관리를 미세 조정할 수 있습니다. Microsoft 365의 가용성에 대한 자세한 내용은 [Intune의 가용성을 참조하세요.](../basic-mobility-security/choose-between-basic-mobility-and-security-and-intune.md#availability-of-basic-mobility-and-security-and-intune)

    Microsoft Intune은 MDM(모바일 장치 관리) 및 MAM(모바일 응용 프로그램 관리)에 중점을 두는 클라우드 기반 서비스입니다. 휴대폰, 태블릿 및 노트북을 포함하여 조직의 장치를 사용하는 방법을 제어할 수 있습니다. 응용 프로그램을 제어하도록 특정 정책을 구성할 수도 있습니다. 자세한 내용은 [Microsoft Intune 설명서를 참조하세요.](/mem/intune/)

- **Azure AD(Active Directory) Premium** 요금제는 일부 비즈니스 및 엔터프라이즈용 Microsoft 365 요금제와 함께 제공된 독립 실행형 요금제입니다. 자세한 내용은 [Azure AD 가격을 참조하세요.](https://azure.microsoft.com/pricing/details/active-directory/)

     Azure AD Premium P1 및 Azure AD Premium P2를 사용하면 조건부 액세스 기능, 셀프 서비스 암호 재설정 등을 설정할 수 있습니다. Premium 요금제의 기능에 대한 자세한 내용은 Azure AD 가격 페이지를 [참조하세요.](https://azure.microsoft.com/pricing/details/active-directory/)
- **Microsoft 365 Business Premium에는** Intune 및 Azure Active Directory Premium P1 및 Office 365 Advanced Threat Protection이 포함되어 있습니다. 
 
    Microsoft 365 Business Premium은 장치 및 앱 데이터를 보호하기 위한 정책 템플릿 집합을 제공합니다. 300명 미만의 대부분의 기업에 대해 좋은 수준의 보안 및 위협 보호를 제공합니다. 자세한 내용은 설치 마법사, 보안 [Windows 10](../../business/secure-win-10-pcs.md)컴퓨터 및 [Microsoft 365 Business Premium](../../business/set-up.md)보안 및 규정 준수 기능에서 Microsoft [365 Business Premium 설정을 참조하세요.](../../business/security-features.md)

- **엔터프라이즈용 Microsoft 365** 구독에는 Microsoft Intune이 포함되어 있으며 E5에는 Azure AD Premium 요금제 1과 2도 포함되어 있습니다.

    Microsoft 365 E5는 모든 Microsoft 365 구독의 최고 수준의 보안 및 위협 보호를 제공합니다. 자세한 내용은 [엔터프라이즈용 Microsoft 365 개요를 참조하세요.](../../enterprise/microsoft-365-overview.md)