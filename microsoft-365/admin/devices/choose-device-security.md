---
title: 서로 다른 장치 및 앱 데이터 보호 방법 비교
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
description: 여러 MDM 및 MAM 방법 중에서 선택 합니다.
ms.openlocfilehash: 6231b7c82f280a60ae9d30bcf27697dc131b2471
ms.sourcegitcommit: 5a355bde865369f64ea1788a378da23c65b1d249
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/06/2020
ms.locfileid: "48930283"
---
# <a name="options-for-protecting-your-devices-and-app-data"></a>장치 및 앱 데이터를 보호 하기 위한 옵션

비즈니스 및 기업을 위해 Microsoft 365을 사용 하 여 조직 장치 및 데이터를 보호 하는 몇 가지 방법이 있습니다. 다음 독립 실행형 계획을 사용할 수 있습니다.

- Intune (Microsoft Endpoint Management의 일부)
- Azure Active Directory Premium 요금제입니다.
- 기본 이동성 및 보안 (비즈니스 및 엔터프라이즈 요금제에 대 한 대부분의 Microsoft 365에 포함 됨) 또는 이전 독립 실행형 계획이 일부 또는 모두 포함 된 구독을 사용 합니다.

- Microsoft 365 Business Premium subscription-300 사용자의 중소 기업에 대 한 보안 및 위협 보호를 포함 합니다.
- Microsoft 365 advanced security 및 threat protection이 포함 된 Enterprise 요금제입니다.

## <a name="device-management-options"></a>장치 관리 옵션

![어떤 구독에서 어떤 MDM 및 MAM 방법을 사용 해야 하는지 보여 주는 그림입니다.](../../m365-mam-mdm.png)

- **기본 이동성 및 보안** 은 대부분의 microsoft 365 요금제와 함께 제공 되며 Microsoft 365 business Standard 및 Microsoft 365 business Basic에 제공 되는 유일한 기본 제공 옵션입니다. 자세한 내용은 [기본 이동성 및 보안의 가용성](../basic-mobility-security/choose-between-basic-mobility-and-security-and-intune.md#availability-of-basic-mobility-and-security-and-intune)을 참조 하세요. 

    Microsoft 365 Business Basic 또는 Microsoft 365 Business Standard를 보유 하 고 있는 경우 조직의 보안 요구 사항이 더 복잡 한 경우 Intune을 구입할 수도 있습니다.
 
- **Microsoft Intune** 은 비즈니스 또는 기업 요금제에 대 한 일부 microsoft 365에도 포함 되어 있는 독립 실행형 계획입니다. 독립 실행형 또는 구독 일부로 Intune을 사용 하는 경우에는 장치 및 응용 프로그램 데이터 관리를 미세 조정할 수 있는 기능을 제공 합니다. Microsoft 365의 가용성에 대 한 자세한 내용은 [Intune 가용성](../basic-mobility-security/choose-between-basic-mobility-and-security-and-intune.md#availability-of-basic-mobility-and-security-and-intune)를 참조 하세요.

    Microsoft Intune은 MDM (모바일 장치 관리) 및 MAM (모바일 응용 프로그램 관리)에 중점을 둔 클라우드 기반 서비스입니다. 휴대폰, 태블릿 및 랩톱을 포함 하 여 조직의 장치를 사용 하는 방법을 제어 합니다. 응용 프로그램을 제어 하도록 특정 정책을 구성할 수도 있습니다. 자세한 내용은 [Microsoft Intune 설명서](https://docs.microsoft.com/mem/intune/)를 참조 하세요.

- **AZURE AD (Active Directory) 프리미엄** 계획은 비즈니스 및 엔터프라이즈 요금제 용 Microsoft 365도 함께 제공 되는 독립 실행형 계획입니다. 자세한 내용은 [AZURE AD 가격 책정](https://azure.microsoft.com/pricing/details/active-directory/)를 참조 하세요.

     Azure AD premium P1 및 Azure AD Premium P2를 사용 하면 조건부 액세스 기능, 셀프 서비스 암호 재설정 등을 설정할 수 있습니다. 프리미엄 계획의 기능에 대 한 자세한 내용은 [AZURE AD 가격](https://azure.microsoft.com/pricing/details/active-directory/) 페이지를 참조 하세요.
- **Microsoft 365 Business Premium** 에는 Intune 및 Azure Active Directory premium P1 및 Office 365 Advanced Threat Protection이 포함 되어 있습니다. 
 
    Microsoft 365 Business Premium에서는 장치 및 앱 데이터를 보호 하기 위한 정책 템플릿 집합을 제공 합니다. 이를 통해 300 사용자에 게 있어 대부분의 비즈니스에 대 한 보안 및 위협 보호 수준이 향상 됩니다. 자세한 내용은 [설치 마법사에서 microsoft 365 Business premium 설정](../../business/set-up.md), [Windows 10 컴퓨터 보안](../../business/secure-win-10-pcs.md)및 [microsoft 365 business premium 보안 및 규정 준수 기능](../../business/security-features.md)을 참조 하세요.

- **Enterprise 구독에 대 한 microsoft 365에** 는 microsoft Intune 및 E5에도 Azure AD premium 요금제 1 및 2가 포함 됩니다.

    Microsoft 365 E5는 모든 Microsoft 365 구독에 대 한 보안 및 위협 보호를 최고 수준으로 제공 합니다. 자세한 내용은 [Microsoft 365 for 엔터프라이즈 개요](../../enterprise/microsoft-365-overview.md)를 참조 하세요.
