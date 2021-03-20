---
title: 기본 이동성 및 보안 FAQ(질문과 대답)
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: reference
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
description: 기본 모바일 및 보안에 대한 질문과 대답
ms.openlocfilehash: a538c0b3f9fa6a4bf1861734fc9dea94030760a3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906267"
---
# <a name="basic-mobility-and-security-frequently-asked-questions-faq"></a>기본 이동성 및 보안 FAQ(질문과 대답)

이 문서에는 Microsoft 365에서 모바일 장치를 관리하고 보호하는 데 도움이 되는 기능인 기본 이동성 및 보안에 대한 질문과 대답이 포함되어 있습니다. 질문에 대한 답변을 찾을 수 없는 경우 이 문서에 질문을 추가할 수 있도록 페이지에 설명을 남기면 알려주세요.

## <a name="how-can-i-get-basic-mobility-and-security-i-dont-see-it-in-the-microsoft-365-admin-center"></a>기본 이동성 및 보안을 어떻게 얻을 수 있나요? Microsoft 365 관리 센터에서 볼 수 없습니다.

1.  [Office 365](https://protection.office.com/) 보안 및 준수 페이지로 이동하여 기본 모바일 & 활성화합니다.

2.  장치 관리에 대한 데이터 > 이동하세요.

## <a name="how-can-i-get-started-with-device-management-in-basic-mobility-and-security"></a>기본 이동성 및 보안에서 장치 관리를 시작하려면 어떻게 하나요?

기본 이동성 및 보안을 시작하는 네 가지 단계가 있습니다. 

1. [Office 365](https://protection.office.com/)보안 및 준수로 이동하여 기본 모바일 & 활성화합니다.

2. 장치 정책에 대한 장치 > 데이터 손실 > 이동하세요.
    
3. 장치 관리 정책을 만들고 보안 그룹에 설정된 사용자 그룹에 적용합니다. 먼저 소규모 테스트 그룹에 정책을 배포하는 것이 좋습니다. 자세한 내용은 기본 모바일 및 보안에서 장치 보안 [정책 만들기를 참조하세요.](create-device-security-policies.md)

4. 정책이 적용된 사용자에게는 Microsoft 365 데이터에 액세스하려고 할 때 장치를 등록하라는 메시지가 표시될 수 있습니다. 자세한 내용은 기본 모바일 및 보안을 사용하여 모바일 장치 [등록을 참조하세요.](enroll-your-mobile-device.md)

자세한 내용은 Set [up Basic Mobility and Security을 참조합니다.](set-up.md)

## <a name="im-trying-to-set-up-basic-mobility-and-security-but-it-seems-stuck-the-microsoft-365-service-health-has-been-showing-provisioning-for-a-while-what-can-i-do"></a>기본 이동성 및 보안을 설정하려고 했지만 정체된 것 같은데요. Microsoft 365 서비스 상태는 한 동안 "프로비저닝"을 표시하고 있습니다. 어떻게 해야 하나요?

서비스를 준비하는 데 시간이 걸릴 수 있습니다. 프로비전이 완료되면 기본 모바일 및 보안 페이지가 표시됩니다. If you've waited 24 hours and the status is still provisioning, please contact Support and we'll help help out what the issue is. 지원 옵션에 대한 자세한 내용은 [여전히 도움이 필요하세요? 을 참조하세요.](https://support.microsoft.com/office/frequently-asked-questions-about-basic-mobility-and-security-3871f99c-c9db-4a23-86f9-902c1b02f58d#bkmk_needhelp)

## <a name="what-can-i-do-if-device-enrollment-fails"></a>장치 등록에 실패하면 어떻게 해야 하나요?

장치를 등록하는 데 문제가 있는 경우 먼저 다음을 확인합니다.

- 장치가 Intune과 같은 다른 모바일 장치 관리 공급자에 이미 등록되어 있지 않은지 확인합니다.

- 장치가 올바른 날짜 및 시간으로 설정되어 있는지 확인합니다.

- 디바이스의 다른 WIFI 또는 셀룰러 네트워크로 전환합니다.

- Android 또는 iOS 장치의 경우 디바이스에서 Intune 회사 포털 앱을 제거하고 다시 설치합니다.
    
등록이 여전히 작동하지 않는 경우 [Troubleshoot Basic Mobility and Security을 참조합니다.](troubleshoot.md)

## <a name="whats-the-difference-between-intune-and-basic-mobility-and-security"></a>Intune과 기본 이동성 및 보안의 차이점은 무엇입니까?

기본 Mobility and Security는 Intune 서비스에서 호스팅합니다. Microsoft 365에 추가된 혜택으로 제공되는 Intune 서비스의 하위 집합으로, 조직의 장치를 관리하기 위한 기본 제공 클라우드 기반 솔루션입니다. Intune 또는 Microsoft 365용 Basic Mobility and Security를 사용하는 것이 가장 적합한지 결정하는 데 도움이 되는 두 서비스를 나란히 비교한 내용은 [Choose between Basic Mobility Security and Intune을](choose-between-basic-mobility-and-security-and-intune.md)참조합니다.

## <a name="how-do-policies-work-for-basic-mobility-and-security-how-do-i-set-them-up-disable-them"></a>기본 이동성 및 보안에 대한 정책은 어떻게 작동하나요? 설정 방법 사용하지 않도록 설정하세요?

기본 모바일 및 보안에 대한 초기 설정을 완료한 후 정책을 만들어 보안 및 준수 센터의 사용자 & 적용합니다. 정책을 사용하려면 정책 사용자가 기본 이동성 및 보안에 장치를 등록해야 장치를 사용하여 Microsoft 365 데이터에 액세스할 수 있습니다. 설정하는 정책에 따라 모바일 장치의 설정(예: 암호를 다시 설정해야 하는 방법 또는 데이터 암호화가 필요한지 여부)이 결정됩니다. 자세한 내용은 [기본](create-device-security-policies.md)모바일 및 보안 및 Microsoft 365 규정 준수 센터에서 장치 보안   정책 [만들기를 참조하세요.](https://support.microsoft.com/office/7e696a40-b86b-4a20-afcc-559218b7b1b8)

장치 정책을 만들고 배포하는 단계별 지침은 [Create device security policies in Basic Mobility and Security를 참조하십시오.](create-device-security-policies.md)

특정 사용자 그룹이 정책의 영향을 받지 못하도록 제외하려는 경우 제외 그룹에 그룹을 추가할 수 있습니다.

## <a name="can-i-switch-from-exchange-activesync-device-management-to-basic-mobility-and-security-for-microsoft-365"></a>장치 관리에서 Exchange ActiveSync Microsoft 365의 기본 이동성 및 보안으로 전환할 수 있나요?

모바일 장치를 관리하기 위해 Exchange ActiveSync 정책을 이미 사용하고 있는 경우 기본 모바일 및 보안을 설정하는 단계에 따라 기본 모바일 및 보안을 사용할 수 있습니다. 자세한 내용은 사용자 및 장치 [액세스](../../compliance/protect-access-to-data-and-services.md) 보호 및 기본 이동성 [및 보안 설정 을 참조하세요.](set-up.md)

기본 모바일 및 보안에서 만든 정책을 사용자 그룹에 적용하면 이러한 정책은 Exchange ActiveSync 사용자에 대해 Exchange 관리 센터에서 이전에 만든 모바일 장치 사서함 정책 및 장치 액세스 규칙에 대해 다시 적용됩니다.

장치가 기본 모바일 및 보안에 등록된 후 Exchange ActiveSync 적용된 모바일 장치 사서함 정책 또는 장치 액세스 규칙은 무시됩니다.

## <a name="i--set-up-basic-mobility-and-security-but-now-i-want-to-remove-it-what-are-the-steps"></a>기본 Mobility and Security를 설정했지만 이제 제거합니다. 단계는 무엇입니까?

아쉽게도 기본 이동성 및 보안을 설정한 후에 단순히 "비프로비전"할 수 없습니다. 그러나 만든 장치 정책에서 사용자 보안 그룹을 제거하여 사용자 그룹에 대해 제거할 수 있습니다. 또는 디바이스 정책이 적용되지 않고 적용되지 않도록 장치 정책을 제거하여 모든 사용자에 대해 사용하지 않도록 설정할 수 있습니다. 자세한 내용은 기본 모바일 및 [보안 끄기 를 참조하세요.](turn-off.md)