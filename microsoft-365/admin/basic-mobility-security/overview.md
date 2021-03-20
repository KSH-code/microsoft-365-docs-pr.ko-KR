---
title: Microsoft 365의 기본 모바일 및 보안 개요
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
description: 기본 모바일 및 보안을 사용하여 장치 보안 정책 및 액세스 규칙을 설정할 수 있습니다.
ms.openlocfilehash: e74a5df6d10f8f3fb7b420e428380af97ba75597
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906255"
---
# <a name="overview-of-basic-mobility-and-security-for-microsoft-365"></a>Microsoft 365의 기본 모바일 및 보안 개요

모바일 장치가 Microsoft 365 조직에 연결되어 있는 경우 기본 이동성 및 보안을 사용하여 모바일 장치를 관리하고 보호할 수 있습니다. 스마트폰 및 태블릿과 같은 모바일 장치를 사용하여 회사 전자 메일, 일정, 연락처 및 문서에 액세스하는 방식은 직원들이 시간과 장소의 구애를 받지 않고 업무를 완료하도록 하는 데 큰 역할을 합니다. 따라서 사용자가 장치를 사용할 때 조직의 정보를 보호하는 것이 중요합니다. 기본 모바일 및 보안을 사용하여 장치 보안 정책 및 액세스 규칙을 설정하고 분실하거나 도난당한 모바일 장치를 초기화할 수 있습니다.

:::image type="content" source="../../media/basic-mobility-security/bms-3-setup.png" alt-text="기본 이동성 및 보안 설정":::

## <a name="what-types-of-devices-can-you-manage"></a>어떤 종류의 장치를 관리할 수 있나요?

기본 모바일 및 보안을 사용하여 Windows Phone, Android, iPhone 및 iPad와 같은 다양한 유형의 모바일 장치를 관리할 수 있습니다. 조직의 사용자들이 사용하는 모바일 장치를 관리하려면 각 사용자마다 해당 Microsoft 365 라이선스가 있어야 합니다. 해당 장치는 기본 Mobility and Security에 등록되어야 합니다.

각 장치 유형에 대해 지원되는 기본 모바일 및 보안 기능을 자세한 내용은 [Capabilities of Basic Mobility and Security을 참조하세요.](capabilities.md)

## <a name="setup-steps-for-basic-mobility-and-security"></a>기본 모바일 및 보안 설정 단계

Microsoft 365 전역 관리자는 다음 단계를 완료하여 기본 모바일 및 보안을 활성화하고 설정해야 합니다. 자세한 단계는 [Set up Basic Mobility and Security의 지침을 따르세요.](set-up.md) 

다음은 단계에 대한 요약입니다.

**1단계:** 기본 이동성 및 보안 설정의 단계에 따라 기본 모바일 및  [보안을 활성화합니다.](set-up.md)

**2단계:** 예를 들어 iOS 장치를 관리하는 APNs 인증서를 만들고 Windows 휴대폰을 지원하기 위해 도메인에 대한 DNS(Domain Name System) 레코드를 추가하여 기본 모바일 및 보안을 설정합니다.

**3단계:** 장치 정책을 만들어 사용자 그룹에 적용합니다. 이 작업을 통해 사용자는 디바이스에서 등록 메시지를 받을 수 있으며 등록을 완료하면 장치에 대해 설정한 정책에 따라 디바이스가 제한됩니다. 자세한 내용은 기본 모바일 및 보안을 사용하여 모바일 장치 [등록을 참조하세요.](enroll-your-mobile-device.md) 

:::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="기본 보안 및 모바일 정책 설정":::

## <a name="device-management-tasks"></a>장치 관리 작업

기본 Mobility and Security를 설정하고 사용자가 장치를 등록한 후 필요한 경우 디바이스를 관리하거나 액세스를 차단하거나 장치를 초기화할 수 있습니다. 작업을 완료할 위치를 포함하여 몇 가지 일반적인 장치 관리 작업에 대한 자세한 내용은 [Microsoft 365용](manage-enrolled-devices.md)모바일 장치 관리에 등록된 장치 관리를 참조하세요.

## <a name="other-ways-to-manage-devices-and-apps"></a>장치 및 앱을 관리하는 다른 방법

MAM(모바일 앱 관리)만 필요한 경우(예: 자신의 장치에서 작업 프로젝트를 업데이트하는 사용자) Intune은 장치 등록 및 관리 외에 다른 옵션을 제공합니다. Intune 구독을 사용하면 사용자 장치가 Intune에 등록되지 않은 경우에도 Azure Portal을 사용하여 MAM 정책을 설정할 수 있습니다. 자세한 내용은 앱 보호 정책 [개요를 참조하세요.](/mem/intune/apps/app-protection-policy)

## <a name="related-topics"></a>관련 주제

[기본 이동성 및 보안 설정](set-up.md)

[기본 모바일 및 보안을 사용하여 모바일 장치 등록](enroll-your-mobile-device.md)

[Microsoft 365용 모바일 장치 관리에 등록된 장치 관리](manage-enrolled-devices.md)

[기본 모바일 및 보안으로 관리되는 장치에 대한 세부 정보 확인](get-details-about-managed-devices.md)