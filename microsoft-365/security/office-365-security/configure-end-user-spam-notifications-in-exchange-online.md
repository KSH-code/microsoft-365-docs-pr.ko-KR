---
title: Exchange Online에서 최종 사용자 스팸 알림 구성
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: bfc91c73-a955-40e1-a95f-ad466624339a
ms.collection:
- M365-security-compliance
description: 회사 전체의 기본 스팸 필터 정책 또는 도메인에 적용 되는 사용자 지정 스팸 필터 정책에 대 한 최종 사용자 스팸 알림을 구성할 수 있습니다.
ms.openlocfilehash: 7292d75afb07864fc50d4df30fa5f84691087820
ms.sourcegitcommit: 3f8957ddd04b8710bb5f314a0902fdee50c7c9b7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "41573015"
---
# <a name="configure-end-user-spam-notifications-in-exchange-online"></a>Exchange Online에서 최종 사용자 스팸 알림 구성

> [!IMPORTANT]
> 이 항목은 클라우드 호스트 사서함을 보호 하는 Exchange Online 고객을 위한 것입니다. EOP (Exchange Online Protection) 온-프레미스 사서함을 보호 하는 독립 실행형 고객은 [EOP에서 최종 사용자 스팸 알림 구성](configure-end-user-spam-notifications-in-eop.md)항목을 대신 읽어 보십시오. 
  
회사 전체의 기본 스팸 필터 정책 또는 사용자 지정 스팸 필터 정책에 대 한 최종 사용자 스팸 알림을 구성할 수 있습니다. 최종 사용자 스팸 알림 메시지를 사용 하도록 설정 하면 사용자가 자신의 스팸 격리 된 메시지를 직접 관리할 수 있습니다. 
  
최종 사용자 스팸 알림에는 사용자가 구성한 기간(1일부터 15일 사이의 값을 지정할 수 있음)에 최종 사용자가 받은, 스팸으로 격리된 모든 메시지의 목록이 포함됩니다. 알림 메시지를 작성하는 언어도 구성할 수 있습니다.
  
최종 사용자는 알림 메시지를 받은 후 다음 옵션 중에서 선택할 수 있습니다.

Office 365에서 수신 거부 목록에 보낸 사람을 추가 하려는 경우 **보낸 사람을 차단** 합니다.

메시지가 스팸으로 아니면 Office 365에서 사서함으로 메시지를 보내도록 하려면 **릴리스** 를 선택 합니다.

Preview 또는 Release와 같은 다른 작업을 수행 하려는 경우 보안 & 준수 센터 내의 격리 포털로 이동 하는 방법을 **검토** 합니다.
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용

예상 완료 시간: 2분
  
이러한 절차를 수행하려면 먼저 사용 권한을 할당받아야 합니다. 필요한 사용 권한을 확인 하려면 [Exchange Online의 기능 사용 권한](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions) 항목에서 "스팸 방지" 항목을 참조 하세요. 
  
이 항목의 절차에 적용할 수 있는 바로 가기 키에 대 한 자세한 내용은 [Exchange Online에서 exchange 관리 센터에 대 한 바로 가기 키](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)를 참조 하십시오.
  
## <a name="use-the-eac-to-configure-end-user-spam-notifications"></a>EAC를 통해 최종 사용자 스팸 알림 구성

1. EAC (Exchange 관리 센터)에서 **보호** \> **스팸 필터로**이동 합니다.
    
2. 최종 사용자 스팸 알림을 사용 하도록 설정 하려는 스팸 필터 정책을 선택 합니다 (기본적으로 사용 하지 않도록 설정 됨).
    
3. 정책 요약 정보가 표시되는 오른쪽 창에서 **최종 사용자 스팸 알림 구성** 링크를 클릭합니다. 
    
4. 이후 표시되는 대화 상자에서 다음 옵션을 구성할 수 있습니다.
    
   - **최종 사용자 스팸 알림 사용** 해당 정책에 대한 최종 사용자 스팸 알림을 사용하도록 설정하려면 이 확인란을 선택합니다. 그러나 반대로 해당 정책이 사용하도록 설정되어 있으면 이 확인란을 선택 취소하여 해당 정책에 대한 최종 사용자 스팸 알림을 사용하지 않도록 설정할 수 있습니다. 
    
   - **최종 사용자 스팸 알림을 매번(매일) 전송** 최종 사용자 스팸 알림의 전송 빈도를 지정합니다. 기본값은 3일입니다. 1일부터 15일 사이의 값을 지정할 수 있습니다. 예를 들어 7일을 지정하면 스팸 격리 사서함으로 전송되는 대신 지난 7일 이내에 해당 사용자에게 보내려고 했던 모든 메시지의 목록이 알림에 포함됩니다. 
    
   - **알림 언어** 드롭다운 목록을 사용하여 이 정책의 최종 사용자 스팸 알림에 작성할 언어를 선택합니다. 
    
   - **저장**을 클릭합니다. 최종 사용자 스팸 알림 설정을 비롯 한 스팸 필터 정책 설정에 대 한 요약이 오른쪽 창에 표시 됩니다.
    
> [!NOTE]
>  최종 사용자 스팸 알림은 사용 하도록 설정 된 스팸 필터 정책에 대해서만 작동 합니다. >  최종 사용자 스팸 알림은 하루에 한 번만 전송됩니다. 특정 고객에 대한 알림 배달 시간을 보장하거나 구성할 수는 없습니다. 
  
 **팁:** 최종 사용자 스팸 알림을 완전히 구현 하기 전에 제한 된 사용자 집합에 전송 하 여 테스트 하려면 사용자가 거주 하는 도메인에 대 한 최종 사용자 스팸 알림을 사용 하도록 설정 하는 사용자 지정 스팸 필터 정책을 만듭니다. 그런 다음 EAC의 **메일 흐름 \> 규칙**에서 메일 흐름 규칙 (전송 규칙이 라고도 함)을 만들어 알림을 수신 하려는 사용자에 대 한 예외와 함께 quarantine@messaging.microsoft.com (알림을 보내는 전자 메일 주소)에서 메시지를 차단 합니다. 다음 그림은 Contoso.com 도메인의 두 사용자(SaraD 및 AlexD)에 대한 예외를 만드는 예제입니다. 
  
![최종 사용자 스팸 알림을 테스트할 전송 규칙](../media/EOP-ESN-testspecificusers.jpg)
  
## <a name="use-the-scc-to-configure-end-user-spam-notifications"></a>SCC를 사용 하 여 최종 사용자 스팸 알림 구성

또한 SCC (보안 및 준수 센터)를 사용 하 여 최종 사용자 스팸 알림을 구성할 수도 있습니다. 다음 단계를 따릅니다:

1. 보안 및 준수 센터를 열고 **스팸 방지** https://protection.office.com/antispam를 위한 **위협 관리** \> **정책** \> 으로 이동 하거나 직접 링크를 사용 합니다.

2. 최종 사용자 스팸 알림을 사용 하도록 설정 하려는 스팸 필터 정책 옆의 아래쪽 화살표를 클릭 합니다.

3. **최종 사용자 스팸 알림 구성** 링크를 클릭 합니다.

4. 이후 표시되는 대화 상자에서 다음 옵션을 구성할 수 있습니다.
    
   - **최종 사용자 스팸 알림 사용** 해당 정책에 대한 최종 사용자 스팸 알림을 사용하도록 설정하려면 이 확인란을 선택합니다. 그러나 반대로 해당 정책이 사용하도록 설정되어 있으면 이 확인란을 선택 취소하여 해당 정책에 대한 최종 사용자 스팸 알림을 사용하지 않도록 설정할 수 있습니다. 
    
   - **최종 사용자 스팸 알림을 매번(매일) 전송** 최종 사용자 스팸 알림의 전송 빈도를 지정합니다. 기본값은 3일입니다. 1일부터 15일 사이의 값을 지정할 수 있습니다. 예를 들어 7일을 지정하면 스팸 격리 사서함으로 전송되는 대신 지난 7일 이내에 해당 사용자에게 보내려고 했던 모든 메시지의 목록이 알림에 포함됩니다. 
    
   - **알림 언어** 드롭다운 목록을 사용하여 이 정책의 최종 사용자 스팸 알림에 작성할 언어를 선택합니다. 
    
   - **저장**을 클릭합니다. 최종 사용자 스팸 알림 설정을 비롯 한 스팸 필터 정책 설정에 대 한 요약이 창에 표시 됩니다.

## <a name="for-more-information"></a>자세한 내용

[스팸 필터 정책 구성](configure-your-spam-filter-policies.md)
  
