---
title: Microsoft Teams의 기본 데이터 손실 방지 정책에 대한 자세한 정보(미리 보기)
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: 2013의 기본 데이터 손실 방지 정책에 대해 Microsoft Teams
ms.openlocfilehash: 0663c370373708009346d4f858729e17436f0f62
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114146"
---
# <a name="learn-about-the-default-data-loss-prevention-policy-in-microsoft-teams-preview"></a>Microsoft Teams의 기본 데이터 손실 방지 정책에 대한 자세한 정보(미리 보기)

[개인 채널 메시지를](dlp-learn-about-dlp.md) 포함하여 Microsoft Teams 및 채널 메시지를 포함하기 위해 데이터 손실 방지 기능이 확장되어 있습니다. 이 릴리스의 일부로 규정 준수 센터에 처음 고객을 위한 기본 DLP 정책을 만들 수 있습니다.

## <a name="applies-to"></a>적용 대상

하나 이상의 라이선스가 부여된 테넌트 및 활성 사용자 Teams
 
- ME5, 
- MA5, 
- E5/A5 규정 준수, 
- IP+G, 
- OE5, 
- O365 고급 규정 준수 
- EMS E5


## <a name="what-does-the-default-policy-do"></a>기본 정책은 어떤 작업을 하나요?

기본 DLP 정책은 조직 내부 및 외부적으로 공유되는 모든 신용 카드 번호를 추적합니다. 이 정책은 테넌트의 모든 사용자에 대해 기본적으로 설정되어 있습니다. 최종 사용자를 위한 정책 팁은 생성하지 않지만 경고 이벤트를 생성하며, 관리자에게 낮은 심각도 전자 메일(정책에 추가)을 트리거합니다. 관리자는 준수 센터에 로그인하여 활동을 보고 정책 세부 정보를 편집할 수 있습니다.

관리자는 데이터 손실 방지 정책 페이지의 준수 센터에서 [>](https://compliance.microsoft.com/compliancesettings) 수 있습니다.


> [!div class="mx-imgBorder"]
> ![기본 Teams DLP 정책](../media/default-teams-dlp-policy.png)

## <a name="edit-or-delete-the-default-policy"></a>기본 정책 편집 또는 삭제

더 [나은 성능을 위해](create-test-tune-dlp-policy.md#tune-a-dlp-policy)기본 정책을 편집하거나 삭제하려면 **DLP** 준수 관리 권한이 있는 계정을 사용하세요. 자세한 내용은 사용 권한을 [참조하세요.](create-test-tune-dlp-policy.md#permissions)

