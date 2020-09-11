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
description: 기본 모바일 및 보안을 사용 하 여 장치 보안 정책 및 액세스 규칙을 설정 합니다.
ms.openlocfilehash: 177b0769f3cad928d05a41cfe95d5d62ab2b4786
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430249"
---
# <a name="overview-of-basic-mobility-and-security-for-microsoft-365"></a>Microsoft 365의 기본 모바일 및 보안 개요

기본 모바일 및 보안을 사용 하 여 Microsoft 365 조직에 연결 되어 있는 모바일 장치를 관리 하 고 보호할 수 있습니다. 스마트폰 및 태블릿과 같은 모바일 장치를 사용하여 회사 전자 메일, 일정, 연락처 및 문서에 액세스하는 방식은 직원들이 시간과 장소의 구애를 받지 않고 업무를 완료하도록 하는 데 큰 역할을 합니다. 따라서 사용자가 장치를 사용할 때 조직의 정보를 보호 하는 것이 중요 합니다. 기본 이동성 및 보안을 사용 하 여 장치 보안 정책 및 액세스 규칙을 설정 하 고 분실 하거나 도난당 한 모바일 장치를 지울 수 있습니다.

:::image type="content" source="../../media/basic-mobility-security/bms-3-setup.png" alt-text="기본 이동성 및 보안 설정":::

## <a name="what-types-of-devices-can-you-manage"></a>어떤 종류의 장치를 관리할 수 있나요?

기본 이동성 및 보안을 사용 하 여 Windows Phone, Android, iPhone 및 iPad와 같은 다양 한 유형의 모바일 장치를 관리할 수 있습니다. 조직의 사용자가 사용 하는 모바일 장치를 관리 하려면 각 사용자에 게 해당 하는 Microsoft 365 라이선스가 있어야 하며 해당 장치를 기본 Mobility and Security에 등록 해야 합니다.

각 장치 유형에 대해 지원 되는 기본 이동성 및 보안에 대 한 자세한 내용은 [기본 이동성 및 보안 기능](capabilities.md)을 참조 하세요.

## <a name="setup-steps-for-basic-mobility-and-security"></a>기본 이동성 및 보안을 위한 설치 단계

Microsoft 365 전역 관리자는 다음 단계를 완료 하 여 기본적인 이동성 및 보안을 활성화 하 고 설정 해야 합니다. 자세한 단계는 [기본 이동성 및 보안 설정](set-up.md)의 지침을 따르세요. 

다음은 단계를 요약 한 것입니다.

**1 단계:**  [기본 이동성 및 보안 설정](set-up.md)의 단계를 수행 하 여 기본 이동성 및 보안을 활성화 합니다.

**2 단계:** Windows phone을 지원 하기 위해 iOS 장치를 관리 하 고 도메인에 대 한 DNS (Domain Name System) 레코드를 추가 하는 APNs 인증서를 만드는 등의 방법으로 기본 이동성 및 보안을 설정 합니다.

**3 단계:** 장치 정책을 만들고 사용자 그룹에 적용 합니다. 이렇게 하면 사용자가 자신의 장치에서 등록 메시지를 가져오고 등록이 완료 되 면 해당 장치가 설정한 정책에 따라 제한 됩니다. 자세한 내용은 [기본 이동성 및 보안을 사용 하 여 모바일 장치 등록](enroll-your-mobile-device.md)을 참조 하세요. 

:::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="기본 보안 및 이동성 정책 설정":::

## <a name="device-management-tasks"></a>장치 관리 작업

기본 이동성 및 보안을 설정 하 고 사용자가 장치를 등록 한 후에는 필요에 따라 장치를 관리 하거나, 액세스를 차단 하거나, 장치를 지울 수 있습니다. 작업 완료 위치를 비롯 한 일부 일반 장치 관리 작업에 대 한 자세한 내용은 [모바일 장치 관리에 등록 된 장치 관리 Microsoft 365](manage-enrolled-devices.md)를 참조 하십시오.

## <a name="other-ways-to-manage-devices-and-apps"></a>장치 및 앱을 관리 하는 다른 방법

사용자가 자신의 장치에서 작업 프로젝트를 업데이트 하는 경우에는 MAM (모바일 앱 관리)만 필요한 경우 Intune에서 장치를 등록 하 고 관리 하는 것 외에 다른 옵션을 제공 합니다. Intune 구독을 사용 하면 사용자의 장치가 Intune에 등록 되어 있지 않더라도 Azure portal을 통해 MAM 정책을 설정할 수 있습니다. 자세한 내용은 [앱 보호 정책 개요](https://go.microsoft.com/fwlink/?LinkId=2132517)를 참조 하세요.

## <a name="related-topics"></a>관련 항목

[기본 이동성 및 보안 설정](set-up.md)

[기본 이동성 및 보안을 사용 하 여 모바일 장치 등록](enroll-your-mobile-device.md)

[Microsoft 365에 대 한 모바일 장치 관리에 등록 되어 있는 장치 관리](manage-enrolled-devices.md)

[기본 이동성 및 보안으로 관리 되는 장치에 대 한 세부 정보 보기](get-details-about-managed-devices.md)