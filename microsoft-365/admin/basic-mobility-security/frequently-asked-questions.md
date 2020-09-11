---
title: 기본 모바일 및 보안에 대해 자주 묻는 질문 (FAQ)
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
description: 기본적인 모바일 및 보안에 대 한 질문과 대답
ms.openlocfilehash: e05815392510ad54bb530457d7f0f6490ece4a95
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430260"
---
# <a name="basic-mobility-and-security-frequently-asked-questions-faq"></a>기본 모바일 및 보안에 대해 자주 묻는 질문 (FAQ)

이 문서에는 Microsoft 365에서 모바일 장치를 관리 하 고 보호 하는 데 도움이 되는 기능인 기본 이동성 및 보안에 대 한 질문과 대답이 포함 되어 있습니다. 질문에 대 한 답변을 찾을 수 없는 경우이 문서에 질문을 추가 하는 것을 고려할 수 있도록 페이지에 설명을 남겨 두는 것을 알려주십시오.

## <a name="how-can-i-get-basic-mobility-and-security-i-dont-see-it-in-the-microsoft-365-admin-center"></a>기본적인 이동성 및 보안을 얻으려면 어떻게 해야 합니까? Microsoft 365 관리 센터에 표시 되지 않음

1.  [Office 365 보안 & 준수](https://protection.office.com/) 페이지로 이동 하 여 기본적인 모바일 및 보안을 활성화 합니다.   

2.  장치 관리 > 데이터 손실 방지로 이동 합니다.   

## <a name="how-can-i-get-started-with-device-management-in-basic-mobility-and-security"></a>기본 이동성 및 보안에서 장치 관리를 시작 하려면 어떻게 해야 하나요?

기본 이동성 및 보안을 시작 하는 데는 다음과 같은 네 가지 단계가 있습니다. 

1. [Office 365 보안 & 준수](https://protection.office.com/)로 이동 하 여 기본적인 모바일 및 보안을 활성화 합니다.
    
2. 장치 관리 > 장치 정책에 > 데이터 손실 방지로 이동 합니다.
    
3. 장치 관리 정책을 만들고 보안 그룹에 설정 된 사용자 그룹에 적용 합니다. 먼저 소규모 테스트 그룹에 정책을 배포 하는 것이 좋습니다. 자세한 내용은 [기본 이동성 및 보안에서 장치 보안 정책 만들기](create-device-security-policies.md)를 참조 하세요.      

4. 정책이 적용 된 사용자는 Microsoft 365 데이터에 액세스 하려고 할 때 장치를 등록 하 라는 메시지가 표시 됩니다. 자세한 내용은 [기본 이동성 및 보안을 사용 하 여 모바일 장치 등록](enroll-your-mobile-device.md)을 참조 하세요.

자세한 내용은 [기본 이동성 및 보안 설정을](set-up.md)참조 하십시오.

## <a name="im-trying-to-set-up-basic-mobility-and-security-but-it-seems-stuck-the-microsoft-365-service-health-has-been-showing-provisioning-for-a-while-what-can-i-do"></a>기본 Mobility and Security을 설정 하려고 했지만 중단 되었습니다. Microsoft 365 서비스 상태에는 한 동안 "프로 비전"이 표시 되어 있습니다. 어떻게 해야 하나요?

서비스를 준비 하는 데 시간이 오래 걸릴 수 있습니다. 프로비저닝이 완료 되 면 Microsoft 365 용 모바일 장치 관리 페이지가 표시 됩니다. 24 시간을 기다린 후 상태가 여전히 프로 비전 중인 경우 지원 서비스에 문의 하 여 문제를 파악 하는 것이 좋습니다. 지원 옵션에 대 한 자세한 내용은 [여전히 도움이 필요 하세요?](https://support.microsoft.com/office/frequently-asked-questions-about-basic-mobility-and-security-3871f99c-c9db-4a23-86f9-902c1b02f58d#bkmk_needhelp) 

## <a name="what-can-i-do-if-device-enrollment-fails"></a>장치 등록에 실패 한 경우 어떻게 해야 하나요?

등록 된 장치가 제대로 수신 되는 데 문제가 있는 경우 먼저 다음 사항을 확인 하세요.

- 장치가 Intune과 같은 다른 모바일 장치 관리 공급자에 등록 되어 있지 않은지 확인 합니다.
    
- 장치가 올바른 날짜 및 시간으로 설정 되어 있는지 확인 합니다.
    
- 장치에서 다른 WIFI 또는 셀룰러 네트워크로 전환 합니다.
    
- Android 또는 iOS 장치의 경우 장치에서 Intune 회사 포털 앱을 제거 하 고 다시 설치 합니다.
    
등록이 여전히 작동 하지 않는 경우 [기본 이동성 및 보안 문제 해결](troubleshoot.md)을 참조 하세요.

## <a name="whats-the-difference-between-intune-and-basic-mobility-and-security"></a>Intune과 기본 이동성 및 보안의 차이점은 무엇 인가요?

기본 Mobility and Security는 Intune 서비스에 의해 호스팅됩니다. 이는 Microsoft 365에 추가 된 혜택으로 제공 되는 Intune 서비스의 하위 집합으로, 조직의 장치를 관리 하기 위한 기본 제공 되는 클라우드 기반 솔루션입니다. Intune 또는 Microsoft 365에 대 한 보안을 사용 하는 것이 가장 적절 한지를 결정 하는 데 도움이 되는 두 서비스를 나란히 비교 하려면 [기본 이동성 보안 및 Intune 간 선택을](choose-between-basic-mobility-and-security-and-intune.md)참조 하세요.

## <a name="how-do-policies-work-for-basic-mobility-and-security-how-do-i-set-them-up-disable-them"></a>기본 이동성 및 보안에 대 한 정책 작동 방식 이를 설정 하려면 어떻게 해야 합니까? 사용 하지 않도록 설정

기본 이동성 및 보안에 대 한 초기 설치를 완료 한 후에는 정책을 만들고 보안 & 준수 센터의 사용자 그룹에 적용 합니다. 정책을 사용 하 여 장치를 Microsoft 365 데이터에 액세스 하는 데 사용할 수 있으려면 먼저 정책 사용자가 장치를 기본 이동성 및 보안으로 등록 해야 합니다. 설정 하는 정책에 따라 모바일 장치에 대 한 설정 (예: 암호를 다시 설정 해야 하는 빈도 또는 데이터 암호화 필요 여부)이 결정 됩니다. 자세한 내용은 [기본 이동성 및 보안](create-device-security-policies.md)   및 [Microsoft 365 준수 센터](https://support.microsoft.com/office/7e696a40-b86b-4a20-afcc-559218b7b1b8)에서 장치 보안 정책 만들기를 참조 하세요.

장치 정책 만들기 및 배포에 대 한 단계별 지침은 [기본 Mobility And security에서 장치 보안 정책 만들기](create-device-security-policies.md)를 참조 하십시오.

특정 사용자 그룹을 정책의 영향을 받지 않도록 제외 하려면 제외 그룹에 그룹을 추가할 수 있습니다.

## <a name="can-i-switch-from-exchange-activesync-device-management-to-basic-mobility-and-security-for-microsoft-365"></a>Exchange ActiveSync 장치 관리에서 기본 이동성 및 Microsoft 365에 대 한 보안으로 전환할 수 있나요?

이미 Exchange ActiveSync 정책을 사용 하 여 모바일 장치를 관리 하 고 있는 경우 기본 이동성 및 보안을 설정 하는 단계에 따라 기본 이동성 및 보안을 시작할 수 있습니다. 자세한 내용은 [사용자 및 장치 액세스 보호](https://go.microsoft.com/fwlink/?LinkId=615145) 및 [기본 모바일 및 보안 설정](set-up.md)를 참조 하세요.

사용자 그룹에 기본 이동성 및 보안으로 만든 정책을 적용 하는 경우 이러한 정책은 이전에 해당 사용자에 대해 Exchange 관리 센터에서 만든 Exchange ActiveSync 모바일 장치 사서함 정책 및 장치 액세스 규칙을 재정의 합니다.

장치를 기본 Mobility and Security에 등록 한 후에는 장치에 적용 된 모든 Exchange ActiveSync 모바일 장치 사서함 정책 또는 장치 액세스 규칙이 무시 됩니다.

## <a name="i--set-up-basic-mobility-and-security-but-now-i-want-to-remove-it-what-are-the-steps"></a>기본 이동성 및 보안을 설정 했지만 지금 제거 하려고 합니다. 단계는 무엇입니까?

아쉽게도 기본 이동성 및 보안을 설정한 후에는이를 "구축 취소" 할 수 없습니다. 그러나 만든 장치 정책에서 사용자 보안 그룹을 제거 하 여 사용자 그룹에 대해이를 제거할 수 있습니다. 또는 장치 정책을 제거 하 여 모든 사용자에 대해이 기능을 사용 하지 않도록 설정할 수 있으며 적용 되지 않습니다. 자세한 내용은 [기본 이동성 및 보안 해제](turn-off.md)를 참조 하세요.

